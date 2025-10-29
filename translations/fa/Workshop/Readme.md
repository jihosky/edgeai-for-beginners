<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "45923ada94573fee7c82cc4f0c3bb344",
  "translation_date": "2025-10-28T20:25:16+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "fa"
}
-->
# EdgeAI برای مبتدیان - کارگاه

> **مسیر یادگیری عملی برای ساخت برنامه‌های هوش مصنوعی آماده تولید در لبه**
>
> تسلط بر استقرار هوش مصنوعی محلی با Microsoft Foundry Local، از اولین تکمیل چت تا هماهنگی چند عامل در ۶ جلسه پیشرفته.

---

## 🎯 مقدمه

به **کارگاه EdgeAI برای مبتدیان** خوش آمدید - راهنمای عملی شما برای ساخت برنامه‌های هوشمند که به طور کامل بر روی سخت‌افزار محلی اجرا می‌شوند. این کارگاه مفاهیم نظری هوش مصنوعی لبه را به مهارت‌های واقعی تبدیل می‌کند، از طریق تمرین‌های چالش‌برانگیز با استفاده از Microsoft Foundry Local و مدل‌های زبان کوچک (SLMs).

### چرا این کارگاه؟

**انقلاب هوش مصنوعی لبه آغاز شده است**

سازمان‌ها در سراسر جهان به دلایل مهم زیر از هوش مصنوعی وابسته به ابر به محاسبات لبه روی آورده‌اند:

1. **حریم خصوصی و انطباق** - پردازش داده‌های حساس به صورت محلی بدون انتقال به ابر (HIPAA، GDPR، مقررات مالی)
2. **عملکرد** - حذف تأخیر شبکه (۵۰-۵۰۰ میلی‌ثانیه محلی در مقابل ۵۰۰-۲۰۰۰ میلی‌ثانیه رفت و برگشت ابر)
3. **کنترل هزینه** - حذف هزینه‌های API بر اساس توکن و مقیاس‌پذیری بدون هزینه‌های ابر

**اما هوش مصنوعی لبه متفاوت است**

اجرای هوش مصنوعی در محل نیاز به مهارت‌های جدید دارد:
- انتخاب و بهینه‌سازی مدل برای محدودیت‌های منابع
- مدیریت خدمات محلی و شتاب‌دهی سخت‌افزاری
- مهندسی درخواست برای مدل‌های کوچک‌تر
- الگوهای استقرار تولید برای دستگاه‌های لبه

**این کارگاه این مهارت‌ها را ارائه می‌دهد**

در ۶ جلسه متمرکز (~۳ ساعت در مجموع)، شما از "سلام دنیا" تا استقرار سیستم‌های چند عاملی آماده تولید پیشرفت خواهید کرد - همه به صورت محلی بر روی دستگاه شما اجرا می‌شوند.

---

## 📚 اهداف یادگیری

با تکمیل این کارگاه، شما قادر خواهید بود:

### مهارت‌های اصلی
1. **استقرار و مدیریت خدمات هوش مصنوعی محلی**
   - نصب و پیکربندی Microsoft Foundry Local
   - انتخاب مدل‌های مناسب برای استقرار لبه
   - مدیریت چرخه عمر مدل (دانلود، بارگذاری، ذخیره‌سازی)
   - نظارت بر استفاده از منابع و بهینه‌سازی عملکرد

2. **ساخت برنامه‌های هوش مصنوعی**
   - پیاده‌سازی تکمیل چت سازگار با OpenAI به صورت محلی
   - طراحی درخواست‌های مؤثر برای مدل‌های زبان کوچک
   - مدیریت پاسخ‌های جریان برای تجربه کاربری بهتر
   - ادغام مدل‌های محلی در برنامه‌های موجود

3. **ایجاد سیستم‌های RAG (تولید تقویت‌شده با بازیابی)**
   - ساخت جستجوی معنایی با تعبیه‌ها
   - پایه‌گذاری پاسخ‌های LLM در دانش خاص دامنه
   - ارزیابی کیفیت RAG با معیارهای استاندارد صنعتی
   - مقیاس‌پذیری از نمونه اولیه تا تولید

