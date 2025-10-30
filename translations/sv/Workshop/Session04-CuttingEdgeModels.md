<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "d9e354c0182311726dc037a8809524e2",
  "translation_date": "2025-10-28T22:03:24+00:00",
  "source_file": "Workshop/Session04-CuttingEdgeModels.md",
  "language_code": "sv"
}
-->
# Session 4: Utforska banbrytande modeller – LLMs, SLMs & lokal inferens

## Sammanfattning

Jämför Large Language Models (LLMs) och Small Language Models (SLMs) för lokala kontra molnbaserade inferensscenarier. Lär dig implementeringsmönster som utnyttjar ONNX Runtime-acceleration, WebGPU-exekvering och hybrid RAG-upplevelser. Inkluderar en Chainlit RAG-demo med en lokal modell samt en valfri utforskning av OpenWebUI. Du kommer att anpassa en WebGPU-inferensstart och utvärdera Phi kontra GPT-OSS-20B vad gäller kapacitet och kostnads-/prestandaavvägningar.

## Lärandemål

- **Jämför** SLM och LLM utifrån latens, minne och kvalitet
- **Implementera** modeller med ONNXRuntime och (där det stöds) WebGPU
- **Kör** webbläsarbaserad inferens (integritetsbevarande interaktiv demo)
- **Integrera** en Chainlit RAG-pipeline med en lokal SLM-backend
- **Utvärdera** med hjälp av lättviktiga kvalitets- och kostnadsheuristiker

## Förkunskapskrav

- Sessioner 1–3 genomförda
- `chainlit` installerat (redan inkluderat i `requirements.txt` för Modul08)
- WebGPU-kompatibel webbläsare (Edge / Chrome senaste versionen på Windows 11)
- Foundry Local igång (`foundry status`)

### Plattformsspecifika anteckningar

Windows är fortfarande den primära målmiljön. För macOS-utvecklare som väntar på inhemska binärfiler:
1. Kör Foundry Local i en Windows 11 VM (Parallels / UTM) ELLER en fjärransluten Windows-arbetsstation.
2. Exponera tjänsten (standardport 5273) och ställ in på macOS:
```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```
3. Använd samma Python-virtuella miljösteg som i tidigare sessioner.

Chainlit-installation (båda plattformarna):
```bash
pip install chainlit
```

## Demo-flöde (30 min)

### 1. Jämför Phi (SLM) och GPT-OSS-20B (LLM) (6 min)

```powershell
foundry model run phi-4-mini
foundry model run gpt-oss-20b

# Quick capability probes (one-shot non-interactive)
foundry model run phi-4-mini   --prompt "Summarize retrieval augmented generation in 2 sentences."
foundry model run gpt-oss-20b --prompt "Summarize retrieval augmented generation in 2 sentences."

# Basic token / latency test (repeat a few times for intuition)
foundry model run phi-4-mini   --prompt "List 5 creative IoT edge AI ideas."
foundry model run gpt-oss-20b --prompt "List 5 creative IoT edge AI ideas."
```

Spåra: svarsdjup, faktakorrekthet, stilistisk rikedom, latens.

### 2. ONNX Runtime-acceleration (5 min)

```powershell
foundry config set compute.onnx.enable_gpu true
# Re-run Python benchmark script for quantitative latency / throughput after enabling GPU
#   cd Workshop/samples
#   set BENCH_MODELS=phi-4-mini
#   python -m session03.benchmark_oss_models
```

Observera genomströmningsförändringar efter att ha aktiverat GPU kontra endast CPU.

### 3. WebGPU-inferens i webbläsaren (6 min)

Anpassa startfilen `04-webgpu-inference` (skapa `samples/04-cutting-edge/webgpu_demo.html`):

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Foundry Local WebGPU Demo</title>
  <style>body{font-family:system-ui;margin:2rem;max-width:820px;} textarea{width:100%;height:120px;} pre{background:#111;color:#eee;padding:1rem;} .resp{white-space:pre-wrap;margin-top:1rem;border:1px solid #444;padding:1rem;border-radius:6px;}</style>
</head>
<body>
  <h1>WebGPU Inference (Experimental)</h1>
  <p>Demonstration placeholder for a WebGPU-backed transformer (concept). Replace with actual JS runtime once exposed by Foundry Local or associated runtime libs.</p>
  <textarea id="prompt" placeholder="Enter your prompt..."></textarea>
  <button id="run">Generate</button>
  <div id="out" class="resp"></div>
  <script>
    document.getElementById('run').onclick = async () => {
      const p = document.getElementById('prompt').value.trim();
      if(!p) return;
      document.getElementById('out').textContent = 'Running (simulated)...';
      // Placeholder: in a real implementation you'd call into a WASM/WebGPU pipeline or local gateway endpoint.
      const resp = await fetch('http://localhost:5273/v1/chat/completions', {
        method: 'POST', headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          model: 'phi-4-mini',
          messages: [ { role: 'user', content: p } ],
          max_tokens: 200, temperature: 0.5
        })
      }).then(r=>r.json()).catch(e=>({error:e.toString()}));
      if(resp.error){
        document.getElementById('out').textContent = 'Error: '+resp.error;
      } else {
        document.getElementById('out').textContent = resp.choices?.[0]?.message?.content || JSON.stringify(resp,null,2);
      }
    };
  </script>
