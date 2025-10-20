<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b994c57f1207012e4d7f58b7c0d1ae7",
  "translation_date": "2025-10-17T09:42:16+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "th"
}
-->
# EdgeAI สำหรับผู้เริ่มต้น - เวิร์กช็อป

> **เส้นทางการเรียนรู้แบบลงมือปฏิบัติสำหรับการสร้างแอปพลิเคชัน Edge AI พร้อมใช้งานจริง**
>
> เรียนรู้การใช้งาน AI ในพื้นที่ด้วย Microsoft Foundry Local ตั้งแต่การสร้างแชทครั้งแรกไปจนถึงการจัดการหลายตัวแทนใน 6 เซสชันที่ก้าวหน้า

---

## 🎯 บทนำ

ยินดีต้อนรับสู่ **เวิร์กช็อป EdgeAI สำหรับผู้เริ่มต้น** - คู่มือการลงมือปฏิบัติจริงสำหรับการสร้างแอปพลิเคชันอัจฉริยะที่ทำงานบนฮาร์ดแวร์ในพื้นที่ทั้งหมด เวิร์กช็อปนี้เปลี่ยนแนวคิด Edge AI เชิงทฤษฎีให้กลายเป็นทักษะในโลกจริงผ่านการฝึกฝนที่ท้าทายมากขึ้นเรื่อย ๆ โดยใช้ Microsoft Foundry Local และ Small Language Models (SLMs)

### ทำไมต้องเข้าร่วมเวิร์กช็อปนี้?

**การปฏิวัติ Edge AI มาถึงแล้ว**

องค์กรทั่วโลกกำลังเปลี่ยนจาก AI ที่พึ่งพา Cloud ไปสู่การประมวลผล Edge ด้วยเหตุผลสำคัญสามประการ:

1. **ความเป็นส่วนตัวและการปฏิบัติตามกฎระเบียบ** - ประมวลผลข้อมูลที่ละเอียดอ่อนในพื้นที่โดยไม่ต้องส่งไปยัง Cloud (HIPAA, GDPR, กฎระเบียบทางการเงิน)
2. **ประสิทธิภาพ** - ลดความล่าช้าของเครือข่าย (50-500ms ในพื้นที่เทียบกับ 500-2000ms รอบการส่งข้อมูลไปยัง Cloud)
3. **การควบคุมต้นทุน** - ลดค่าใช้จ่าย API ต่อโทเค็นและขยายขนาดโดยไม่ต้องเสียค่าใช้จ่าย Cloud

**แต่ Edge AI นั้นแตกต่างออกไป**

การใช้งาน AI ในพื้นที่ต้องการทักษะใหม่:
- การเลือกและปรับแต่งโมเดลให้เหมาะสมกับข้อจำกัดของทรัพยากร
- การจัดการบริการในพื้นที่และการเร่งความเร็วฮาร์ดแวร์
- การออกแบบคำสั่งสำหรับโมเดลขนาดเล็ก
- รูปแบบการปรับใช้สำหรับอุปกรณ์ Edge

**เวิร์กช็อปนี้มอบทักษะเหล่านั้นให้คุณ**

ใน 6 เซสชันที่มุ่งเน้น (~3 ชั่วโมงทั้งหมด) คุณจะก้าวจาก "Hello World" ไปสู่การปรับใช้ระบบหลายตัวแทนที่พร้อมใช้งานจริง - ทั้งหมดทำงานในพื้นที่บนเครื่องของคุณ

---

## 📚 วัตถุประสงค์การเรียนรู้

เมื่อจบเวิร์กช็อปนี้ คุณจะสามารถ:

### ทักษะหลัก
1. **ปรับใช้และจัดการบริการ AI ในพื้นที่**
   - ติดตั้งและกำหนดค่า Microsoft Foundry Local
   - เลือกโมเดลที่เหมาะสมสำหรับการใช้งาน Edge
   - จัดการวงจรชีวิตของโมเดล (ดาวน์โหลด โหลด แคช)
   - ตรวจสอบการใช้งานทรัพยากรและปรับปรุงประสิทธิภาพ

2. **สร้างแอปพลิเคชันที่ขับเคลื่อนด้วย AI**
   - ใช้งานแชทที่เข้ากันได้กับ OpenAI ในพื้นที่
   - ออกแบบคำสั่งที่มีประสิทธิภาพสำหรับ Small Language Models
   - จัดการการตอบสนองแบบสตรีมเพื่อ UX ที่ดียิ่งขึ้น
   - ผสานรวมโมเดลในพื้นที่เข้ากับแอปพลิเคชันที่มีอยู่

