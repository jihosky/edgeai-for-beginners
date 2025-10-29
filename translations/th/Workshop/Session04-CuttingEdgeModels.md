<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "d9e354c0182311726dc037a8809524e2",
  "translation_date": "2025-10-28T21:58:11+00:00",
  "source_file": "Workshop/Session04-CuttingEdgeModels.md",
  "language_code": "th"
}
-->
# เซสชัน 4: สำรวจโมเดลล้ำสมัย – LLMs, SLMs และการประมวลผลบนอุปกรณ์

## บทคัดย่อ

เปรียบเทียบ Large Language Models (LLMs) และ Small Language Models (SLMs) สำหรับสถานการณ์การประมวลผลในเครื่องและบนคลาวด์ เรียนรู้รูปแบบการปรับใช้งานที่ใช้การเร่งความเร็วของ ONNX Runtime, การประมวลผลด้วย WebGPU และประสบการณ์แบบไฮบริด RAG รวมถึงการสาธิต Chainlit RAG ด้วยโมเดลในเครื่อง พร้อมการสำรวจ OpenWebUI ที่เป็นตัวเลือก คุณจะปรับการเริ่มต้นการประมวลผล WebGPU และประเมินความสามารถและการแลกเปลี่ยนต้นทุน/ประสิทธิภาพระหว่าง Phi และ GPT-OSS-20B

## วัตถุประสงค์การเรียนรู้

- **เปรียบเทียบ** SLM กับ LLM ในด้านความหน่วงเวลา, หน่วยความจำ, และคุณภาพ
- **ปรับใช้** โมเดลด้วย ONNXRuntime และ (ในกรณีที่รองรับ) WebGPU
- **เรียกใช้** การประมวลผลในเบราว์เซอร์ (การสาธิตแบบโต้ตอบที่รักษาความเป็นส่วนตัว)
- **ผสานรวม** ท่อส่ง Chainlit RAG กับ SLM ในเครื่อง
- **ประเมิน** โดยใช้ตัวชี้วัดคุณภาพและต้นทุนที่เบา

## ข้อกำหนดเบื้องต้น

- ผ่านเซสชัน 1–3 แล้ว
- ติดตั้ง `chainlit` (มีอยู่ใน `requirements.txt` สำหรับ Module08)
- เบราว์เซอร์ที่รองรับ WebGPU (Edge / Chrome เวอร์ชันล่าสุดบน Windows 11)
- Foundry Local ทำงานอยู่ (`foundry status`)

### หมายเหตุข้ามแพลตฟอร์ม

Windows ยังคงเป็นเป้าหมายหลัก สำหรับนักพัฒนาบน macOS ที่รอไบนารีเนทีฟ:
1. รัน Foundry Local ใน VM Windows 11 (Parallels / UTM) หรือเวิร์กสเตชัน Windows ระยะไกล
2. เปิดเผยบริการ (พอร์ตเริ่มต้น 5273) และตั้งค่าบน macOS:
```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```
3. ใช้ขั้นตอนสภาพแวดล้อมเสมือน Python เดียวกันกับเซสชันก่อนหน้า

การติดตั้ง Chainlit (ทั้งสองแพลตฟอร์ม):
```bash
pip install chainlit
```

## ลำดับการสาธิต (30 นาที)

### 1. เปรียบเทียบ Phi (SLM) กับ GPT-OSS-20B (LLM) (6 นาที)

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

ติดตาม: ความลึกของการตอบกลับ, ความถูกต้องของข้อมูล, ความหลากหลายของสไตล์, ความหน่วงเวลา

### 2. การเร่งความเร็วด้วย ONNX Runtime (5 นาที)

```powershell
foundry config set compute.onnx.enable_gpu true
# Re-run Python benchmark script for quantitative latency / throughput after enabling GPU
#   cd Workshop/samples
#   set BENCH_MODELS=phi-4-mini
#   python -m session03.benchmark_oss_models
```

สังเกตการเปลี่ยนแปลงของปริมาณงานหลังจากเปิดใช้งาน GPU เทียบกับ CPU เท่านั้น