4. **بهینه‌سازی عملکرد مدل**
   - ارزیابی چندین مدل برای مورد استفاده شما
   - اندازه‌گیری تأخیر، توان عملیاتی، و زمان اولین توکن
   - انتخاب مدل‌های بهینه بر اساس تعادل سرعت/کیفیت
   - مقایسه تعادل SLM و LLM در سناریوهای واقعی

5. **هماهنگی سیستم‌های چند عاملی**
   - طراحی عوامل تخصصی برای وظایف مختلف
   - پیاده‌سازی حافظه عامل و مدیریت زمینه
   - هماهنگی عوامل در جریان‌های کاری پیچیده
   - هدایت درخواست‌ها به صورت هوشمندانه در میان مدل‌های مختلف

6. **استقرار راه‌حل‌های آماده تولید**
   - پیاده‌سازی مدیریت خطا و منطق تلاش مجدد
   - نظارت بر استفاده از توکن و منابع سیستم
   - ساخت معماری‌های مقیاس‌پذیر با الگوهای مدل به عنوان ابزار
   - برنامه‌ریزی مسیرهای مهاجرت از لبه به ترکیبی (لبه + ابر)

---

## 🎓 نتایج یادگیری

### آنچه خواهید ساخت

تا پایان این کارگاه، شما موارد زیر را ایجاد خواهید کرد:

| جلسه | خروجی | مهارت‌های نشان داده شده |
|------|-------|--------------------------|
| **۱** | برنامه چت با جریان | راه‌اندازی خدمات، تکمیل‌های پایه، تجربه کاربری جریان |
| **۲** | سیستم RAG با ارزیابی | تعبیه‌ها، جستجوی معنایی، معیارهای کیفیت |
| **۳** | مجموعه ارزیابی چند مدل | اندازه‌گیری عملکرد، مقایسه مدل‌ها |
| **۴** | مقایسه‌کننده SLM و LLM | تحلیل تعادل، استراتژی‌های بهینه‌سازی |
| **۵** | هماهنگ‌کننده چند عامل | طراحی عامل، مدیریت حافظه، هماهنگی |
| **۶** | سیستم هدایت هوشمند | تشخیص قصد، انتخاب مدل، مقیاس‌پذیری |

### ماتریس مهارت‌ها

| سطح مهارت | جلسه ۱-۲ | جلسه ۳-۴ | جلسه ۵-۶ |
|-----------|----------|----------|----------|
| **مبتدی** | ✅ راه‌اندازی و اصول | ⚠️ چالش‌برانگیز | ❌ خیلی پیشرفته |
| **متوسط** | ✅ مرور سریع | ✅ یادگیری اصلی | ⚠️ اهداف کششی |
| **پیشرفته** | ✅ آسان | ✅ پالایش | ✅ الگوهای تولید |

### مهارت‌های آماده شغلی

**پس از این کارگاه، شما آماده خواهید بود:**

✅ **ساخت برنامه‌های اولویت‌دار حریم خصوصی**
- برنامه‌های بهداشتی که اطلاعات PHI/PII را به صورت محلی پردازش می‌کنند
- خدمات مالی با نیازهای انطباق
- سیستم‌های دولتی با نیازهای حاکمیت داده

✅ **بهینه‌سازی برای محیط‌های لبه**
- دستگاه‌های IoT با منابع محدود
- برنامه‌های موبایل آفلاین
- سیستم‌های بلادرنگ با تأخیر کم

✅ **طراحی معماری‌های هوشمند**
- سیستم‌های چند عاملی برای جریان‌های کاری پیچیده
- استقرار ترکیبی لبه-ابر
- زیرساخت‌های هوش مصنوعی بهینه‌سازی شده از نظر هزینه