</body>
</html>
```

Öppna filen i en webbläsare; observera låg latens vid lokal rundresa.

### 4. Chainlit RAG-chattapp (7 min)

Minimal `samples/04-cutting-edge/chainlit_app.py`:

```python
#!/usr/bin/env python3
"""Chainlit RAG demo using Foundry Local SLM as backend."""
import chainlit as cl
from openai import OpenAI

DOCS = [
  "Foundry Local enables local model execution with OpenAI-compatible APIs.",
  "RAG combines retrieval and generation for grounded answers.",
  "SLMs provide efficiency advantages on constrained hardware."  
]

client = OpenAI(base_url="http://localhost:5273/v1", api_key="not-needed")

def build_context(query: str):
    # Naive lexical scoring
    scored = sorted(DOCS, key=lambda d: sum(w in d.lower() for w in query.lower().split()), reverse=True)
    return "\n".join(scored[:2])

@cl.on_message
async def main(message: cl.Message):
    ctx = build_context(message.content)
    resp = client.chat.completions.create(
        model="phi-4-mini",
        messages=[
            {"role": "system", "content": "Answer using ONLY the provided context. If insufficient, say so."},
            {"role": "user", "content": f"Context:\n{ctx}\n\nQuestion: {message.content}"}
        ],
        max_tokens=300,
        temperature=0.3
    )
    await cl.Message(content=resp.choices[0].message.content).send()
```

Kör:

```powershell
chainlit run samples/04-cutting-edge/chainlit_app.py -w
```

### 5. Startprojekt: Anpassa `04-webgpu-inference` (6 min)

Leveranser:
- Ersätt platshållarens hämtningslogik med strömmande tokens (använd `stream=True` endpoint-variant när den är aktiverad)
- Lägg till latensdiagram (klientsidan) för Phi kontra GPT-OSS-20B-växlingar
- Bädda in RAG-kontekst inline (textområde för referensdokument)

## Utvärderingsheuristik

| Kategori | Phi-4-mini | GPT-OSS-20B | Observation |
|----------|------------|-------------|-------------|
| Latens (kallstart) | Snabb | Långsammare | SLM värms upp snabbt |
| Minne | Låg | Hög | Möjlighet att köra på enheter |
| Kontextföljsamhet | Bra | Stark | Större modell kan vara mer ordrik |
| Kostnad (lokalt) | Minimal | Högre (resurser) | Energi-/tidsavvägning |
| Bästa användningsområde | Edge-appar | Djupgående resonemang | Hybridpipeline möjlig |

## Validering av miljö

```powershell
# List catalog (no --running flag; loaded models are those you have previously run)
foundry model list

# For runtime metrics use the Python benchmark script (Session 3) and OS tools (Task Manager / nvidia-smi) instead of 'model stats'
# Example:
#   cd Workshop/samples
#   set BENCH_MODELS=phi-4-mini,gpt-oss-20b
#   python -m session03.benchmark_oss_models
```

## Felsökning

| Symptom | Orsak | Åtgärd |
|---------|-------|--------|
| Webbsidans hämtning misslyckas | CORS eller tjänsten nere | Använd `curl` för att verifiera endpoint; aktivera CORS-proxy om det behövs |
| Chainlit tom | Miljö inte aktiv | Aktivera venv och installera om beroenden |
| Hög latens | Modellen precis laddad | Värm upp med en liten promptsekvens |

## Referenser

- Foundry Local SDK: https://github.com/microsoft/Foundry-Local/tree/main/sdk/python
- Chainlit-dokumentation: https://docs.chainlit.io
- RAG-utvärdering (Ragas): https://docs.ragas.io

---

**Sessionens längd**: 30 min  
**Svårighetsgrad**: Avancerad

## Exempelscenario & workshopkartläggning

| Workshopartefakter | Scenario | Mål | Data / promptkälla |
|--------------------|----------|-----|--------------------|
| `samples/session04/model_compare.py` / `notebooks/session04_model_compare.ipynb` | Arkitektteam som utvärderar SLM kontra LLM för sammanfattningsgenerator för ledningsgrupp | Kvantifiera latens + tokenanvändningsskillnad | Enstaka `COMPARE_PROMPT` miljövariabel |
| `chainlit_app.py` (RAG-demo) | Prototyp för intern kunskapsassistent | Grundlägg korta svar med minimal lexikalisk hämtning | Inline `DOCS`-lista i filen |
| `webgpu_demo.html` | Framtida lokal webbläsarinferensförhandsvisning | Visa låg latens vid lokal rundresa + UX-berättelse | Endast live användarprompt |

### Scenarionarrativ
Produktorganisationen vill ha en generator för ledningsgruppssammanfattningar. En lättviktig SLM (phi‑4‑mini) skapar utkast till sammanfattningar; en större LLM (gpt‑oss‑20b) kan endast förfina högprioriterade rapporter. Sessionsskripten fångar empiriska latens- och tokenmått för att motivera en hybriddesign, medan Chainlit-demon illustrerar hur grundad hämtning håller små modellers svar faktiska. WebGPU-konceptet ger en vision för helt klientbaserad bearbetning när webbläsaracceleration mognar.

### Minimal RAG-kontekst (Chainlit)
```python
DOCS = [
  "Foundry Local enables local model execution with OpenAI-compatible APIs.",
  "RAG combines retrieval and generation for grounded answers.",
  "SLMs provide efficiency advantages on constrained hardware."
]
```

### Hybridutkast→Förfina-flöde (Pseudo)
```python
draft, _ = chat_once('phi-4-mini', messages=[{"role":"user","content":prompt}], max_tokens=280)
if len(draft) < 600:  # heuristic: escalate only for longer briefs or flagged topics
    final = draft
