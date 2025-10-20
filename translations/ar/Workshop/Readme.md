<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b994c57f1207012e4d7f58b7c0d1ae7",
  "translation_date": "2025-10-17T09:08:12+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "ar"
}
-->
# EdgeAI للمبتدئين - ورشة عمل

> **مسار تعليمي عملي لبناء تطبيقات Edge AI جاهزة للإنتاج**
>
> تعلم كيفية نشر الذكاء الاصطناعي محليًا باستخدام Microsoft Foundry Local، بدءًا من أول استكمال محادثة إلى تنسيق متعدد الوكلاء في 6 جلسات متقدمة.

---

## 🎯 المقدمة

مرحبًا بكم في **ورشة عمل EdgeAI للمبتدئين** - دليلك العملي لبناء تطبيقات ذكية تعمل بالكامل على الأجهزة المحلية. هذه الورشة تحول مفاهيم Edge AI النظرية إلى مهارات عملية من خلال تمارين تدريجية باستخدام Microsoft Foundry Local ونماذج اللغة الصغيرة (SLMs).

### لماذا هذه الورشة؟

**ثورة Edge AI بدأت الآن**

تتجه المؤسسات حول العالم من الاعتماد على الذكاء الاصطناعي السحابي إلى الحوسبة الطرفية لثلاثة أسباب رئيسية:

1. **الخصوصية والامتثال** - معالجة البيانات الحساسة محليًا دون إرسالها إلى السحابة (HIPAA، GDPR، اللوائح المالية)
2. **الأداء** - القضاء على تأخير الشبكة (50-500 مللي ثانية محليًا مقابل 500-2000 مللي ثانية في السحابة)
3. **التحكم في التكاليف** - التخلص من تكاليف API لكل رمز والتوسع دون نفقات السحابة

**لكن Edge AI مختلف**

تشغيل الذكاء الاصطناعي محليًا يتطلب مهارات جديدة:
- اختيار النماذج وتحسينها لتناسب القيود المواردية
- إدارة الخدمات المحلية وتسريع الأجهزة
- هندسة التوجيه للنماذج الصغيرة
- أنماط نشر الإنتاج للأجهزة الطرفية

**هذه الورشة تقدم تلك المهارات**

في 6 جلسات مركزة (~3 ساعات إجمالاً)، ستنتقل من "Hello World" إلى نشر أنظمة متعددة الوكلاء جاهزة للإنتاج - جميعها تعمل محليًا على جهازك.

---

## 📚 أهداف التعلم

عند إكمال هذه الورشة، ستكون قادرًا على:

### الكفاءات الأساسية
1. **نشر وإدارة خدمات الذكاء الاصطناعي المحلية**
   - تثبيت وتكوين Microsoft Foundry Local
   - اختيار النماذج المناسبة للنشر الطرفي
   - إدارة دورة حياة النموذج (تحميل، تخزين، تخزين مؤقت)
   - مراقبة استخدام الموارد وتحسين الأداء

2. **بناء تطبيقات مدعومة بالذكاء الاصطناعي**
   - تنفيذ استكمالات المحادثة المتوافقة مع OpenAI محليًا
   - تصميم توجيهات فعالة لنماذج اللغة الصغيرة
   - التعامل مع الردود المتدفقة لتحسين تجربة المستخدم
   - دمج النماذج المحلية في التطبيقات الحالية

3. **إنشاء أنظمة RAG (توليد معزز بالاسترجاع)**
   - بناء بحث دلالي باستخدام التضمينات
   - ربط ردود LLM بمعرفة محددة بالمجال
   - تقييم جودة RAG باستخدام مقاييس معيارية
   - التوسع من النموذج الأولي إلى الإنتاج

4. **تحسين أداء النموذج**
   - قياس أداء نماذج متعددة لحالتك
   - قياس التأخير، الإنتاجية، ووقت أول رمز
   - اختيار النماذج المثلى بناءً على توازن السرعة والجودة
   - مقارنة التوازن بين SLM و LLM في سيناريوهات حقيقية

