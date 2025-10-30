<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "66985bbc1a3f888335c827173a58bc5e",
  "translation_date": "2025-10-28T21:32:21+00:00",
  "source_file": "Workshop/Session06-ModelsAsTools.md",
  "language_code": "pt"
}
-->
# Sessão 6: Foundry Local – Modelos como Ferramentas

## Resumo

Trate os modelos como ferramentas compostas dentro de uma camada operacional de IA local. Esta sessão mostra como encadear múltiplas chamadas especializadas de SLM/LLM, encaminhar tarefas seletivamente e expor uma interface unificada de SDK para aplicações. Você irá construir um roteador de modelos leve + planejador de tarefas, integrá-lo em um script de aplicação e delinear o caminho de escalonamento para o Azure AI Foundry para cargas de trabalho em produção.

## Objetivos de Aprendizagem

- **Conceber** modelos como ferramentas atômicas com capacidades declaradas
- **Encaminhar** pedidos com base em intenção / pontuação heurística
- **Encadear** saídas em tarefas de múltiplas etapas (decompor → resolver → refinar)
- **Integrar** uma API de cliente unificada para aplicações downstream
- **Escalar** o design para a nuvem (mesmo contrato compatível com OpenAI)

## Pré-requisitos

- Sessões 1–5 concluídas
- Vários modelos locais armazenados em cache (ex.: `phi-4-mini`, `deepseek-coder-1.3b`, `qwen2.5-0.5b`)

### Trecho de Ambiente Multiplataforma

Windows PowerShell:
```powershell
py -m venv .venv
 .\.venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install foundry-local-sdk openai
```

macOS / Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install foundry-local-sdk openai
```

Acesso remoto/serviço VM a partir de macOS:
```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```


## Fluxo da Demonstração (30 min)

### 1. Declaração de Capacidade de Ferramentas (5 min)

Crie `samples/06-tools/models_catalog.py`:

```python
CATALOG = {
  "phi-4-mini": {
    "capabilities": ["general", "reasoning", "summarize"],
    "priority": 2
  },
  "deepseek-coder-1.3b": {
    "capabilities": ["code", "refactor", "explain_code"],
    "priority": 1
  },
  "qwen2.5-0.5b": {
    "capabilities": ["fast", "classification", "lightweight"],
    "priority": 3
  }
}
```


### 2. Detecção de Intenção e Encaminhamento (8 min)

Crie `samples/06-tools/router.py`:

```python
#!/usr/bin/env python3
"""Model-as-tool router using Foundry Local OpenAI-compatible endpoint."""
from openai import OpenAI
from models_catalog import CATALOG
import re

client = OpenAI(base_url="http://localhost:5273/v1", api_key="not-needed")

INTENT_RULES = [
  (re.compile(r"code|function|refactor|bug|optimi", re.I), "code"),
  (re.compile(r"summari|abstract|tl;dr", re.I), "summarize"),
  (re.compile(r"classif|label|category", re.I), "classification"),
]

def detect_intent(prompt: str) -> str:
    for pat, intent in INTENT_RULES:
        if pat.search(prompt):
            return intent
    return "general"

def select_model(intent: str) -> str:
    # Score catalog: capability match first, then priority
    scored = []
    for name, meta in CATALOG.items():
        caps = meta["capabilities"]
        match = intent in caps
        scored.append((name, match, meta["priority"]))
    # Sort: match True first, then lowest priority value
    scored.sort(key=lambda t: (not t[1], t[2]))
    return scored[0][0]

def run(prompt: str):
    intent = detect_intent(prompt)
    model = select_model(intent)
    resp = client.chat.completions.create(
        model=model,
        messages=[{"role": "user", "content": prompt}],
        max_tokens=400,
        temperature=0.5
    )
    return {"intent": intent, "model": model, "output": resp.choices[0].message.content}

if __name__ == "__main__":
    tests = [
        "Refactor this Python function for readability",
        "Summarize the importance of local AI governance",
        "Classify this feedback: 'The UI is slow and confusing'"
    ]
    for t in tests:
        r = run(t)
        print(f"Prompt: {t}\nModel: {r['model']} (intent={r['intent']})\nOutput: {r['output'][:160]}...\n")
```


### 3. Encadeamento de Tarefas em Múltiplas Etapas (7 min)

Crie `samples/06-tools/pipeline.py`:

```python
#!/usr/bin/env python3
"""Multi-step pipeline: plan -> solve -> refine using specialized models."""
from openai import OpenAI
from router import detect_intent, select_model

client = OpenAI(base_url="http://localhost:5273/v1", api_key="not-needed")

