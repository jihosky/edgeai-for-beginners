<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "45923ada94573fee7c82cc4f0c3bb344",
  "translation_date": "2025-10-28T23:37:19+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "my"
}
-->
# EdgeAI အတွက် အခြေခံ - အလုပ်ရုံဆွေးနွေးပွဲ

> **ထုတ်လုပ်မှုအဆင်သင့် Edge AI အက်ပလီကေးရှင်းများ တည်ဆောက်ရန် လေ့လာမှုလမ်းကြောင်း**
>
> Microsoft Foundry Local ကို အသုံးပြု၍ ပထမဆုံး chat completion မှ multi-agent orchestration အထိ ၆ ခုသော အဆင့်ဆင့် session များတွင် ဒေသခံ AI ကို deploy လုပ်ခြင်းကို ကျွမ်းကျင်ပါ။

---

## 🎯 အကျဉ်းချုပ်

**EdgeAI အတွက် အခြေခံ အလုပ်ရုံဆွေးနွေးပွဲ** သို့ ကြိုဆိုပါသည်။ ဒေသခံ hardware ပေါ်တွင် အပြည့်အဝ လည်ပတ်နိုင်သော ဉာဏ်ရည်ရှိသော အက်ပလီကေးရှင်းများ တည်ဆောက်ရန် လက်တွေ့ လေ့လာမှုလမ်းညွှန်ဖြစ်သည်။ ဒီအလုပ်ရုံဆွေးနွေးပွဲသည် Microsoft Foundry Local နှင့် Small Language Models (SLMs) ကို အသုံးပြု၍ Edge AI အယူအဆများကို အမှန်တကယ် ကျွမ်းကျင်မှုများအဖြစ် ပြောင်းလဲပေးသည်။

### ဒီအလုပ်ရုံဆွေးနွေးပွဲကို ဘာကြောင့် လေ့လာသင့်သလဲ?

**Edge AI တိုးတက်မှုကာလ ရောက်ရှိနေပြီ**

ကမ္ဘာတစ်ဝှမ်းရှိ အဖွဲ့အစည်းများသည် cloud မှာ အခြေခံထားသော AI မှ edge computing သို့ အရေးကြီးသော အကြောင်းရင်း ၃ ခုကြောင့် ပြောင်းလဲနေကြသည်။

1. **Privacy & Compliance** - Cloud သို့ data ပို့ခြင်းမရှိဘဲ ဒေသခံတွင် sensitive data ကို လုပ်ဆောင်ခြင်း (HIPAA, GDPR, ငွေကြေးဆိုင်ရာ စည်းမျဉ်းများ)
2. **Performance** - Network latency ကို ဖယ်ရှားခြင်း (ဒေသခံ 50-500ms vs cloud round-trip 500-2000ms)
3. **Cost Control** - Per-token API ကုန်ကျစရိတ်များကို ဖယ်ရှားပြီး cloud ကုန်ကျစရိတ်မရှိဘဲ scale လုပ်ခြင်း

**သို့သော် Edge AI က မတူပါ**

On-premises တွင် AI ကို လည်ပတ်ရန် ကျွမ်းကျင်မှုအသစ်များ လိုအပ်သည်။
- အရင်းအမြစ် အကန့်အသတ်များအတွက် model ရွေးချယ်ခြင်းနှင့် optimization
- ဒေသခံ service စီမံခန့်ခွဲမှုနှင့် hardware acceleration
- Smaller models အတွက် prompt engineering
- Edge devices အတွက် production deployment patterns

**ဒီအလုပ်ရုံဆွေးနွေးပွဲက အဲဒီကျွမ်းကျင်မှုများကို ပေးစွမ်းပါမည်**

အဓိက session ၆ ခု (~၃ နာရီ စုစုပေါင်း) တွင် "Hello World" မှ production-ready multi-agent systems ကို deploy လုပ်ခြင်းအထိ တိုးတက်မှုရှိသော လေ့လာမှုများကို သင်ယူနိုင်ပါမည်။

---

## 📚 လေ့လာမှုရည်မှန်းချက်များ

ဒီအလုပ်ရုံဆွေးနွေးပွဲကို ပြီးမြောက်ပြီးနောက် သင်သည် အောက်ပါများကို လုပ်ဆောင်နိုင်ပါမည်။