5. **تنسيق أنظمة متعددة الوكلاء**
   - تصميم وكلاء متخصصين لمهام مختلفة
   - تنفيذ ذاكرة الوكيل وإدارة السياق
   - تنسيق الوكلاء في سير عمل معقد
   - توجيه الطلبات بذكاء عبر نماذج متعددة

6. **نشر حلول جاهزة للإنتاج**
   - تنفيذ معالجة الأخطاء ومنطق إعادة المحاولة
   - مراقبة استخدام الرموز وموارد النظام
   - بناء بنى قابلة للتوسع باستخدام أنماط النموذج كأدوات
   - تخطيط مسارات الانتقال من الطرف إلى الهجين (الطرف + السحابة)

---

## 🎓 نتائج التعلم

### ما الذي ستبنيه

بنهاية هذه الورشة، ستكون قد أنشأت:

| الجلسة | النتيجة | المهارات المكتسبة |
|--------|---------|--------------------|
| **1** | تطبيق محادثة مع تدفق الردود | إعداد الخدمة، استكمالات أساسية، تجربة المستخدم المتدفقة |
| **2** | نظام RAG مع تقييم | تضمينات، بحث دلالي، مقاييس الجودة |
| **3** | مجموعة مقارنة نماذج متعددة | قياس الأداء، مقارنة النماذج |
| **4** | مقارنة بين SLM و LLM | تحليل التوازن، استراتيجيات التحسين |
| **5** | منسق متعدد الوكلاء | تصميم الوكلاء، إدارة الذاكرة، التنسيق |
| **6** | نظام توجيه ذكي | اكتشاف النوايا، اختيار النموذج، قابلية التوسع |

### مصفوفة الكفاءة

| مستوى المهارة | الجلسة 1-2 | الجلسة 3-4 | الجلسة 5-6 |
|---------------|------------|------------|------------|
| **مبتدئ** | ✅ إعداد وأساسي | ⚠️ تحدي | ❌ متقدم جدًا |
| **متوسط** | ✅ مراجعة سريعة | ✅ تعلم أساسي | ⚠️ أهداف ممتدة |
| **متقدم** | ✅ سهل التنفيذ | ✅ تحسين | ✅ أنماط الإنتاج |

### مهارات جاهزة للعمل

**بعد هذه الورشة، ستكون مستعدًا لـ:**

✅ **بناء تطبيقات تركز على الخصوصية**
- تطبيقات الرعاية الصحية التي تعالج PHI/PII محليًا
- خدمات مالية مع متطلبات الامتثال
- أنظمة حكومية مع احتياجات سيادة البيانات

✅ **تحسين البيئات الطرفية**
- أجهزة إنترنت الأشياء ذات الموارد المحدودة
- تطبيقات الهواتف المحمولة التي تعمل بدون اتصال
- أنظمة الوقت الحقيقي منخفضة التأخير

✅ **تصميم بنى ذكية**
- أنظمة متعددة الوكلاء لسير العمل المعقد
- نشرات هجينة بين الطرف والسحابة
- بنية تحتية للذكاء الاصطناعي بتكلفة محسّنة

✅ **قيادة مبادرات Edge AI**
- تقييم جدوى Edge AI للمشاريع
- اختيار النماذج والأطر المناسبة
- تصميم حلول ذكاء اصطناعي محلية قابلة للتوسع

---

## 🗺️ هيكل الورشة

### نظرة عامة على الجلسات (6 جلسات × 30 دقيقة = 3 ساعات)

| الجلسة | الموضوع | التركيز | المدة |
|--------|---------|---------|-------|
| **1** | البدء مع Foundry Local | التثبيت، التحقق، أول استكمالات | 30 دقيقة |
| **2** | بناء حلول الذكاء الاصطناعي مع RAG | هندسة التوجيه، التضمينات، التقييم | 30 دقيقة |
| **3** | نماذج المصدر المفتوح | اكتشاف النماذج، قياس الأداء، الاختيار | 30 دقيقة |
| **4** | نماذج متقدمة | SLM مقابل LLM، التحسين، الأطر | 30 دقيقة |
| **5** | وكلاء مدعومون بالذكاء الاصطناعي | تصميم الوكلاء، التنسيق، الذاكرة | 30 دقيقة |
| **6** | النماذج كأدوات | التوجيه، الربط، استراتيجيات التوسع | 30 دقيقة |