def chat(model, content, temp=0.4):
    r = client.chat.completions.create(
        model=model,
        messages=[{"role": "user", "content": content}],
        max_tokens=350,
        temperature=temp
    )
    return r.choices[0].message.content

def pipeline(task: str):
    plan_model = select_model("general")
    plan = chat(plan_model, f"Break the task into 3 ordered steps. Task: {task}")
    steps = [s for s in plan.split('\n') if s.strip()][:3]
    outputs = []
    for step in steps:
        intent = detect_intent(step)
        model = select_model(intent)
        out = chat(model, step)
        outputs.append((step, model, out))
    refine_model = select_model("summarize")
    combined = '\n'.join(o[2] for o in outputs)
    refined = chat(refine_model, f"Condense results into a cohesive answer:\n{combined}")
    return {"plan": plan, "steps": outputs, "final": refined}

if __name__ == '__main__':
    result = pipeline("Generate a refactored version of a slow Python loop and summarize performance gains.")
    print("PLAN:\n", result['plan'])
    print("FINAL:\n", result['final'][:400])
```


### 4. Projeto Inicial: Adaptar `06-models-as-tools` (5 min)

Melhorias:
- Adicionar suporte a streaming de tokens (atualização progressiva da interface)
- Adicionar pontuação de confiança: sobreposição lexical ou rubrica de prompt
- Exportar JSON de rastreamento (intenção → modelo → latência → uso de tokens)
- Implementar reutilização de cache para subetapas repetidas

### 5. Caminho de Escalabilidade para Azure (5 min)

| Camada | Local (Foundry) | Nuvem (Azure AI Foundry) | Estratégia de Transição |
|--------|-----------------|--------------------------|--------------------------|
| Encaminhamento | Python heurístico | Microsserviço durável | Containerizar e implementar API |
| Modelos | SLMs armazenados em cache | Implementações geridas | Mapear nomes locais para IDs de implementação |
| Observabilidade | Estatísticas CLI/manual | Registro centralizado e métricas | Adicionar eventos de rastreamento estruturados |
| Segurança | Apenas host local | Autenticação/rede Azure | Introduzir cofre de chaves para segredos |
| Custo | Recursos do dispositivo | Cobrança por consumo | Adicionar limites de orçamento |

## Lista de Verificação de Validação

```powershell
foundry model run phi-4-mini
foundry model run deepseek-coder-1.3b
python samples/06-tools/router.py
python samples/06-tools/pipeline.py
```

Esperar seleção de modelo baseada em intenção e saída final refinada.

## Resolução de Problemas

| Problema | Causa | Solução |
|----------|-------|---------|
| Todas as tarefas encaminhadas para o mesmo modelo | Regras fracas | Enriquecer conjunto de regex INTENT_RULES |
| Falha na pipeline na metade da etapa | Modelo não carregado | Executar `foundry model run <model>` |
| Baixa coesão de saída | Sem fase de refinamento | Adicionar etapa de sumarização/validação |

## Referências

- Foundry Local SDK: https://github.com/microsoft/Foundry-Local/tree/main/sdk/python
- Documentação do Azure AI Foundry: https://learn.microsoft.com/azure/ai-foundry
- Padrões de Qualidade de Prompt: Ver Sessão 2

---

**Duração da Sessão**: 30 min  
**Dificuldade**: Avançado

## Cenário de Exemplo e Mapeamento do Workshop

| Scripts / Notebooks do Workshop | Cenário | Objetivo | Fonte do Conjunto de Dados / Catálogo |
|---------------------------------|---------|----------|---------------------------------------|
| `samples/session06/models_router.py` / `notebooks/session06_models_router.ipynb` | Assistente de desenvolvedor lidando com prompts de intenção mista (refatorar, resumir, classificar) | Intenção heurística → encaminhamento de alias de modelo com uso de tokens | `CATALOG` embutido + regex `RULES` |
| `samples/session06/models_pipeline.py` / `notebooks/session06_models_pipeline.ipynb` | Planeamento e refinamento em múltiplas etapas para tarefa complexa de assistência em codificação | Decompor → execução especializada → etapa de refinamento de sumarização | Mesmo `CATALOG`; etapas derivadas da saída do plano |

### Narrativa do Cenário
Uma ferramenta de produtividade de engenharia recebe tarefas heterogêneas: refatorar código, resumir notas arquiteturais, classificar feedback. Para minimizar latência e uso de recursos, um pequeno modelo geral planeja e resume, um modelo especializado em código lida com a refatoração, e um modelo leve capaz de classificação rotula o feedback. O script da pipeline demonstra encadeamento + refinamento; o script do roteador isola o encaminhamento adaptativo de um único prompt.

### Instantâneo do Catálogo
```python
CATALOG = {
    "phi-4-mini": {"capabilities": ["general", "summarize"], "priority": 2},
    "deepseek-coder-1.3b": {"capabilities": ["code", "refactor"], "priority": 1},
    "qwen2.5-0.5b": {"capabilities": ["classification", "fast"], "priority": 3}
}
```


### Exemplos de Prompts de Teste
```json
[
    "Refactor this Python function for readability",
    "Summarize the importance of small language models",
    "Classify this feedback: The UI is slow but pretty",
    "Generate a refactored version of a slow Python loop and summarize performance gains."
]
```


### Extensão de Rastreamento (Opcional)
Adicionar linhas de JSON de rastreamento por etapa para `models_pipeline.py`:
```python
trace.append({
    "step": step_idx,
    "intent": intent,
    "alias": alias,
    "latency_ms": round((end-start)*1000,2),
    "tokens": getattr(usage,'total_tokens',None)
})
```


### Heurística de Escalação (Ideia)
Se o plano contiver palavras-chave como "otimizar", "segurança", ou o comprimento da etapa > 280 caracteres → escalar para um modelo maior (ex.: `gpt-oss-20b`) apenas para essa etapa.

### Melhorias Opcionais

| Área | Melhoria | Valor | Dica |
|------|----------|-------|------|
| Cache | Reutilizar objetos de gerenciador + cliente | Menor latência, menos sobrecarga | Usar `workshop_utils.get_client` |
| Métricas de Uso | Capturar tokens e latência por etapa | Perfilamento e otimização | Cronometrar cada chamada roteada; armazenar na lista de rastreamento |
| Encaminhamento Adaptativo | Confiança / ciente de custo | Melhor relação qualidade-custo | Adicionar pontuação: se o prompt > N caracteres ou regex corresponder ao domínio → escalar para modelo maior |
| Registro Dinâmico de Capacidades | Catálogo de recarga dinâmica | Sem necessidade de reinício ou reimplantação | Carregar `catalog.json` em tempo de execução; monitorar carimbo de data/hora do arquivo |
| Estratégia de Contingência | Robustez em falhas | Maior disponibilidade | Tentar primário → em caso de exceção, usar alias de contingência |
| Pipeline de Streaming | Feedback antecipado | Melhoria de UX | Transmitir cada etapa e armazenar em buffer a entrada final de refinamento |
| Embeddings de Intenção Vetorial | Encaminhamento mais detalhado | Maior precisão de intenção | Incorporar prompt, agrupar e mapear centróide → capacidade |
| Exportação de Rastreamento | Encadeamento auditável | Conformidade/relatórios | Emitir linhas JSON: etapa, intenção, modelo, latência_ms, tokens |
| Simulação de Custos | Estimativa pré-nuvem | Planeamento de orçamento | Atribuir custo notional/token por modelo e agregar por tarefa |
| Modo Determinístico | Reproducibilidade | Benchmarking estável | Ambiente: `temperature=0`, número fixo de etapas |

#### Exemplo de Estrutura de Rastreamento

```python
trace.append({
  "step": idx,
  "intent": intent,
  "alias": alias,
  "latency_ms": round((end-start)*1000,2),
  "tokens": getattr(usage,'total_tokens',None)
})
```


#### Esboço de Escalação Adaptativa

```python
if len(prompt) > 280 or 'compliance' in prompt.lower():
    # escalate to larger reasoning model if available
    alias = 'gpt-oss-20b'
```


#### Recarga Dinâmica do Catálogo de Modelos

```python
import json, time, os
CATALOG_PATH = 'catalog.json'
last_mtime = 0
def get_catalog():
    global last_mtime, CATALOG
    m = os.path.getmtime(CATALOG_PATH)
    if m != last_mtime:
        CATALOG = json.load(open(CATALOG_PATH))
        last_mtime = m
    return CATALOG
```

---

**Aviso**:  
Este documento foi traduzido utilizando o serviço de tradução por IA [Co-op Translator](https://github.com/Azure/co-op-translator). Embora nos esforcemos pela precisão, esteja ciente de que traduções automáticas podem conter erros ou imprecisões. O documento original na sua língua nativa deve ser considerado a fonte autoritária. Para informações críticas, recomenda-se uma tradução profissional realizada por humanos. Não nos responsabilizamos por quaisquer mal-entendidos ou interpretações incorretas decorrentes do uso desta tradução.