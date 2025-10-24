<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8f958250b0b94976c721e6cbdc541581",
  "translation_date": "2025-10-24T10:00:31+00:00",
  "source_file": "README.md",
  "language_code": "sr"
}
-->
# EdgeAI за почетнике

![Слика курса](../../translated_images/cover.eb18d1b9605d754b30973f4e17c6e11ea4f8473d9686ee378d6e7b44e3c70ac7.sr.png)

[![GitHub contributors](https://img.shields.io/github/contributors/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/graphs/contributors)  
[![GitHub issues](https://img.shields.io/github/issues/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/issues)  
[![GitHub pull-requests](https://img.shields.io/github/issues-pr/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/pulls)  
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)  

[![GitHub watchers](https://img.shields.io/github/watchers/microsoft/edgeai-for-beginners.svg?style=social&label=Watch)](https://GitHub.com/microsoft/edgeai-for-beginners/watchers)  
[![GitHub forks](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)  
[![GitHub stars](https://img.shields.io/github/stars/microsoft/edgeai-for-beginners?style=social&label=Star)](https://GitHub.com/microsoft/edgeai-for-beginners/stargazers)  

[![Microsoft Azure AI Foundry Discord](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://discord.com/invite/ByRwuEEgH4)

Пратите ове кораке да бисте започели коришћење ових ресурса:

1. **Fork репозиторијума**: Кликните [![GitHub forks](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)  
2. **Клонирајте репозиторијум**: `git clone https://github.com/microsoft/edgeai-for-beginners.git`  
3. [**Придружите се Azure AI Foundry Discord серверу и упознајте стручњаке и друге програмере**](https://discord.com/invite/ByRwuEEgH4)  

### 🌐 Подршка за више језика

#### Подржано преко GitHub Action (аутоматски и увек ажурирано)

[Арапски](../ar/README.md) | [Бенгалски](../bn/README.md) | [Бугарски](../bg/README.md) | [Бирмански (Мјанмар)](../my/README.md) | [Кинески (поједностављени)](../zh/README.md) | [Кинески (традиционални, Хонг Конг)](../hk/README.md) | [Кинески (традиционални, Макао)](../mo/README.md) | [Кинески (традиционални, Тајван)](../tw/README.md) | [Хрватски](../hr/README.md) | [Чешки](../cs/README.md) | [Дански](../da/README.md) | [Холандски](../nl/README.md) | [Естонски](../et/README.md) | [Фински](../fi/README.md) | [Француски](../fr/README.md) | [Немачки](../de/README.md) | [Грчки](../el/README.md) | [Хебрејски](../he/README.md) | [Хинди](../hi/README.md) | [Мађарски](../hu/README.md) | [Индонежански](../id/README.md) | [Италијански](../it/README.md) | [Јапански](../ja/README.md) | [Корејски](../ko/README.md) | [Литвански](../lt/README.md) | [Малајски](../ms/README.md) | [Марати](../mr/README.md) | [Непалски](../ne/README.md) | [Норвешки](../no/README.md) | [Персијски (фарси)](../fa/README.md) | [Пољски](../pl/README.md) | [Португалски (Бразил)](../br/README.md) | [Португалски (Португал)](../pt/README.md) | [Пунџаби (Гурмуки)](../pa/README.md) | [Румунски](../ro/README.md) | [Руски](../ru/README.md) | [Српски (ћирилица)](./README.md) | [Словачки](../sk/README.md) | [Словеначки](../sl/README.md) | [Шпански](../es/README.md) | [Свахили](../sw/README.md) | [Шведски](../sv/README.md) | [Тагалог (Филипински)](../tl/README.md) | [Тамилски](../ta/README.md) | [Тајландски](../th/README.md) | [Турски](../tr/README.md) | [Украјински](../uk/README.md) | [Урду](../ur/README.md) | [Вијетнамски](../vi/README.md)

**Ако желите да додате подршку за додатне језике, списак подржаних језика је доступан [овде](https://github.com/Azure/co-op-translator/blob/main/getting_started/supported-languages.md)**

## Увод

Добродошли у **EdgeAI за почетнике** – ваш свеобухватни водич кроз трансформативни свет вештачке интелигенције на ивици. Овај курс повезује моћне могућности вештачке интелигенције са практичном применом у стварном свету на уређајима на ивици, омогућавајући вам да искористите потенцијал вештачке интелигенције директно тамо где се подаци генеришу и где је потребно доносити одлуке.

### Шта ћете савладати

Овај курс вас води од основних концепата до имплементација спремних за производњу, обухватајући:
- **Мали језички модели (SLMs)** оптимизовани за примену на ивици
- **Оптимизацију у складу са хардвером** на различитим платформама
- **Инференцију у реалном времену** са могућностима очувања приватности
- **Стратегије примене у производњи** за пословне апликације

### Зашто је EdgeAI важан

Edge AI представља промену парадигме која решава кључне савремене изазове:
- **Приватност и безбедност**: Обрада осетљивих података локално, без излагања облаку
- **Перформансе у реалном времену**: Елиминисање кашњења мреже за апликације критичне за време
- **Ефикасност трошкова**: Смањење трошкова пропусног опсега и рачунарства у облаку
- **Отпорност у раду**: Одржавање функционалности током прекида мреже
- **Усклађеност са прописима**: Испуњавање захтева за суверенитет података

### Edge AI

Edge AI се односи на покретање алгоритама вештачке интелигенције и језичких модела локално на хардверу, близу места где се подаци генеришу, без ослањања на ресурсе облака за инференцију. Смањује кашњење, побољшава приватност и омогућава доношење одлука у реалном времену.

### Основни принципи:
- **Инференција на уређају**: AI модели се покрећу на уређајима на ивици (телефони, рутери, микроконтролери, индустријски рачунари)
- **Офлајн могућност**: Функционише без сталне интернет конекције
- **Ниско кашњење**: Одговори у реалном времену погодни за системе у реалном времену
- **Суверенитет података**: Чува осетљиве податке локално, побољшавајући безбедност и усклађеност

### Мали језички модели (SLMs)

SLMs попут Phi-4, Mistral-7B и Gemma су оптимизоване верзије већих LLM-ова – обучене или дестиловане за:
- **Смањену меморијску потрошњу**: Ефикасно коришћење ограничене меморије уређаја на ивици
- **Мање захтеве за рачунарском снагом**: Оптимизовани за перформансе CPU-а и GPU-а на ивици
- **Брже време покретања**: Брза иницијализација за одзивне апликације

Они омогућавају моћне NLP могућности уз испуњавање ограничења:
- **Уграђени системи**: IoT уређаји и индустријски контролери
- **Мобилни уређаји**: Паметни телефони и таблети са офлајн могућностима
- **IoT уређаји**: Сензори и паметни уређаји са ограниченим ресурсима
- **Сервери на ивици**: Локалне јединице за обраду са ограниченим GPU ресурсима
- **Лични рачунари**: Сценарији примене на десктоп и лаптоп рачунарима

## Модули курса и навигација

| Модул | Тема | Област фокуса | Кључни садржај | Ниво | Трајање |
|-------|------|---------------|----------------|-------|---------|
| [📖 00 ](./introduction.md) | [Увод у EdgeAI](./introduction.md) | Основе и контекст | Преглед EdgeAI • Примена у индустрији • Увод у SLM • Циљеви учења | Почетни | 1-2 сата |
| [📚 01](../../Module01) | [Основе EdgeAI](./Module01/README.md) | Поређење облака и Edge AI | Основе EdgeAI • Студије случаја из стварног света • Водич за имплементацију • Примена на ивици | Почетни | 3-4 сата |
| [🧠 02](../../Module02) | [Основе SLM модела](./Module02/README.md) | Породице модела и архитектура | Phi породица • Qwen породица • Gemma породица • BitNET • μModel • Phi-Silica | Почетни | 4-5 сати |
| [🚀 03](../../Module03) | [Практична примена SLM](./Module03/README.md) | Локална и облачна примена | Напредно учење • Локално окружење • Примена у облаку | Средњи | 4-5 сати |
| [⚙️ 04](../../Module04) | [Алат за оптимизацију модела](./Module04/README.md) | Оптимизација на више платформи | Увод • Llama.cpp • Microsoft Olive • OpenVINO • Apple MLX • Синтеза радног процеса | Средњи | 5-6 сати |
| [🔧 05](../../Module05) | [SLMOps у производњи](./Module05/README.md) | Операције у производњи | Увод у SLMOps • Дестилација модела • Фино подешавање • Примена у производњи | Напредни | 5-6 сати |
| [🤖 06](../../Module06) | [AI агенти и позивање функција](./Module06/README.md) | Оквири агената и MCP | Увод у агенте • Позивање функција • Протокол контекста модела | Напредни | 4-5 сати |
| [💻 07](../../Module07) | [Примена на платформи](./Module07/README.md) | Примери на више платформи | AI алатке • Foundry Local • Развој за Windows | Напредни | 3-4 сата |
| [🏭 08](../../Module08) | [Foundry Local Toolkit](./Module08/README.md) | Примери спремни за производњу | Пример апликација (погледајте детаље испод) | Експерт | 8-10 сати |

### 🏭 **Модул 08: Пример апликација**

- [01: Брзи почетак REST Chat](./Module08/samples/01/README.md)  
- [02: Интеграција OpenAI SDK](./Module08/samples/02/README.md)  
- [03: Откривање модела и бенчмаркинг](./Module08/samples/03/README.md)  
- [04: Chainlit RAG апликација](./Module08/samples/04/README.md)  
- [05: Оркестрација више агената](./Module08/samples/05/README.md)  
- [06: Рутер за моделе као алатке](./Module08/samples/06/README.md)  
- [07: Клијент директног API](./Module08/samples/07/README.md)  
- [08: Windows 11 Chat апликација](./Module08/samples/08/README.md)  
- [09: Напредни систем за више агената](./Module08/samples/09/README.md)  
- [10: Foundry Tools Framework](./Module08/samples/10/README.md)  

### 🎓 **Радионица: Практични пут учења**

Свеобухватни материјали за радионицу са имплементацијама спремним за производњу:

- **[Водич за радионицу](./Workshop/Readme.md)** - Комплетни циљеви учења, исходи и навигација ресурсима  
- **Python примери** (6 сесија) - Ажурирано са најбољим праксама, обрадом грешака и свеобухватном документацијом  
- **Jupyter бележнице** (8 интерактивних) - Водичи корак по корак са бенчмарковима и праћењем перформанси  
- **Водичи за сесије** - Детаљни водичи у Markdown формату за сваку сесију радионице  
- **Алатке за валидацију** - Скрипте за проверу квалитета кода и тестирање  

**Шта ћете изградити:**  
- Локалне AI апликације за ћаскање са подршком за стриминг  
- RAG цевоводе са проценом квалитета (RAGAS)  
- Алатке за бенчмаркинг и поређење више модела  
- Системе за оркестрацију више агената  
- Интелигентно рутирање модела са избором заснованим на задацима  

### 📊 **Резиме пута учења**
- **Укупно трајање**: 36-45 сати  
- **Почетни пут**: Модули 01-02 (7-9 сати)  
- **Средњи пут**: Модули 03-04 (9-11 сати)  
- **Напредни пут**: Модули 05-07 (12-15 сати)  
- **Експертски пут**: Модул 08 (8-10 сати)  

## Шта ћете изградити

### 🎯 Основне компетенције
- **Архитектура Edge AI**: Дизајнирање AI система који су локално оријентисани са интеграцијом облака  
- **Оптимизација модела**: Квантизација и компресија модела за примену на ивици (85% убрзање, 75% смањење величине)  
- **Примена на више платформи**: Windows, мобилни, уграђени и хибридни системи облак-ивица  
- **Операције у производњи**: Праћење, скалирање и одржавање edge AI у производњи

### 🏗️ Практични пројекти
- **Foundry локалне апликације за ћаскање**: Нативна апликација за Windows 11 са могућношћу промене модела
- **Системи са више агената**: Координатор са специјализованим агентима за сложене радне токове  
- **RAG апликације**: Обрада локалних докумената уз претрагу вектора
- **Рутери модела**: Интелигентан избор између модела на основу анализе задатка
- **API оквири**: Клијенти спремни за производњу са стримингом и праћењем здравља система
- **Мултиплатформски алати**: LangChain/Semantic Kernel интеграциони обрасци

### 🏢 Примена у индустрији
**Производња** • **Здравство** • **Аутономна возила** • **Паметни градови** • **Мобилне апликације**

## Брзи почетак

**Препоручени пут учења** (укупно 20-30 сати):

0. **📖 Увод** ([Introduction.md](./introduction.md)): Основе EdgeAI + контекст индустрије + оквир за учење
1. **📚 Основе** (Модули 01-02): Концепти EdgeAI + породице SLM модела
2. **⚙️ Оптимизација** (Модули 03-04): Дистрибуција + оквири за квантизацију  
3. **🚀 Производња** (Модули 05-06): SLMOps + AI агенти + позивање функција
4. **💻 Имплементација** (Модули 07-08): Примери платформи + Foundry Local алат

Сваки модул укључује теорију, практичне вежбе и узорке кода спремне за производњу.

## Утицај на каријеру

**Техничке улоге**: Архитекта решења за EdgeAI • ML инжењер (Edge) • IoT AI програмер • Програмер мобилних AI апликација

**Сектори индустрије**: Производња 4.0 • Технологија у здравству • Аутономни системи • FinTech • Потрошачка електроника

**Пројекти за портфолио**: Системи са више агената • RAG апликације у производњи • Мултиплатформска дистрибуција • Оптимизација перформанси

## Структура репозиторијума

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

## Истакнути делови курса

✅ **Прогресивно учење**: Теорија → Практика → Дистрибуција у производњи  
✅ **Студије случаја из стварног живота**: Microsoft, Japan Airlines, имплементације у предузећима  
✅ **Практични примери**: 50+ примера, 10 свеобухватних Foundry Local демонстрација  
✅ **Фокус на перформансе**: Побољшање брзине за 85%, смањење величине за 75%  
✅ **Мултиплатформски приступ**: Windows, мобилни уређаји, уграђени системи, хибридни cloud-edge  
✅ **Спремно за производњу**: Праћење, скалирање, безбедност, оквири за усклађеност

📖 **[Доступан водич за учење](STUDY_GUIDE.md)**: Структурисан пут учења од 20 сати са смерницама за расподелу времена и алатима за самопроцену.

---

**EdgeAI представља будућност AI дистрибуције**: локално оријентисан, са очувањем приватности и ефикасношћу. Савладајте ове вештине да бисте изградили следећу генерацију интелигентних апликација.

## Остали курсеви

Наш тим производи и друге курсеве! Погледајте:

### Azure / Edge / MCP / Агенти
[![AZD за почетнике](https://img.shields.io/badge/AZD%20for%20Beginners-0078D4?style=for-the-badge&labelColor=E5E7EB&color=0078D4)](https://github.com/microsoft/AZD-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Edge AI за почетнике](https://img.shields.io/badge/Edge%20AI%20for%20Beginners-00B8E4?style=for-the-badge&labelColor=E5E7EB&color=00B8E4)](https://github.com/microsoft/edgeai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![MCP за почетнике](https://img.shields.io/badge/MCP%20for%20Beginners-009688?style=for-the-badge&labelColor=E5E7EB&color=009688)](https://github.com/microsoft/mcp-for-beginners?WT.mc_id=academic-105485-koreyst)
[![AI агенти за почетнике](https://img.shields.io/badge/AI%20Agents%20for%20Beginners-00C49A?style=for-the-badge&labelColor=E5E7EB&color=00C49A)](https://github.com/microsoft/ai-agents-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Генеративни AI серијал
[![Генеративни AI за почетнике](https://img.shields.io/badge/Generative%20AI%20for%20Beginners-8B5CF6?style=for-the-badge&labelColor=E5E7EB&color=8B5CF6)](https://github.com/microsoft/generative-ai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Генеративни AI (.NET)](https://img.shields.io/badge/Generative%20AI%20(.NET)-9333EA?style=for-the-badge&labelColor=E5E7EB&color=9333EA)](https://github.com/microsoft/Generative-AI-for-beginners-dotnet?WT.mc_id=academic-105485-koreyst)
[![Генеративни AI (Java)](https://img.shields.io/badge/Generative%20AI%20(Java)-C084FC?style=for-the-badge&labelColor=E5E7EB&color=C084FC)](https://github.com/microsoft/generative-ai-for-beginners-java?WT.mc_id=academic-105485-koreyst)
[![Генеративни AI (JavaScript)](https://img.shields.io/badge/Generative%20AI%20(JavaScript)-E879F9?style=for-the-badge&labelColor=E5E7EB&color=E879F9)](https://github.com/microsoft/generative-ai-with-javascript?WT.mc_id=academic-105485-koreyst)

---

### Основни курсеви
[![ML за почетнике](https://img.shields.io/badge/ML%20for%20Beginners-22C55E?style=for-the-badge&labelColor=E5E7EB&color=22C55E)](https://aka.ms/ml-beginners?WT.mc_id=academic-105485-koreyst)
[![Наука о подацима за почетнике](https://img.shields.io/badge/Data%20Science%20for%20Beginners-84CC16?style=for-the-badge&labelColor=E5E7EB&color=84CC16)](https://aka.ms/datascience-beginners?WT.mc_id=academic-105485-koreyst)
[![AI за почетнике](https://img.shields.io/badge/AI%20for%20Beginners-A3E635?style=for-the-badge&labelColor=E5E7EB&color=A3E635)](https://aka.ms/ai-beginners?WT.mc_id=academic-105485-koreyst)
[![Сајбер безбедност за почетнике](https://img.shields.io/badge/Cybersecurity%20for%20Beginners-F97316?style=for-the-badge&labelColor=E5E7EB&color=F97316)](https://github.com/microsoft/Security-101?WT.mc_id=academic-96948-sayoung)
[![Веб развој за почетнике](https://img.shields.io/badge/Web%20Dev%20for%20Beginners-EC4899?style=for-the-badge&labelColor=E5E7EB&color=EC4899)](https://aka.ms/webdev-beginners?WT.mc_id=academic-105485-koreyst)
[![IoT за почетнике](https://img.shields.io/badge/IoT%20for%20Beginners-14B8A6?style=for-the-badge&labelColor=E5E7EB&color=14B8A6)](https://aka.ms/iot-beginners?WT.mc_id=academic-105485-koreyst)
[![XR развој за почетнике](https://img.shields.io/badge/XR%20Development%20for%20Beginners-38BDF8?style=for-the-badge&labelColor=E5E7EB&color=38BDF8)](https://github.com/microsoft/xr-development-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Copilot серијал
[![Copilot за парно програмирање са AI](https://img.shields.io/badge/Copilot%20for%20AI%20Paired%20Programming-FACC15?style=for-the-badge&labelColor=E5E7EB&color=FACC15)](https://aka.ms/GitHubCopilotAI?WT.mc_id=academic-105485-koreyst)
[![Copilot за C#/.NET](https://img.shields.io/badge/Copilot%20for%20C%23/.NET-FBBF24?style=for-the-badge&labelColor=E5E7EB&color=FBBF24)](https://github.com/microsoft/mastering-github-copilot-for-dotnet-csharp-developers?WT.mc_id=academic-105485-koreyst)
[![Copilot авантура](https://img.shields.io/badge/Copilot%20Adventure-FDE68A?style=for-the-badge&labelColor=E5E7EB&color=FDE68A)](https://github.com/microsoft/CopilotAdventures?WT.mc_id=academic-105485-koreyst)

## Помоћ

Ако се заглавите или имате питања о изради AI апликација, придружите се:

[![Azure AI Foundry Discord](https://img.shields.io/badge/Discord-Azure_AI_Foundry_Community_Discord-blue?style=for-the-badge&logo=discord&color=5865f2&logoColor=fff)](https://aka.ms/foundry/discord)

Ако имате повратне информације о производу или наиђете на грешке током израде, посетите:

[![Azure AI Foundry Developer Forum](https://img.shields.io/badge/GitHub-Azure_AI_Foundry_Developer_Forum-blue?style=for-the-badge&logo=github&color=000000&logoColor=fff)](https://aka.ms/foundry/forum)

---

**Одрицање од одговорности**:  
Овај документ је преведен помоћу услуге за превођење вештачке интелигенције [Co-op Translator](https://github.com/Azure/co-op-translator). Иако настојимо да обезбедимо тачност, молимо вас да имате у виду да аутоматски преводи могу садржати грешке или нетачности. Оригинални документ на изворном језику треба сматрати меродавним извором. За критичне информације препоручује се професионални превод од стране људи. Не преузимамо одговорност за било каква погрешна тумачења или неспоразуме који могу настати услед коришћења овог превода.