### 3. การประมวลผล WebGPU ในเบราว์เซอร์ (6 นาที)

ปรับการเริ่มต้น `04-webgpu-inference` (สร้าง `samples/04-cutting-edge/webgpu_demo.html`):

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

เปิดไฟล์ในเบราว์เซอร์; สังเกตการตอบกลับที่มีความหน่วงต่ำในเครื่อง

### 4. แอปแชท Chainlit RAG (7 นาที)

`samples/04-cutting-edge/chainlit_app.py` ขั้นต่ำ:

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

รัน:

```powershell
chainlit run samples/04-cutting-edge/chainlit_app.py -w
```

### 5. โครงการเริ่มต้น: ปรับ `04-webgpu-inference` (6 นาที)

สิ่งที่ต้องส่งมอบ:
- แทนที่ตรรกะการดึงข้อมูลตัวอย่างด้วยการสตรีมโทเค็น (ใช้ตัวแปร endpoint `stream=True` เมื่อเปิดใช้งาน)
- เพิ่มแผนภูมิความหน่วงเวลา (ฝั่งไคลเอนต์) สำหรับการสลับระหว่าง phi และ gpt-oss-20b
- ฝังบริบท RAG แบบอินไลน์ (กล่องข้อความสำหรับเอกสารอ้างอิง)

## ตัวชี้วัดการประเมิน

| หมวดหมู่ | Phi-4-mini | GPT-OSS-20B | ข้อสังเกต |
|----------|------------|-------------|-------------|
| ความหน่วงเวลา (เริ่มต้น) | เร็ว | ช้ากว่า | SLM อุ่นเครื่องได้เร็ว |
| หน่วยความจำ | ต่ำ | สูง | ความเป็นไปได้ในการใช้งานบนอุปกรณ์ |
| การยึดติดกับบริบท | ดี | แข็งแกร่ง | โมเดลขนาดใหญ่อาจมีความละเอียดมากกว่า |
| ต้นทุน (ในเครื่อง) | น้อยมาก | สูงกว่า (ทรัพยากร) | การแลกเปลี่ยนพลังงาน/เวลา |
| กรณีการใช้งานที่ดีที่สุด | แอปบนอุปกรณ์ | การให้เหตุผลเชิงลึก | ท่อส่งแบบไฮบริดเป็นไปได้ |

## การตรวจสอบสภาพแวดล้อม

```powershell
# List catalog (no --running flag; loaded models are those you have previously run)
foundry model list

# For runtime metrics use the Python benchmark script (Session 3) and OS tools (Task Manager / nvidia-smi) instead of 'model stats'
# Example:
#   cd Workshop/samples
#   set BENCH_MODELS=phi-4-mini,gpt-oss-20b
#   python -m session03.benchmark_oss_models
```

## การแก้ไขปัญหา

| อาการ | สาเหตุ | การดำเนินการ |
|-------|-------|-------------|
| การดึงหน้าเว็บล้มเหลว | CORS หรือบริการล่ม | ใช้ `curl` เพื่อตรวจสอบ endpoint; เปิดใช้งาน CORS proxy หากจำเป็น |
| Chainlit ว่างเปล่า | สภาพแวดล้อมไม่ทำงาน | เปิดใช้งาน venv และติดตั้ง dependencies ใหม่ |
| ความหน่วงสูง | โมเดลเพิ่งโหลด | อุ่นเครื่องด้วยลำดับ prompt สั้น ๆ |

## อ้างอิง

- Foundry Local SDK: https://github.com/microsoft/Foundry-Local/tree/main/sdk/python
- เอกสาร Chainlit: https://docs.chainlit.io
- การประเมิน RAG (Ragas): https://docs.ragas.io

---

**ระยะเวลาเซสชัน**: 30 นาที  
**ระดับความยาก**: ขั้นสูง

## ตัวอย่างสถานการณ์และการจับคู่เวิร์กช็อป