### အဓိက ကျွမ်းကျင်မှုများ
1. **ဒေသခံ AI Services ကို Deploy နှင့် စီမံခန့်ခွဲခြင်း**
   - Microsoft Foundry Local ကို install နှင့် configure လုပ်ခြင်း
   - Edge deployment အတွက် သင့်လျော်သော models ရွေးချယ်ခြင်း
   - Model lifecycle ကို စီမံခန့်ခွဲခြင်း (download, load, cache)
   - အရင်းအမြစ်အသုံးပြုမှုကို စောင့်ကြည့်ပြီး performance ကို optimize လုပ်ခြင်း

2. **AI-Powered Applications တည်ဆောက်ခြင်း**
   - OpenAI-compatible chat completions ကို ဒေသခံတွင် အကောင်အထည်ဖော်ခြင်း
   - Small Language Models အတွက် prompt များကို ထိရောက်စွာ ဒီဇိုင်းဆွဲခြင်း
   - UX အတွက် streaming responses ကို ကိုင်တွယ်ခြင်း
   - ဒေသခံ models ကို ရှိပြီးသား applications တွင် ပေါင်းစပ်ခြင်း

3. **RAG (Retrieval Augmented Generation) Systems တည်ဆောက်ခြင်း**
   - Embeddings ဖြင့် semantic search တည်ဆောက်ခြင်း
   - LLM responses ကို domain-specific knowledge တွင် အခြေခံခြင်း
   - RAG quality ကို စက်မှုလုပ်ငန်းစံချိန်စံညွှန်းများဖြင့် အကဲဖြတ်ခြင်း
   - Prototype မှ production သို့ scale လုပ်ခြင်း

4. **Model Performance ကို Optimize လုပ်ခြင်း**
   - သင့်ရဲ့ use case အတွက် models များကို benchmark လုပ်ခြင်း
   - Latency, throughput, နှင့် first-token time ကို တိုင်းတာခြင်း
   - Speed/quality tradeoffs အပေါ် အခြေခံပြီး optimal models ရွေးချယ်ခြင်း
   - အမှန်တကယ် scenarios တွင် SLM နှင့် LLM trade-offs ကို နှိုင်းယှဉ်ခြင်း

5. **Multi-Agent Systems ကို Orchestrate လုပ်ခြင်း**
   - အလုပ်အမျိုးမျိုးအတွက် အထူး agent များကို ဒီဇိုင်းဆွဲခြင်း
   - Agent memory နှင့် context management ကို အကောင်အထည်ဖော်ခြင်း
   - ရှုပ်ထွေးသော workflows တွင် agents များကို စီမံခန့်ခွဲခြင်း
   - Models များအကြား requests များကို ဉာဏ်ရည်ရှိစွာ route လုပ်ခြင်း

6. **Production-Ready Solutions ကို Deploy လုပ်ခြင်း**
   - Error handling နှင့် retry logic ကို အကောင်အထည်ဖော်ခြင်း
   - Token usage နှင့် system resources ကို စောင့်ကြည့်ခြင်း
   - Model-as-tools patterns ဖြင့် scalable architectures တည်ဆောက်ခြင်း
   - Edge မှ hybrid (edge + cloud) သို့ ပြောင်းလဲမှုလမ်းကြောင်းများကို စီစဉ်ခြင်း

---

## 🎓 လေ့လာမှုရလဒ်များ

### သင်တည်ဆောက်မည့်အရာများ

ဒီအလုပ်ရုံဆွေးနွေးပွဲကို ပြီးမြောက်ပြီးနောက် သင်သည် အောက်ပါအရာများကို တည်ဆောက်ထားမည်ဖြစ်သည်။

| Session | Deliverable | Skills Demonstrated |
|---------|-------------|---------------------|
| **1** | Streaming ဖြင့် Chat application | Service setup, basic completions, streaming UX |
| **2** | RAG system နှင့် evaluation | Embeddings, semantic search, quality metrics |
| **3** | Multi-model benchmark suite | Performance measurement, model comparison |
| **4** | SLM vs LLM comparator | Trade-off analysis, optimization strategies |
| **5** | Multi-agent orchestrator | Agent design, memory management, coordination |
| **6** | Intelligent routing system | Intent detection, model selection, scalability |

### ကျွမ်းကျင်မှု အဆင့်ဇယား