✅ **رهبری ابتکارات هوش مصنوعی لبه**
- ارزیابی امکان‌پذیری هوش مصنوعی لبه برای پروژه‌ها
- انتخاب مدل‌ها و چارچوب‌های مناسب
- طراحی راه‌حل‌های هوش مصنوعی محلی مقیاس‌پذیر

---

## 🗺️ ساختار کارگاه

### نمای کلی جلسات (۶ جلسه × ۳۰ دقیقه = ۳ ساعت)

| جلسه | موضوع | تمرکز | مدت زمان |
|------|-------|-------|----------|
| **۱** | شروع کار با Foundry Local | نصب، اعتبارسنجی، اولین تکمیل‌ها | ۳۰ دقیقه |
| **۲** | ساخت راه‌حل‌های هوش مصنوعی با RAG | مهندسی درخواست، تعبیه‌ها، ارزیابی | ۳۰ دقیقه |
| **۳** | مدل‌های متن‌باز | کشف مدل، ارزیابی، انتخاب | ۳۰ دقیقه |
| **۴** | مدل‌های پیشرفته | SLM در مقابل LLM، بهینه‌سازی، چارچوب‌ها | ۳۰ دقیقه |
| **۵** | عوامل هوش مصنوعی | طراحی عامل، هماهنگی، حافظه | ۳۰ دقیقه |
| **۶** | مدل‌ها به عنوان ابزار | هدایت، زنجیره‌سازی، استراتژی‌های مقیاس‌پذیری | ۳۰ دقیقه |

---

## 🚀 شروع سریع

### پیش‌نیازها

**نیازمندی‌های سیستم:**
- **سیستم عامل**: Windows 10/11، macOS 11+، یا Linux (Ubuntu 20.04+)
- **رم**: حداقل ۸ گیگابایت، توصیه شده ۱۶ گیگابایت+
- **فضای ذخیره‌سازی**: حداقل ۱۰ گیگابایت فضای آزاد برای مدل‌ها
- **پردازنده**: پردازنده مدرن با پشتیبانی از AVX2
- **GPU** (اختیاری): سازگار با CUDA یا Qualcomm NPU برای شتاب‌دهی

