<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b994c57f1207012e4d7f58b7c0d1ae7",
  "translation_date": "2025-10-17T09:23:34+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "bn"
}
-->
# EdgeAI for Beginners - কর্মশালা

> **প্রোডাকশন-রেডি এজ এআই অ্যাপ্লিকেশন তৈরির জন্য হাতে-কলমে শেখার পথ**
>
> Microsoft Foundry Local ব্যবহার করে প্রথম চ্যাট কমপ্লিশন থেকে মাল্টি-এজেন্ট অর্কেস্ট্রেশন পর্যন্ত ৬টি প্রগতিশীল সেশনে স্থানীয় AI ডিপ্লয়মেন্টে দক্ষতা অর্জন করুন।

---

## 🎯 পরিচিতি

**EdgeAI for Beginners Workshop**-এ আপনাকে স্বাগতম - এটি এমন একটি হাতে-কলমে গাইড যা আপনাকে স্থানীয় হার্ডওয়্যারে সম্পূর্ণভাবে চালিত বুদ্ধিমান অ্যাপ্লিকেশন তৈরি করতে শেখাবে। এই কর্মশালা তাত্ত্বিক Edge AI ধারণাগুলিকে বাস্তব দক্ষতায় রূপান্তরিত করে, Microsoft Foundry Local এবং Small Language Models (SLMs) ব্যবহার করে ক্রমশ চ্যালেঞ্জিং অনুশীলনের মাধ্যমে।

### কেন এই কর্মশালা?

**এজ এআই বিপ্লব শুরু হয়েছে**

বিশ্বজুড়ে প্রতিষ্ঠানগুলো তিনটি গুরুত্বপূর্ণ কারণে ক্লাউড-নির্ভর AI থেকে এজ কম্পিউটিংয়ে স্থানান্তরিত হচ্ছে:

1. **গোপনীয়তা ও সম্মতি** - সংবেদনশীল ডেটা স্থানীয়ভাবে প্রক্রিয়া করুন, ক্লাউডে প্রেরণ ছাড়াই (HIPAA, GDPR, আর্থিক নিয়মাবলী)
2. **পারফরম্যান্স** - নেটওয়ার্ক লেটেন্সি দূর করুন (স্থানীয় ৫০-৫০০ms বনাম ক্লাউড ৫০০-২০০০ms রাউন্ড-ট্রিপ)
3. **খরচ নিয়ন্ত্রণ** - প্রতি-টোকেন API খরচ সরিয়ে দিন এবং ক্লাউড ব্যয় ছাড়াই স্কেল করুন

**কিন্তু এজ এআই আলাদা**

অন-প্রিমাইস AI চালানোর জন্য নতুন দক্ষতার প্রয়োজন:
- মডেল নির্বাচন এবং রিসোর্স সীমাবদ্ধতার জন্য অপ্টিমাইজেশন
- স্থানীয় সার্ভিস ম্যানেজমেন্ট এবং হার্ডওয়্যার অ্যাক্সিলারেশন
- ছোট মডেলের জন্য প্রম্পট ইঞ্জিনিয়ারিং
- এজ ডিভাইসের জন্য প্রোডাকশন ডিপ্লয়মেন্ট প্যাটার্ন

**এই কর্মশালা সেই দক্ষতাগুলি প্রদান করে**

৬টি ফোকাসড সেশনে (~৩ ঘণ্টা মোট), আপনি "হ্যালো ওয়ার্ল্ড" থেকে প্রোডাকশন-রেডি মাল্টি-এজেন্ট সিস্টেম ডিপ্লয়মেন্ট পর্যন্ত অগ্রসর হবেন - সবকিছুই আপনার মেশিনে স্থানীয়ভাবে চলবে।

---

## 📚 শেখার লক্ষ্য

এই কর্মশালা সম্পন্ন করার মাধ্যমে আপনি সক্ষম হবেন:

### মূল দক্ষতা
1. **স্থানীয় AI সার্ভিস ডিপ্লয় এবং ম্যানেজ করুন**
   - Microsoft Foundry Local ইনস্টল এবং কনফিগার করুন
   - এজ ডিপ্লয়মেন্টের জন্য উপযুক্ত মডেল নির্বাচন করুন
   - মডেল লাইফসাইকেল পরিচালনা করুন (ডাউনলোড, লোড, ক্যাশ)
   - রিসোর্স ব্যবহার পর্যবেক্ষণ করুন এবং পারফরম্যান্স অপ্টিমাইজ করুন

2. **AI-চালিত অ্যাপ্লিকেশন তৈরি করুন**
   - স্থানীয়ভাবে OpenAI-সামঞ্জস্যপূর্ণ চ্যাট কমপ্লিশন বাস্তবায়ন করুন
   - Small Language Models-এর জন্য কার্যকর প্রম্পট ডিজাইন করুন
   - স্ট্রিমিং রেসপন্স পরিচালনা করুন আরও ভালো UX-এর জন্য
   - বিদ্যমান অ্যাপ্লিকেশনে স্থানীয় মডেল ইন্টিগ্রেট করুন