---

## 🚀 البداية السريعة

### المتطلبات الأساسية

**متطلبات النظام:**
- **نظام التشغيل**: Windows 10/11، macOS 11+، أو Linux (Ubuntu 20.04+)
- **RAM**: 8GB كحد أدنى، 16GB+ موصى به
- **التخزين**: مساحة خالية 10GB+ للنماذج
- **المعالج**: معالج حديث يدعم AVX2
- **GPU** (اختياري): متوافق مع CUDA أو Qualcomm NPU للتسريع

**متطلبات البرمجيات:**
- **Python 3.8+** ([تحميل](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([دليل التثبيت](../../../Workshop))
- **Git** ([تحميل](https://git-scm.com/downloads))
- **Visual Studio Code** (موصى به) ([تحميل](https://code.visualstudio.com/))

### الإعداد في 3 خطوات

#### 1. تثبيت Foundry Local

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**التحقق من التثبيت:**
```bash
foundry --version
foundry service status
```

**تأكد من تشغيل Azure AI Foundry Local مع منفذ ثابت**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**التحقق من العمل:**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**العثور على النماذج المتاحة**
لرؤية النماذج المتاحة في مثيل Foundry Local الخاص بك، يمكنك استعلام نقطة النهاية للنماذج:

```bash
# cmd/bash/powershell
foundry model list
```

باستخدام نقطة النهاية على الويب 

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### 2. استنساخ المستودع وتثبيت التبعيات

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

#### 3. تشغيل أول نموذج

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples/session01
python chat_bootstrap.py "What is edge AI?"
```

**✅ نجاح!** يجب أن ترى ردًا متدفقًا حول Edge AI.

---

## 📦 موارد الورشة

### أمثلة Python

أمثلة عملية تدريجية توضح كل مفهوم:

| الجلسة | المثال | الوصف | وقت التشغيل |
|--------|--------|-------|-------------|
| 1 | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | محادثة أساسية وتدفق الردود | ~30 ثانية |
| 2 | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | RAG مع التضمينات | ~45 ثانية |
| 2 | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | تقييم جودة RAG | ~60 ثانية |
| 3 | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | قياس أداء نماذج متعددة | ~2-3 دقائق |
| 4 | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | مقارنة بين SLM و LLM | ~45 ثانية |
| 5 | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | نظام متعدد الوكلاء | ~60 ثانية |
| 6 | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | التوجيه بناءً على النوايا | ~45 ثانية |
| 6 | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | خط أنابيب متعدد الخطوات | ~60 ثانية |

### دفاتر Jupyter

استكشاف تفاعلي مع شروحات ورسوم بيانية:

| الجلسة | الدفتر | الوصف | الصعوبة |
|--------|-------|-------|---------|
| 1 | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | أساسيات المحادثة والتدفق | ⭐ مبتدئ |
| 2 | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline.ipynb) | بناء نظام RAG | ⭐⭐ متوسط |
| 2 | [`session02_rag_eval_ragas.ipynb`](./notebooks/session02_rag_eval_ragas.ipynb) | تقييم جودة RAG | ⭐⭐ متوسط |
| 3 | [`session03_benchmark_oss_models.ipynb`](./notebooks/session03_benchmark_oss_models.ipynb) | قياس أداء النماذج | ⭐⭐ متوسط |
| 4 | [`session04_model_compare.ipynb`](./notebooks/session04_model_compare.ipynb) | مقارنة النماذج | ⭐⭐ متوسط |
| 5 | [`session05_agents_orchestrator.ipynb`](./notebooks/session05_agents_orchestrator.ipynb) | تنسيق الوكلاء | ⭐⭐⭐ متقدم |
| 6 | [`session06_models_router.ipynb`](./notebooks/session06_models_router.ipynb) | توجيه النوايا | ⭐⭐⭐ متقدم |
| 6 | [`session06_models_pipeline.ipynb`](./notebooks/session06_models_pipeline.ipynb) | تنسيق خط الأنابيب | ⭐⭐⭐ متقدم |

### الوثائق

أدلة ومراجع شاملة:

| الوثيقة | الوصف | الاستخدام |
|---------|-------|-----------|
| [QUICK_START.md](./QUICK_START.md) | دليل الإعداد السريع | البدء من الصفر |
| [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) | ورقة الغش للأوامر وواجهة برمجة التطبيقات | عند الحاجة إلى إجابات سريعة |
| [FOUNDRY_SDK_QUICKREF.md](./FOUNDRY_SDK_QUICKREF.md) | أنماط وأمثلة SDK | كتابة الكود |
| [ENV_CONFIGURATION.md](./ENV_CONFIGURATION.md) | دليل متغيرات البيئة | تكوين الأمثلة |
| [SAMPLES_UPDATE_SUMMARY.md](./SAMPLES_UPDATE_SUMMARY.md) | تحسينات العينات الأخيرة | فهم التغييرات |
| [SDK_MIGRATION_NOTES.md](./SDK_MIGRATION_NOTES.md) | دليل الترحيل | تحديث الكود |
| [notebooks/TROUBLESHOOTING.md](./notebooks/TROUBLESHOOTING.md) | المشكلات الشائعة والحلول | استكشاف الأخطاء وإصلاحها |

---

## 🎓 توصيات مسار التعلم

### للمبتدئين (3-4 ساعات)
1. ✅ الجلسة 1: البدء (التركيز على الإعداد والمحادثة الأساسية)
2. ✅ الجلسة 2: أساسيات RAG (تجاوز التقييم في البداية)
3. ✅ الجلسة 3: قياس الأداء البسيط (نموذجين فقط)
4. ⏭️ تجاوز الجلسات 4-6 في الوقت الحالي
5. 🔄 العودة إلى الجلسات 4-6 بعد بناء التطبيق الأول

### للمطورين المتوسطين (3 ساعات)
1. ⚡ الجلسة 1: التحقق السريع من الإعداد
2. ✅ الجلسة 2: إكمال خط أنابيب RAG مع التقييم
3. ✅ الجلسة 3: مجموعة قياس الأداء الكاملة
4. ✅ الجلسة 4: تحسين النموذج
5. ✅ الجلسات 5-6: التركيز على أنماط البنية

### للممارسين المتقدمين (2-3 ساعات)
1. ⚡ الجلسات 1-3: مراجعة سريعة والتحقق
2. ✅ الجلسة 4: تعمق في التحسين
3. ✅ الجلسة 5: بنية متعددة الوكلاء
4. ✅ الجلسة 6: أنماط الإنتاج والتوسع
5. 🚀 التوسع: بناء منطق توجيه مخصص ونشرات هجينة

---

## حزمة جلسات الورشة (مختبرات مركزة لمدة 30 دقيقة)

إذا كنت تتبع تنسيق الورشة المكثف المكون من 6 جلسات، فاستخدم هذه الأدلة المخصصة (كل منها يتوافق مع ويكمل وثائق الوحدة الأوسع أعلاه):

| جلسة الورشة | الدليل | التركيز الأساسي |
|-------------|--------|-----------------|
| 1 | [Session01-GettingStartedFoundryLocal](./Session01-GettingStartedFoundryLocal.md) | التثبيت، التحقق، تشغيل phi و GPT-OSS-20B، التسريع |
| 2 | [Session02-BuildAISolutionsRAG](./Session02-BuildAISolutionsRAG.md) | هندسة التوجيه، أنماط RAG، تأريض CSV والمستندات، الترحيل |
| 3 | [Session03-OpenSourceModels](./Session03-OpenSourceModels.md) | تكامل Hugging Face، قياس الأداء، اختيار النموذج |
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | مقارنة بين SLM و LLM، WebGPU، Chainlit RAG، تسريع ONNX |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | أدوار الوكلاء، الذاكرة، الأدوات، التنسيق |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | التوجيه، الربط، مسار التوسع إلى Azure |

كل ملف جلسة يتضمن: ملخص، أهداف التعلم، عرض توضيحي لمدة 30 دقيقة، مشروع البداية، قائمة التحقق من التحقق، استكشاف الأخطاء وإصلاحها، ومراجع إلى Foundry Local Python SDK الرسمي.

### نصوص نموذجية

تثبيت متطلبات الورشة (Windows):

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

إذا كنت تستخدم خدمة Foundry Local على جهاز (Windows) مختلف أو VM من macOS، قم بتصدير نقطة النهاية:

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| الجلسة | النصوص | الوصف |
|---------|-----------|-------------|
| 1 | `samples/session01/chat_bootstrap.py` | خدمة التهيئة والدردشة المتدفقة |
| 2 | `samples/session02/rag_pipeline.py` | RAG بسيط (تضمينات في الذاكرة) |
|   | `samples/session02/rag_eval_ragas.py` | تقييم RAG باستخدام مقاييس ragas |
| 3 | `samples/session03/benchmark_oss_models.py` | قياس زمن الاستجابة والإنتاجية لنماذج متعددة |
| 4 | `samples/session04/model_compare.py` | مقارنة بين SLM و LLM (زمن الاستجابة ونتائج العينة) |
| 5 | `samples/session05/agents_orchestrator.py` | خط بحث وكيلين → تحرير |
| 6 | `samples/session06/models_router.py` | عرض توجيه يعتمد على النوايا |
|   | `samples/session06/models_pipeline.py` | سلسلة تخطيط/تنفيذ/تحسين متعددة الخطوات |

### متغيرات البيئة (مشتركة بين النصوص)

| المتغير | الغرض | المثال |
|----------|---------|---------|
| `FOUNDRY_LOCAL_ALIAS` | الاسم المستعار الافتراضي لنموذج واحد للنصوص الأساسية | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | نموذج SLM مقابل نموذج أكبر للمقارنة | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | قائمة بالأسماء المستعارة للنماذج المراد قياسها | `qwen2.5-0.5b,gemma-2-2b,mistral-7b` |
| `BENCH_ROUNDS` | عدد تكرارات القياس لكل نموذج | `3` |
| `BENCH_PROMPT` | النص المستخدم في القياس | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | نموذج تضمين sentence-transformers | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | تجاوز استعلام الاختبار لخط أنابيب RAG | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | تجاوز استعلام خط أنابيب الوكلاء | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | الاسم المستعار لنموذج وكيل البحث | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | الاسم المستعار لنموذج وكيل التحرير (يمكن أن يختلف) | `gpt-oss-20b` |
| `SHOW_USAGE` | عند `1`، يطبع استخدام الرموز لكل إكمال | `1` |
| `RETRY_ON_FAIL` | عند `1`، يعيد المحاولة مرة واحدة عند حدوث أخطاء عابرة في الدردشة | `1` |
| `RETRY_BACKOFF` | عدد الثواني للانتظار قبل إعادة المحاولة | `1.0` |

إذا لم يتم تعيين متغير، فإن النصوص تعتمد على الإعدادات الافتراضية المعقولة. بالنسبة للعروض التوضيحية لنموذج واحد، عادةً ما تحتاج فقط إلى `FOUNDRY_LOCAL_ALIAS`.

### وحدة المساعدة

تشارك جميع النصوص الآن مساعدًا `samples/workshop_utils.py` يوفر:

* إنشاء مدير `FoundryLocalManager` + عميل OpenAI مع التخزين المؤقت
* مساعد `chat_once()` مع خيار إعادة المحاولة + طباعة الاستخدام
* تقرير بسيط عن استخدام الرموز (تمكين عبر `SHOW_USAGE=1`)

هذا يقلل من التكرار ويبرز أفضل الممارسات لتنسيق النماذج المحلية بكفاءة.

## تحسينات اختيارية (عبر الجلسات)

| الموضوع | التحسين | الجلسات | البيئة / التبديل |
|-------|-------------|----------|--------------|
| الحتمية | درجة حرارة ثابتة + مجموعات نصوص مستقرة | 1–6 | تعيين `temperature=0`, `top_p=1` |
| رؤية استخدام الرموز | تعليم التكلفة/الكفاءة بشكل متسق | 1–6 | `SHOW_USAGE=1` |
| أول رمز متدفق | مقياس زمن الاستجابة المدرك | 1,3,4,6 | `BENCH_STREAM=1` (القياس) |
| مرونة إعادة المحاولة | معالجة بدء التشغيل البارد العابر | الكل | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| وكلاء متعدد النماذج | تخصص الأدوار المتغاير | 5 | `AGENT_MODEL_PRIMARY`, `AGENT_MODEL_EDITOR` |
| التوجيه التكيفي | النوايا + إرشادات التكلفة | 6 | تمديد الموجه بمنطق التصعيد |
| ذاكرة المتجه | استدعاء دلالي طويل الأمد | 2,5,6 | دمج مؤشر تضمين FAISS/Chroma |
| تصدير التتبع | التدقيق والتقييم | 2,5,6 | إضافة خطوط JSON لكل خطوة |
| معايير الجودة | تتبع نوعي | 3–6 | مطالب تسجيل النقاط الثانوية |
| اختبارات الدخان | التحقق السريع قبل الورشة | الكل | `python Workshop/tests/smoke.py` |

### البدء السريع الحتمي

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

توقع عدد رموز مستقر عبر إدخالات متطابقة متكررة.

### تقييم RAG (الجلسة 2)

استخدم `rag_eval_ragas.py` لحساب مدى ملاءمة الإجابة، الدقة، ودقة السياق على مجموعة بيانات صغيرة اصطناعية:

```powershell
python samples/session02/rag_eval_ragas.py
```

قم بالتوسيع عن طريق توفير JSONL أكبر للأسئلة، السياقات، والحقائق الأساسية، ثم تحويلها إلى `Dataset` من Hugging Face.

## ملحق دقة أوامر CLI

تستخدم الورشة فقط أوامر CLI الموثقة والمستقرة حاليًا لـ Foundry Local.

### الأوامر المستقرة المشار إليها

| الفئة | الأمر | الغرض |
|----------|---------|---------|
| الأساسية | `foundry --version` | عرض الإصدار المثبت |
| الأساسية | `foundry init` | تهيئة التكوين |
| الخدمة | `foundry service start` | بدء الخدمة المحلية (إذا لم تكن تلقائية) |
| الخدمة | `foundry status` | عرض حالة الخدمة |
| النماذج | `foundry model list` | قائمة الكتالوج / النماذج المتاحة |
| النماذج | `foundry model download <alias>` | تنزيل أوزان النموذج إلى ذاكرة التخزين المؤقت |
| النماذج | `foundry model run <alias>` | تشغيل (تحميل) نموذج محليًا؛ الجمع مع `--prompt` لجلسة واحدة |
| النماذج | `foundry model unload <alias>` / `foundry model stop <alias>` | تفريغ نموذج من الذاكرة (إذا كان مدعومًا) |
| ذاكرة التخزين المؤقت | `foundry cache list` | قائمة النماذج المخزنة (المنزلة) |
| النظام | `foundry system info` | لقطة قدرات الأجهزة والتسريع |
| النظام | `foundry system gpu-info` | معلومات تشخيص GPU |
| التكوين | `foundry config list` | عرض قيم التكوين الحالية |
| التكوين | `foundry config set <key> <value>` | تحديث التكوين |

### نمط النص الواحد

بدلاً من الأمر الفرعي القديم `model chat`، استخدم:

```powershell
foundry model run <alias> --prompt "Your question here"
```

هذا ينفذ دورة نص/استجابة واحدة ثم ينتهي.

### الأنماط المحذوفة / المتجنبة

| محذوف / غير موثق | البديل / التوجيه |
|---------------------------|------------------------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | استخدم `foundry model list` العادي + النشاط الأخير / السجلات |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | استخدم نص قياس Python + أدوات النظام (مدير المهام / `nvidia-smi`) |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### القياس عن بعد والقياس

- زمن الاستجابة، p95، الرموز/الثانية: `samples/session03/benchmark_oss_models.py`
- زمن الاستجابة لأول رمز (التدفق): تعيين `BENCH_STREAM=1`
- استخدام الموارد: مراقبات النظام (مدير المهام، مراقب النشاط، `nvidia-smi`) + `foundry system info`.

مع استقرار أوامر القياس عن بعد CLI الجديدة، يمكن دمجها مع تعديلات بسيطة على ملفات markdown للجلسة.

### الحارس التلقائي للمدقق

مدقق تلقائي يمنع إعادة إدخال أنماط CLI القديمة داخل كتل التعليمات البرمجية المسورة لملفات markdown:

النص: `Workshop/scripts/lint_markdown_cli.py`

الأنماط المحذوفة محظورة داخل أسوار التعليمات البرمجية.

البدائل الموصى بها:
| محذوف | البديل |
|------------|-------------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | نص القياس + أدوات النظام |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

تشغيل محليًا:
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

إجراء GitHub: `.github/workflows/markdown-cli-lint.yml` يتم تشغيله عند كل دفع & PR.

خطاف اختياري قبل الالتزام:
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## جدول ترحيل CLI → SDK السريع

| المهمة | أمر CLI سطر واحد | المكافئ في SDK (Python) | الملاحظات |
|------|---------------|-------------------------|-------|
| تشغيل نموذج مرة واحدة (النص) | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK يقوم بتهيئة الخدمة والتخزين المؤقت تلقائيًا |
| تنزيل (تخزين مؤقت) النموذج | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # triggers download/load` | المدير يختار أفضل إصدار إذا كان الاسم المستعار يشير إلى عدة إصدارات |
| قائمة الكتالوج | `foundry model list` | `# use manager for each alias or maintain known list` | CLI يجمع؛ SDK حاليًا لكل اسم مستعار |
| قائمة النماذج المخزنة | `foundry cache list` | `manager.list_cached_models()` | بعد تهيئة المدير (أي اسم مستعار) |
| تمكين تسريع GPU | `foundry config set compute.onnx.enable_gpu true` | `# CLI action; SDK assumes config already applied` | التكوين هو تأثير خارجي |
| الحصول على عنوان URL لنقطة النهاية | (ضمنيًا) | `manager.endpoint` | يستخدم لإنشاء عميل متوافق مع OpenAI |
| تسخين نموذج | `foundry model run <alias>` ثم النص الأول | `chat_once(alias, messages=[...])` (utility) | الأدوات تتعامل مع زمن الاستجابة الأولي |
| قياس زمن الاستجابة | `python benchmark_oss_models.py` | `import benchmark_oss_models` (or new exporter script) | يفضل النص للحصول على مقاييس متسقة |
| إيقاف / تفريغ النموذج | `foundry model unload <alias>` | (غير مكشوف – إعادة تشغيل الخدمة / العملية) | عادةً غير مطلوب لتدفق الورشة |
| استرداد استخدام الرموز | (عرض الإخراج) | `resp.usage.total_tokens` | يتم توفيره إذا أعاد الخلفية كائن الاستخدام |

## تصدير Markdown للقياس

استخدم النص `Workshop/scripts/export_benchmark_markdown.py` لتشغيل قياس جديد (نفس المنطق مثل `samples/session03/benchmark_oss_models.py`) وإصدار جدول Markdown مناسب لـ GitHub بالإضافة إلى JSON الخام.

### مثال

```powershell
python Workshop\scripts\export_benchmark_markdown.py --models "qwen2.5-0.5b,gemma-2-2b,mistral-7b" --prompt "Explain retrieval augmented generation briefly." --rounds 3 --output benchmark_report.md
```

الملفات المولدة:
| الملف | المحتويات |
|------|----------|
| `benchmark_report.md` | جدول Markdown + تلميحات التفسير |
| `benchmark_report.json` | مصفوفة المقاييس الخام (للمقارنة / تتبع الاتجاهات) |

قم بتعيين `BENCH_STREAM=1` في البيئة لتضمين زمن الاستجابة لأول رمز إذا كان مدعومًا.

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الموثوق. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسيرات خاطئة تنشأ عن استخدام هذه الترجمة.