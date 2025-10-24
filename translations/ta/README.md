<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8f958250b0b94976c721e6cbdc541581",
  "translation_date": "2025-10-24T10:11:32+00:00",
  "source_file": "README.md",
  "language_code": "ta"
}
-->
# EdgeAI ஆரம்பக்கட்ட பயிற்சி

![பாடநெறி அட்டைப்படம்](../../translated_images/cover.eb18d1b9605d754b30973f4e17c6e11ea4f8473d9686ee378d6e7b44e3c70ac7.ta.png)

[![GitHub contributors](https://img.shields.io/github/contributors/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/graphs/contributors)
[![GitHub issues](https://img.shields.io/github/issues/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/issues)
[![GitHub pull-requests](https://img.shields.io/github/issues-pr/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/pulls)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

[![GitHub watchers](https://img.shields.io/github/watchers/microsoft/edgeai-for-beginners.svg?style=social&label=Watch)](https://GitHub.com/microsoft/edgeai-for-beginners/watchers)
[![GitHub forks](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)
[![GitHub stars](https://img.shields.io/github/stars/microsoft/edgeai-for-beginners?style=social&label=Star)](https://GitHub.com/microsoft/edgeai-for-beginners/stargazers)

[![Microsoft Azure AI Foundry Discord](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://discord.com/invite/ByRwuEEgH4)

இந்த வளங்களை பயன்படுத்த தொடங்க கீழே உள்ள படிகளை பின்பற்றவும்:

1. **Repository-ஐ Fork செய்யவும்**: கிளிக் செய்யவும் [![GitHub forks](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)
2. **Repository-ஐ Clone செய்யவும்**: `git clone https://github.com/microsoft/edgeai-for-beginners.git`
3. [**Azure AI Foundry Discord-ஐ சேர்ந்து நிபுணர்களையும் மற்ற டெவலப்பர்களையும் சந்திக்கவும்**](https://discord.com/invite/ByRwuEEgH4)

### 🌐 பல மொழி ஆதரவு

#### GitHub Action மூலம் ஆதரவு (தானியங்கி மற்றும் எப்போதும் புதுப்பிக்கப்பட்டது)

<!-- CO-OP TRANSLATOR LANGUAGES TABLE START -->
[Arabic](../ar/README.md) | [Bengali](../bn/README.md) | [Bulgarian](../bg/README.md) | [Burmese (Myanmar)](../my/README.md) | [Chinese (Simplified)](../zh/README.md) | [Chinese (Traditional, Hong Kong)](../hk/README.md) | [Chinese (Traditional, Macau)](../mo/README.md) | [Chinese (Traditional, Taiwan)](../tw/README.md) | [Croatian](../hr/README.md) | [Czech](../cs/README.md) | [Danish](../da/README.md) | [Dutch](../nl/README.md) | [Estonian](../et/README.md) | [Finnish](../fi/README.md) | [French](../fr/README.md) | [German](../de/README.md) | [Greek](../el/README.md) | [Hebrew](../he/README.md) | [Hindi](../hi/README.md) | [Hungarian](../hu/README.md) | [Indonesian](../id/README.md) | [Italian](../it/README.md) | [Japanese](../ja/README.md) | [Korean](../ko/README.md) | [Lithuanian](../lt/README.md) | [Malay](../ms/README.md) | [Marathi](../mr/README.md) | [Nepali](../ne/README.md) | [Norwegian](../no/README.md) | [Persian (Farsi)](../fa/README.md) | [Polish](../pl/README.md) | [Portuguese (Brazil)](../br/README.md) | [Portuguese (Portugal)](../pt/README.md) | [Punjabi (Gurmukhi)](../pa/README.md) | [Romanian](../ro/README.md) | [Russian](../ru/README.md) | [Serbian (Cyrillic)](../sr/README.md) | [Slovak](../sk/README.md) | [Slovenian](../sl/README.md) | [Spanish](../es/README.md) | [Swahili](../sw/README.md) | [Swedish](../sv/README.md) | [Tagalog (Filipino)](../tl/README.md) | [Tamil](./README.md) | [Thai](../th/README.md) | [Turkish](../tr/README.md) | [Ukrainian](../uk/README.md) | [Urdu](../ur/README.md) | [Vietnamese](../vi/README.md)
<!-- CO-OP TRANSLATOR LANGUAGES TABLE END -->

**கூடுதல் மொழிபெயர்ப்புகளை ஆதரிக்க விரும்பினால், [இங்கே](https://github.com/Azure/co-op-translator/blob/main/getting_started/supported-languages.md) பட்டியலிடப்பட்டுள்ள மொழிகளைப் பார்க்கவும்**

## அறிமுகம்

**EdgeAI for Beginners**-க்கு வரவேற்கிறோம் – Edge Artificial Intelligence-இன் மாற்றத்திற்கான உலகில் உங்கள் விரிவான பயணம். இந்த பாடநெறி சக்திவாய்ந்த AI திறன்களுக்கும், edge சாதனங்களில் நடைமுறை, உண்மையான உலகப் பயன்பாட்டிற்கும் இடையிலான இடைவெளியை நிரப்புகிறது, AI-யின் திறன்களை நேரடியாக தரவுகள் உருவாக்கப்படும் இடத்தில் மற்றும் முடிவுகள் எடுக்க வேண்டிய இடத்தில் பயன்படுத்துவதற்கான திறனை உங்களுக்கு வழங்குகிறது.

### நீங்கள் கற்றுக்கொள்ளும் திறன்கள்

இந்த பாடநெறி அடிப்படை கருத்துக்களிலிருந்து தயாரிப்பு தயாராகும் செயல்பாடுகளுக்கு உங்களை அழைத்துச் செல்கிறது, இதில்:
- **Small Language Models (SLMs)** edge deployment-க்கு உகந்தவை
- **Hardware-aware optimization** பல்வேறு தளங்களில்
- **Real-time inference** தனியுரிமை பாதுகாப்பு திறன்களுடன்
- **Production deployment** நிறுவன பயன்பாடுகளுக்கான உத்திகள்

### EdgeAI ஏன் முக்கியம்

Edge AI முக்கியமான நவீன சவால்களை தீர்க்கும் ஒரு புதிய முறை:
- **தனியுரிமை மற்றும் பாதுகாப்பு**: தரவுகளை உள்ளூரில் செயலாக்கி, cloud-க்கு வெளிப்படாமல் பாதுகாக்கவும்
- **உடனடி செயல்திறன்**: நேரம் முக்கியமான பயன்பாடுகளுக்கு network latency-ஐ நீக்கவும்
- **செலவுக் குறைவு**: bandwidth மற்றும் cloud கணினி செலவுகளை குறைக்கவும்
- **நிலையான செயல்பாடுகள்**: network outage-களின் போது செயல்பாடுகளை பராமரிக்கவும்
- **சட்டப்பூர்வ இணக்கம்**: தரவின் உரிமை தேவைகளை பூர்த்தி செய்யவும்

### Edge AI

Edge AI என்பது AI algorithm-கள் மற்றும் மொழி மாதிரிகளை hardware-ல் உள்ளூரில் இயக்குவது, தரவுகள் உருவாக்கப்படும் இடத்திற்கு அருகில், inference-க்கு cloud வளங்களை நம்பாமல். இது latency-ஐ குறைக்கிறது, தனியுரிமையை மேம்படுத்துகிறது, மற்றும் உடனடி முடிவெடுப்பை சாத்தியமாக்குகிறது.

### முக்கியக் கொள்கைகள்:
- **On-device inference**: AI மாதிரிகள் edge சாதனங்களில் (தொலைபேசிகள், routers, microcontrollers, தொழில்துறை PCs) இயங்குகின்றன
- **Offline திறன்**: நிலையான இணைய இணைப்பின்றி செயல்படுகிறது
- **குறைந்த latency**: உடனடி பதில்கள், real-time அமைப்புகளுக்கு உகந்தவை
- **தரவு உரிமை**: முக்கியமான தரவுகளை உள்ளூரில் வைத்துக்கொண்டு, பாதுகாப்பு மற்றும் இணக்கத்தை மேம்படுத்துகிறது

### Small Language Models (SLMs)

Phi-4, Mistral-7B, மற்றும் Gemma போன்ற SLM-கள் பெரிய LLM-களின் உகந்த பதிப்புகள் – பயிற்சி அல்லது distillation மூலம்:
- **குறைந்த memory footprint**: edge சாதன memory-ஐ திறமையாக பயன்படுத்துகிறது
- **குறைந்த கணினி தேவைகள்**: CPU மற்றும் edge GPU செயல்திறனுக்கு உகந்தவை
- **விரைவான தொடக்க நேரங்கள்**: பதிலளிக்கும் பயன்பாடுகளுக்கு விரைவான initialization

இவை சக்திவாய்ந்த NLP திறன்களை திறக்கின்றன, ஆனால் கீழே உள்ள கட்டுப்பாடுகளை பூர்த்தி செய்கின்றன:
- **Embedded systems**: IoT சாதனங்கள் மற்றும் தொழில்துறை கட்டுப்படுத்திகள்
- **Mobile devices**: Smartphones மற்றும் tablets-கள் offline திறன்களுடன்
- **IoT Devices**: குறைந்த வளங்களுடன் உள்ள சென்சார்கள் மற்றும் smart சாதனங்கள்
- **Edge servers**: குறைந்த GPU வளங்களுடன் உள்ள உள்ளூர் செயலாக்க அலகுகள்
- **Personal Computers**: Desktop மற்றும் laptop deployment சூழல்கள்

## பாடநெறி தொகுதிகள் மற்றும் வழிசெலுத்தல்

| Module | தலைப்பு | கவனம் செலுத்தும் பகுதி | முக்கிய உள்ளடக்கம் | நிலை | கால அளவு |
|--------|-------|------------|-------------|--------|----------|
| [📖 00 ](./introduction.md) | [EdgeAI-க்கு அறிமுகம்](./introduction.md) | அடிப்படை மற்றும் சூழல் | EdgeAI கண்ணோட்டம் • தொழில்துறை பயன்பாடுகள் • SLM அறிமுகம் • கற்றல் நோக்கங்கள் | ஆரம்பம் | 1-2 மணி |
| [📚 01](../../Module01) | [EdgeAI அடிப்படைகள்](./Module01/README.md) | Cloud மற்றும் Edge AI ஒப்பீடு | EdgeAI அடிப்படைகள் • உண்மையான உலகக் கேஸ் ஸ்டடிகள் • செயல்படுத்தல் வழிகாட்டி • Edge Deployment | ஆரம்பம் | 3-4 மணி |
| [🧠 02](../../Module02) | [SLM மாதிரி அடிப்படைகள்](./Module02/README.md) | மாதிரி குடும்பங்கள் மற்றும் கட்டமைப்பு | Phi குடும்பம் • Qwen குடும்பம் • Gemma குடும்பம் • BitNET • μModel • Phi-Silica | ஆரம்பம் | 4-5 மணி |
| [🚀 03](../../Module03) | [SLM Deployment நடைமுறை](./Module03/README.md) | உள்ளூர் மற்றும் cloud deployment | மேம்பட்ட கற்றல் • உள்ளூர் சூழல் • Cloud Deployment | இடைநிலை | 4-5 மணி |
| [⚙️ 04](../../Module04) | [மாதிரி Optimization கருவிகள்](./Module04/README.md) | பல தள optimization | அறிமுகம் • Llama.cpp • Microsoft Olive • OpenVINO • Apple MLX • Workflow Synthesis | இடைநிலை | 5-6 மணி |
| [🔧 05](../../Module05) | [SLMOps தயாரிப்பு](./Module05/README.md) | தயாரிப்பு செயல்பாடுகள் | SLMOps அறிமுகம் • மாதிரி Distillation • Fine-tuning • தயாரிப்பு Deployment | மேம்பட்ட | 5-6 மணி |
| [🤖 06](../../Module06) | [AI Agents மற்றும் Function Calling](./Module06/README.md) | Agent frameworks மற்றும் MCP | Agent அறிமுகம் • Function Calling • Model Context Protocol | மேம்பட்ட | 4-5 மணி |
| [💻 07](../../Module07) | [தள செயல்படுத்தல்](./Module07/README.md) | பல தள மாதிரிகள் | AI கருவிகள் • Foundry Local • Windows Development | மேம்பட்ட | 3-4 மணி |
| [🏭 08](../../Module08) | [Foundry Local Toolkit](./Module08/README.md) | தயாரிப்பு தயாராகும் மாதிரிகள் | மாதிரி பயன்பாடுகள் (கீழே விவரங்களைப் பார்க்கவும்) | நிபுணர் | 8-10 மணி |

### 🏭 **Module 08: மாதிரி பயன்பாடுகள்**

- [01: REST Chat Quickstart](./Module08/samples/01/README.md)
- [02: OpenAI SDK Integration](./Module08/samples/02/README.md)
- [03: Model Discovery & Benchmarking](./Module08/samples/03/README.md)
- [04: Chainlit RAG Application](./Module08/samples/04/README.md)
- [05: Multi-Agent Orchestration](./Module08/samples/05/README.md)
- [06: Models-as-Tools Router](./Module08/samples/06/README.md)
- [07: Direct API Client](./Module08/samples/07/README.md)
- [08: Windows 11 Chat App](./Module08/samples/08/README.md)
- [09: Advanced Multi-Agent System](./Module08/samples/09/README.md)
- [10: Foundry Tools Framework](./Module08/samples/10/README.md)

### 🎓 **Workshop: கைக்கூலி கற்றல் பாதை**

தயாரிப்பு தயாராகும் செயல்பாடுகளுடன் விரிவான கைக்கூலி workshop பொருட்கள்:

- **[Workshop Guide](./Workshop/Readme.md)** - முழுமையான கற்றல் நோக்கங்கள், முடிவுகள், மற்றும் வள வழிசெலுத்தல்
- **Python மாதிரிகள்** (6 அமர்வுகள்) - சிறந்த நடைமுறைகள், பிழை கையாளுதல், மற்றும் விரிவான ஆவணங்களுடன் புதுப்பிக்கப்பட்டது
- **Jupyter Notebooks** (8 interactive) - படிப்படியாக வழிகாட்டிகள், தரவுத்திறன் மற்றும் செயல்திறன் கண்காணிப்பு
- **Session Guides** - ஒவ்வொரு workshop அமர்விற்கும் விரிவான markdown வழிகாட்டிகள்
- **Validation Tools** - குறியீட்டு தரத்தை சரிபார்க்கவும் மற்றும் smoke tests இயக்கவும்

**நீங்கள் உருவாக்குவது:**
- Streaming ஆதரவுடன் உள்ளூர் AI chat பயன்பாடுகள்
- RAG தரவுப் குழாய்கள் தரத்தினை மதிப்பீடு செய்யும் (RAGAS)
- பல மாதிரி தரவுத்திறன் மற்றும் ஒப்பீட்டு கருவிகள்
- Multi-agent orchestration அமைப்புகள்
- Task-based தேர்வுடன் புத்திசாலி மாதிரி வழிமுறைகள்

### 📊 **கற்றல் பாதை சுருக்கம்**
- **மொத்த கால அளவு**: 36-45 மணி
- **ஆரம்ப பாதை**: Modules 01-02 (7-9 மணி)  
- **இடைநிலை பாதை**: Modules 03-04 (9-11 மணி)
- **மேம்பட்ட பாதை**: Modules 05-07 (12-15 மணி)
- **நிபுணர் பாதை**: Module 08 (8-10 மணி)

## நீங்கள் உருவாக்குவது

### 🎯 முக்கிய திறன்கள்
- **Edge AI கட்டமைப்பு**: உள்ளூர்-முதல் AI அமைப்புகளை cloud இணைப்புடன் வடிவமைக்கவும்
- **மாதிரி Optimization**: Edge deployment-க்கு மாதிரிகளை Quantize மற்றும் Compress செய்யவும் (85% வேக மேம்பாடு, 75% அளவு குறைப்பு)
- **பல தள செயல்படுத்தல்**: Windows, mobile, embedded, மற்றும் cloud-edge hybrid அமைப்புகள்
- **உற்பத்தி செயல்பாடுகள்**: Edge AI-யை உற்பத்தியில் கண்காணித்தல், அளவீடு செய்தல் மற்றும் பராமரித்தல்

### 🏗️ நடைமுறை திட்டங்கள்
- **Foundry உள்ளூர் உரையாடல் பயன்பாடுகள்**: மாடல் மாற்றத்துடன் Windows 11 இயற்கை பயன்பாடு  
- **பல முகவர் அமைப்புகள்**: சிக்கலான பணிச்சூழல்களுக்கு நிபுணர் முகவர்களுடன் ஒருங்கிணைப்பாளர்  
- **RAG பயன்பாடுகள்**: உள்ளூர் ஆவணங்களை வெக்டர் தேடலுடன் செயலாக்குதல்  
- **மாடல் வழிமுறைகள்**: பணியின் பகுப்பாய்வின் அடிப்படையில் மாடல்களை புத்திசாலித்தனமாக தேர்வு செய்தல்  
- **API கட்டமைப்புகள்**: ஸ்ட்ரீமிங் மற்றும் ஆரோக்கிய கண்காணிப்புடன் உற்பத்திக்கு தயாரான கிளையன்ட்கள்  
- **குறுக்குவெளி கருவிகள்**: LangChain/Semantic Kernel ஒருங்கிணைப்பு முறை

### 🏢 தொழில்துறை பயன்பாடுகள்
**தயாரிப்பு** • **சுகாதாரம்** • **தன்னாட்சி வாகனங்கள்** • **சிறந்த நகரங்கள்** • **மொபைல் பயன்பாடுகள்**

## விரைவான தொடக்கம்

**பரிந்துரைக்கப்பட்ட கற்றல் பாதை** (மொத்தம் 20-30 மணி நேரம்):

0. **📖 அறிமுகம்** ([Introduction.md](./introduction.md)): EdgeAI அடிப்படை + தொழில்துறை சூழல் + கற்றல் கட்டமைப்பு  
1. **📚 அடிப்படை** (Modules 01-02): EdgeAI கருத்துக்கள் + SLM மாடல் குடும்பங்கள்  
2. **⚙️ மேம்பாடு** (Modules 03-04): வெளியீடு + அளவீட்டு கட்டமைப்புகள்  
3. **🚀 உற்பத்தி** (Modules 05-06): SLMOps + AI முகவர்கள் + செயல்பாட்டு அழைப்பு  
4. **💻 செயல்படுத்தல்** (Modules 07-08): தளம் மாதிரிகள் + Foundry உள்ளூர் கருவிகள்  

ஒவ்வொரு தொகுதியிலும் கோட்பாடு, நடைமுறை பயிற்சிகள் மற்றும் உற்பத்திக்கு தயாரான குறியீடு மாதிரிகள் அடங்கும்.

## தொழில் தாக்கம்

**தொழில்நுட்ப பங்குகள்**: EdgeAI தீர்வு வடிவமைப்பாளர் • ML பொறியாளர் (Edge) • IoT AI டெவலப்பர் • மொபைல் AI டெவலப்பர்  

**தொழில்துறை துறைகள்**: தயாரிப்பு 4.0 • சுகாதார தொழில்நுட்பம் • தன்னாட்சி அமைப்புகள் • நிதி தொழில்நுட்பம் • நுகர்வோர் மின்னணுவியல்  

**தொகுப்பு திட்டங்கள்**: பல முகவர் அமைப்புகள் • உற்பத்தி RAG பயன்பாடுகள் • குறுக்குவெளி வெளியீடு • செயல்திறன் மேம்பாடு  

## களஞ்சிய அமைப்பு

```
edgeai-for-beginners/
├── 📖 introduction.md  # Foundation: EdgeAI Overview & Learning Framework
├── 📚 Module01-04/     # Fundamentals → SLMs → Deployment → Optimization  
├── 🔧 Module05-06/     # SLMOps → AI Agents → Function Calling
├── 💻 Module07/        # Platform Samples (VS Code, Windows, Jetson, Mobile)
├── 🏭 Module08/        # Foundry Local Toolkit + 10 Comprehensive Samples
│   ├── samples/01-06/  # Foundation: REST, SDK, RAG, Agents, Routing
│   └── samples/07-10/  # Advanced: API Client, Windows App, Enterprise Agents, Tools
├── 🌐 translations/    # Multi-language support (8+ languages)
└── 📋 STUDY_GUIDE.md   # Structured learning paths & time allocation
```

## பாடநெறி சிறப்பம்சங்கள்

✅ **முன்னேற்றமான கற்றல்**: கோட்பாடு → நடைமுறை → உற்பத்தி வெளியீடு  
✅ **உண்மையான வழக்குக் களங்கள்**: Microsoft, Japan Airlines, நிறுவன செயல்பாடுகள்  
✅ **நடைமுறை மாதிரிகள்**: 50+ உதாரணங்கள், 10 Foundry Local முழுமையான டெமோக்கள்  
✅ **செயல்திறன் கவனம்**: 85% வேக மேம்பாடுகள், 75% அளவு குறைப்புகள்  
✅ **பல தளம்**: Windows, மொபைல், எம்பெடட், கிளவுட்-எட்ஜ் ஹைப்ரிட்  
✅ **உற்பத்திக்கு தயாரானது**: கண்காணித்தல், அளவீடு, பாதுகாப்பு, இணக்கத்தன்மை கட்டமைப்புகள்  

📖 **[படிப்பு வழிகாட்டி கிடைக்கிறது](STUDY_GUIDE.md)**: 20 மணி நேர கட்டமைப்பான கற்றல் பாதை நேர ஒதுக்கீடு வழிகாட்டுதல் மற்றும் சுய மதிப்பீட்டு கருவிகள்.

---

**EdgeAI AI-யை வெளியிடுவதற்கான எதிர்காலத்தை பிரதிநிதித்துவம் செய்கிறது**: உள்ளூர்-முதல், தனியுரிமை பாதுகாப்பு மற்றும் திறமையானது. இந்த திறன்களை கற்றுக்கொண்டு அடுத்த தலைமுறை புத்திசாலி பயன்பாடுகளை உருவாக்குங்கள்.

## பிற பாடநெறிகள்

எங்கள் குழு பிற பாடநெறிகளை உருவாக்குகிறது! பாருங்கள்:

### Azure / Edge / MCP / முகவர்கள்
[![AZD for Beginners](https://img.shields.io/badge/AZD%20for%20Beginners-0078D4?style=for-the-badge&labelColor=E5E7EB&color=0078D4)](https://github.com/microsoft/AZD-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Edge AI for Beginners](https://img.shields.io/badge/Edge%20AI%20for%20Beginners-00B8E4?style=for-the-badge&labelColor=E5E7EB&color=00B8E4)](https://github.com/microsoft/edgeai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![MCP for Beginners](https://img.shields.io/badge/MCP%20for%20Beginners-009688?style=for-the-badge&labelColor=E5E7EB&color=009688)](https://github.com/microsoft/mcp-for-beginners?WT.mc_id=academic-105485-koreyst)
[![AI Agents for Beginners](https://img.shields.io/badge/AI%20Agents%20for%20Beginners-00C49A?style=for-the-badge&labelColor=E5E7EB&color=00C49A)](https://github.com/microsoft/ai-agents-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Generative AI தொடர்
[![Generative AI for Beginners](https://img.shields.io/badge/Generative%20AI%20for%20Beginners-8B5CF6?style=for-the-badge&labelColor=E5E7EB&color=8B5CF6)](https://github.com/microsoft/generative-ai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Generative AI (.NET)](https://img.shields.io/badge/Generative%20AI%20(.NET)-9333EA?style=for-the-badge&labelColor=E5E7EB&color=9333EA)](https://github.com/microsoft/Generative-AI-for-beginners-dotnet?WT.mc_id=academic-105485-koreyst)
[![Generative AI (Java)](https://img.shields.io/badge/Generative%20AI%20(Java)-C084FC?style=for-the-badge&labelColor=E5E7EB&color=C084FC)](https://github.com/microsoft/generative-ai-for-beginners-java?WT.mc_id=academic-105485-koreyst)
[![Generative AI (JavaScript)](https://img.shields.io/badge/Generative%20AI%20(JavaScript)-E879F9?style=for-the-badge&labelColor=E5E7EB&color=E879F9)](https://github.com/microsoft/generative-ai-with-javascript?WT.mc_id=academic-105485-koreyst)

---

### முக்கிய கற்றல்
[![ML for Beginners](https://img.shields.io/badge/ML%20for%20Beginners-22C55E?style=for-the-badge&labelColor=E5E7EB&color=22C55E)](https://aka.ms/ml-beginners?WT.mc_id=academic-105485-koreyst)
[![Data Science for Beginners](https://img.shields.io/badge/Data%20Science%20for%20Beginners-84CC16?style=for-the-badge&labelColor=E5E7EB&color=84CC16)](https://aka.ms/datascience-beginners?WT.mc_id=academic-105485-koreyst)
[![AI for Beginners](https://img.shields.io/badge/AI%20for%20Beginners-A3E635?style=for-the-badge&labelColor=E5E7EB&color=A3E635)](https://aka.ms/ai-beginners?WT.mc_id=academic-105485-koreyst)
[![Cybersecurity for Beginners](https://img.shields.io/badge/Cybersecurity%20for%20Beginners-F97316?style=for-the-badge&labelColor=E5E7EB&color=F97316)](https://github.com/microsoft/Security-101?WT.mc_id=academic-96948-sayoung)
[![Web Dev for Beginners](https://img.shields.io/badge/Web%20Dev%20for%20Beginners-EC4899?style=for-the-badge&labelColor=E5E7EB&color=EC4899)](https://aka.ms/webdev-beginners?WT.mc_id=academic-105485-koreyst)
[![IoT for Beginners](https://img.shields.io/badge/IoT%20for%20Beginners-14B8A6?style=for-the-badge&labelColor=E5E7EB&color=14B8A6)](https://aka.ms/iot-beginners?WT.mc_id=academic-105485-koreyst)
[![XR Development for Beginners](https://img.shields.io/badge/XR%20Development%20for%20Beginners-38BDF8?style=for-the-badge&labelColor=E5E7EB&color=38BDF8)](https://github.com/microsoft/xr-development-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Copilot தொடர்
[![Copilot for AI Paired Programming](https://img.shields.io/badge/Copilot%20for%20AI%20Paired%20Programming-FACC15?style=for-the-badge&labelColor=E5E7EB&color=FACC15)](https://aka.ms/GitHubCopilotAI?WT.mc_id=academic-105485-koreyst)
[![Copilot for C#/.NET](https://img.shields.io/badge/Copilot%20for%20C%23/.NET-FBBF24?style=for-the-badge&labelColor=E5E7EB&color=FBBF24)](https://github.com/microsoft/mastering-github-copilot-for-dotnet-csharp-developers?WT.mc_id=academic-105485-koreyst)
[![Copilot Adventure](https://img.shields.io/badge/Copilot%20Adventure-FDE68A?style=for-the-badge&labelColor=E5E7EB&color=FDE68A)](https://github.com/microsoft/CopilotAdventures?WT.mc_id=academic-105485-koreyst)

## உதவி பெறுதல்

AI பயன்பாடுகளை உருவாக்குவதில் சிக்கலாக இருந்தால் அல்லது கேள்விகள் இருந்தால், இணைந்திடுங்கள்:

[![Azure AI Foundry Discord](https://img.shields.io/badge/Discord-Azure_AI_Foundry_Community_Discord-blue?style=for-the-badge&logo=discord&color=5865f2&logoColor=fff)](https://aka.ms/foundry/discord)

தயாரிப்பு கருத்துகள் அல்லது கட்டமைப்பில் பிழைகள் இருந்தால், பாருங்கள்:

[![Azure AI Foundry Developer Forum](https://img.shields.io/badge/GitHub-Azure_AI_Foundry_Developer_Forum-blue?style=for-the-badge&logo=github&color=000000&logoColor=fff)](https://aka.ms/foundry/forum)

---

**குறிப்பு**:  
இந்த ஆவணம் AI மொழிபெயர்ப்பு சேவை [Co-op Translator](https://github.com/Azure/co-op-translator) பயன்படுத்தி மொழிபெயர்க்கப்பட்டுள்ளது. நாங்கள் துல்லியத்திற்காக முயற்சிக்கிறோம், ஆனால் தானியங்கி மொழிபெயர்ப்புகளில் பிழைகள் அல்லது தவறுகள் இருக்கக்கூடும் என்பதை கவனத்தில் கொள்ளவும். அதன் தாய்மொழியில் உள்ள மூல ஆவணம் அதிகாரப்பூர்வ ஆதாரமாக கருதப்பட வேண்டும். முக்கியமான தகவல்களுக்கு, தொழில்முறை மனித மொழிபெயர்ப்பு பரிந்துரைக்கப்படுகிறது. இந்த மொழிபெயர்ப்பைப் பயன்படுத்துவதால் ஏற்படும் எந்த தவறான புரிதல்கள் அல்லது தவறான விளக்கங்களுக்கு நாங்கள் பொறுப்பல்ல.