3. **RAG (Retrieval Augmented Generation) সিস্টেম তৈরি করুন**
   - এম্বেডিংস ব্যবহার করে সেমান্টিক সার্চ তৈরি করুন
   - LLM রেসপন্সকে ডোমেইন-নির্দিষ্ট জ্ঞানে ভিত্তি দিন
   - ইন্ডাস্ট্রি-স্ট্যান্ডার্ড মেট্রিক্স দিয়ে RAG গুণমান মূল্যায়ন করুন
   - প্রোটোটাইপ থেকে প্রোডাকশনে স্কেল করুন

4. **মডেল পারফরম্যান্স অপ্টিমাইজ করুন**
   - আপনার ব্যবহারের ক্ষেত্রে একাধিক মডেল বেঞ্চমার্ক করুন
   - লেটেন্সি, থ্রুপুট এবং ফার্স্ট-টোকেন টাইম পরিমাপ করুন
   - স্পিড/কোয়ালিটি ট্রেডঅফের ভিত্তিতে অপ্টিমাল মডেল নির্বাচন করুন
   - বাস্তব পরিস্থিতিতে SLM বনাম LLM ট্রেডঅফ তুলনা করুন

5. **মাল্টি-এজেন্ট সিস্টেম অর্কেস্ট্রেট করুন**
   - বিভিন্ন কাজের জন্য বিশেষ এজেন্ট ডিজাইন করুন
   - এজেন্ট মেমরি এবং কনটেক্সট ম্যানেজমেন্ট বাস্তবায়ন করুন
   - জটিল ওয়ার্কফ্লোতে এজেন্ট সমন্বয় করুন
   - একাধিক মডেলের মধ্যে বুদ্ধিমত্তার সাথে রিকোয়েস্ট রাউট করুন

6. **প্রোডাকশন-রেডি সলিউশন ডিপ্লয় করুন**
   - এরর হ্যান্ডলিং এবং রিট্রাই লজিক বাস্তবায়ন করুন
   - টোকেন ব্যবহার এবং সিস্টেম রিসোর্স পর্যবেক্ষণ করুন
   - মডেল-অ্যাজ-টুলস প্যাটার্ন দিয়ে স্কেলেবল আর্কিটেকচার তৈরি করুন
   - এজ থেকে হাইব্রিড (এজ + ক্লাউড) মাইগ্রেশন পরিকল্পনা করুন

---

## 🎓 শেখার ফলাফল

### আপনি যা তৈরি করবেন

কর্মশালার শেষে, আপনি তৈরি করবেন:

| সেশন | ডেলিভারেবল | প্রদর্শিত দক্ষতা |
|------|-------------|------------------|
| **১** | স্ট্রিমিং সহ চ্যাট অ্যাপ্লিকেশন | সার্ভিস সেটআপ, বেসিক কমপ্লিশন, স্ট্রিমিং UX |
| **২** | মূল্যায়ন সহ RAG সিস্টেম | এম্বেডিংস, সেমান্টিক সার্চ, গুণমান মেট্রিক্স |
| **৩** | মাল্টি-মডেল বেঞ্চমার্ক স্যুট | পারফরম্যান্স পরিমাপ, মডেল তুলনা |
| **৪** | SLM বনাম LLM তুলনা | ট্রেড-অফ বিশ্লেষণ, অপ্টিমাইজেশন কৌশল |
| **৫** | মাল্টি-এজেন্ট অর্কেস্ট্রেটর | এজেন্ট ডিজাইন, মেমরি ম্যানেজমেন্ট, সমন্বয় |
| **৬** | বুদ্ধিমান রাউটিং সিস্টেম | ইন্টেন্ট ডিটেকশন, মডেল নির্বাচন, স্কেলেবিলিটি |

### দক্ষতার ম্যাট্রিক্স

| দক্ষতার স্তর | সেশন ১-২ | সেশন ৩-৪ | সেশন ৫-৬ |
|---------------|-----------|-----------|-----------|
| **শুরু** | ✅ সেটআপ ও বেসিক | ⚠️ চ্যালেঞ্জিং | ❌ খুবই উন্নত |
| **মধ্যম** | ✅ দ্রুত পর্যালোচনা | ✅ মূল শেখা | ⚠️ স্ট্রেচ লক্ষ্য |
| **উন্নত** | ✅ সহজে সম্পন্ন | ✅ পরিমার্জন | ✅ প্রোডাকশন প্যাটার্ন |

### ক্যারিয়ার-রেডি দক্ষতা

**এই কর্মশালার পরে, আপনি প্রস্তুত থাকবেন:**

