<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "d9e354c0182311726dc037a8809524e2",
  "translation_date": "2025-10-28T23:34:49+00:00",
  "source_file": "Workshop/Session04-CuttingEdgeModels.md",
  "language_code": "my"
}
-->
# အစည်းအဝေး ၄: နောက်ဆုံးပေါ်မော်ဒယ်များကို ရှာဖွေပါ – LLMs, SLMs & On-Device Inference

## အကျဉ်းချုပ်

Local နှင့် Cloud Inference အခြေအနေများအတွက် Large Language Models (LLMs) နှင့် Small Language Models (SLMs) ကို နှိုင်းယှဉ်ပါ။ ONNX Runtime acceleration, WebGPU execution, နှင့် hybrid RAG အတွေ့အကြုံများကို အသုံးပြု၍ deployment patterns ကို သင်ယူပါ။ Chainlit RAG demo ကို local model နှင့်အတူ ပြသပြီး OpenWebUI exploration ကို ရွေးချယ်နိုင်ပါသည်။ WebGPU inference starter ကို ပြင်ဆင်ပြီး Phi နှင့် GPT-OSS-20B ၏ capability & cost/perf trade-offs ကို အကဲဖြတ်ပါ။

## သင်ယူရမည့် ရည်ရွယ်ချက်များ

- **နှိုင်းယှဉ်ပါ** SLM နှင့် LLM ကို latency, memory, quality axes အပေါ်
- **Deploy** မော်ဒယ်များကို ONNXRuntime နှင့် (support ရှိသောနေရာတွင်) WebGPU ဖြင့်
- **Run** browser-based inference (privacy-preserving interactive demo)
- **Integrate** Chainlit RAG pipeline ကို local SLM backend နှင့်
- **Evaluate** lightweight quality + cost heuristics အသုံးပြု၍

## ကြိုတင်လိုအပ်ချက်များ

- အစည်းအဝေး ၁–၃ ပြီးစီးထားရမည်
- `chainlit` install လုပ်ထားရမည် (`requirements.txt` တွင် Module08 အတွက် ရှိပြီးသား)
- WebGPU-capable browser (Windows 11 အတွက် Edge / Chrome latest)
- Foundry Local running (`foundry status`)

### Cross-Platform မှတ်ချက်များ

Windows သည် primary target environment ဖြစ်သည်။ macOS developer များအတွက် native binaries မရရှိသေးသည့်အခြေအနေတွင်:
1. Foundry Local ကို Windows 11 VM (Parallels / UTM) OR remote Windows workstation တွင် run လုပ်ပါ။
2. Service ကို (default port 5273) expose လုပ်ပြီး macOS တွင် set လုပ်ပါ:
```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```
3. အစည်းအဝေးများတွင် အသုံးပြုခဲ့သော Python virtual environment အဆင့်များကို အသုံးပြုပါ။

Chainlit install (platform နှစ်ခုအတွက်):
```bash
pip install chainlit
```

## Demo Flow (၃၀ မိနစ်)

### ၁. Phi (SLM) နှင့် GPT-OSS-20B (LLM) ကို နှိုင်းယှဉ်ပါ (၆ မိနစ်)

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

Track: response depth, factual accuracy, stylistic richness, latency.

### ၂. ONNX Runtime Acceleration (၅ မိနစ်)

```powershell
foundry config set compute.onnx.enable_gpu true
# Re-run Python benchmark script for quantitative latency / throughput after enabling GPU
#   cd Workshop/samples
#   set BENCH_MODELS=phi-4-mini
#   python -m session03.benchmark_oss_models
```

GPU ကို enable လုပ်ပြီး CPU-only နှင့် throughput အပြောင်းအလဲကို ကြည့်ပါ။

### ၃. WebGPU Inference in Browser (၆ မိနစ်)

Starter `04-webgpu-inference` ကို ပြင်ဆင်ပါ (create `samples/04-cutting-edge/webgpu_demo.html`):

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

File ကို browser တွင်ဖွင့်ပါ; low-latency local roundtrip ကို ကြည့်ပါ။

### ၄. Chainlit RAG Chat App (၇ မိနစ်)

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

Run:

```powershell
chainlit run samples/04-cutting-edge/chainlit_app.py -w
```

### ၅. Starter Project: Adapt `04-webgpu-inference` (၆ မိနစ်)

Deliverables:
- Placeholder fetch logic ကို streaming tokens ဖြင့် အစားထိုးပါ (`stream=True` endpoint variant ကို enable လုပ်ပြီးအသုံးပြုပါ)
- Latency chart (client-side) ကို phi နှင့် gpt-oss-20b toggles အတွက် ထည့်ပါ
- RAG context ကို inline ထည့်ပါ (textarea for reference docs)