| Skill Level | Session 1-2 | Session 3-4 | Session 5-6 |
|-------------|-------------|-------------|-------------|
| **Beginner** | ✅ Setup & basics | ⚠️ Challenging | ❌ Too advanced |
| **Intermediate** | ✅ Quick review | ✅ Core learning | ⚠️ Stretch goals |
| **Advanced** | ✅ Breeze through | ✅ Refinement | ✅ Production patterns |

### အလုပ်အကိုင်အတွက် အသင့်ဖြစ်သော ကျွမ်းကျင်မှုများ

**ဒီအလုပ်ရုံဆွေးနွေးပွဲကို ပြီးမြောက်ပြီးနောက် သင်သည် အောက်ပါများကို ပြုလုပ်နိုင်ပါမည်။**

✅ **Privacy-First Applications တည်ဆောက်ခြင်း**
- PHI/PII ကို ဒေသခံတွင် လုပ်ဆောင်သော Healthcare apps
- Compliance လိုအပ်ချက်များနှင့် Financial services
- Data sovereignty လိုအပ်ချက်များနှင့် Government systems

✅ **Edge Environments အတွက် Optimize လုပ်ခြင်း**
- အရင်းအမြစ် အကန့်အသတ်ရှိသော IoT devices
- Offline-first mobile applications
- Low-latency real-time systems

✅ **Intelligent Architectures ကို ဒီဇိုင်းဆွဲခြင်း**
- ရှုပ်ထွေးသော workflows အတွက် Multi-agent systems
- Hybrid edge-cloud deployments
- Cost-optimized AI infrastructure

✅ **Edge AI Initiatives ကို ဦးဆောင်ခြင်း**
- Project များအတွက် Edge AI feasibility ကို အကဲဖြတ်ခြင်း
- သင့်လျော်သော models နှင့် frameworks ကို ရွေးချယ်ခြင်း
- Scalable local AI solutions ကို architect လုပ်ခြင်း

---

## 🗺️ အလုပ်ရုံဆွေးနွေးပွဲ ဖွဲ့စည်းမှု

### Session အကျဉ်းချုပ် (6 Sessions × 30 မိနစ် = 3 နာရီ)

| Session | Topic | Focus | Duration |
|---------|-------|-------|----------|
| **1** | Foundry Local ဖြင့် စတင်ခြင်း | Install, validate, first completions | 30 min |
| **2** | RAG ဖြင့် AI Solutions တည်ဆောက်ခြင်း | Prompt engineering, embeddings, evaluation | 30 min |
| **3** | Open Source Models | Model discovery, benchmarking, selection | 30 min |
| **4** | Cutting Edge Models | SLM vs LLM, optimization, frameworks | 30 min |
| **5** | AI-Powered Agents | Agent design, orchestration, memory | 30 min |
| **6** | Models as Tools | Routing, chaining, scaling strategies | 30 min |

---

## 🚀 အမြန်စတင်ခြင်း

### လိုအပ်ချက်များ

**System Requirements:**
- **OS**: Windows 10/11, macOS 11+, or Linux (Ubuntu 20.04+)
- **RAM**: အနည်းဆုံး 8GB, အကြံပြုချက် 16GB+
- **Storage**: Models အတွက် အခမဲ့နေရာ 10GB+
- **CPU**: AVX2 support ပါသော Modern processor
- **GPU** (optional): CUDA-compatible သို့မဟုတ် Qualcomm NPU acceleration အတွက်