✅ **গোপনীয়তা-প্রথম অ্যাপ্লিকেশন তৈরি করতে**
- স্বাস্থ্যসেবা অ্যাপ যা স্থানীয়ভাবে PHI/PII পরিচালনা করে
- সম্মতি প্রয়োজনীয়তা সহ আর্থিক পরিষেবা
- ডেটা সার্বভৌমত্বের প্রয়োজনীয়তা সহ সরকারি সিস্টেম

✅ **এজ পরিবেশের জন্য অপ্টিমাইজ করতে**
- সীমিত রিসোর্স সহ IoT ডিভাইস
- অফলাইন-প্রথম মোবাইল অ্যাপ্লিকেশন
- লো-লেটেন্সি রিয়েল-টাইম সিস্টেম

✅ **বুদ্ধিমান আর্কিটেকচার ডিজাইন করতে**
- জটিল ওয়ার্কফ্লোর জন্য মাল্টি-এজেন্ট সিস্টেম
- হাইব্রিড এজ-ক্লাউড ডিপ্লয়মেন্ট
- খরচ-অপ্টিমাইজড AI অবকাঠামো

✅ **এজ এআই উদ্যোগ পরিচালনা করতে**
- প্রকল্পের জন্য এজ এআই সম্ভাব্যতা মূল্যায়ন করুন
- উপযুক্ত মডেল এবং ফ্রেমওয়ার্ক নির্বাচন করুন
- স্কেলেবল স্থানীয় AI সমাধান আর্কিটেক্ট করুন

---

## 🗺️ কর্মশালার কাঠামো

### সেশন ওভারভিউ (৬ সেশন × ৩০ মিনিট = ৩ ঘণ্টা)

| সেশন | বিষয় | ফোকাস | সময়কাল |
|------|-------|-------|---------|
| **১** | Foundry Local দিয়ে শুরু | ইনস্টল, যাচাই, প্রথম কমপ্লিশন | ৩০ মিনিট |
| **২** | RAG দিয়ে AI সমাধান তৈরি | প্রম্পট ইঞ্জিনিয়ারিং, এম্বেডিংস, মূল্যায়ন | ৩০ মিনিট |
| **৩** | ওপেন সোর্স মডেল | মডেল আবিষ্কার, বেঞ্চমার্কিং, নির্বাচন | ৩০ মিনিট |
| **৪** | আধুনিক মডেল | SLM বনাম LLM, অপ্টিমাইজেশন, ফ্রেমওয়ার্ক | ৩০ মিনিট |
| **৫** | AI-চালিত এজেন্ট | এজেন্ট ডিজাইন, অর্কেস্ট্রেশন, মেমরি | ৩০ মিনিট |
| **৬** | মডেল-অ্যাজ-টুলস | রাউটিং, চেইনিং, স্কেলিং কৌশল | ৩০ মিনিট |

---

## 🚀 দ্রুত শুরু

### প্রয়োজনীয়তা

**সিস্টেমের প্রয়োজনীয়তা:**
- **OS**: Windows 10/11, macOS 11+, অথবা Linux (Ubuntu 20.04+)
- **RAM**: ন্যূনতম ৮GB, সুপারিশকৃত ১৬GB+
- **স্টোরেজ**: মডেলের জন্য ১০GB+ ফ্রি স্পেস
- **CPU**: আধুনিক প্রসেসর AVX2 সাপোর্ট সহ
- **GPU** (ঐচ্ছিক): CUDA-সামঞ্জস্যপূর্ণ অথবা Qualcomm NPU অ্যাক্সিলারেশনের জন্য