| สิ่งประดิษฐ์ในเวิร์กช็อป | สถานการณ์ | วัตถุประสงค์ | แหล่งข้อมูล / prompt |
|--------------------|----------|-----------|----------------------|
| `samples/session04/model_compare.py` / `notebooks/session04_model_compare.ipynb` | ทีมสถาปัตยกรรมประเมิน SLM กับ LLM สำหรับตัวสร้างสรุปผู้บริหาร | วัดความแตกต่างของความหน่วงเวลา + การใช้โทเค็น | ตัวแปรสภาพแวดล้อม `COMPARE_PROMPT` เดียว |
| `chainlit_app.py` (การสาธิต RAG) | ต้นแบบผู้ช่วยความรู้ภายใน | ตอบคำถามสั้น ๆ โดยมีการดึงข้อมูลน้อยที่สุด | รายการ `DOCS` แบบอินไลน์ในไฟล์ |
| `webgpu_demo.html` | การประมวลผลในเบราว์เซอร์บนอุปกรณ์ในอนาคต | แสดงการตอบกลับที่มีความหน่วงต่ำในเครื่อง + การเล่าเรื่อง UX | prompt ผู้ใช้สดเท่านั้น |

### การเล่าเรื่องสถานการณ์
องค์กรผลิตภัณฑ์ต้องการตัวสร้างสรุปสำหรับการบรรยายสรุปผู้บริหาร SLM น้ำหนักเบา (phi‑4‑mini) สร้างสรุป; LLM ขนาดใหญ่ (gpt‑oss‑20b) อาจปรับปรุงเฉพาะรายงานที่มีความสำคัญสูง สคริปต์เซสชันจับตัวชี้วัดความหน่วงเวลาและโทเค็นเชิงประจักษ์เพื่อให้เหตุผลการออกแบบแบบไฮบริด ในขณะที่การสาธิต Chainlit แสดงให้เห็นว่าการดึงข้อมูลที่มีพื้นฐานช่วยให้คำตอบของโมเดลขนาดเล็กมีความถูกต้อง การสาธิตแนวคิดหน้า WebGPU ให้เส้นทางวิสัยทัศน์สำหรับการประมวลผลแบบฝั่งไคลเอนต์ทั้งหมดเมื่อการเร่งความเร็วในเบราว์เซอร์พัฒนาเต็มที่

### บริบท RAG ขั้นต่ำ (Chainlit)
```python
DOCS = [
  "Foundry Local enables local model execution with OpenAI-compatible APIs.",
  "RAG combines retrieval and generation for grounded answers.",
  "SLMs provide efficiency advantages on constrained hardware."
]
```

### รูปแบบไฮบริด Draft→Refine (Pseudo)
```python
draft, _ = chat_once('phi-4-mini', messages=[{"role":"user","content":prompt}], max_tokens=280)
if len(draft) < 600:  # heuristic: escalate only for longer briefs or flagged topics
    final = draft
else:
    final, _ = chat_once('gpt-oss-20b', messages=[{"role":"user","content":f"Refine and polish:\n{draft}"}], max_tokens=220)
```

ติดตามทั้งสองส่วนของความหน่วงเวลาเพื่อรายงานต้นทุนเฉลี่ยแบบผสม

### การปรับปรุงเพิ่มเติมที่เป็นตัวเลือก

