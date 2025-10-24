<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8f958250b0b94976c721e6cbdc541581",
  "translation_date": "2025-10-24T10:08:01+00:00",
  "source_file": "README.md",
  "language_code": "uk"
}
-->
# EdgeAI для початківців

![Зображення обкладинки курсу](../../translated_images/cover.eb18d1b9605d754b30973f4e17c6e11ea4f8473d9686ee378d6e7b44e3c70ac7.uk.png)

[![Учасники GitHub](https://img.shields.io/github/contributors/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/graphs/contributors)
[![Проблеми GitHub](https://img.shields.io/github/issues/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/issues)
[![Запити на GitHub](https://img.shields.io/github/issues-pr/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/pulls)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

[![Спостерігачі GitHub](https://img.shields.io/github/watchers/microsoft/edgeai-for-beginners.svg?style=social&label=Watch)](https://GitHub.com/microsoft/edgeai-for-beginners/watchers)
[![Форки GitHub](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)
[![Зірки GitHub](https://img.shields.io/github/stars/microsoft/edgeai-for-beginners?style=social&label=Star)](https://GitHub.com/microsoft/edgeai-for-beginners/stargazers)

[![Microsoft Azure AI Foundry Discord](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://discord.com/invite/ByRwuEEgH4)

Дотримуйтесь цих кроків, щоб розпочати використання цих ресурсів:

1. **Форкніть репозиторій**: Натисніть [![Форки GitHub](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)
2. **Клонування репозиторію**: `git clone https://github.com/microsoft/edgeai-for-beginners.git`
3. [**Приєднайтеся до Azure AI Foundry Discord і зустріньтеся з експертами та іншими розробниками**](https://discord.com/invite/ByRwuEEgH4)

### 🌐 Підтримка багатомовності

#### Підтримується через GitHub Action (автоматично та завжди актуально)

[Арабська](../ar/README.md) | [Бенгальська](../bn/README.md) | [Болгарська](../bg/README.md) | [Бірманська (М'янма)](../my/README.md) | [Китайська (спрощена)](../zh/README.md) | [Китайська (традиційна, Гонконг)](../hk/README.md) | [Китайська (традиційна, Макао)](../mo/README.md) | [Китайська (традиційна, Тайвань)](../tw/README.md) | [Хорватська](../hr/README.md) | [Чеська](../cs/README.md) | [Данська](../da/README.md) | [Нідерландська](../nl/README.md) | [Естонська](../et/README.md) | [Фінська](../fi/README.md) | [Французька](../fr/README.md) | [Німецька](../de/README.md) | [Грецька](../el/README.md) | [Іврит](../he/README.md) | [Гінді](../hi/README.md) | [Угорська](../hu/README.md) | [Індонезійська](../id/README.md) | [Італійська](../it/README.md) | [Японська](../ja/README.md) | [Корейська](../ko/README.md) | [Литовська](../lt/README.md) | [Малайська](../ms/README.md) | [Маратхі](../mr/README.md) | [Непальська](../ne/README.md) | [Норвезька](../no/README.md) | [Перська (фарсі)](../fa/README.md) | [Польська](../pl/README.md) | [Португальська (Бразилія)](../br/README.md) | [Португальська (Португалія)](../pt/README.md) | [Панджабі (Гурмухі)](../pa/README.md) | [Румунська](../ro/README.md) | [Російська](../ru/README.md) | [Сербська (кирилиця)](../sr/README.md) | [Словацька](../sk/README.md) | [Словенська](../sl/README.md) | [Іспанська](../es/README.md) | [Суахілі](../sw/README.md) | [Шведська](../sv/README.md) | [Тагальська (Філіппіни)](../tl/README.md) | [Тамільська](../ta/README.md) | [Тайська](../th/README.md) | [Турецька](../tr/README.md) | [Українська](./README.md) | [Урду](../ur/README.md) | [В'єтнамська](../vi/README.md)

**Якщо ви бажаєте додати додаткові переклади, підтримувані мови наведені [тут](https://github.com/Azure/co-op-translator/blob/main/getting_started/supported-languages.md)**

## Вступ

Ласкаво просимо до **EdgeAI для початківців** – вашої всебічної подорожі у світ Edge штучного інтелекту. Цей курс об'єднує потужні можливості AI з практичним розгортанням на пристроях, дозволяючи використовувати потенціал AI безпосередньо там, де генерується дані та приймаються рішення.

### Що ви опануєте

Цей курс охоплює все – від основних концепцій до готових до виробництва реалізацій:
- **Малі мовні моделі (SLM)**, оптимізовані для розгортання на пристроях
- **Оптимізація з урахуванням апаратного забезпечення** для різних платформ
- **Інференція в реальному часі** з функціями збереження конфіденційності
- **Стратегії розгортання у виробництві** для корпоративних застосувань

### Чому EdgeAI важливий

Edge AI змінює правила гри, вирішуючи сучасні виклики:
- **Конфіденційність і безпека**: Обробка чутливих даних локально без передачі в хмару
- **Продуктивність у реальному часі**: Усунення затримок мережі для критичних додатків
- **Економічна ефективність**: Зменшення витрат на пропускну здатність і хмарні обчислення
- **Стійкість роботи**: Збереження функціональності під час перебоїв у мережі
- **Відповідність регуляторним вимогам**: Дотримання вимог щодо суверенітету даних

### Edge AI

Edge AI означає виконання алгоритмів AI та мовних моделей локально на апаратному забезпеченні, близько до місця генерації даних, без залежності від хмарних ресурсів для інференції. Це зменшує затримку, покращує конфіденційність і дозволяє приймати рішення в реальному часі.

### Основні принципи:
- **Інференція на пристрої**: Моделі AI працюють на пристроях (телефонах, маршрутизаторах, мікроконтролерах, промислових ПК)
- **Офлайн-можливості**: Функціонування без постійного підключення до інтернету
- **Низька затримка**: Миттєва реакція, що підходить для систем реального часу
- **Суверенітет даних**: Зберігання чутливих даних локально, покращуючи безпеку та відповідність

### Малі мовні моделі (SLM)

SLM, такі як Phi-4, Mistral-7B і Gemma, є оптимізованими версіями великих LLM, які були навчені або скорочені для:
- **Зменшення обсягу пам'яті**: Ефективне використання обмеженої пам'яті пристроїв
- **Менше навантаження на обчислення**: Оптимізація для продуктивності CPU та GPU на пристроях
- **Швидший запуск**: Швидка ініціалізація для оперативних додатків

Вони забезпечують потужні можливості NLP, відповідаючи обмеженням:
- **Вбудовані системи**: IoT-пристрої та промислові контролери
- **Мобільні пристрої**: Смартфони та планшети з офлайн-можливостями
- **IoT-пристрої**: Датчики та розумні пристрої з обмеженими ресурсами
- **Сервери на краю**: Локальні обчислювальні одиниці з обмеженими ресурсами GPU
- **Персональні комп'ютери**: Сценарії розгортання на настільних і портативних комп'ютерах

## Модулі курсу та навігація

| Модуль | Тема | Область фокусу | Основний зміст | Рівень | Тривалість |
|--------|-------|----------------|----------------|--------|------------|
| [📖 00 ](./introduction.md) | [Вступ до EdgeAI](./introduction.md) | Основи та контекст | Огляд EdgeAI • Застосування в індустрії • Вступ до SLM • Цілі навчання | Початківець | 1-2 год |
| [📚 01](../../Module01) | [Основи EdgeAI](./Module01/README.md) | Порівняння хмари та Edge AI | Основи EdgeAI • Реальні приклади • Посібник з реалізації • Розгортання на краю | Початківець | 3-4 год |
| [🧠 02](../../Module02) | [Основи моделі SLM](./Module02/README.md) | Сімейства моделей та архітектура | Сімейство Phi • Сімейство Qwen • Сімейство Gemma • BitNET • μModel • Phi-Silica | Початківець | 4-5 год |
| [🚀 03](../../Module03) | [Практика розгортання SLM](./Module03/README.md) | Локальне та хмарне розгортання | Розширене навчання • Локальне середовище • Хмарне розгортання | Середній | 4-5 год |
| [⚙️ 04](../../Module04) | [Інструментарій оптимізації моделі](./Module04/README.md) | Оптимізація для різних платформ | Вступ • Llama.cpp • Microsoft Olive • OpenVINO • Apple MLX • Синтез робочого процесу | Середній | 5-6 год |
| [🔧 05](../../Module05) | [SLMOps у виробництві](./Module05/README.md) | Операції у виробництві | Вступ до SLMOps • Дистиляція моделі • Тонке налаштування • Розгортання у виробництві | Просунутий | 5-6 год |
| [🤖 06](../../Module06) | [AI-агенти та виклик функцій](./Module06/README.md) | Фреймворки агентів та MCP | Вступ до агентів • Виклик функцій • Протокол контексту моделі | Просунутий | 4-5 год |
| [💻 07](../../Module07) | [Реалізація платформи](./Module07/README.md) | Зразки для різних платформ | Інструментарій AI • Foundry Local • Розробка для Windows | Просунутий | 3-4 год |
| [🏭 08](../../Module08) | [Інструментарій Foundry Local](./Module08/README.md) | Зразки, готові до виробництва | Зразкові додатки (див. деталі нижче) | Експерт | 8-10 год |

### 🏭 **Модуль 08: Зразкові додатки**

- [01: Швидкий старт REST Chat](./Module08/samples/01/README.md)
- [02: Інтеграція OpenAI SDK](./Module08/samples/02/README.md)
- [03: Відкриття та тестування моделей](./Module08/samples/03/README.md)
- [04: Застосунок Chainlit RAG](./Module08/samples/04/README.md)
- [05: Оркестрація мультиагентів](./Module08/samples/05/README.md)
- [06: Маршрутизатор моделей як інструментів](./Module08/samples/06/README.md)
- [07: Прямий клієнт API](./Module08/samples/07/README.md)
- [08: Чат-додаток для Windows 11](./Module08/samples/08/README.md)
- [09: Розширена система мультиагентів](./Module08/samples/09/README.md)
- [10: Фреймворк інструментів Foundry](./Module08/samples/10/README.md)

### 🎓 **Майстерня: Практичний навчальний шлях**

Комплексні матеріали для практичної майстерні з реалізаціями, готовими до виробництва:

- **[Посібник з майстерні](./Workshop/Readme.md)** - Повні цілі навчання, результати та навігація по ресурсах
- **Зразки Python** (6 сесій) - Оновлені з найкращими практиками, обробкою помилок та детальною документацією
- **Jupyter Notebooks** (8 інтерактивних) - Покрокові навчальні посібники з тестами продуктивності та моніторингом
- **Посібники сесій** - Детальні посібники у форматі markdown для кожної сесії майстерні
- **Інструменти перевірки** - Скрипти для перевірки якості коду та запуску тестів

**Що ви створите:**
- Локальні AI-додатки для чату зі підтримкою потокової передачі
- RAG-пайплайни з оцінкою якості (RAGAS)
- Інструменти для тестування та порівняння моделей
- Системи оркестрації мультиагентів
- Інтелектуальний маршрутизатор моделей з вибором завдань

### 📊 **Резюме навчального шляху**
- **Загальна тривалість**: 36-45 годин
- **Шлях початківця**: Модулі 01-02 (7-9 годин)  
- **Середній шлях**: Модулі 03-04 (9-11 годин)
- **Просунутий шлях**: Модулі 05-07 (12-15 годин)
- **Експертний шлях**: Модуль 08 (8-10 годин)

## Що ви створите

### 🎯 Основні компетенції
- **Архітектура Edge AI**: Проектування локальних AI-систем з інтеграцією хмари
- **Оптимізація моделі**: Квантування та стиснення моделей для розгортання на пристроях (прискорення на 85%, зменшення розміру на 75%)
- **Розгортання на різних платформах**: Windows, мобільні пристрої, вбудовані системи та гібридні хмарно-крайові системи
- **Операції у виробництві**: Моніторинг, масштабування та підтримка Edge AI у виробничому середовищі

### 🏗️ Практичні проєкти
- **Foundry Local Chat Apps**: Нативний додаток для Windows 11 із перемиканням моделей
- **Системи з багатьма агентами**: Координатор зі спеціалізованими агентами для складних робочих процесів  
- **RAG-додатки**: Обробка локальних документів із пошуком за векторами
- **Маршрутизатори моделей**: Інтелектуальний вибір між моделями на основі аналізу завдань
- **Фреймворки API**: Клієнти, готові до виробництва, зі стрімінгом і моніторингом стану
- **Кросплатформні інструменти**: Шаблони інтеграції LangChain/Semantic Kernel

### 🏢 Галузеві застосування
**Виробництво** • **Охорона здоров'я** • **Автономні транспортні засоби** • **Розумні міста** • **Мобільні додатки**

## Швидкий старт

**Рекомендований навчальний шлях** (загалом 20-30 годин):

0. **📖 Вступ** ([Introduction.md](./introduction.md)): Основи EdgeAI + контекст галузі + навчальна структура
1. **📚 Основи** (Модулі 01-02): Концепції EdgeAI + сімейства моделей SLM
2. **⚙️ Оптимізація** (Модулі 03-04): Розгортання + фреймворки квантування  
3. **🚀 Виробництво** (Модулі 05-06): SLMOps + AI-агенти + виклик функцій
4. **💻 Реалізація** (Модулі 07-08): Зразки платформ + інструментарій Foundry Local

Кожен модуль включає теорію, практичні вправи та зразки коду, готові до використання у виробництві.

## Вплив на кар'єру

**Технічні ролі**: Архітектор рішень EdgeAI • Інженер ML (Edge) • Розробник IoT AI • Розробник мобільного AI

**Галузі**: Виробництво 4.0 • Технології охорони здоров'я • Автономні системи • FinTech • Споживча електроніка

**Проєкти для портфоліо**: Системи з багатьма агентами • Виробничі RAG-додатки • Кросплатформне розгортання • Оптимізація продуктивності

## Структура репозиторію

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

## Основні моменти курсу

✅ **Прогресивне навчання**: Теорія → Практика → Розгортання у виробництві  
✅ **Реальні кейси**: Microsoft, Japan Airlines, корпоративні впровадження  
✅ **Практичні приклади**: 50+ прикладів, 10 комплексних демонстрацій Foundry Local  
✅ **Фокус на продуктивності**: Покращення швидкості на 85%, зменшення розміру на 75%  
✅ **Багатоплатформність**: Windows, мобільні пристрої, вбудовані системи, гібридні хмарно-периферійні рішення  
✅ **Готовність до виробництва**: Моніторинг, масштабування, безпека, фреймворки відповідності

📖 **[Доступний навчальний посібник](STUDY_GUIDE.md)**: Структурований навчальний шлях на 20 годин із рекомендаціями щодо розподілу часу та інструментами самооцінки.

---

**EdgeAI представляє майбутнє розгортання AI**: локально-орієнтоване, збереження конфіденційності та ефективність. Опановуйте ці навички, щоб створювати наступне покоління інтелектуальних додатків.

## Інші курси

Наша команда створює й інші курси! Ознайомтеся:

### Azure / Edge / MCP / Agents
[![AZD для початківців](https://img.shields.io/badge/AZD%20for%20Beginners-0078D4?style=for-the-badge&labelColor=E5E7EB&color=0078D4)](https://github.com/microsoft/AZD-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Edge AI для початківців](https://img.shields.io/badge/Edge%20AI%20for%20Beginners-00B8E4?style=for-the-badge&labelColor=E5E7EB&color=00B8E4)](https://github.com/microsoft/edgeai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![MCP для початківців](https://img.shields.io/badge/MCP%20for%20Beginners-009688?style=for-the-badge&labelColor=E5E7EB&color=009688)](https://github.com/microsoft/mcp-for-beginners?WT.mc_id=academic-105485-koreyst)
[![AI Agents для початківців](https://img.shields.io/badge/AI%20Agents%20for%20Beginners-00C49A?style=for-the-badge&labelColor=E5E7EB&color=00C49A)](https://github.com/microsoft/ai-agents-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Серія Generative AI
[![Generative AI для початківців](https://img.shields.io/badge/Generative%20AI%20for%20Beginners-8B5CF6?style=for-the-badge&labelColor=E5E7EB&color=8B5CF6)](https://github.com/microsoft/generative-ai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Generative AI (.NET)](https://img.shields.io/badge/Generative%20AI%20(.NET)-9333EA?style=for-the-badge&labelColor=E5E7EB&color=9333EA)](https://github.com/microsoft/Generative-AI-for-beginners-dotnet?WT.mc_id=academic-105485-koreyst)
[![Generative AI (Java)](https://img.shields.io/badge/Generative%20AI%20(Java)-C084FC?style=for-the-badge&labelColor=E5E7EB&color=C084FC)](https://github.com/microsoft/generative-ai-for-beginners-java?WT.mc_id=academic-105485-koreyst)
[![Generative AI (JavaScript)](https://img.shields.io/badge/Generative%20AI%20(JavaScript)-E879F9?style=for-the-badge&labelColor=E5E7EB&color=E879F9)](https://github.com/microsoft/generative-ai-with-javascript?WT.mc_id=academic-105485-koreyst)

---

### Основне навчання
[![ML для початківців](https://img.shields.io/badge/ML%20for%20Beginners-22C55E?style=for-the-badge&labelColor=E5E7EB&color=22C55E)](https://aka.ms/ml-beginners?WT.mc_id=academic-105485-koreyst)
[![Data Science для початківців](https://img.shields.io/badge/Data%20Science%20for%20Beginners-84CC16?style=for-the-badge&labelColor=E5E7EB&color=84CC16)](https://aka.ms/datascience-beginners?WT.mc_id=academic-105485-koreyst)
[![AI для початківців](https://img.shields.io/badge/AI%20for%20Beginners-A3E635?style=for-the-badge&labelColor=E5E7EB&color=A3E635)](https://aka.ms/ai-beginners?WT.mc_id=academic-105485-koreyst)
[![Кібербезпека для початківців](https://img.shields.io/badge/Cybersecurity%20for%20Beginners-F97316?style=for-the-badge&labelColor=E5E7EB&color=F97316)](https://github.com/microsoft/Security-101?WT.mc_id=academic-96948-sayoung)
[![Web Dev для початківців](https://img.shields.io/badge/Web%20Dev%20for%20Beginners-EC4899?style=for-the-badge&labelColor=E5E7EB&color=EC4899)](https://aka.ms/webdev-beginners?WT.mc_id=academic-105485-koreyst)
[![IoT для початківців](https://img.shields.io/badge/IoT%20for%20Beginners-14B8A6?style=for-the-badge&labelColor=E5E7EB&color=14B8A6)](https://aka.ms/iot-beginners?WT.mc_id=academic-105485-koreyst)
[![Розробка XR для початківців](https://img.shields.io/badge/XR%20Development%20for%20Beginners-38BDF8?style=for-the-badge&labelColor=E5E7EB&color=38BDF8)](https://github.com/microsoft/xr-development-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Серія Copilot
[![Copilot для парного програмування AI](https://img.shields.io/badge/Copilot%20for%20AI%20Paired%20Programming-FACC15?style=for-the-badge&labelColor=E5E7EB&color=FACC15)](https://aka.ms/GitHubCopilotAI?WT.mc_id=academic-105485-koreyst)
[![Copilot для C#/.NET](https://img.shields.io/badge/Copilot%20for%20C%23/.NET-FBBF24?style=for-the-badge&labelColor=E5E7EB&color=FBBF24)](https://github.com/microsoft/mastering-github-copilot-for-dotnet-csharp-developers?WT.mc_id=academic-105485-koreyst)
[![Copilot Adventure](https://img.shields.io/badge/Copilot%20Adventure-FDE68A?style=for-the-badge&labelColor=E5E7EB&color=FDE68A)](https://github.com/microsoft/CopilotAdventures?WT.mc_id=academic-105485-koreyst)

## Отримання допомоги

Якщо ви застрягли або маєте запитання щодо створення AI-додатків, приєднуйтесь:

[![Discord спільнота Azure AI Foundry](https://img.shields.io/badge/Discord-Azure_AI_Foundry_Community_Discord-blue?style=for-the-badge&logo=discord&color=5865f2&logoColor=fff)](https://aka.ms/foundry/discord)

Якщо у вас є відгуки про продукт або виникають помилки під час розробки, відвідайте:

[![Форум розробників Azure AI Foundry](https://img.shields.io/badge/GitHub-Azure_AI_Foundry_Developer_Forum-blue?style=for-the-badge&logo=github&color=000000&logoColor=fff)](https://aka.ms/foundry/forum)

---

**Відмова від відповідальності**:  
Цей документ був перекладений за допомогою сервісу автоматичного перекладу [Co-op Translator](https://github.com/Azure/co-op-translator). Хоча ми прагнемо до точності, будь ласка, майте на увазі, що автоматичні переклади можуть містити помилки або неточності. Оригінальний документ на його рідній мові слід вважати авторитетним джерелом. Для критичної інформації рекомендується професійний людський переклад. Ми не несемо відповідальності за будь-які непорозуміння або неправильні тлумачення, що виникають внаслідок використання цього перекладу.