3. **สร้างระบบ RAG (Retrieval Augmented Generation)**
   - สร้างการค้นหาเชิงความหมายด้วย embeddings
   - เชื่อมโยงการตอบสนอง LLM กับความรู้เฉพาะด้าน
   - ประเมินคุณภาพ RAG ด้วยเมตริกมาตรฐานอุตสาหกรรม
   - ขยายจากต้นแบบไปสู่การใช้งานจริง

4. **ปรับปรุงประสิทธิภาพของโมเดล**
   - ทดสอบโมเดลหลายตัวสำหรับกรณีการใช้งานของคุณ
   - วัดความล่าช้า อัตราการส่งข้อมูล และเวลาการตอบสนองโทเค็นแรก
   - เลือกโมเดลที่เหมาะสมที่สุดตามการแลกเปลี่ยนระหว่างความเร็ว/คุณภาพ
   - เปรียบเทียบข้อดีข้อเสียระหว่าง SLM และ LLM ในสถานการณ์จริง

5. **จัดการระบบหลายตัวแทน**
   - ออกแบบตัวแทนเฉพาะสำหรับงานต่าง ๆ
   - ใช้งานหน่วยความจำและการจัดการบริบทของตัวแทน
   - ประสานงานตัวแทนในกระบวนการทำงานที่ซับซ้อน
   - เส้นทางคำขออย่างชาญฉลาดระหว่างโมเดลหลายตัว

6. **ปรับใช้โซลูชันที่พร้อมใช้งานจริง**
   - ใช้งานการจัดการข้อผิดพลาดและตรรกะการลองใหม่
   - ตรวจสอบการใช้งานโทเค็นและทรัพยากรระบบ
   - สร้างสถาปัตยกรรมที่สามารถขยายได้ด้วยรูปแบบ model-as-tools
   - วางแผนเส้นทางการย้ายจาก Edge ไปยัง Hybrid (Edge + Cloud)

---

## 🎓 ผลลัพธ์การเรียนรู้

### สิ่งที่คุณจะสร้าง

เมื่อจบเวิร์กช็อปนี้ คุณจะได้สร้าง:

| เซสชัน | ผลงาน | ทักษะที่แสดง |
|--------|--------|--------------|
| **1** | แอปพลิเคชันแชทพร้อมการสตรีม | การตั้งค่าบริการ การตอบสนองพื้นฐาน UX สตรีม |
| **2** | ระบบ RAG พร้อมการประเมิน | Embeddings การค้นหาเชิงความหมาย เมตริกคุณภาพ |
| **3** | ชุดทดสอบเปรียบเทียบโมเดลหลายตัว | การวัดประสิทธิภาพ การเปรียบเทียบโมเดล |
| **4** | ตัวเปรียบเทียบ SLM กับ LLM | การวิเคราะห์ข้อดีข้อเสีย กลยุทธ์การปรับปรุง |
| **5** | ตัวจัดการหลายตัวแทน | การออกแบบตัวแทน การจัดการหน่วยความจำ การประสานงาน |
| **6** | ระบบการจัดเส้นทางอัจฉริยะ | การตรวจจับเจตนา การเลือกโมเดล การขยายขนาด |

### ตารางทักษะ

| ระดับทักษะ | เซสชัน 1-2 | เซสชัน 3-4 | เซสชัน 5-6 |
|-------------|------------|------------|------------|
| **ผู้เริ่มต้น** | ✅ การตั้งค่าและพื้นฐาน | ⚠️ ท้าทาย | ❌ ขั้นสูงเกินไป |
| **ระดับกลาง** | ✅ ทบทวนเร็ว | ✅ การเรียนรู้หลัก | ⚠️ เป้าหมายที่ท้าทาย |
| **ขั้นสูง** | ✅ ผ่านได้ง่าย | ✅ ปรับปรุง | ✅ รูปแบบการใช้งานจริง |

### ทักษะพร้อมสำหรับอาชีพ

**หลังจากเวิร์กช็อปนี้ คุณจะพร้อมที่จะ:**