| โฟกัส | การปรับปรุง | เหตุผล | คำแนะนำการดำเนินการ |
|-------|------------|-----|---------------------|
| ตัวชี้วัดเปรียบเทียบ | ติดตามการใช้โทเค็น + ความหน่วงของโทเค็นแรก | มุมมองประสิทธิภาพแบบองค์รวม | ใช้สคริปต์ benchmark ที่ปรับปรุงแล้ว (เซสชัน 3) พร้อม `BENCH_STREAM=1` |
| ท่อส่งแบบไฮบริด | SLM สร้าง → LLM ปรับปรุง | ลดความหน่วงและต้นทุน | สร้างด้วย phi-4-mini, ปรับปรุงสรุปด้วย gpt-oss-20b |
| UI สตรีมมิ่ง | UX ที่ดีกว่าใน Chainlit | ข้อเสนอแนะทีละขั้นตอน | ใช้ `stream=True` เมื่อการสตรีมในเครื่องเปิดใช้งาน; สะสมชิ้นส่วน |
| การแคช WebGPU | การเริ่มต้น JS ที่เร็วขึ้น | ลดค่าใช้จ่ายในการคอมไพล์ใหม่ | แคชสิ่งประดิษฐ์ shader ที่คอมไพล์แล้ว (ความสามารถ runtime ในอนาคต) |
| ชุด QA ที่กำหนด | การเปรียบเทียบโมเดลที่ยุติธรรม | ลดความแปรปรวน | รายการ prompt คงที่ + `temperature=0` สำหรับการรันการประเมิน |
| การให้คะแนนผลลัพธ์ | เลนส์คุณภาพที่มีโครงสร้าง | ก้าวข้ามการเล่าเรื่อง | รูบิคง่าย ๆ: ความสอดคล้อง / ความถูกต้อง / ความกระชับ (1–5) |
| หมายเหตุพลังงาน / ทรัพยากร | การอภิปรายในห้องเรียน | แสดงการแลกเปลี่ยน | ใช้ตัวตรวจสอบ OS (`foundry system info`, Task Manager, `nvidia-smi`) + ผลลัพธ์สคริปต์ benchmark |
| การจำลองต้นทุน | การให้เหตุผลก่อนคลาวด์ | วางแผนการปรับขนาด | แมปโทเค็นกับการกำหนดราคาคลาวด์สมมุติสำหรับการเล่าเรื่อง TCO |
| การแยกส่วนความหน่วงเวลา | ระบุคอขวด | เป้าหมายการปรับปรุง | วัดการเตรียม prompt, การส่งคำขอ, โทเค็นแรก, การเสร็จสิ้นทั้งหมด |
| RAG + LLM สำรอง | เครือข่ายความปลอดภัยคุณภาพ | ปรับปรุงคำถามที่ยาก | หากความยาวคำตอบ SLM < เกณฑ์หรือความมั่นใจต่ำ → ยกระดับ |

#### รูปแบบไฮบริด Draft/Refine ตัวอย่าง

```python
draft, _ = chat_once('phi-4-mini', messages=[{"role":"user","content":task}], max_tokens=300, temperature=0.4)
refine, _ = chat_once('gpt-oss-20b', messages=[{"role":"user","content":f"Improve clarity but keep facts:\n{draft}"}], max_tokens=220, temperature=0.3)
```

#### สเก็ตช์การแยกส่วนความหน่วงเวลา

```python
import time
t0 = time.time(); # build messages
prep_ms = (time.time()-t0)*1000
t1 = time.time(); text,_ = chat_once(alias, messages=msgs, max_tokens=180)
full_ms = (time.time()-t1)*1000
print({"prep_ms": prep_ms, "full_gen_ms": full_ms})
```

ใช้โครงสร้างการวัดที่สอดคล้องกันระหว่างโมเดลเพื่อการเปรียบเทียบที่ยุติธรรม

---

**ข้อจำกัดความรับผิดชอบ**:  
เอกสารนี้ได้รับการแปลโดยใช้บริการแปลภาษา AI [Co-op Translator](https://github.com/Azure/co-op-translator) แม้ว่าเราจะพยายามให้การแปลมีความถูกต้อง แต่โปรดทราบว่าการแปลอัตโนมัติอาจมีข้อผิดพลาดหรือความไม่ถูกต้อง เอกสารต้นฉบับในภาษาที่เป็นต้นฉบับควรถือว่าเป็นแหล่งข้อมูลที่เชื่อถือได้ สำหรับข้อมูลที่สำคัญ ขอแนะนำให้ใช้บริการแปลภาษามืออาชีพ เราไม่รับผิดชอบต่อความเข้าใจผิดหรือการตีความผิดที่เกิดจากการใช้การแปลนี้