**Software Requirements:**
- **Python 3.8+** ([Download](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([Installation Guide](../../../Workshop))
- **Git** ([Download](https://git-scm.com/downloads))
- **Visual Studio Code** (recommended) ([Download](https://code.visualstudio.com/))

### 3 ခြေလှမ်းဖြင့် Setup

#### 1. Foundry Local ကို Install လုပ်ပါ

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**Verify Installation:**
```bash
foundry --version
foundry service status
```

**Azure AI Foundry Local ကို fixed port ဖြင့် လည်ပတ်နေသည်ကို သေချာပါ**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**Verify လုပ်ပါ:**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**ရနိုင်သော Models ရှာဖွေခြင်း**
Foundry Local instance တွင် ရနိုင်သော models များကို models endpoint ကို query လုပ်ခြင်းဖြင့် ကြည့်နိုင်သည်။

```bash
# cmd/bash/powershell
foundry model list
```

Web Endpoint ကို အသုံးပြုခြင်း

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### 2. Repository ကို Clone လုပ်ပြီး Dependencies များ Install လုပ်ပါ

```bash
# Clone repository
git clone https://github.com/microsoft/edgeai-for-beginners.git
cd edgeai-for-beginners/Workshop

# Create virtual environment
python -m venv .venv

# Activate virtual environment
# Windows:
.\.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

#### 3. သင့်ရဲ့ ပထမဆုံး Sample ကို Run လုပ်ပါ

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples
python -m session01.chat_bootstrap "What is edge AI?"
```

**✅ အောင်မြင်ပါပြီ!** Edge AI အကြောင်း streaming response ကို တွေ့ရပါမည်။

---

## 📦 အလုပ်ရုံဆွေးနွေးပွဲ အရင်းအမြစ်များ

### Python Samples

အဓိက concept တစ်ခုချင်းစီကို ဖော်ပြသော လက်တွေ့နမူနာများ:

| Session | Sample | Description | Run Time |
|---------|--------|-------------|----------|
| 1 | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | Basic & streaming chat | ~30s |
| 2 | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | RAG with embeddings | ~45s |
| 2 | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | RAG quality evaluation | ~60s |
| 3 | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | Multi-model benchmarking | ~2-3m |
| 4 | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | SLM vs LLM comparison | ~45s |
| 5 | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | Multi-agent system | ~60s |
| 6 | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | Intent-based routing | ~45s |
| 6 | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | Multi-step pipeline | ~60s |

### Jupyter Notebooks

ရှင်းလင်းချက်များနှင့် ရှင်းလင်းပြသမှုများပါဝင်သော interactive exploration:

| Session | Notebook | Description | Difficulty |
|---------|----------|-------------|------------|
| 1 | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | Chat basics & streaming | ⭐ Beginner |
| 2 | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline.ipynb) | Build RAG system | ⭐⭐ Intermediate |
| 2 | [`session02_rag_eval_ragas.ipynb`](./notebooks/session02_rag_eval_ragas.ipynb) | Evaluate RAG quality | ⭐⭐ Intermediate |
| 3 | [`session03_benchmark_oss_models.ipynb`](./notebooks/session03_benchmark_oss_models.ipynb) | Model benchmarking | ⭐⭐ Intermediate |
| 4 | [`session04_model_compare.ipynb`](./notebooks/session04_model_compare.ipynb) | Model comparison | ⭐⭐ Intermediate |
| 5 | [`session05_agents_orchestrator.ipynb`](./notebooks/session05_agents_orchestrator.ipynb) | Agent orchestration | ⭐⭐⭐ Advanced |
| 6 | [`session06_models_router.ipynb`](./notebooks/session06_models_router.ipynb) | Intent routing | ⭐⭐⭐ Advanced |
| 6 | [`session06_models_pipeline.ipynb`](./notebooks/session06_models_pipeline.ipynb) | Pipeline orchestration | ⭐⭐⭐ Advanced |

### Documentation

လမ်းညွှန်များနှင့် ရည်ညွှန်းချက်များ:

| Document | Description | Use When |
|----------|-------------|----------|
| [QUICK_START.md](./QUICK_START.md) | Fast-track setup guide | Starting from scratch |
| [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) | Command & API cheat sheet | Need quick answers |
| [FOUNDRY_SDK_QUICKREF.md](./FOUNDRY_SDK_QUICKREF.md) | SDK patterns & examples | Writing code |
| [ENV_CONFIGURATION.md](./ENV_CONFIGURATION.md) | Environment variable guide | Configuring samples |
| [SAMPLES_UPDATE_SUMMARY.md](./SAMPLES_UPDATE_SUMMARY.md) | Latest sample improvements | Understanding changes |
| [SDK_MIGRATION_NOTES.md](./SDK_MIGRATION_NOTES.md) | Migration guide | Upgrading code |
| [notebooks/TROUBLESHOOTING.md](./notebooks/TROUBLESHOOTING.md) | Common issues & fixes | Debugging problems |

---

## 🎓 လေ့လာမှုလမ်းကြောင်း အကြံပြုချက်များ

### Beginner များအတွက် (3-4 နာရီ)
1. ✅ Session 1: စတင်ခြင်း (setup နှင့် basic chat အပေါ် အာရုံစိုက်ပါ)
2. ✅ Session 2: RAG Basics (evaluation ကို အစပိုင်းတွင် ကျော်သွားပါ)
3. ✅ Session 3: ရိုးရှင်းသော Benchmarking (model ၂ ခုသာ)
4. ⏭️ Sessions 4-6 ကို ယာယီ ကျော်သွားပါ
5. 🔄 ပထမဆုံး application တည်ဆောက်ပြီးနောက် Sessions 4-6 သို့ ပြန်လာပါ

### Intermediate Developers အတွက် (3 နာရီ)
1. ⚡ Session 1: Setup validation ကို အမြန်လုပ်ဆောင်ပါ
2. ✅ Session 2: RAG pipeline ကို evaluation ဖြင့် ပြည့်စုံစွာ ပြုလုပ်ပါ
3. ✅ Session 3: Benchmarking suite အပြည့်အစုံ
4. ✅ Session 4: Model optimization
5. ✅ Sessions 5-6: Architecture patterns အပေါ် အာရုံစိုက်ပါ

### Advanced Practitioners အတွက် (2-3 နာရီ)
1. ⚡ Sessions 1-3: Quick review နှင့် validation
2. ✅ Session 4: Optimization deep-dive
3. ✅ Session 5: Multi-agent architecture
4. ✅ Session 6: Production patterns နှင့် scaling
5. 🚀 Extend: Custom routing logic နှင့် hybrid deployments တည်ဆောက်ပါ

---

## အလုပ်ရုံဆွေးနွေးပွဲ Session Pack (30‑Minute Labs အာရုံစိုက်မှု)

Condensed 6-session workshop format ကို လိုက်နာနေပါက အောက်ပါ လမ်းညွှန်များကို အသုံးပြုပါ (တစ်ခုချင်းစီသည် module docs များနှင့် အညီဖြစ်သည်):

| Workshop Session | Guide | Core Focus |
|------------------|-------|------------|
| 1 | [Session01-GettingStartedFoundryLocal](./Session01-GettingStartedFoundryLocal.md) | Install, validate, run phi & GPT-OSS-20B, acceleration |
| 2
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | SLM နှင့် LLM, WebGPU, Chainlit RAG, ONNX acceleration |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | Agent အခန်းကဏ္ဍများ၊ မှတ်ဉာဏ်၊ ကိရိယာများ၊ စီမံခန့်ခွဲမှု |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | Routing, chaining, Azure သို့အရွယ်အစားချဲ့ထွင်ခြင်း |

Session ဖိုင်တစ်ခုစီတွင် ပါဝင်သည်မှာ - အကျဉ်းချုပ်၊ သင်ယူရမည့်ရည်ရွယ်ချက်များ၊ ၃၀ မိနစ်အတွင်း ပြသမှုစဉ်၊ စတင်ရန်ပရောဂျက်၊ အတည်ပြုမှုစာရင်း၊ ပြဿနာများကိုဖြေရှင်းခြင်းနှင့် Foundry Local Python SDK အတွက် တရားဝင်အညွှန်းများ။

### နမူနာ Scripts

Workshop အတွက်လိုအပ်သော dependencies ကိုထည့်သွင်းပါ (Windows):

```powershell
cd Workshop
py -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

macOS / Linux:

```bash
cd Workshop
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Foundry Local service ကို macOS မှ Windows စက်လုံး သို့မဟုတ် VM မှာ run လုပ်မယ်ဆို export endpoint ကိုသတ်မှတ်ပါ:

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| Session | Script(s) | ဖော်ပြချက် |
|---------|-----------|-------------|
| 1 | `samples/session01/chat_bootstrap.py` | Bootstrap service & streaming chat |
| 2 | `samples/session02/rag_pipeline.py` | အနည်းဆုံး RAG (in-memory embeddings) |
|   | `samples/session02/rag_eval_ragas.py` | RAG ကို ragas metrics ဖြင့်အကဲဖြတ်ခြင်း |
| 3 | `samples/session03/benchmark_oss_models.py` | Multi-model latency & throughput benchmarking |
| 4 | `samples/session04/model_compare.py` | SLM နှင့် LLM နှိုင်းယှဉ်ခြင်း (latency & sample output) |
| 5 | `samples/session05/agents_orchestrator.py` | Two-agent research → editorial pipeline |
| 6 | `samples/session06/models_router.py` | Intent-based routing demo |
|   | `samples/session06/models_pipeline.py` | Multi-step plan/execute/refine chain |

### Environment Variables (Samples များအတွက် အများဆုံး)

| Variable | ရည်ရွယ်ချက် | နမူနာ |
|----------|-------------|---------|
| `FOUNDRY_LOCAL_ALIAS` | အခြေခံနမူနာများအတွက် default single model alias | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | SLM နှင့် model အကြီးကြီးကိုနှိုင်းယှဉ်ရန် | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | benchmark လုပ်ရန် aliases များစာရင်း | `qwen2.5-0.5b,mistral-7b` |
| `BENCH_ROUNDS` | model တစ်ခုချင်းစီအတွက် benchmark ပြန်လုပ်မှု | `3` |
| `BENCH_PROMPT` | benchmarking တွင်အသုံးပြုသော prompt | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | Sentence-transformers embedding model | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | RAG pipeline အတွက် test query ကို override | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | agents pipeline query ကို override | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | research agent အတွက် model alias | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | editor agent အတွက် model alias (ကွဲပြားနိုင်သည်) | `gpt-oss-20b` |
| `SHOW_USAGE` | `1` ဖြစ်ပါက completion တစ်ခုစီအတွက် token usage ကို print လုပ်သည် | `1` |
| `RETRY_ON_FAIL` | `1` ဖြစ်ပါက transient chat errors တွေမှာတစ်ကြိမ်ပြန်လုပ်သည် | `1` |
| `RETRY_BACKOFF` | ပြန်လုပ်မည့်အချိန်အတွင်းစောင့်ဆိုင်းရမည့်စက္ကန့် | `1.0` |

Variable မရှိပါက script များသည် default အတိုင်းပြန်လည်လုပ်ဆောင်မည်။ Single-model demos များအတွက် `FOUNDRY_LOCAL_ALIAS` ကိုသာလိုအပ်သည်။

### Utility Module

နမူနာများအားလုံးသည် `samples/workshop_utils.py` helper ကိုမျှဝေပြီး:

* Cached `FoundryLocalManager` + OpenAI client ဖန်တီးခြင်း
* `chat_once()` helper (optional retry + usage printing ပါဝင်သည်)
* ရိုးရှင်းသော token usage report (enable via `SHOW_USAGE=1`)

ဤသည်သည် duplication ကိုလျှော့ချပြီး efficient local model orchestration အတွက်အကောင်းဆုံးအလေ့အကျင့်များကိုဖော်ပြသည်။

## Optional Enhancements (Cross-Session)

| Theme | Enhancement | Sessions | Env / Toggle |
|-------|-------------|----------|--------------|
| Determinism | Fixed temperature + stable prompt sets | 1–6 | Set `temperature=0`, `top_p=1` |
| Token Usage Visibility | Consistent cost/efficiency teaching | 1–6 | `SHOW_USAGE=1` |
| Streaming First Token | Perceived latency metric | 1,3,4,6 | `BENCH_STREAM=1` (benchmark) |
| Retry Resilience | Handles transient cold-start | All | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| Multi-Model Agents | Heterogeneous role specialization | 5 | `AGENT_MODEL_PRIMARY`, `AGENT_MODEL_EDITOR` |
| Adaptive Routing | Intent + cost heuristics | 6 | Extend router with escalation logic |
| Vector Memory | Long-term semantic recall | 2,5,6 | Integrate FAISS/Chroma embedding index |
| Trace Export | Auditing & evaluation | 2,5,6 | Append JSON lines per step |
| Quality Rubrics | Qualitative tracking | 3–6 | Secondary scoring prompts |
| Smoke Tests | Quick pre-workshop validation | All | `python Workshop/tests/smoke.py` |

### Deterministic Quick Start

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

တူညီသော input များကိုထပ်ခါတလဲလဲထည့်သွင်းခြင်းဖြင့် stable token count များကိုမျှော်လင့်နိုင်သည်။

### RAG Evaluation (Session 2)

`rag_eval_ragas.py` ကိုအသုံးပြု၍ tiny synthetic dataset တွင် relevancy, faithfulness, နှင့် context precision ကိုတွက်ချက်ပါ:

```powershell
cd Workshop/samples
python -m session02.rag_eval_ragas
```

မေးခွန်းများ၊ contexts နှင့် ground truths များပါဝင်သော JSONL အကြီးကိုထည့်သွင်းပြီး Hugging Face `Dataset` သို့ပြောင်းလဲခြင်းဖြင့်တိုးချဲ့နိုင်သည်။

## CLI Command Accuracy Appendix

Workshop သည် Foundry Local CLI commands တွင်လက်ရှိတရားဝင်/တည်ငြိမ်သော command များကိုသာအသုံးပြုသည်။

### Stable Commands Referenced

| Category | Command | ရည်ရွယ်ချက် |
|----------|---------|-------------|
| Core | `foundry --version` | Installed version ကိုပြသည် |
| Core | `foundry init` | Configuration ကို initialize လုပ်သည် |
| Service | `foundry service start` | Local service ကိုစတင်သည် (auto မဟုတ်ပါက) |
| Service | `foundry status` | Service status ကိုပြသည် |
| Models | `foundry model list` | Catalog / available models ကိုစာရင်းပြုစုသည် |
| Models | `foundry model download <alias>` | Model weights များကို cache ထဲသို့ download လုပ်သည် |
| Models | `foundry model run <alias>` | Model ကို locally launch (load) လုပ်သည်; `--prompt` နှင့်ပေါင်းစပ်၍ one-shot |
| Models | `foundry model unload <alias>` / `foundry model stop <alias>` | Model ကို memory မှ unload လုပ်သည် (supported ဖြစ်ပါက) |
| Cache | `foundry cache list` | Cached (downloaded) models များကိုစာရင်းပြုစုသည် |
| System | `foundry system info` | Hardware & acceleration capabilities snapshot |
| System | `foundry system gpu-info` | GPU diagnostic info |
| Config | `foundry config list` | လက်ရှိ config values ကိုပြသည် |
| Config | `foundry config set <key> <value>` | Configuration ကို update လုပ်သည် |

### One‑Shot Prompt Pattern

Deprecated ဖြစ်သော `model chat` subcommand အစား:

```powershell
foundry model run <alias> --prompt "Your question here"
```

ဤသည်သည် prompt/response cycle တစ်ခုကို run လုပ်ပြီးနောက် exit လုပ်သည်။

### Removed / Avoided Patterns

| Deprecated / Undocumented | Replacement / Guidance |
|---------------------------|------------------------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | `foundry model list` + recent activity / logs ကိုအသုံးပြုပါ |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | Benchmark Python script + OS tools (Task Manager / `nvidia-smi`) ကိုအသုံးပြုပါ |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### Benchmarking & Telemetry

- Latency, p95, tokens/sec: `samples/session03/benchmark_oss_models.py`
- First-token latency (streaming): `BENCH_STREAM=1` ကို environment တွင် set လုပ်ပါ
- Resource usage: OS monitors (Task Manager, Activity Monitor, `nvidia-smi`) + `foundry system info` ကိုအသုံးပြုပါ။

CLI telemetry commands အသစ်များ upstream တွင်တည်ငြိမ်လာသည်နှင့်အညီ session markdown များတွင်အနည်းဆုံးပြင်ဆင်မှုများဖြင့်ထည့်သွင်းနိုင်သည်။

### Automated Lint Guard

Automated linter သည် markdown files ၏ fenced code blocks အတွင်း deprecated CLI patterns များပြန်လည်ထည့်သွင်းခြင်းကိုတားဆီးသည်:

Script: `Workshop/scripts/lint_markdown_cli.py`

Deprecated patterns များကို code fences အတွင်းတွင် block လုပ်သည်။

အကြံပြုထားသောအစားထိုးများ:
| Deprecated | Replacement |
|------------|-------------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | Benchmark script + system tools |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

Local မှ run လုပ်ပါ:
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

GitHub Action: `.github/workflows/markdown-cli-lint.yml` သည် push & PR တစ်ခုစီတွင် run လုပ်သည်။

Optional pre-commit hook:
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## Quick CLI → SDK Migration Table

| Task | CLI One-Liner | SDK (Python) Equivalent | မှတ်ချက်များ |
|------|---------------|-------------------------|-------|
| Run a model once (prompt) | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK သည် service & caching ကို auto bootstraps လုပ်သည် |
| Download (cache) model | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # triggers download/load` | Manager သည် alias များကိုအကောင်းဆုံး variant ရွေးချယ်သည် |
| List catalog | `foundry model list` | `# manager ကို alias တစ်ခုချင်းစီအတွက်အသုံးပြုပါ သို့မဟုတ် known list ကိုထိန်းသိမ်းပါ` | CLI သည် aggregate လုပ်သည်; SDK သည်လက်ရှိအခြေအနေမှာ per-alias instantiation ဖြစ်သည် |
| List cached models | `foundry cache list` | `manager.list_cached_models()` | Manager init (alias မည်သည့်အရာမဆို) ပြီးနောက် |
| Enable GPU acceleration | `foundry config set compute.onnx.enable_gpu true` | `# CLI action; SDK သည် config ကိုပြီးသား apply လုပ်ထားသည်ဟုယူဆသည်` | Configuration သည် external side effect ဖြစ်သည် |
| Get endpoint URL | (implicit) | `manager.endpoint` | OpenAI-compatible client ဖန်တီးရန်အသုံးပြုသည် |
| Warm a model | `foundry model run <alias>` then first prompt | `chat_once(alias, messages=[...])` (utility) | Utilities သည် initial cold latency warmup ကိုကိုင်တွယ်သည် |
| Measure latency | `python -m session03.benchmark_oss_models` | `import benchmark_oss_models` (သို့မဟုတ် new exporter script) | Consistent metrics အတွက် script ကိုအသုံးပြုပါ |
| Stop / unload model | `foundry model unload <alias>` | (Not exposed – service / process ကို restart လုပ်ပါ) | Workshop flow အတွက်မလိုအပ်ပါ |
| Retrieve token usage | (output ကိုကြည့်ပါ) | `resp.usage.total_tokens` | Backend သည် usage object ကိုပြန်ပေးပါကရရှိနိုင်သည် |

## Benchmark Markdown Export

`Workshop/scripts/export_benchmark_markdown.py` script ကိုအသုံးပြု၍ fresh benchmark ကို run လုပ်ပြီး GitHub-friendly Markdown table နှင့် raw JSON ကိုထုတ်ပေးပါ။

### နမူနာ

```powershell
python Workshop\scripts\export_benchmark_markdown.py --models "qwen2.5-0.5b,mistral-7b" --prompt "Explain retrieval augmented generation briefly." --rounds 3 --output benchmark_report.md
```

ထုတ်လုပ်ထားသောဖိုင်များ:
| File | Contents |
|------|----------|
| `benchmark_report.md` | Markdown table + interpretation hints |
| `benchmark_report.json` | Raw metrics array (diffing / trend tracking အတွက်) |

Environment တွင် `BENCH_STREAM=1` ကို set လုပ်၍ first-token latency ကိုထည့်သွင်းပါ (supported ဖြစ်ပါက)။

---

**အကြောင်းကြားချက်**:  
ဤစာရွက်စာတမ်းကို AI ဘာသာပြန်ဝန်ဆောင်မှု [Co-op Translator](https://github.com/Azure/co-op-translator) ကို အသုံးပြု၍ ဘာသာပြန်ထားပါသည်။ ကျွန်ုပ်တို့သည် တိကျမှုအတွက် ကြိုးစားနေသော်လည်း အလိုအလျောက် ဘာသာပြန်မှုများတွင် အမှားများ သို့မဟုတ် မတိကျမှုများ ပါဝင်နိုင်သည်ကို သတိပြုပါ။ မူရင်းဘာသာစကားဖြင့် ရေးသားထားသော စာရွက်စာတမ်းကို အာဏာတရားရှိသော အရင်းအမြစ်အဖြစ် သတ်မှတ်သင့်ပါသည်။ အရေးကြီးသော အချက်အလက်များအတွက် လူသားမှ ပရော်ဖက်ရှင်နယ် ဘာသာပြန်မှုကို အကြံပြုပါသည်။ ဤဘာသာပြန်မှုကို အသုံးပြုခြင်းမှ ဖြစ်ပေါ်လာသော အလွဲအမှားများ သို့မဟုတ် အနားယူမှုများအတွက် ကျွန်ုပ်တို့သည် တာဝန်မယူပါ။