✅ **สร้างแอปพลิเคชันที่เน้นความเป็นส่วนตัว**
- แอปพลิเคชันด้านสุขภาพที่จัดการ PHI/PII ในพื้นที่
- บริการทางการเงินที่มีข้อกำหนดด้านการปฏิบัติตามกฎระเบียบ
- ระบบรัฐบาลที่มีความต้องการด้านอธิปไตยข้อมูล

✅ **ปรับปรุงสำหรับสภาพแวดล้อม Edge**
- อุปกรณ์ IoT ที่มีทรัพยากรจำกัด
- แอปพลิเคชันมือถือที่เน้นการใช้งานแบบออฟไลน์
- ระบบเรียลไทม์ที่มีความล่าช้าต่ำ

✅ **ออกแบบสถาปัตยกรรมอัจฉริยะ**
- ระบบหลายตัวแทนสำหรับกระบวนการทำงานที่ซับซ้อน
- การปรับใช้แบบ Hybrid ระหว่าง Edge และ Cloud
- โครงสร้างพื้นฐาน AI ที่ปรับต้นทุนได้

✅ **เป็นผู้นำโครงการ Edge AI**
- ประเมินความเป็นไปได้ของ Edge AI สำหรับโครงการ
- เลือกโมเดลและเฟรมเวิร์กที่เหมาะสม
- ออกแบบโซลูชัน AI ในพื้นที่ที่สามารถขยายได้

---

## 🗺️ โครงสร้างเวิร์กช็อป

### ภาพรวมเซสชัน (6 เซสชัน × 30 นาที = 3 ชั่วโมง)

| เซสชัน | หัวข้อ | จุดเน้น | ระยะเวลา |
|--------|--------|---------|----------|
| **1** | เริ่มต้นใช้งาน Foundry Local | ติดตั้ง ตรวจสอบ การตอบสนองครั้งแรก | 30 นาที |
| **2** | สร้างโซลูชัน AI ด้วย RAG | การออกแบบคำสั่ง Embeddings การประเมิน | 30 นาที |
| **3** | โมเดลโอเพ่นซอร์ส | การค้นหาโมเดล การทดสอบ การเลือก | 30 นาที |
| **4** | โมเดลล้ำสมัย | SLM กับ LLM การปรับปรุง เฟรมเวิร์ก | 30 นาที |
| **5** | ตัวแทนที่ขับเคลื่อนด้วย AI | การออกแบบตัวแทน การประสานงาน หน่วยความจำ | 30 นาที |
| **6** | โมเดลเป็นเครื่องมือ | การจัดเส้นทาง การเชื่อมโยง กลยุทธ์การขยาย | 30 นาที |

---

## 🚀 เริ่มต้นอย่างรวดเร็ว

### ข้อกำหนดเบื้องต้น

**ข้อกำหนดระบบ:**
- **OS**: Windows 10/11, macOS 11+ หรือ Linux (Ubuntu 20.04+)
- **RAM**: ขั้นต่ำ 8GB แนะนำ 16GB+
- **พื้นที่เก็บข้อมูล**: พื้นที่ว่าง 10GB+ สำหรับโมเดล
- **CPU**: โปรเซสเซอร์รุ่นใหม่ที่รองรับ AVX2
- **GPU** (ตัวเลือก): CUDA-compatible หรือ Qualcomm NPU สำหรับการเร่งความเร็ว