else:
    final, _ = chat_once('gpt-oss-20b', messages=[{"role":"user","content":f"Refine and polish:\n{draft}"}], max_tokens=220)
```

Spåra båda latenskomponenterna för att rapportera genomsnittlig blandad kostnad.

### Valfria förbättringar

| Fokus | Förbättring | Varför | Implementeringshint |
|-------|------------|-------|---------------------|
| Jämförande mått | Spåra tokenanvändning + latens för första token | Holistisk prestandavy | Använd förbättrat benchmark-skript (Session 3) med `BENCH_STREAM=1` |
| Hybridpipeline | SLM-utkast → LLM-förfining | Minska latens och kostnad | Generera med phi-4-mini, förfina sammanfattning med gpt-oss-20b |
| Strömmande UI | Bättre UX i Chainlit | Inkrementell feedback | Använd `stream=True` när lokal strömning är aktiverad; ackumulera delar |
| WebGPU-caching | Snabbare JS-initiering | Minska omkompileringens overhead | Cachea kompilerade shader-artefakter (framtida runtime-funktion) |
| Deterministisk QA-uppsättning | Rättvis modelljämförelse | Ta bort variation | Fast promptlista + `temperature=0` för utvärderingskörningar |
| Resultatbedömning | Strukturerad kvalitetslins | Gå bortom anekdoter | Enkel rubricering: sammanhang / faktakorrekthet / korthet (1–5) |
| Energi-/resursanteckningar | Klassrumsdiskussion | Visa avvägningar | Använd OS-övervakning (`foundry system info`, Aktivitetshanteraren, `nvidia-smi`) + benchmark-skriptutgångar |
| Kostnadssimulering | Förberedelse för moln | Planera skalning | Kartlägg tokens till hypotetisk molnprissättning för TCO-berättelse |
| Latensnedbrytning | Identifiera flaskhalsar | Måloptimera | Mät promptförberedelse, begäran, första token, fullständig slutförande |
| RAG + LLM-fallback | Kvalitetssäkerhetsnät | Förbättra svåra frågor | Om SLM-svarslängd < tröskel eller låg säkerhet → eskalera |

#### Exempel på hybridutkast/förfiningsmönster

```python
draft, _ = chat_once('phi-4-mini', messages=[{"role":"user","content":task}], max_tokens=300, temperature=0.4)
refine, _ = chat_once('gpt-oss-20b', messages=[{"role":"user","content":f"Improve clarity but keep facts:\n{draft}"}], max_tokens=220, temperature=0.3)
```

#### Latensnedbrytningsskiss

```python
import time
t0 = time.time(); # build messages
prep_ms = (time.time()-t0)*1000
t1 = time.time(); text,_ = chat_once(alias, messages=msgs, max_tokens=180)
full_ms = (time.time()-t1)*1000
print({"prep_ms": prep_ms, "full_gen_ms": full_ms})
```

Använd konsekvent mätstruktur över modeller för rättvisa jämförelser.

---

**Ansvarsfriskrivning**:  
Detta dokument har översatts med hjälp av AI-översättningstjänsten [Co-op Translator](https://github.com/Azure/co-op-translator). Även om vi strävar efter noggrannhet, bör det noteras att automatiska översättningar kan innehålla fel eller felaktigheter. Det ursprungliga dokumentet på dess ursprungliga språk bör betraktas som den auktoritativa källan. För kritisk information rekommenderas professionell mänsklig översättning. Vi ansvarar inte för eventuella missförstånd eller feltolkningar som uppstår vid användning av denna översättning.