**সফটওয়্যার প্রয়োজনীয়তা:**
- **Python 3.8+** ([ডাউনলোড](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([ইনস্টলেশন গাইড](../../../Workshop))
- **Git** ([ডাউনলোড](https://git-scm.com/downloads))
- **Visual Studio Code** (সুপারিশকৃত) ([ডাউনলোড](https://code.visualstudio.com/))

### ৩ ধাপে সেটআপ

#### ১. Foundry Local ইনস্টল করুন

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**ইনস্টলেশন যাচাই করুন:**
```bash
foundry --version
foundry service status
```

**নিশ্চিত করুন Azure AI Foundry Local একটি নির্দিষ্ট পোর্টে চলছে**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**যাচাই করুন এটি কাজ করছে:**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**উপলব্ধ মডেল খুঁজে পাওয়া**
আপনার Foundry Local ইনস্ট্যান্সে কোন মডেলগুলি উপলব্ধ তা দেখতে, আপনি মডেল এন্ডপয়েন্টে প্রশ্ন করতে পারেন:

```bash
# cmd/bash/powershell
foundry model list
```

ওয়েব এন্ডপয়েন্ট ব্যবহার করে 

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### ২. রিপোজিটরি ক্লোন করুন এবং ডিপেনডেন্সি ইনস্টল করুন

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

#### ৩. আপনার প্রথম নমুনা চালান

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples/session01
python chat_bootstrap.py "What is edge AI?"
```

**✅ সফল!** আপনি এজ AI সম্পর্কে একটি স্ট্রিমিং রেসপন্স দেখতে পাবেন।

---

## 📦 কর্মশালার রিসোর্স

### Python নমুনা

প্রতিটি ধারণা প্রদর্শনকারী প্রগতিশীল হাতে-কলমে উদাহরণ:

| সেশন | নমুনা | বিবরণ | রান টাইম |
|------|-------|-------|----------|
| ১ | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | বেসিক ও স্ট্রিমিং চ্যাট | ~৩০ সেকেন্ড |
| ২ | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | এম্বেডিংস সহ RAG | ~৪৫ সেকেন্ড |
| ২ | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | RAG গুণমান মূল্যায়ন | ~৬০ সেকেন্ড |
| ৩ | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | মাল্টি-মডেল বেঞ্চমার্কিং | ~২-৩ মিনিট |
| ৪ | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | SLM বনাম LLM তুলনা | ~৪৫ সেকেন্ড |
| ৫ | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | মাল্টি-এজেন্ট সিস্টেম | ~৬০ সেকেন্ড |
| ৬ | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | ইন্টেন্ট-ভিত্তিক রাউটিং | ~৪৫ সেকেন্ড |
| ৬ | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | মাল্টি-স্টেপ পাইপলাইন | ~৬০ সেকেন্ড |

### Jupyter নোটবুক

ব্যাখ্যা এবং ভিজ্যুয়ালাইজেশনের সাথে ইন্টারঅ্যাকটিভ এক্সপ্লোরেশন:

| সেশন | নোটবুক | বিবরণ | কঠিনতা |
|------|--------|-------|--------|
| ১ | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | চ্যাট বেসিক ও স্ট্রিমিং | ⭐ শুরু |
| ২ | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline.ipynb) | RAG সিস্টেম তৈরি করুন | ⭐⭐ মধ্যম |
| ২ | [`session02_rag_eval_ragas.ipynb`](./notebooks/session02_rag_eval_ragas.ipynb) | RAG গুণমান মূল্যায়ন করুন | ⭐⭐ মধ্যম |
| ৩ | [`session03_benchmark_oss_models.ipynb`](./notebooks/session03_benchmark_oss_models.ipynb) | মডেল বেঞ্চমার্কিং | ⭐⭐ মধ্যম |
| ৪ | [`session04_model_compare.ipynb`](./notebooks/session04_model_compare.ipynb) | মডেল তুলনা | ⭐⭐ মধ্যম |
| ৫ | [`session05_agents_orchestrator.ipynb`](./notebooks/session05_agents_orchestrator.ipynb) | এজেন্ট অর্কেস্ট্রেশন | ⭐⭐⭐ উন্নত |
| ৬ | [`session06_models_router.ipynb`](./notebooks/session06_models_router.ipynb) | ইন্টেন্ট রাউটিং | ⭐⭐⭐ উন্নত |
| ৬ | [`session06_models_pipeline.ipynb`](./notebooks/session06_models_pipeline.ipynb) | পাইপলাইন অর্কেস্ট্রেশন | ⭐⭐⭐ উন্নত |

### ডকুমেন্টেশন

সম্পূর্ণ গাইড এবং রেফারেন্স:

| ডকুমেন্ট | বিবরণ | কখন ব্যবহার করবেন |
|----------|-------|-------------------|
| [QUICK_START.md](./QUICK_START.md) | দ্রুত সেটআপ গাইড | শুরু থেকে |
| [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) | কমান্ড ও API চিট শিট | দ্রুত উত্তর প্রয়োজন |
| [FOUNDRY_SDK_QUICKREF.md](./FOUNDRY_SDK_QUICKREF.md) | SDK প্যাটার্ন ও উদাহরণ | কোড লিখতে |
| [ENV_CONFIGURATION.md](./ENV_CONFIGURATION.md) | পরিবেশ ভেরিয়েবল গাইড | নমুনা কনফিগার করতে |
| [SAMPLES_UPDATE_SUMMARY.md](./SAMPLES_UPDATE_SUMMARY.md) | সর্বশেষ নমুনা উন্নতি | পরিবর্তন বুঝতে |
| [SDK_MIGRATION_NOTES.md](./SDK_MIGRATION_NOTES.md) | মাইগ্রেশন গাইড | কোড আপগ্রেড করতে |
| [notebooks/TROUBLESHOOTING.md](./notebooks/TROUBLESHOOTING.md) | সাধারণ সমস্যা ও সমাধান | সমস্যা সমাধান করতে |

---

## 🎓 শেখার পথের সুপারিশ

### শুরুদের জন্য (৩-৪ ঘণ্টা)
1. ✅ সেশন ১: শুরু করুন (সেটআপ এবং বেসিক চ্যাটে ফোকাস)
2. ✅ সেশন ২: RAG বেসিক (মূল্যায়ন প্রথমে বাদ দিন)
3. ✅ সেশন ৩: সহজ বেঞ্চমার্কিং (শুধু ২টি মডেল)
4. ⏭️ সেশন ৪-৬ আপাতত বাদ দিন
5. 🔄 প্রথম অ্যাপ্লিকেশন তৈরি করার পরে সেশন ৪-৬-এ ফিরে আসুন

### মধ্যম ডেভেলপারদের জন্য (৩ ঘণ্টা)
1. ⚡ সেশন ১: দ্রুত সেটআপ যাচাই
2. ✅ সেশন ২: সম্পূর্ণ RAG পাইপলাইন মূল্যায়ন সহ
3. ✅ সেশন ৩: সম্পূর্ণ বেঞ্চমার্কিং স্যুট
4. ✅ সেশন ৪: মডেল অপ্টিমাইজেশন
5. ✅ সেশন ৫-৬: আর্কিটেকচার প্যাটার্নে ফোকাস

### উন্নত প্র্যাকটিশনারদের জন্য (২-৩ ঘণ্টা)
1. ⚡ সেশন ১-৩: দ্রুত পর্যালোচনা এবং যাচাই
2. ✅ সেশন ৪: অপ্টিমাইজেশনে গভীরভাবে
3. ✅ সেশন ৫: মাল্ট
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | SLM বনাম LLM, WebGPU, Chainlit RAG, ONNX ত্বরান্বিতকরণ |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | এজেন্ট ভূমিকা, মেমরি, টুলস, অর্কেস্ট্রেশন |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | রাউটিং, চেইনিং, Azure-এ স্কেলিং পথ |

প্রতিটি সেশন ফাইল অন্তর্ভুক্ত করে: সারাংশ, শেখার লক্ষ্য, ৩০-মিনিটের ডেমো প্রবাহ, স্টার্টার প্রকল্প, যাচাইকরণ চেকলিস্ট, সমস্যা সমাধান, এবং অফিসিয়াল Foundry Local Python SDK-এর রেফারেন্স।

### নমুনা স্ক্রিপ্ট

ওয়ার্কশপ ডিপেন্ডেন্সি ইনস্টল করুন (Windows):

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

যদি Foundry Local সার্ভিস macOS থেকে ভিন্ন (Windows) মেশিন বা VM-এ চালানো হয়, তাহলে এন্ডপয়েন্ট এক্সপোর্ট করুন:

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| সেশন | স্ক্রিপ্ট(গুলি) | বিবরণ |
|---------|-----------|-------------|
| 1 | `samples/session01/chat_bootstrap.py` | সার্ভিস বুটস্ট্র্যাপ এবং স্ট্রিমিং চ্যাট |
| 2 | `samples/session02/rag_pipeline.py` | মিনিমাল RAG (ইন-মেমরি এম্বেডিংস) |
|   | `samples/session02/rag_eval_ragas.py` | RAG মূল্যায়ন ragas মেট্রিক্স সহ |
| 3 | `samples/session03/benchmark_oss_models.py` | মাল্টি-মডেল লেটেন্সি এবং থ্রুপুট বেঞ্চমার্কিং |
| 4 | `samples/session04/model_compare.py` | SLM বনাম LLM তুলনা (লেটেন্সি এবং নমুনা আউটপুট) |
| 5 | `samples/session05/agents_orchestrator.py` | দুই এজেন্ট গবেষণা → সম্পাদকীয় পাইপলাইন |
| 6 | `samples/session06/models_router.py` | ইন্টেন্ট-ভিত্তিক রাউটিং ডেমো |
|   | `samples/session06/models_pipeline.py` | মাল্টি-স্টেপ পরিকল্পনা/নির্বাহ/পরিমার্জন চেইন |

### পরিবেশ ভেরিয়েবল (নমুনাগুলির জন্য সাধারণ)

| ভেরিয়েবল | উদ্দেশ্য | উদাহরণ |
|----------|---------|---------|
| `FOUNDRY_LOCAL_ALIAS` | বেসিক নমুনার জন্য ডিফল্ট একক মডেল এলিয়াস | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | তুলনার জন্য স্পষ্ট SLM বনাম বড় মডেল | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | বেঞ্চমার্কের জন্য এলিয়াসের কমা তালিকা | `qwen2.5-0.5b,gemma-2-2b,mistral-7b` |
| `BENCH_ROUNDS` | প্রতি মডেলের বেঞ্চমার্ক পুনরাবৃত্তি | `3` |
| `BENCH_PROMPT` | বেঞ্চমার্কিংয়ে ব্যবহৃত প্রম্পট | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | সেন্টেন্স-ট্রান্সফর্মার এম্বেডিং মডেল | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | RAG পাইপলাইনের জন্য টেস্ট কোয়েরি ওভাররাইড | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | এজেন্ট পাইপলাইনের জন্য কোয়েরি ওভাররাইড | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | গবেষণা এজেন্টের জন্য মডেল এলিয়াস | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | সম্পাদক এজেন্টের জন্য মডেল এলিয়াস (ভিন্ন হতে পারে) | `gpt-oss-20b` |
| `SHOW_USAGE` | যখন `1`, প্রতি সম্পন্নকরণে টোকেন ব্যবহার প্রিন্ট করে | `1` |
| `RETRY_ON_FAIL` | যখন `1`, ট্রানজিয়েন্ট চ্যাট ত্রুটিতে একবার পুনরায় চেষ্টা করে | `1` |
| `RETRY_BACKOFF` | পুনরায় চেষ্টা করার আগে অপেক্ষার সময় (সেকেন্ড) | `1.0` |

যদি কোনো ভেরিয়েবল সেট না করা হয়, স্ক্রিপ্টগুলি সংবেদনশীল ডিফল্টে ফিরে যায়। একক-মডেল ডেমোর জন্য সাধারণত শুধুমাত্র `FOUNDRY_LOCAL_ALIAS` প্রয়োজন।

### ইউটিলিটি মডিউল

সব নমুনা এখন একটি হেল্পার `samples/workshop_utils.py` শেয়ার করে যা প্রদান করে:

* ক্যাশড `FoundryLocalManager` + OpenAI ক্লায়েন্ট তৈরি
* `chat_once()` হেল্পার ঐচ্ছিক পুনরায় চেষ্টা + ব্যবহার প্রিন্টিং সহ
* সহজ টোকেন ব্যবহার রিপোর্টিং (`SHOW_USAGE=1` দ্বারা সক্রিয় করুন)

এটি পুনরাবৃত্তি কমায় এবং দক্ষ স্থানীয় মডেল অর্কেস্ট্রেশনের জন্য সেরা অনুশীলনগুলি তুলে ধরে।

## ঐচ্ছিক উন্নতি (ক্রস-সেশন)

| থিম | উন্নতি | সেশন | পরিবেশ / টগল |
|-------|-------------|----------|--------------|
| নির্ধারকতা | নির্দিষ্ট তাপমাত্রা + স্থিতিশীল প্রম্পট সেট | ১–৬ | `temperature=0`, `top_p=1` সেট করুন |
| টোকেন ব্যবহার দৃশ্যমানতা | ধারাবাহিক খরচ/দক্ষতা শিক্ষা | ১–৬ | `SHOW_USAGE=1` |
| স্ট্রিমিং প্রথম টোকেন | উপলব্ধি করা লেটেন্সি মেট্রিক | ১,৩,৪,৬ | `BENCH_STREAM=1` (বেঞ্চমার্ক) |
| পুনরায় চেষ্টা স্থিতিস্থাপকতা | ট্রানজিয়েন্ট কোল্ড-স্টার্ট পরিচালনা করে | সব | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| মাল্টি-মডেল এজেন্ট | হেটেরোজেনিয়াস ভূমিকা বিশেষীকরণ | ৫ | `AGENT_MODEL_PRIMARY`, `AGENT_MODEL_EDITOR` |
| অভিযোজিত রাউটিং | ইন্টেন্ট + খরচ হিউরিস্টিক্স | ৬ | রাউটারকে এসকেলেশন লজিক দিয়ে প্রসারিত করুন |
| ভেক্টর মেমরি | দীর্ঘমেয়াদী সেমান্টিক রিকল | ২,৫,৬ | FAISS/Chroma এম্বেডিং ইনডেক্স ইন্টিগ্রেট করুন |
| ট্রেস এক্সপোর্ট | অডিটিং এবং মূল্যায়ন | ২,৫,৬ | প্রতি ধাপে JSON লাইন যোগ করুন |
| গুণমান রুব্রিক্স | গুণগত ট্র্যাকিং | ৩–৬ | সেকেন্ডারি স্কোরিং প্রম্পট |
| স্মোক টেস্ট | দ্রুত ওয়ার্কশপ যাচাইকরণ | সব | `python Workshop/tests/smoke.py` |

### নির্ধারক দ্রুত শুরু

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

একই ইনপুট বারবার দিলে স্থিতিশীল টোকেন সংখ্যা আশা করুন।

### RAG মূল্যায়ন (সেশন ২)

`rag_eval_ragas.py` ব্যবহার করে একটি ছোট সিন্থেটিক ডেটাসেটে উত্তর প্রাসঙ্গিকতা, বিশ্বাসযোগ্যতা, এবং প্রসঙ্গ নির্ভুলতা গণনা করুন:

```powershell
python samples/session02/rag_eval_ragas.py
```

প্রশ্ন, প্রসঙ্গ, এবং গ্রাউন্ড ট্রুথের একটি বড় JSONL সরবরাহ করে প্রসারিত করুন, তারপর এটি Hugging Face `Dataset`-এ রূপান্তর করুন।

## CLI কমান্ড সঠিকতা সংযোজন

ওয়ার্কশপ ইচ্ছাকৃতভাবে শুধুমাত্র বর্তমানে ডকুমেন্টেড / স্থিতিশীল Foundry Local CLI কমান্ড ব্যবহার করে।

### উল্লেখিত স্থিতিশীল কমান্ড

| বিভাগ | কমান্ড | উদ্দেশ্য |
|----------|---------|---------|
| কোর | `foundry --version` | ইনস্টল করা সংস্করণ দেখান |
| কোর | `foundry init` | কনফিগারেশন আরম্ভ করুন |
| সার্ভিস | `foundry service start` | স্থানীয় সার্ভিস শুরু করুন (যদি স্বয়ংক্রিয় না হয়) |
| সার্ভিস | `foundry status` | সার্ভিস স্ট্যাটাস দেখান |
| মডেল | `foundry model list` | ক্যাটালগ / উপলব্ধ মডেল তালিকা |
| মডেল | `foundry model download <alias>` | মডেল ওজন ক্যাশে ডাউনলোড করুন |
| মডেল | `foundry model run <alias>` | একটি মডেল স্থানীয়ভাবে চালু করুন; এক-শটের জন্য `--prompt` এর সাথে সংযুক্ত করুন |
| মডেল | `foundry model unload <alias>` / `foundry model stop <alias>` | মেমরি থেকে একটি মডেল আনলোড করুন (যদি সমর্থিত হয়) |
| ক্যাশে | `foundry cache list` | ক্যাশে করা (ডাউনলোড করা) মডেল তালিকা |
| সিস্টেম | `foundry system info` | হার্ডওয়্যার এবং ত্বরান্বিত করার ক্ষমতার স্ন্যাপশট |
| সিস্টেম | `foundry system gpu-info` | GPU ডায়াগনস্টিক তথ্য |
| কনফিগ | `foundry config list` | বর্তমান কনফিগ মান দেখান |
| কনফিগ | `foundry config set <key> <value>` | কনফিগারেশন আপডেট করুন |

### এক-শট প্রম্পট প্যাটার্ন

অপ্রচলিত `model chat` সাবকমান্ডের পরিবর্তে ব্যবহার করুন:

```powershell
foundry model run <alias> --prompt "Your question here"
```

এটি একটি একক প্রম্পট/প্রতিক্রিয়া চক্র সম্পাদন করে তারপর প্রস্থান করে।

### অপসারণ করা / এড়ানো প্যাটার্ন

| অপ্রচলিত / অপ্রকাশিত | প্রতিস্থাপন / নির্দেশিকা |
|---------------------------|------------------------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | সাধারণ `foundry model list` + সাম্প্রতিক কার্যকলাপ / লগ |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | বেঞ্চমার্ক Python স্ক্রিপ্ট + OS টুলস (Task Manager / `nvidia-smi`) |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### বেঞ্চমার্কিং এবং টেলিমেট্রি

- লেটেন্সি, p95, টোকেন/সেকেন্ড: `samples/session03/benchmark_oss_models.py`
- প্রথম-টোকেন লেটেন্সি (স্ট্রিমিং): `BENCH_STREAM=1` সেট করুন
- রিসোর্স ব্যবহার: OS মনিটর (Task Manager, Activity Monitor, `nvidia-smi`) + `foundry system info`।

যখন নতুন CLI টেলিমেট্রি কমান্ড আপস্ট্রিমে স্থিতিশীল হয়, সেগুলি সামান্য সম্পাদনা সহ সেশন মার্কডাউনগুলিতে অন্তর্ভুক্ত করা যেতে পারে।

### স্বয়ংক্রিয় লিন্ট গার্ড

একটি স্বয়ংক্রিয় লিন্টার মার্কডাউন ফাইলের fenced কোড ব্লকের ভিতরে অপ্রচলিত CLI প্যাটার্ন পুনঃপ্রবর্তন প্রতিরোধ করে:

স্ক্রিপ্ট: `Workshop/scripts/lint_markdown_cli.py`

অপ্রচলিত প্যাটার্নগুলি কোড ফেন্সের ভিতরে ব্লক করা হয়।

প্রস্তাবিত প্রতিস্থাপন:
| অপ্রচলিত | প্রতিস্থাপন |
|------------|-------------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | বেঞ্চমার্ক স্ক্রিপ্ট + সিস্টেম টুলস |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

স্থানীয়ভাবে চালান:
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

GitHub Action: `.github/workflows/markdown-cli-lint.yml` প্রতি পুশ এবং PR-এ চালানো হয়।

ঐচ্ছিক প্রি-কমিট হুক:
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## দ্রুত CLI → SDK মাইগ্রেশন টেবিল

| কাজ | CLI এক-লাইনার | SDK (Python) সমতুল্য | নোট |
|------|---------------|-------------------------|-------|
| একটি মডেল একবার চালান (প্রম্পট) | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK স্বয়ংক্রিয়ভাবে সার্ভিস এবং ক্যাশিং বুটস্ট্র্যাপ করে |
| মডেল ডাউনলোড (ক্যাশে) | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # triggers download/load` | ম্যানেজার সেরা ভেরিয়েন্ট বেছে নেয় যদি এলিয়াস একাধিক বিল্ডে ম্যাপ করে |
| ক্যাটালগ তালিকা | `foundry model list` | `# use manager for each alias or maintain known list` | CLI একত্রিত করে; SDK বর্তমানে প্রতি-এলিয়াস ইনস্ট্যান্সিয়েশন |
| ক্যাশে করা মডেল তালিকা | `foundry cache list` | `manager.list_cached_models()` | ম্যানেজার আরম্ভের পরে (যেকোনো এলিয়াস) |
| GPU ত্বরান্বিতকরণ সক্ষম করুন | `foundry config set compute.onnx.enable_gpu true` | `# CLI action; SDK assumes config already applied` | কনফিগারেশন বাহ্যিক পার্শ্বপ্রভাব |
| এন্ডপয়েন্ট URL পান | (অস্পষ্ট) | `manager.endpoint` | OpenAI-সামঞ্জস্যপূর্ণ ক্লায়েন্ট তৈরি করতে ব্যবহৃত |
| একটি মডেল উষ্ণ করুন | `foundry model run <alias>` তারপর প্রথম প্রম্পট | `chat_once(alias, messages=[...])` (ইউটিলিটি) | ইউটিলিটি প্রাথমিক কোল্ড লেটেন্সি ওয়ার্মআপ পরিচালনা করে |
| লেটেন্সি পরিমাপ করুন | `python benchmark_oss_models.py` | `import benchmark_oss_models` (বা নতুন এক্সপোর্টার স্ক্রিপ্ট) | ধারাবাহিক মেট্রিকের জন্য স্ক্রিপ্ট পছন্দ করুন |
| মডেল বন্ধ / আনলোড করুন | `foundry model unload <alias>` | (প্রকাশিত নয় – সার্ভিস / প্রক্রিয়া পুনরায় চালু করুন) | সাধারণত ওয়ার্কশপ প্রবাহের জন্য প্রয়োজন হয় না |
| টোকেন ব্যবহার পুনরুদ্ধার করুন | (আউটপুট দেখুন) | `resp.usage.total_tokens` | যদি ব্যাকএন্ড ব্যবহার অবজেক্ট প্রদান করে |

## বেঞ্চমার্ক মার্কডাউন এক্সপোর্ট

একটি নতুন বেঞ্চমার্ক চালানোর জন্য স্ক্রিপ্ট `Workshop/scripts/export_benchmark_markdown.py` ব্যবহার করুন (একই লজিক `samples/session03/benchmark_oss_models.py` হিসাবে) এবং একটি GitHub-বন্ধুত্বপূর্ণ মার্কডাউন টেবিল এবং কাঁচা JSON প্রকাশ করুন।

### উদাহরণ

```powershell
python Workshop\scripts\export_benchmark_markdown.py --models "qwen2.5-0.5b,gemma-2-2b,mistral-7b" --prompt "Explain retrieval augmented generation briefly." --rounds 3 --output benchmark_report.md
```

জেনারেট করা ফাইল:
| ফাইল | বিষয়বস্তু |
|------|----------|
| `benchmark_report.md` | মার্কডাউন টেবিল + ব্যাখ্যা ইঙ্গিত |
| `benchmark_report.json` | কাঁচা মেট্রিক্স অ্যারে (ডিফিং / প্রবণতা ট্র্যাকিংয়ের জন্য) |

পরিবেশে `BENCH_STREAM=1` সেট করুন যদি প্রথম-টোকেন লেটেন্সি অন্তর্ভুক্ত করা সমর্থিত হয়।

---

**অস্বীকৃতি**:  
এই নথিটি AI অনুবাদ পরিষেবা [Co-op Translator](https://github.com/Azure/co-op-translator) ব্যবহার করে অনুবাদ করা হয়েছে। আমরা যথাসাধ্য সঠিকতা নিশ্চিত করার চেষ্টা করি, তবে অনুগ্রহ করে মনে রাখবেন যে স্বয়ংক্রিয় অনুবাদে ত্রুটি বা অসঙ্গতি থাকতে পারে। মূল ভাষায় থাকা নথিটিকে প্রামাণিক উৎস হিসেবে বিবেচনা করা উচিত। গুরুত্বপূর্ণ তথ্যের জন্য, পেশাদার মানব অনুবাদ সুপারিশ করা হয়। এই অনুবাদ ব্যবহারের ফলে কোনো ভুল বোঝাবুঝি বা ভুল ব্যাখ্যা হলে আমরা দায়বদ্ধ থাকব না।