**ข้อกำหนดซอฟต์แวร์:**
- **Python 3.8+** ([ดาวน์โหลด](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([คู่มือการติดตั้ง](../../../Workshop))
- **Git** ([ดาวน์โหลด](https://git-scm.com/downloads))
- **Visual Studio Code** (แนะนำ) ([ดาวน์โหลด](https://code.visualstudio.com/))

### การตั้งค่าใน 3 ขั้นตอน

#### 1. ติดตั้ง Foundry Local

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**ตรวจสอบการติดตั้ง:**
```bash
foundry --version
foundry service status
```

**ตรวจสอบให้แน่ใจว่า Azure AI Foundry Local กำลังทำงานด้วยพอร์ตที่กำหนด**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**ตรวจสอบการทำงาน:**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**ค้นหาโมเดลที่มีอยู่**
เพื่อดูว่าโมเดลใดที่มีอยู่ใน Foundry Local ของคุณ คุณสามารถสอบถาม endpoint ของโมเดล:

```bash
# cmd/bash/powershell
foundry model list
```

ใช้ Web Endpoint 

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### 2. โคลน Repository และติดตั้ง Dependencies

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

#### 3. รันตัวอย่างแรกของคุณ

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples/session01
python chat_bootstrap.py "What is edge AI?"
```

**✅ สำเร็จ!** คุณควรเห็นการตอบสนองแบบสตรีมเกี่ยวกับ Edge AI

---

## 📦 ทรัพยากรเวิร์กช็อป

### ตัวอย่าง Python

ตัวอย่างการลงมือปฏิบัติที่แสดงแนวคิดแต่ละข้อ:

| เซสชัน | ตัวอย่าง | คำอธิบาย | เวลาในการรัน |
|--------|----------|-----------|--------------|
| 1 | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | แชทพื้นฐานและการสตรีม | ~30 วินาที |
| 2 | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | RAG พร้อม embeddings | ~45 วินาที |
| 2 | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | การประเมินคุณภาพ RAG | ~60 วินาที |
| 3 | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | การทดสอบโมเดลหลายตัว | ~2-3 นาที |
| 4 | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | การเปรียบเทียบ SLM กับ LLM | ~45 วินาที |
| 5 | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | ระบบหลายตัวแทน | ~60 วินาที |
| 6 | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | การจัดเส้นทางตามเจตนา | ~45 วินาที |
| 6 | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | กระบวนการหลายขั้นตอน | ~60 วินาที |

### Jupyter Notebooks

การสำรวจแบบโต้ตอบพร้อมคำอธิบายและภาพประกอบ:

| เซสชัน | Notebook | คำอธิบาย | ระดับความยาก |
|--------|----------|-----------|---------------|
| 1 | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | พื้นฐานแชทและการสตรีม | ⭐ ผู้เริ่มต้น |
| 2 | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline.ipynb) | สร้างระบบ RAG | ⭐⭐ ระดับกลาง |
| 2 | [`session02_rag_eval_ragas.ipynb`](./notebooks/session02_rag_eval_ragas.ipynb) | ประเมินคุณภาพ RAG | ⭐⭐ ระดับกลาง |
| 3 | [`session03_benchmark_oss_models.ipynb`](./notebooks/session03_benchmark_oss_models.ipynb) | การทดสอบโมเดล | ⭐⭐ ระดับกลาง |
| 4 | [`session04_model_compare.ipynb`](./notebooks/session04_model_compare.ipynb) | การเปรียบเทียบโมเดล | ⭐⭐ ระดับกลาง |
| 5 | [`session05_agents_orchestrator.ipynb`](./notebooks/session05_agents_orchestrator.ipynb) | การประสานงานตัวแทน | ⭐⭐⭐ ขั้นสูง |
| 6 | [`session06_models_router.ipynb`](./notebooks/session06_models_router.ipynb) | การจัดเส้นทางตามเจตนา | ⭐⭐⭐ ขั้นสูง |
| 6 | [`session06_models_pipeline.ipynb`](./notebooks/session06_models_pipeline.ipynb) | การประสานงานกระบวนการ | ⭐⭐⭐ ขั้นสูง |

### เอกสาร

คู่มือและข้อมูลอ้างอิงที่ครอบคลุม:

| เอกสาร | คำอธิบาย | ใช้เมื่อ |
|--------|----------|----------|
| [QUICK_START.md](./QUICK_START.md) | คู่มือการตั้งค่าแบบรวดเร็ว | เริ่มต้นจากศูนย์ |
| [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) | แผ่นโกงคำสั่งและ API | ต้องการคำตอบด่วน |
| [FOUNDRY_SDK_QUICKREF.md](./FOUNDRY_SDK_QUICKREF.md) | รูปแบบ SDK และตัวอย่าง | เขียนโค้ด |
| [ENV_CONFIGURATION.md](./ENV_CONFIGURATION.md) | คู่มือการตั้งค่าตัวแปรสภาพแวดล้อม | กำหนดค่าตัวอย่าง |
| [SAMPLES_UPDATE_SUMMARY.md](./SAMPLES_UPDATE_SUMMARY.md) | การปรับปรุงตัวอย่างล่าสุด | เข้าใจการเปลี่ยนแปลง |
| [SDK_MIGRATION_NOTES.md](./SDK_MIGRATION_NOTES.md) | คู่มือการย้าย SDK | อัปเกรดโค้ด |
| [notebooks/TROUBLESHOOTING.md](./notebooks/TROUBLESHOOTING.md) | ปัญหาทั่วไปและการแก้ไข | แก้ไขปัญหา |

---

## 🎓 คำแนะนำเส้นทางการเรียนรู้

### สำหรับผู้เริ่มต้น (3-4 ชั่วโมง)
1. ✅ เซสชัน 1: เริ่มต้นใช้งาน (เน้นการตั้งค่าและแชทพื้นฐาน)
2. ✅ เซสชัน 2: พื้นฐาน RAG (ข้ามการประเมินในตอนแรก)
3. ✅ เซสชัน 3: การทดสอบง่าย ๆ (โมเดล 2 ตัวเท่านั้น)
4. ⏭️ ข้ามเซสชัน 4-6 ในตอนนี้
5. 🔄 กลับไปที่เซสชัน 4-6 หลังจากสร้างแอปพลิเคชันแรก

### สำหรับนักพัฒนาระดับกลาง (3 ชั่วโมง)
1. ⚡ เซสชัน 1: การตรวจสอบการตั้งค่าอย่างรวดเร็ว
2. ✅ เซสชัน 2: ระบบ RAG ที่สมบูรณ์พร้อมการประเมิน
3. ✅ เซสชัน 3: ชุดการทดสอบเต็มรูปแบบ
4. ✅ เซสชัน 4: การปรับปรุงโมเดล
5. ✅ เซสชัน 5-6: เน้นรูปแบบสถาปัตยกรรม

### สำหรับผู้เชี่ยวชาญขั้นสูง (2-3 ชั่วโมง)
1. ⚡ เซสชัน 1-3: ทบทวนและตรวจสอบอย่างรวดเร็ว
2. ✅ เซสชัน 4: การเจาะลึกการปรับปรุง
3. ✅ เซสชัน 5: สถาปัตยกรรมหลายตัวแทน
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | SLM เทียบกับ LLM, WebGPU, Chainlit RAG, การเร่งความเร็วด้วย ONNX |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | บทบาทของเอเจนต์, หน่วยความจำ, เครื่องมือ, การจัดการ |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | การกำหนดเส้นทาง, การเชื่อมโยง, เส้นทางการขยายไปยัง Azure |

แต่ละไฟล์เซสชันประกอบด้วย: บทคัดย่อ, วัตถุประสงค์การเรียนรู้, การสาธิต 30 นาที, โครงการเริ่มต้น, เช็คลิสต์การตรวจสอบ, การแก้ไขปัญหา และการอ้างอิงไปยัง Foundry Local Python SDK อย่างเป็นทางการ

### สคริปต์ตัวอย่าง

ติดตั้ง dependencies สำหรับ workshop (Windows):

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

หากรัน Foundry Local service บนเครื่องหรือ VM (Windows) ที่แตกต่างจาก macOS ให้ส่งออก endpoint:

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| เซสชัน | สคริปต์ | คำอธิบาย |
|--------|----------|-----------|
| 1 | `samples/session01/chat_bootstrap.py` | บูตสแตรปเซอร์วิส & การแชทแบบสตรีม |
| 2 | `samples/session02/rag_pipeline.py` | RAG ขั้นต่ำ (embedding ในหน่วยความจำ) |
|   | `samples/session02/rag_eval_ragas.py` | การประเมิน RAG ด้วยเมตริก ragas |
| 3 | `samples/session03/benchmark_oss_models.py` | การวัดประสิทธิภาพหลายโมเดล (latency & throughput) |
| 4 | `samples/session04/model_compare.py` | การเปรียบเทียบ SLM กับ LLM (latency & ตัวอย่างผลลัพธ์) |
| 5 | `samples/session05/agents_orchestrator.py` | การวิจัยด้วยเอเจนต์สองตัว → กระบวนการแก้ไข |
| 6 | `samples/session06/models_router.py` | การสาธิตการกำหนดเส้นทางตามเจตนา |
|   | `samples/session06/models_pipeline.py` | การเชื่อมโยงแบบหลายขั้นตอน: วางแผน/ดำเนินการ/ปรับปรุง |

### ตัวแปรสภาพแวดล้อม (ใช้ร่วมกันในตัวอย่าง)

| ตัวแปร | วัตถุประสงค์ | ตัวอย่าง |
|--------|---------------|----------|
| `FOUNDRY_LOCAL_ALIAS` | Alias โมเดลเดียวเริ่มต้นสำหรับตัวอย่างพื้นฐาน | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | SLM ที่ชัดเจนเทียบกับโมเดลขนาดใหญ่สำหรับการเปรียบเทียบ | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | รายการ alias ที่จะวัดประสิทธิภาพ | `qwen2.5-0.5b,gemma-2-2b,mistral-7b` |
| `BENCH_ROUNDS` | จำนวนรอบการวัดประสิทธิภาพต่อโมเดล | `3` |
| `BENCH_PROMPT` | Prompt ที่ใช้ในการวัดประสิทธิภาพ | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | โมเดล embedding ของ sentence-transformers | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | การแทนที่คำถามทดสอบสำหรับ RAG pipeline | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | การแทนที่คำถาม pipeline ของเอเจนต์ | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | Alias โมเดลสำหรับเอเจนต์วิจัย | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | Alias โมเดลสำหรับเอเจนต์แก้ไข (สามารถแตกต่างกันได้) | `gpt-oss-20b` |
| `SHOW_USAGE` | เมื่อ `1` จะแสดงการใช้ token ต่อการทำงาน | `1` |
| `RETRY_ON_FAIL` | เมื่อ `1` จะลองใหม่หนึ่งครั้งเมื่อเกิดข้อผิดพลาดชั่วคราว | `1` |
| `RETRY_BACKOFF` | วินาทีที่รอระหว่างการลองใหม่ | `1.0` |

หากตัวแปรไม่ได้ถูกตั้งค่า สคริปต์จะใช้ค่าตั้งต้นที่เหมาะสม สำหรับการสาธิตโมเดลเดียว คุณมักจะต้องใช้แค่ `FOUNDRY_LOCAL_ALIAS`

### โมดูลยูทิลิตี้

ตัวอย่างทั้งหมดตอนนี้ใช้ `samples/workshop_utils.py` ซึ่งเป็นตัวช่วยที่ให้:

* การสร้าง `FoundryLocalManager` + OpenAI client ที่แคชไว้
* ตัวช่วย `chat_once()` พร้อมการลองใหม่ + การพิมพ์การใช้งานแบบเลือกได้
* การรายงานการใช้ token อย่างง่าย (เปิดใช้งานผ่าน `SHOW_USAGE=1`)

สิ่งนี้ช่วยลดการทำซ้ำและเน้นแนวทางปฏิบัติที่ดีที่สุดสำหรับการจัดการโมเดลในพื้นที่อย่างมีประสิทธิภาพ

## การปรับปรุงเพิ่มเติม (ข้ามเซสชัน)

| ธีม | การปรับปรุง | เซสชัน | Env / Toggle |
|-----|-------------|--------|--------------|
| Determinism | อุณหภูมิที่คงที่ + ชุด prompt ที่เสถียร | 1–6 | ตั้งค่า `temperature=0`, `top_p=1` |
| การมองเห็นการใช้ Token | การสอนต้นทุน/ประสิทธิภาพที่สม่ำเสมอ | 1–6 | `SHOW_USAGE=1` |
| การสตรีม Token แรก | เมตริก latency ที่รับรู้ได้ | 1,3,4,6 | `BENCH_STREAM=1` (benchmark) |
| ความยืดหยุ่นในการลองใหม่ | จัดการ cold-start ชั่วคราว | ทั้งหมด | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| เอเจนต์หลายโมเดล | การเชี่ยวชาญบทบาทที่หลากหลาย | 5 | `AGENT_MODEL_PRIMARY`, `AGENT_MODEL_EDITOR` |
| การกำหนดเส้นทางแบบปรับตัว | เจตนา + ฮิวริสติกต้นทุน | 6 | ขยาย router ด้วยตรรกะการยกระดับ |
| หน่วยความจำแบบเวกเตอร์ | การเรียกคืนความหมายระยะยาว | 2,5,6 | รวม FAISS/Chroma embedding index |
| การส่งออก Trace | การตรวจสอบและการประเมินผล | 2,5,6 | เพิ่ม JSON lines ต่อขั้นตอน |
| รูบริกคุณภาพ | การติดตามเชิงคุณภาพ | 3–6 | prompt การให้คะแนนรอง |
| การทดสอบ Smoke | การตรวจสอบก่อน workshop อย่างรวดเร็ว | ทั้งหมด | `python Workshop/tests/smoke.py` |

### การเริ่มต้นอย่างรวดเร็วแบบ Deterministic

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

คาดหวังจำนวน token ที่เสถียรในอินพุตที่เหมือนกันซ้ำๆ

### การประเมิน RAG (เซสชัน 2)

ใช้ `rag_eval_ragas.py` เพื่อคำนวณความเกี่ยวข้องของคำตอบ ความถูกต้อง และความแม่นยำของบริบทในชุดข้อมูลสังเคราะห์ขนาดเล็ก:

```powershell
python samples/session02/rag_eval_ragas.py
```

ขยายโดยการจัดหาคำถาม บริบท และความจริงที่เป็นพื้นฐานในรูปแบบ JSONL ขนาดใหญ่ จากนั้นแปลงเป็น Hugging Face `Dataset`

## ภาคผนวกความแม่นยำของคำสั่ง CLI

Workshop ใช้เฉพาะคำสั่ง Foundry Local CLI ที่มีการบันทึกไว้ในปัจจุบัน / เสถียรเท่านั้น

### คำสั่งที่เสถียรที่อ้างถึง

| หมวดหมู่ | คำสั่ง | วัตถุประสงค์ |
|----------|---------|--------------|
| Core | `foundry --version` | แสดงเวอร์ชันที่ติดตั้ง |
| Core | `foundry init` | เริ่มต้นการตั้งค่า |
| Service | `foundry service start` | เริ่มเซอร์วิสในพื้นที่ (หากไม่ได้เริ่มอัตโนมัติ) |
| Service | `foundry status` | แสดงสถานะเซอร์วิส |
| Models | `foundry model list` | แสดงแคตตาล็อก / โมเดลที่มีอยู่ |
| Models | `foundry model download <alias>` | ดาวน์โหลดน้ำหนักโมเดลลงในแคช |
| Models | `foundry model run <alias>` | เปิดตัว (โหลด) โมเดลในพื้นที่; ใช้ร่วมกับ `--prompt` สำหรับการทำงานครั้งเดียว |
| Models | `foundry model unload <alias>` / `foundry model stop <alias>` | ยกเลิกการโหลดโมเดลจากหน่วยความจำ (หากรองรับ) |
| Cache | `foundry cache list` | แสดงโมเดลที่แคชไว้ (ดาวน์โหลดแล้ว) |
| System | `foundry system info` | สแนปช็อตความสามารถของฮาร์ดแวร์ & การเร่งความเร็ว |
| System | `foundry system gpu-info` | ข้อมูลวินิจฉัย GPU |
| Config | `foundry config list` | แสดงค่าการตั้งค่าปัจจุบัน |
| Config | `foundry config set <key> <value>` | อัปเดตการตั้งค่า |

### รูปแบบ Prompt ครั้งเดียว

แทนคำสั่งย่อย `model chat` ที่เลิกใช้แล้ว ใช้:

```powershell
foundry model run <alias> --prompt "Your question here"
```

สิ่งนี้จะดำเนินการรอบ prompt/response ครั้งเดียวแล้วออก

### รูปแบบที่ถูกลบ / หลีกเลี่ยง

| เลิกใช้ / ไม่มีการบันทึก | คำแนะนำ / ทดแทน |
|--------------------------|-----------------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | ใช้ `foundry model list` + กิจกรรมล่าสุด / logs |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | ใช้สคริปต์ benchmark Python + เครื่องมือ OS (Task Manager / `nvidia-smi`) |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### การวัดประสิทธิภาพ & การวัดผล

- Latency, p95, tokens/sec: `samples/session03/benchmark_oss_models.py`
- Latency ของ token แรก (สตรีม): ตั้งค่า `BENCH_STREAM=1`
- การใช้ทรัพยากร: ตัวตรวจสอบ OS (Task Manager, Activity Monitor, `nvidia-smi`) + `foundry system info`

เมื่อคำสั่ง CLI telemetry ใหม่มีความเสถียร upstream สามารถรวมเข้ากับ markdown เซสชันได้ด้วยการแก้ไขเพียงเล็กน้อย

### การป้องกัน Lint Guard อัตโนมัติ

Linter อัตโนมัติป้องกันการนำรูปแบบ CLI ที่เลิกใช้กลับมาใน code block ที่ fenced ของไฟล์ markdown:

สคริปต์: `Workshop/scripts/lint_markdown_cli.py`

รูปแบบที่เลิกใช้จะถูกบล็อกใน code fence

คำแนะนำการทดแทน:
| เลิกใช้ | ทดแทน |
|---------|-------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | สคริปต์ benchmark + เครื่องมือระบบ |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

รันในเครื่อง:
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

GitHub Action: `.github/workflows/markdown-cli-lint.yml` รันทุกครั้งที่ push & PR

hook pre-commit แบบเลือกได้:
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## ตารางการย้าย CLI → SDK อย่างรวดเร็ว

| งาน | CLI One-Liner | SDK (Python) เทียบเท่า | หมายเหตุ |
|-----|---------------|-------------------------|----------|
| รันโมเดลครั้งเดียว (prompt) | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK บูตเซอร์วิส & แคชโดยอัตโนมัติ |
| ดาวน์โหลด (แคช) โมเดล | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # triggers download/load` | Manager เลือกตัวแปรที่ดีที่สุดหาก alias แมปกับหลาย build |
| แสดงแคตตาล็อก | `foundry model list` | `# ใช้ manager สำหรับแต่ละ alias หรือรักษารายการที่ทราบ` | CLI รวม; SDK ปัจจุบันสำหรับการสร้างแต่ละ alias |
| แสดงโมเดลที่แคชไว้ | `foundry cache list` | `manager.list_cached_models()` | หลังจาก manager init (alias ใดก็ได้) |
| เปิดใช้งานการเร่ง GPU | `foundry config set compute.onnx.enable_gpu true` | `# CLI action; SDK สมมติว่าการตั้งค่าได้ถูกนำไปใช้แล้ว` | การตั้งค่าเป็นผลกระทบภายนอก |
| รับ URL endpoint | (โดยนัย) | `manager.endpoint` | ใช้เพื่อสร้าง OpenAI-compatible client |
| อุ่นโมเดล | `foundry model run <alias>` แล้ว prompt แรก | `chat_once(alias, messages=[...])` (utility) | Utilities จัดการ cold latency warmup เริ่มต้น |
| วัด latency | `python benchmark_oss_models.py` | `import benchmark_oss_models` (หรือสคริปต์ส่งออกใหม่) | ใช้สคริปต์เพื่อเมตริกที่สม่ำเสมอ |
| หยุด / ยกเลิกการโหลดโมเดล | `foundry model unload <alias>` | (ไม่เปิดเผย – รีสตาร์ทเซอร์วิส / กระบวนการ) | โดยทั่วไปไม่จำเป็นสำหรับ flow ของ workshop |
| ดึงการใช้ token | (ดู output) | `resp.usage.total_tokens` | ให้เมื่อ backend ส่งคืนวัตถุการใช้งาน |

## การส่งออก Markdown การวัดประสิทธิภาพ

ใช้สคริปต์ `Workshop/scripts/export_benchmark_markdown.py` เพื่อรันการวัดประสิทธิภาพใหม่ (ตรรกะเดียวกับ `samples/session03/benchmark_oss_models.py`) และส่งออกตาราง Markdown ที่เหมาะกับ GitHub พร้อม JSON ดิบ

### ตัวอย่าง

```powershell
python Workshop\scripts\export_benchmark_markdown.py --models "qwen2.5-0.5b,gemma-2-2b,mistral-7b" --prompt "Explain retrieval augmented generation briefly." --rounds 3 --output benchmark_report.md
```

ไฟล์ที่สร้าง:
| ไฟล์ | เนื้อหา |
|------|---------|
| `benchmark_report.md` | ตาราง Markdown + คำแนะนำการตีความ |
| `benchmark_report.json` | อาร์เรย์เมตริกดิบ (สำหรับการเปรียบเทียบ / การติดตามแนวโน้ม) |

ตั้งค่า `BENCH_STREAM=1` ในสภาพแวดล้อมเพื่อรวม latency ของ token แรกหากรองรับ

---

**ข้อจำกัดความรับผิดชอบ**:  
เอกสารนี้ได้รับการแปลโดยใช้บริการแปลภาษา AI [Co-op Translator](https://github.com/Azure/co-op-translator) แม้ว่าเราจะพยายามให้การแปลมีความถูกต้อง แต่โปรดทราบว่าการแปลอัตโนมัติอาจมีข้อผิดพลาดหรือความไม่ถูกต้อง เอกสารต้นฉบับในภาษาดั้งเดิมควรถือเป็นแหล่งข้อมูลที่เชื่อถือได้ สำหรับข้อมูลที่สำคัญ ขอแนะนำให้ใช้บริการแปลภาษามืออาชีพ เราไม่รับผิดชอบต่อความเข้าใจผิดหรือการตีความผิดที่เกิดจากการใช้การแปลนี้