## အကဲဖြတ်မှု Heuristics

| Category | Phi-4-mini | GPT-OSS-20B | Observation |
|----------|------------|-------------|-------------|
| Latency (cold) | အလွန်မြန် | ပိုနှေး | SLM သည် အလွန်မြန်စွာ အပူပေးနိုင်သည် |
| Memory | နည်း | များ | Device feasibility |
| Context adherence | ကောင်း | အလွန်ကောင်း | Model ကြီးသည် ပို verbose ဖြစ်နိုင်သည် |
| Cost (local) | အနည်းငယ် | ပိုများ (resource) | Energy/time trade-off |
| Best use case | Edge apps | Deep reasoning | Hybrid pipeline ဖြစ်နိုင်သည် |

## Environment ကို Validate လုပ်ခြင်း

```powershell
# List catalog (no --running flag; loaded models are those you have previously run)
foundry model list

# For runtime metrics use the Python benchmark script (Session 3) and OS tools (Task Manager / nvidia-smi) instead of 'model stats'
# Example:
#   cd Workshop/samples
#   set BENCH_MODELS=phi-4-mini,gpt-oss-20b
#   python -m session03.benchmark_oss_models
```

## Troubleshooting

| Symptom | Cause | Action |
|---------|-------|--------|
| Web page fetch fails | CORS or service down | Endpoint ကို `curl` ဖြင့် verify လုပ်ပါ; CORS proxy ကို enable လုပ်ပါ |
| Chainlit blank | Env not active | venv ကို activate လုပ်ပြီး dependencies ကို reinstall လုပ်ပါ |
| High latency | Model just loaded | Small prompt sequence ဖြင့် warm လုပ်ပါ |

## References

- Foundry Local SDK: https://github.com/microsoft/Foundry-Local/tree/main/sdk/python
- Chainlit Docs: https://docs.chainlit.io
- RAG Evaluation (Ragas): https://docs.ragas.io

---

**Session Duration**: ၃၀ မိနစ်  
**Difficulty**: Advanced

## Sample Scenario & Workshop Mapping

| Workshop Artifacts | Scenario | Objective | Data / Prompt Source |
|--------------------|----------|-----------|----------------------|
| `samples/session04/model_compare.py` / `notebooks/session04_model_compare.ipynb` | Architecture team evaluating SLM vs LLM for executive summary generator | Latency နှင့် token usage delta ကို တိုင်းတာပါ | Single `COMPARE_PROMPT` env var |
| `chainlit_app.py` (RAG demo) | Internal knowledge assistant prototype | Short answers ကို minimal lexical retrieval ဖြင့် ground လုပ်ပါ | Inline `DOCS` list in file |
| `webgpu_demo.html` | Futuristic on‑device browser inference preview | Low‑latency local roundtrip + UX narrative ကို ပြသပါ | Live user prompt only |

### Scenario Narrative
Product org သည် executive briefing generator ကိုလိုအပ်သည်။ Lightweight SLM (phi‑4‑mini) သည် summary များကို draft လုပ်ပြီး; LLM (gpt‑oss‑20b) သည် high‑priority reports များကိုသာ refine လုပ်နိုင်သည်။ Session scripts သည် empirical latency & token metrics ကို capture လုပ်ပြီး hybrid design ကို အတည်ပြုရန် အသုံးပြုသည်။ Chainlit demo သည် grounded retrieval သည် small model answers ကို factual ဖြစ်စေသည့်အတိုင်း ပြသသည်။ WebGPU concept page သည် browser acceleration mature ဖြစ်လာသောအခါ fully client‑side processing အတွက် vision path ကို ပေးသည်။

### Minimal RAG Context (Chainlit)
```python
DOCS = [
  "Foundry Local enables local model execution with OpenAI-compatible APIs.",
  "RAG combines retrieval and generation for grounded answers.",
  "SLMs provide efficiency advantages on constrained hardware."
]
```

### Hybrid Draft→Refine Flow (Pseudo)
```python
draft, _ = chat_once('phi-4-mini', messages=[{"role":"user","content":prompt}], max_tokens=280)
if len(draft) < 600:  # heuristic: escalate only for longer briefs or flagged topics
    final = draft
else:
    final, _ = chat_once('gpt-oss-20b', messages=[{"role":"user","content":f"Refine and polish:\n{draft}"}], max_tokens=220)
```

Latency components နှစ်ခုလုံးကို track လုပ်ပြီး blended average cost ကို report လုပ်ပါ။

### Optional Enhancements