**نیازمندی‌های نرم‌افزاری:**
- **Python 3.8+** ([دانلود](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([راهنمای نصب](../../../Workshop))
- **Git** ([دانلود](https://git-scm.com/downloads))
- **Visual Studio Code** (توصیه شده) ([دانلود](https://code.visualstudio.com/))

### راه‌اندازی در ۳ مرحله

#### ۱. نصب Foundry Local

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**تأیید نصب:**
```bash
foundry --version
foundry service status
```

**اطمینان حاصل کنید که Azure AI Foundry Local با یک پورت ثابت اجرا می‌شود**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**تأیید عملکرد:**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**مشاهده مدل‌های موجود**
برای مشاهده مدل‌های موجود در نمونه Foundry Local خود، می‌توانید نقطه پایانی مدل‌ها را پرس‌وجو کنید:

```bash
# cmd/bash/powershell
foundry model list
```

با استفاده از نقطه پایانی وب 

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### ۲. کلون کردن مخزن و نصب وابستگی‌ها

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

#### ۳. اجرای نمونه اول

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples
python -m session01.chat_bootstrap "What is edge AI?"
```

**✅ موفقیت!** باید یک پاسخ جریان درباره هوش مصنوعی لبه مشاهده کنید.

---

## 📦 منابع کارگاه

### نمونه‌های پایتون

مثال‌های عملی پیشرفته که هر مفهوم را نشان می‌دهند:

| جلسه | نمونه | توضیحات | زمان اجرا |
|------|-------|---------|-----------|
| ۱ | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | چت پایه و جریان | ~۳۰ ثانیه |
| ۲ | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | RAG با تعبیه‌ها | ~۴۵ ثانیه |
| ۲ | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | ارزیابی کیفیت RAG | ~۶۰ ثانیه |
| ۳ | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | ارزیابی چند مدل | ~۲-۳ دقیقه |
| ۴ | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | مقایسه SLM و LLM | ~۴۵ ثانیه |
| ۵ | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | سیستم چند عاملی | ~۶۰ ثانیه |
| ۶ | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | هدایت مبتنی بر قصد | ~۴۵ ثانیه |
| ۶ | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | خط لوله چند مرحله‌ای | ~۶۰ ثانیه |

### نوت‌بوک‌های Jupyter

کاوش تعاملی با توضیحات و بصری‌سازی‌ها:

| جلسه | نوت‌بوک | توضیحات | سختی |
|------|---------|---------|------|
| ۱ | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | اصول چت و جریان | ⭐ مبتدی |
| ۲ | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline.ipynb) | ساخت سیستم RAG | ⭐⭐ متوسط |
| ۲ | [`session02_rag_eval_ragas.ipynb`](./notebooks/session02_rag_eval_ragas.ipynb) | ارزیابی کیفیت RAG | ⭐⭐ متوسط |
| ۳ | [`session03_benchmark_oss_models.ipynb`](./notebooks/session03_benchmark_oss_models.ipynb) | ارزیابی مدل | ⭐⭐ متوسط |
| ۴ | [`session04_model_compare.ipynb`](./notebooks/session04_model_compare.ipynb) | مقایسه مدل | ⭐⭐ متوسط |
| ۵ | [`session05_agents_orchestrator.ipynb`](./notebooks/session05_agents_orchestrator.ipynb) | هماهنگی عامل | ⭐⭐⭐ پیشرفته |
| ۶ | [`session06_models_router.ipynb`](./notebooks/session06_models_router.ipynb) | هدایت قصد | ⭐⭐⭐ پیشرفته |
| ۶ | [`session06_models_pipeline.ipynb`](./notebooks/session06_models_pipeline.ipynb) | هماهنگی خط لوله | ⭐⭐⭐ پیشرفته |

### مستندات

راهنماها و منابع جامع:

| سند | توضیحات | استفاده زمانی |
|-----|---------|---------------|
| [QUICK_START.md](./QUICK_START.md) | راهنمای راه‌اندازی سریع | شروع از ابتدا |
| [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) | برگه تقلب دستورات و API | نیاز به پاسخ سریع |
| [FOUNDRY_SDK_QUICKREF.md](./FOUNDRY_SDK_QUICKREF.md) | الگوها و مثال‌های SDK | نوشتن کد |
| [ENV_CONFIGURATION.md](./ENV_CONFIGURATION.md) | راهنمای متغیرهای محیطی | پیکربندی نمونه‌ها |
| [SAMPLES_UPDATE_SUMMARY.md](./SAMPLES_UPDATE_SUMMARY.md) | بهبودهای نمونه‌های اخیر | درک تغییرات |
| [SDK_MIGRATION_NOTES.md](./SDK_MIGRATION_NOTES.md) | راهنمای مهاجرت | ارتقاء کد |
| [notebooks/TROUBLESHOOTING.md](./notebooks/TROUBLESHOOTING.md) | مشکلات رایج و راه‌حل‌ها | رفع اشکال مشکلات |

---

## 🎓 توصیه‌های مسیر یادگیری

### برای مبتدیان (۳-۴ ساعت)
1. ✅ جلسه ۱: شروع کار (تمرکز بر راه‌اندازی و چت پایه)
2. ✅ جلسه ۲: اصول RAG (ابتدا ارزیابی را رد کنید)
3. ✅ جلسه ۳: ارزیابی ساده (فقط ۲ مدل)
4. ⏭️ جلسات ۴-۶ را فعلاً رد کنید
5. 🔄 پس از ساخت اولین برنامه به جلسات ۴-۶ بازگردید

### برای توسعه‌دهندگان متوسط (۳ ساعت)
1. ⚡ جلسه ۱: اعتبارسنجی سریع راه‌اندازی
2. ✅ جلسه ۲: تکمیل خط لوله RAG با ارزیابی
3. ✅ جلسه ۳: مجموعه کامل ارزیابی
4. ✅ جلسه ۴: بهینه‌سازی مدل
5. ✅ جلسات ۵-۶: تمرکز بر الگوهای معماری

### برای متخصصان پیشرفته (۲-۳ ساعت)
1. ⚡ جلسات ۱-۳: مرور سریع و اعتبارسنجی
2. ✅ جلسه ۴: بررسی عمیق بهینه‌سازی
3. ✅ جلسه ۵: معماری چند عاملی
4. ✅ جلسه ۶: الگوهای تولید و مقیاس‌پذیری
5. 🚀 گسترش: ساخت منطق هدایت سفارشی و استقرار ترکیبی

---

## بسته جلسات کارگاه (آزمایشگاه‌های متمرکز ۳۰ دقیقه‌ای)

اگر از قالب کارگاه فشرده ۶ جلسه‌ای پیروی می‌کنید، از این راهنماهای اختصاصی استفاده کنید (هر کدام با ماژول‌های گسترده‌تر بالا مطابقت دارند و آن‌ها را تکمیل می‌کنند):

| جلسه کارگاه | راهنما | تمرکز اصلی |
|-------------|--------|------------|
| ۱ | [Session01-GettingStartedFoundryLocal](./Session01-GettingStartedFoundryLocal.md) | نصب، اعتبارسنجی، اجرای phi و GPT-OSS-20B، شتاب‌دهی |
| ۲ | [Session02-BuildAISolutionsRAG](./Session02-BuildAISolutionsRAG.md) | مهندسی درخواست، الگوهای RAG، پایه‌گذاری CSV و سند، مهاجرت |
| ۳ | [Session03-OpenSourceModels](./Session03-OpenSourceModels.md) | یکپارچه‌سازی Hugging Face، ارزیابی، انتخاب مدل |
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | مقایسه SLM و LLM، WebGPU، Chainlit RAG، شتاب‌دهی ONNX |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | نقش‌های عامل، حافظه، ابزارها، هماهنگی |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | مسیریابی، زنجیره‌سازی، مسیر مقیاس‌پذیری به Azure |

هر فایل جلسه شامل موارد زیر است: خلاصه، اهداف یادگیری، جریان نمایشی ۳۰ دقیقه‌ای، پروژه شروع، چک‌لیست اعتبارسنجی، رفع اشکال و ارجاعات به Foundry Local Python SDK رسمی.

### اسکریپت‌های نمونه

نصب وابستگی‌های کارگاه (ویندوز):

```powershell
cd Workshop
py -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

macOS / لینوکس:

```bash
cd Workshop
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

اگر سرویس Foundry Local را روی یک ماشین یا VM دیگر (ویندوز) از macOS اجرا می‌کنید، نقطه پایانی را صادر کنید:

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| جلسه | اسکریپت(ها) | توضیحات |
|------|-------------|---------|
| 1 | `samples/session01/chat_bootstrap.py` | راه‌اندازی سرویس و چت استریمینگ |
| 2 | `samples/session02/rag_pipeline.py` | RAG حداقلی (تعبیه‌های در حافظه) |
|   | `samples/session02/rag_eval_ragas.py` | ارزیابی RAG با معیارهای ragas |
| 3 | `samples/session03/benchmark_oss_models.py` | ارزیابی تأخیر و توان چند مدل |
| 4 | `samples/session04/model_compare.py` | مقایسه SLM و LLM (تأخیر و خروجی نمونه) |
| 5 | `samples/session05/agents_orchestrator.py` | خط لوله تحقیق → ویرایش دو عامل |
| 6 | `samples/session06/models_router.py` | نمایش مسیریابی مبتنی بر هدف |
|   | `samples/session06/models_pipeline.py` | زنجیره برنامه‌ریزی/اجرا/اصلاح چند مرحله‌ای |

### متغیرهای محیطی (مشترک بین نمونه‌ها)

| متغیر | هدف | مثال |
|-------|-----|-------|
| `FOUNDRY_LOCAL_ALIAS` | نام مستعار مدل پیش‌فرض برای نمونه‌های پایه | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | SLM صریح در مقابل مدل بزرگ‌تر برای مقایسه | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | لیست نام مستعار برای ارزیابی | `qwen2.5-0.5b,mistral-7b` |
| `BENCH_ROUNDS` | تعداد تکرار ارزیابی برای هر مدل | `3` |
| `BENCH_PROMPT` | درخواست استفاده شده در ارزیابی | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | مدل تعبیه‌کننده sentence-transformers | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | پرسش آزمایشی برای خط لوله RAG | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | پرسش خط لوله عوامل | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | نام مستعار مدل برای عامل تحقیق | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | نام مستعار مدل برای عامل ویرایشگر (می‌تواند متفاوت باشد) | `gpt-oss-20b` |
| `SHOW_USAGE` | وقتی `1` باشد، استفاده از توکن‌ها را در هر تکمیل چاپ می‌کند | `1` |
| `RETRY_ON_FAIL` | وقتی `1` باشد، در صورت خطای چت موقت یک بار تلاش مجدد می‌کند | `1` |
| `RETRY_BACKOFF` | ثانیه‌های انتظار قبل از تلاش مجدد | `1.0` |

اگر متغیری تنظیم نشده باشد، اسکریپت‌ها به تنظیمات پیش‌فرض منطقی بازمی‌گردند. برای نمایش‌های تک‌مدلی معمولاً فقط به `FOUNDRY_LOCAL_ALIAS` نیاز دارید.

### ماژول کمکی

تمام نمونه‌ها اکنون از یک فایل کمکی مشترک `samples/workshop_utils.py` استفاده می‌کنند که موارد زیر را فراهم می‌کند:

* ایجاد کش شده `FoundryLocalManager` + کلاینت OpenAI
* کمک‌کننده `chat_once()` با تلاش مجدد اختیاری + چاپ استفاده
* گزارش ساده استفاده از توکن (فعال‌سازی با `SHOW_USAGE=1`)

این کار تکرار را کاهش داده و بهترین روش‌ها برای هماهنگی مدل محلی کارآمد را برجسته می‌کند.

## بهبودهای اختیاری (بین جلسات)

| موضوع | بهبود | جلسات | محیط / تغییر |
|-------|-------|-------|--------------|
| تعیین‌پذیری | دمای ثابت + مجموعه درخواست‌های پایدار | ۱–۶ | تنظیم `temperature=0`, `top_p=1` |
| نمایش استفاده از توکن | آموزش هزینه/کارایی مداوم | ۱–۶ | `SHOW_USAGE=1` |
| استریم اولین توکن | معیار تأخیر ادراکی | ۱، ۳، ۴، ۶ | `BENCH_STREAM=1` (ارزیابی) |
| مقاومت در برابر تلاش مجدد | مدیریت شروع سرد موقت | همه | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| عوامل چندمدلی | تخصص نقش‌های ناهمگن | ۵ | `AGENT_MODEL_PRIMARY`, `AGENT_MODEL_EDITOR` |
| مسیریابی تطبیقی | هدف + اکتشاف هزینه | ۶ | گسترش مسیریاب با منطق تشدید |
| حافظه برداری | یادآوری معنایی بلندمدت | ۲، ۵، ۶ | ادغام شاخص تعبیه FAISS/Chroma |
| صادرات ردیابی | حسابرسی و ارزیابی | ۲، ۵، ۶ | افزودن خطوط JSON در هر مرحله |
| معیارهای کیفیت | پیگیری کیفی | ۳–۶ | درخواست‌های امتیازدهی ثانویه |
| آزمایش‌های سریع | اعتبارسنجی سریع پیش از کارگاه | همه | `python Workshop/tests/smoke.py` |

### شروع سریع تعیین‌پذیر

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

انتظار شمارش توکن‌های پایدار در ورودی‌های یکسان تکراری را داشته باشید.

### ارزیابی RAG (جلسه ۲)

از `rag_eval_ragas.py` برای محاسبه مرتبط بودن پاسخ، صحت و دقت زمینه در یک مجموعه داده مصنوعی کوچک استفاده کنید:

```powershell
cd Workshop/samples
python -m session02.rag_eval_ragas
```

با ارائه یک JSONL بزرگ‌تر از پرسش‌ها، زمینه‌ها و حقایق پایه گسترش دهید، سپس آن را به یک `Dataset` Hugging Face تبدیل کنید.

## ضمیمه دقت دستورات CLI

در کارگاه فقط از دستورات CLI مستند و پایدار Foundry Local استفاده شده است.

### دستورات پایدار مورد استفاده

| دسته‌بندی | دستور | هدف |
|-----------|-------|-----|
| اصلی | `foundry --version` | نمایش نسخه نصب شده |
| اصلی | `foundry init` | پیکربندی اولیه |
| سرویس | `foundry service start` | شروع سرویس محلی (در صورت عدم خودکار بودن) |
| سرویس | `foundry status` | نمایش وضعیت سرویس |
| مدل‌ها | `foundry model list` | لیست کاتالوگ / مدل‌های موجود |
| مدل‌ها | `foundry model download <alias>` | دانلود وزن‌های مدل به کش |
| مدل‌ها | `foundry model run <alias>` | اجرای (بارگذاری) یک مدل محلی؛ ترکیب با `--prompt` برای یک بار اجرا |
| مدل‌ها | `foundry model unload <alias>` / `foundry model stop <alias>` | بارگذاری مدل از حافظه (در صورت پشتیبانی) |
| کش | `foundry cache list` | لیست مدل‌های کش شده (دانلود شده) |
| سیستم | `foundry system info` | عکس‌برداری از قابلیت‌های سخت‌افزاری و شتاب‌دهی |
| سیستم | `foundry system gpu-info` | اطلاعات تشخیصی GPU |
| پیکربندی | `foundry config list` | نمایش مقادیر پیکربندی فعلی |
| پیکربندی | `foundry config set <key> <value>` | به‌روزرسانی پیکربندی |

### الگوی درخواست یک‌بار اجرا

به جای دستور منسوخ شده `model chat`، از این استفاده کنید:

```powershell
foundry model run <alias> --prompt "Your question here"
```

این یک چرخه درخواست/پاسخ را اجرا کرده و سپس خارج می‌شود.

### الگوهای حذف شده / اجتناب شده

| منسوخ / مستند نشده | جایگزین / راهنما |
|--------------------|------------------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | استفاده از `foundry model list` ساده + فعالیت اخیر / لاگ‌ها |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | استفاده از اسکریپت ارزیابی Python + ابزارهای سیستم (Task Manager / `nvidia-smi`) |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### ارزیابی و تله‌متری

- تأخیر، p95، توکن‌ها در ثانیه: `samples/session03/benchmark_oss_models.py`
- تأخیر اولین توکن (استریم): تنظیم `BENCH_STREAM=1`
- استفاده از منابع: مانیتورهای سیستم (Task Manager، Activity Monitor، `nvidia-smi`) + `foundry system info`.

با تثبیت دستورات تله‌متری CLI جدید، می‌توان آن‌ها را با حداقل ویرایش به فایل‌های markdown جلسه اضافه کرد.

### نگهبان خودکار Lint

یک ابزار lint خودکار از بازگشت الگوهای CLI منسوخ شده در داخل بلوک‌های کد محصور شده فایل‌های markdown جلوگیری می‌کند:

اسکریپت: `Workshop/scripts/lint_markdown_cli.py`

الگوهای منسوخ شده در داخل بلوک‌های کد مسدود می‌شوند.

جایگزین‌های پیشنهادی:
| منسوخ شده | جایگزین |
|-----------|---------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | اسکریپت ارزیابی + ابزارهای سیستم |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

اجرای محلی:
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

GitHub Action: `.github/workflows/markdown-cli-lint.yml` در هر push و PR اجرا می‌شود.

هوک اختیاری پیش از commit:
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## جدول مهاجرت سریع CLI → SDK

| وظیفه | دستور CLI یک‌خطی | معادل SDK (Python) | توضیحات |
|-------|------------------|--------------------|---------|
| اجرای یک مدل (درخواست) | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK سرویس و کش را به‌طور خودکار راه‌اندازی می‌کند |
| دانلود (کش) مدل | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # triggers download/load` | مدیر بهترین نسخه را انتخاب می‌کند اگر نام مستعار به چندین نسخه نگاشت شود |
| لیست کاتالوگ | `foundry model list` | `# use manager for each alias or maintain known list` | CLI جمع‌آوری می‌کند؛ SDK در حال حاضر برای هر نام مستعار ایجاد می‌شود |
| لیست مدل‌های کش شده | `foundry cache list` | `manager.list_cached_models()` | پس از راه‌اندازی مدیر (هر نام مستعار) |
| فعال‌سازی شتاب GPU | `foundry config set compute.onnx.enable_gpu true` | `# CLI action; SDK assumes config already applied` | پیکربندی اثر جانبی خارجی است |
| دریافت URL نقطه پایانی | (ضمنی) | `manager.endpoint` | برای ایجاد کلاینت سازگار با OpenAI استفاده می‌شود |
| گرم کردن یک مدل | `foundry model run <alias>` سپس اولین درخواست | `chat_once(alias, messages=[...])` (utility) | ابزارها تأخیر اولیه سرد را مدیریت می‌کنند |
| اندازه‌گیری تأخیر | `python -m session03.benchmark_oss_models` | `import benchmark_oss_models` (or new exporter script) | ترجیحاً از اسکریپت برای معیارهای سازگار استفاده کنید |
| توقف / بارگذاری مدل | `foundry model unload <alias>` | (Not exposed – restart service / process) | معمولاً برای جریان کارگاه مورد نیاز نیست |
| بازیابی استفاده از توکن | (مشاهده خروجی) | `resp.usage.total_tokens` | اگر backend شیء استفاده را بازگرداند ارائه می‌شود |

## صادرات Markdown ارزیابی

از اسکریپت `Workshop/scripts/export_benchmark_markdown.py` برای اجرای یک ارزیابی جدید (منطق مشابه `samples/session03/benchmark_oss_models.py`) و تولید یک جدول Markdown مناسب GitHub به‌علاوه JSON خام استفاده کنید.

### مثال

```powershell
python Workshop\scripts\export_benchmark_markdown.py --models "qwen2.5-0.5b,mistral-7b" --prompt "Explain retrieval augmented generation briefly." --rounds 3 --output benchmark_report.md
```

فایل‌های تولید شده:
| فایل | محتویات |
|------|----------|
| `benchmark_report.md` | جدول Markdown + نکات تفسیر |
| `benchmark_report.json` | آرایه معیارهای خام (برای مقایسه / پیگیری روند) |

تنظیم `BENCH_STREAM=1` در محیط برای شامل کردن تأخیر اولین توکن در صورت پشتیبانی.

---

**سلب مسئولیت**:  
این سند با استفاده از سرویس ترجمه هوش مصنوعی [Co-op Translator](https://github.com/Azure/co-op-translator) ترجمه شده است. در حالی که ما تلاش می‌کنیم دقت را حفظ کنیم، لطفاً توجه داشته باشید که ترجمه‌های خودکار ممکن است شامل خطاها یا نادرستی‌ها باشند. سند اصلی به زبان اصلی آن باید به عنوان منبع معتبر در نظر گرفته شود. برای اطلاعات حساس، ترجمه حرفه‌ای انسانی توصیه می‌شود. ما مسئولیتی در قبال سوء تفاهم‌ها یا تفسیرهای نادرست ناشی از استفاده از این ترجمه نداریم.