| Focus | Enhancement | Why | Implementation Hint |
|-------|------------|-----|---------------------|
| Comparative Metrics | Token usage + first-token latency ကို track လုပ်ပါ | Holistic perf view | Enhanced benchmark script (Session 3) ကို `BENCH_STREAM=1` ဖြင့် အသုံးပြုပါ |
| Hybrid Pipeline | SLM draft → LLM refine | Latency နှင့် cost ကို လျှော့ချရန် | phi-4-mini ဖြင့် generate လုပ်ပြီး summary ကို gpt-oss-20b ဖြင့် refine လုပ်ပါ |
| Streaming UI | Chainlit တွင် UX ကို ပိုကောင်းစေရန် | Incremental feedback | `stream=True` ကို local streaming expose လုပ်ပြီး အသုံးပြုပါ; chunks များကို စုစည်းပါ |
| WebGPU Caching | JS init ကို ပိုမြန်စေရန် | Recompile overhead ကို လျှော့ချရန် | Compiled shader artifacts ကို cache လုပ်ပါ (runtime capability အနာဂတ်တွင်) |
| Deterministic QA Set | Fair model comparison | Variance ကို ဖယ်ရှားရန် | Fixed prompt list + `temperature=0` ကို evaluation runs အတွက် အသုံးပြုပါ |
| Output Scoring | Structured quality lens | Anecdotes ထက် ပိုမိုတိကျသော အကဲဖြတ်မှု | Simple rubric: coherence / factuality / brevity (1–5) |
| Energy / Resource Notes | Classroom discussion | Trade-offs ကို ပြသရန် | OS monitors (`foundry system info`, Task Manager, `nvidia-smi`) + benchmark script outputs ကို အသုံးပြုပါ |
| Cost Emulation | Pre-cloud justification | Scaling ကို စီမံရန် | Tokens များကို hypothetical cloud pricing နှင့် map လုပ်ပြီး TCO narrative ကို ပြုလုပ်ပါ |
| Latency Decomposition | Bottlenecks ကို ရှာဖွေရန် | Optimizations ကို target လုပ်ရန် | Prompt prep, request send, first token, full completion ကို တိုင်းတာပါ |
| RAG + LLM Fallback | Quality safety net | မဖြေရှင်းနိုင်သော queries များကို တိုးတက်စေရန် | SLM answer length < threshold သို့မဟုတ် low confidence ဖြစ်ပါက → escalate လုပ်ပါ |

#### Example Hybrid Draft/Refine Pattern

```python
draft, _ = chat_once('phi-4-mini', messages=[{"role":"user","content":task}], max_tokens=300, temperature=0.4)
refine, _ = chat_once('gpt-oss-20b', messages=[{"role":"user","content":f"Improve clarity but keep facts:\n{draft}"}], max_tokens=220, temperature=0.3)
```

#### Latency Breakdown Sketch

```python
import time
t0 = time.time(); # build messages
prep_ms = (time.time()-t0)*1000
t1 = time.time(); text,_ = chat_once(alias, messages=msgs, max_tokens=180)
full_ms = (time.time()-t1)*1000
print({"prep_ms": prep_ms, "full_gen_ms": full_ms})
```

Models များကို fair comparisons အတွက် consistent measurement scaffolding ကို အသုံးပြုပါ။

---

**အကြောင်းကြားချက်**:  
ဤစာရွက်စာတမ်းကို AI ဘာသာပြန်ဝန်ဆောင်မှု [Co-op Translator](https://github.com/Azure/co-op-translator) ကို အသုံးပြု၍ ဘာသာပြန်ထားပါသည်။ ကျွန်ုပ်တို့သည် တိကျမှုအတွက် ကြိုးစားနေသော်လည်း အလိုအလျောက် ဘာသာပြန်မှုများတွင် အမှားများ သို့မဟုတ် မတိကျမှုများ ပါဝင်နိုင်သည်ကို သတိပြုပါ။ မူရင်းဘာသာစကားဖြင့် ရေးသားထားသော စာရွက်စာတမ်းကို အာဏာတရားရှိသော အရင်းအမြစ်အဖြစ် သတ်မှတ်သင့်ပါသည်။ အရေးကြီးသော အချက်အလက်များအတွက် လူက ဘာသာပြန်မှုကို အကြံပြုပါသည်။ ဤဘာသာပြန်မှုကို အသုံးပြုခြင်းမှ ဖြစ်ပေါ်လာသော အလွဲအမှားများ သို့မဟုတ် အနားလွဲမှုများအတွက် ကျွန်ုပ်တို့သည် တာဝန်မယူပါ။