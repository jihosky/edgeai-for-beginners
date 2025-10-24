<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8f958250b0b94976c721e6cbdc541581",
  "translation_date": "2025-10-24T10:04:07+00:00",
  "source_file": "README.md",
  "language_code": "sl"
}
-->
# EdgeAI za začetnike

![Slika naslovnice tečaja](../../translated_images/cover.eb18d1b9605d754b30973f4e17c6e11ea4f8473d9686ee378d6e7b44e3c70ac7.sl.png)

[![GitHub contributors](https://img.shields.io/github/contributors/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/graphs/contributors)  
[![GitHub issues](https://img.shields.io/github/issues/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/issues)  
[![GitHub pull-requests](https://img.shields.io/github/issues-pr/microsoft/edgeai-for-beginners.svg)](https://GitHub.com/microsoft/edgeai-for-beginners/pulls)  
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)  

[![GitHub watchers](https://img.shields.io/github/watchers/microsoft/edgeai-for-beginners.svg?style=social&label=Watch)](https://GitHub.com/microsoft/edgeai-for-beginners/watchers)  
[![GitHub forks](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)  
[![GitHub stars](https://img.shields.io/github/stars/microsoft/edgeai-for-beginners?style=social&label=Star)](https://GitHub.com/microsoft/edgeai-for-beginners/stargazers)  

[![Microsoft Azure AI Foundry Discord](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://discord.com/invite/ByRwuEEgH4)

Sledite tem korakom, da začnete uporabljati te vire:

1. **Forkajte repozitorij**: Kliknite [![GitHub forks](https://img.shields.io/github/forks/microsoft/edgeai-for-beginners.svg?style=social&label=Fork)](https://GitHub.com/microsoft/edgeai-for-beginners/fork)  
2. **Klonirajte repozitorij**: `git clone https://github.com/microsoft/edgeai-for-beginners.git`  
3. [**Pridružite se Azure AI Foundry Discordu in spoznajte strokovnjake ter druge razvijalce**](https://discord.com/invite/ByRwuEEgH4)

### 🌐 Podpora za več jezikov

#### Podprto prek GitHub Action (samodejno in vedno posodobljeno)

[Arabic](../ar/README.md) | [Bengali](../bn/README.md) | [Bulgarian](../bg/README.md) | [Burmese (Myanmar)](../my/README.md) | [Chinese (Simplified)](../zh/README.md) | [Chinese (Traditional, Hong Kong)](../hk/README.md) | [Chinese (Traditional, Macau)](../mo/README.md) | [Chinese (Traditional, Taiwan)](../tw/README.md) | [Croatian](../hr/README.md) | [Czech](../cs/README.md) | [Danish](../da/README.md) | [Dutch](../nl/README.md) | [Estonian](../et/README.md) | [Finnish](../fi/README.md) | [French](../fr/README.md) | [German](../de/README.md) | [Greek](../el/README.md) | [Hebrew](../he/README.md) | [Hindi](../hi/README.md) | [Hungarian](../hu/README.md) | [Indonesian](../id/README.md) | [Italian](../it/README.md) | [Japanese](../ja/README.md) | [Korean](../ko/README.md) | [Lithuanian](../lt/README.md) | [Malay](../ms/README.md) | [Marathi](../mr/README.md) | [Nepali](../ne/README.md) | [Norwegian](../no/README.md) | [Persian (Farsi)](../fa/README.md) | [Polish](../pl/README.md) | [Portuguese (Brazil)](../br/README.md) | [Portuguese (Portugal)](../pt/README.md) | [Punjabi (Gurmukhi)](../pa/README.md) | [Romanian](../ro/README.md) | [Russian](../ru/README.md) | [Serbian (Cyrillic)](../sr/README.md) | [Slovak](../sk/README.md) | [Slovenian](./README.md) | [Spanish](../es/README.md) | [Swahili](../sw/README.md) | [Swedish](../sv/README.md) | [Tagalog (Filipino)](../tl/README.md) | [Tamil](../ta/README.md) | [Thai](../th/README.md) | [Turkish](../tr/README.md) | [Ukrainian](../uk/README.md) | [Urdu](../ur/README.md) | [Vietnamese](../vi/README.md)

**Če želite dodati dodatne jezike, so podprti jeziki navedeni [tukaj](https://github.com/Azure/co-op-translator/blob/main/getting_started/supported-languages.md)**

## Uvod

Dobrodošli v **EdgeAI za začetnike** – vašem celovitem potovanju v preoblikovalni svet Edge umetne inteligence. Ta tečaj povezuje zmogljivosti AI z praktično uporabo na robnih napravah, kar vam omogoča, da izkoristite potencial AI tam, kjer se podatki ustvarjajo in kjer je treba sprejemati odločitve.

### Kaj boste obvladali

Ta tečaj vas vodi od osnovnih konceptov do implementacij, pripravljenih za proizvodnjo, in zajema:
- **Majhni jezikovni modeli (SLM)**, optimizirani za robno uporabo
- **Optimizacija glede na strojno opremo** na različnih platformah
- **Inferenca v realnem času** z ohranjanjem zasebnosti
- **Strategije za proizvodno uporabo** za poslovne aplikacije

### Zakaj je EdgeAI pomemben

Edge AI predstavlja premik paradigme, ki rešuje ključne sodobne izzive:
- **Zasebnost in varnost**: Obdelava občutljivih podatkov lokalno, brez izpostavljanja v oblaku
- **Zmogljivost v realnem času**: Odprava omrežne zakasnitve za časovno kritične aplikacije
- **Učinkovitost stroškov**: Zmanjšanje stroškov pasovne širine in računalništva v oblaku
- **Odporne operacije**: Delovanje tudi med izpadi omrežja
- **Skladnost z regulativami**: Izpolnjevanje zahtev glede suverenosti podatkov

### Edge AI

Edge AI se nanaša na izvajanje AI algoritmov in jezikovnih modelov lokalno na strojni opremi, blizu mesta, kjer se podatki ustvarjajo, brez odvisnosti od oblačnih virov za inferenco. Zmanjšuje zakasnitev, izboljšuje zasebnost in omogoča sprejemanje odločitev v realnem času.

### Osnovna načela:
- **Inferenca na napravi**: AI modeli se izvajajo na robnih napravah (telefoni, usmerjevalniki, mikrokrmilniki, industrijski računalniki)
- **Zmožnost delovanja brez povezave**: Delovanje brez stalne internetne povezave
- **Nizka zakasnitev**: Takojšnji odzivi, primerni za sisteme v realnem času
- **Suverenost podatkov**: Občutljivi podatki ostanejo lokalni, kar izboljša varnost in skladnost

### Majhni jezikovni modeli (SLM)

SLM, kot so Phi-4, Mistral-7B in Gemma, so optimizirane različice večjih LLM – trenirane ali destilirane za:
- **Zmanjšano porabo pomnilnika**: Učinkovita uporaba omejenega pomnilnika robnih naprav
- **Manjše zahteve po računalniški moči**: Optimizirano za delovanje na CPU in robnih GPU
- **Hitrejši zagonski čas**: Hitro inicializacijo za odzivne aplikacije

Omogočajo zmogljive NLP funkcionalnosti, hkrati pa izpolnjujejo omejitve:
- **Vgrajeni sistemi**: IoT naprave in industrijski krmilniki
- **Mobilne naprave**: Pametni telefoni in tablice z zmožnostjo delovanja brez povezave
- **IoT naprave**: Senzorji in pametne naprave z omejenimi viri
- **Robni strežniki**: Lokalni procesni enoti z omejenimi GPU viri
- **Osebni računalniki**: Scenariji uporabe na namiznih in prenosnih računalnikih

## Moduli tečaja in navigacija

| Modul | Tema | Osrednje področje | Ključna vsebina | Stopnja | Trajanje |
|-------|------|-------------------|-----------------|---------|----------|
| [📖 00 ](./introduction.md) | [Uvod v EdgeAI](./introduction.md) | Osnove in kontekst | Pregled EdgeAI • Industrijske aplikacije • Uvod v SLM • Cilji učenja | Začetnik | 1-2 ure |
| [📚 01](../../Module01) | [Osnove EdgeAI](./Module01/README.md) | Primerjava med oblakom in Edge AI | Osnove EdgeAI • Primeri iz resničnega sveta • Vodnik za implementacijo • Robna uporaba | Začetnik | 3-4 ure |
| [🧠 02](../../Module02) | [Osnove modelov SLM](./Module02/README.md) | Družine modelov in arhitektura | Družina Phi • Družina Qwen • Družina Gemma • BitNET • μModel • Phi-Silica | Začetnik | 4-5 ur |
| [🚀 03](../../Module03) | [Praksa uporabe SLM](./Module03/README.md) | Lokalna in oblačna uporaba | Napredno učenje • Lokalno okolje • Uporaba v oblaku | Srednje | 4-5 ur |
| [⚙️ 04](../../Module04) | [Orodje za optimizacijo modelov](./Module04/README.md) | Optimizacija za različne platforme | Uvod • Llama.cpp • Microsoft Olive • OpenVINO • Apple MLX • Sinteza delovnih tokov | Srednje | 5-6 ur |
| [🔧 05](../../Module05) | [SLMOps proizvodnja](./Module05/README.md) | Operacije v proizvodnji | Uvod v SLMOps • Destilacija modelov • Fino prilagajanje • Uporaba v proizvodnji | Napredno | 5-6 ur |
| [🤖 06](../../Module06) | [AI agenti in klicanje funkcij](./Module06/README.md) | Okviri agentov in MCP | Uvod v agente • Klicanje funkcij • Protokol konteksta modela | Napredno | 4-5 ur |
| [💻 07](../../Module07) | [Implementacija platforme](./Module07/README.md) | Primeri za različne platforme | Orodje AI • Foundry Local • Razvoj za Windows | Napredno | 3-4 ure |
| [🏭 08](../../Module08) | [Orodje Foundry Local](./Module08/README.md) | Primeri, pripravljeni za proizvodnjo | Primeri aplikacij (glejte podrobnosti spodaj) | Strokovnjak | 8-10 ur |

### 🏭 **Modul 08: Primeri aplikacij**

- [01: REST Chat Quickstart](./Module08/samples/01/README.md)  
- [02: Integracija OpenAI SDK](./Module08/samples/02/README.md)  
- [03: Odkritje modelov in primerjava](./Module08/samples/03/README.md)  
- [04: Chainlit RAG aplikacija](./Module08/samples/04/README.md)  
- [05: Orkestracija več agentov](./Module08/samples/05/README.md)  
- [06: Usmerjevalnik modelov kot orodij](./Module08/samples/06/README.md)  
- [07: Neposredni API odjemalec](./Module08/samples/07/README.md)  
- [08: Windows 11 aplikacija za klepet](./Module08/samples/08/README.md)  
- [09: Napreden sistem več agentov](./Module08/samples/09/README.md)  
- [10: Okvir orodij Foundry](./Module08/samples/10/README.md)

### 🎓 **Delavnica: Praktična učna pot**

Celoviti materiali za delavnico s proizvodno pripravljenimi implementacijami:

- **[Vodnik za delavnico](./Workshop/Readme.md)** - Celotni cilji učenja, rezultati in navigacija po virih  
- **Python primeri** (6 sej) - Posodobljeni z najboljšimi praksami, obravnavo napak in celovito dokumentacijo  
- **Jupyter zvezki** (8 interaktivnih) - Korak za korakom vadnice z meritvami in spremljanjem zmogljivosti  
- **Vodniki za seje** - Podrobni markdown vodniki za vsako sejo delavnice  
- **Orodja za validacijo** - Skripte za preverjanje kakovosti kode in izvajanje testov

**Kaj boste zgradili:**
- Lokalno AI aplikacijo za klepet s podporo za pretakanje  
- RAG pipeline z ocenjevanjem kakovosti (RAGAS)  
- Orodja za primerjavo in merjenje več modelov  
- Sisteme za orkestracijo več agentov  
- Inteligentno usmerjanje modelov z izbiro na podlagi nalog  

### 📊 **Povzetek učne poti**
- **Skupno trajanje**: 36-45 ur  
- **Pot za začetnike**: Moduli 01-02 (7-9 ur)  
- **Pot za srednje napredne**: Moduli 03-04 (9-11 ur)  
- **Pot za napredne**: Moduli 05-07 (12-15 ur)  
- **Pot za strokovnjake**: Modul 08 (8-10 ur)

## Kaj boste zgradili

### 🎯 Ključne kompetence
- **Arhitektura Edge AI**: Oblikovanje lokalno usmerjenih AI sistemov z integracijo v oblak  
- **Optimizacija modelov**: Kvantizacija in kompresija modelov za robno uporabo (85% hitrostni pospešek, 75% zmanjšanje velikosti)  
- **Uporaba na več platformah**: Windows, mobilne naprave, vgrajeni sistemi in hibridni sistemi oblak-rob
- **Operacije v produkciji**: Spremljanje, skaliranje in vzdrževanje robne umetne inteligence v produkciji

### 🏗️ Praktični projekti
- **Foundry lokalne aplikacije za klepet**: Izvorna aplikacija za Windows 11 z možnostjo preklapljanja modelov
- **Sistemi z več agenti**: Koordinator s specializiranimi agenti za kompleksne delovne procese  
- **RAG aplikacije**: Lokalna obdelava dokumentov z iskanjem vektorjev
- **Usmerjevalniki modelov**: Inteligentna izbira med modeli na podlagi analize nalog
- **API ogrodja**: Produkcijsko pripravljene stranke s pretočnim prenosom in spremljanjem stanja
- **Orodja za več platform**: Vzorci integracije LangChain/Semantic Kernel

### 🏢 Industrijske aplikacije
**Proizvodnja** • **Zdravstvo** • **Avtonomna vozila** • **Pametna mesta** • **Mobilne aplikacije**

## Hiter začetek

**Priporočena učna pot** (skupno 20-30 ur):

0. **📖 Uvod** ([Introduction.md](./introduction.md)): Osnove EdgeAI + industrijski kontekst + učni okvir
1. **📚 Osnove** (Moduli 01-02): Koncepti EdgeAI + družine modelov SLM
2. **⚙️ Optimizacija** (Moduli 03-04): Implementacija + ogrodja za kvantizacijo  
3. **🚀 Produkcija** (Moduli 05-06): SLMOps + AI agenti + klicanje funkcij
4. **💻 Implementacija** (Moduli 07-08): Vzorci platform + orodje Foundry Local

Vsak modul vključuje teorijo, praktične vaje in produkcijsko pripravljene vzorce kode.

## Vpliv na kariero

**Tehnične vloge**: Arhitekt rešitev EdgeAI • ML inženir (Edge) • IoT AI razvijalec • Mobilni AI razvijalec

**Industrijski sektorji**: Proizvodnja 4.0 • Zdravstvena tehnologija • Avtonomni sistemi • FinTech • Potrošniška elektronika

**Projekti za portfelj**: Sistemi z več agenti • Produkcijske RAG aplikacije • Implementacija na več platformah • Optimizacija zmogljivosti

## Struktura repozitorija

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

## Poudarki tečaja

✅ **Postopno učenje**: Teorija → Praksa → Implementacija v produkciji  
✅ **Resnične študije primerov**: Microsoft, Japan Airlines, implementacije v podjetjih  
✅ **Praktični vzorci**: 50+ primerov, 10 celovitih demo projektov Foundry Local  
✅ **Osredotočenost na zmogljivost**: 85% izboljšanje hitrosti, 75% zmanjšanje velikosti  
✅ **Več platform**: Windows, mobilne naprave, vgrajeni sistemi, hibridni oblak-rob  
✅ **Pripravljeno za produkcijo**: Spremljanje, skaliranje, varnost, okvirji skladnosti

📖 **[Na voljo učni vodič](STUDY_GUIDE.md)**: Strukturirana 20-urna učna pot z navodili za razporeditev časa in orodji za samoocenjevanje.

---

**EdgeAI predstavlja prihodnost implementacije umetne inteligence**: lokalno usmerjeno, z ohranjanjem zasebnosti in učinkovito. Obvladovanje teh veščin vam omogoča gradnjo naslednje generacije inteligentnih aplikacij.

## Drugi tečaji

Naša ekipa pripravlja tudi druge tečaje! Oglejte si:

### Azure / Edge / MCP / Agenti
[![AZD za začetnike](https://img.shields.io/badge/AZD%20za%20začetnike-0078D4?style=for-the-badge&labelColor=E5E7EB&color=0078D4)](https://github.com/microsoft/AZD-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Edge AI za začetnike](https://img.shields.io/badge/Edge%20AI%20za%20začetnike-00B8E4?style=for-the-badge&labelColor=E5E7EB&color=00B8E4)](https://github.com/microsoft/edgeai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![MCP za začetnike](https://img.shields.io/badge/MCP%20za%20začetnike-009688?style=for-the-badge&labelColor=E5E7EB&color=009688)](https://github.com/microsoft/mcp-for-beginners?WT.mc_id=academic-105485-koreyst)
[![AI agenti za začetnike](https://img.shields.io/badge/AI%20agenti%20za%20začetnike-00C49A?style=for-the-badge&labelColor=E5E7EB&color=00C49A)](https://github.com/microsoft/ai-agents-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Serija generativne umetne inteligence
[![Generativna AI za začetnike](https://img.shields.io/badge/Generativna%20AI%20za%20začetnike-8B5CF6?style=for-the-badge&labelColor=E5E7EB&color=8B5CF6)](https://github.com/microsoft/generative-ai-for-beginners?WT.mc_id=academic-105485-koreyst)
[![Generativna AI (.NET)](https://img.shields.io/badge/Generativna%20AI%20(.NET)-9333EA?style=for-the-badge&labelColor=E5E7EB&color=9333EA)](https://github.com/microsoft/Generative-AI-for-beginners-dotnet?WT.mc_id=academic-105485-koreyst)
[![Generativna AI (Java)](https://img.shields.io/badge/Generativna%20AI%20(Java)-C084FC?style=for-the-badge&labelColor=E5E7EB&color=C084FC)](https://github.com/microsoft/generative-ai-for-beginners-java?WT.mc_id=academic-105485-koreyst)
[![Generativna AI (JavaScript)](https://img.shields.io/badge/Generativna%20AI%20(JavaScript)-E879F9?style=for-the-badge&labelColor=E5E7EB&color=E879F9)](https://github.com/microsoft/generative-ai-with-javascript?WT.mc_id=academic-105485-koreyst)

---

### Osnovno učenje
[![ML za začetnike](https://img.shields.io/badge/ML%20za%20začetnike-22C55E?style=for-the-badge&labelColor=E5E7EB&color=22C55E)](https://aka.ms/ml-beginners?WT.mc_id=academic-105485-koreyst)
[![Podatkovna znanost za začetnike](https://img.shields.io/badge/Podatkovna%20znanost%20za%20začetnike-84CC16?style=for-the-badge&labelColor=E5E7EB&color=84CC16)](https://aka.ms/datascience-beginners?WT.mc_id=academic-105485-koreyst)
[![AI za začetnike](https://img.shields.io/badge/AI%20za%20začetnike-A3E635?style=for-the-badge&labelColor=E5E7EB&color=A3E635)](https://aka.ms/ai-beginners?WT.mc_id=academic-105485-koreyst)
[![Kibernetska varnost za začetnike](https://img.shields.io/badge/Kibernetska%20varnost%20za%20začetnike-F97316?style=for-the-badge&labelColor=E5E7EB&color=F97316)](https://github.com/microsoft/Security-101?WT.mc_id=academic-96948-sayoung)
[![Razvoj spletnih aplikacij za začetnike](https://img.shields.io/badge/Razvoj%20spletnih%20aplikacij%20za%20začetnike-EC4899?style=for-the-badge&labelColor=E5E7EB&color=EC4899)](https://aka.ms/webdev-beginners?WT.mc_id=academic-105485-koreyst)
[![IoT za začetnike](https://img.shields.io/badge/IoT%20za%20začetnike-14B8A6?style=for-the-badge&labelColor=E5E7EB&color=14B8A6)](https://aka.ms/iot-beginners?WT.mc_id=academic-105485-koreyst)
[![XR razvoj za začetnike](https://img.shields.io/badge/XR%20razvoj%20za%20začetnike-38BDF8?style=for-the-badge&labelColor=E5E7EB&color=38BDF8)](https://github.com/microsoft/xr-development-for-beginners?WT.mc_id=academic-105485-koreyst)

---

### Serija Copilot
[![Copilot za AI parno programiranje](https://img.shields.io/badge/Copilot%20za%20AI%20parno%20programiranje-FACC15?style=for-the-badge&labelColor=E5E7EB&color=FACC15)](https://aka.ms/GitHubCopilotAI?WT.mc_id=academic-105485-koreyst)
[![Copilot za C#/.NET](https://img.shields.io/badge/Copilot%20za%20C%23/.NET-FBBF24?style=for-the-badge&labelColor=E5E7EB&color=FBBF24)](https://github.com/microsoft/mastering-github-copilot-for-dotnet-csharp-developers?WT.mc_id=academic-105485-koreyst)
[![Copilot pustolovščina](https://img.shields.io/badge/Copilot%20pustolovščina-FDE68A?style=for-the-badge&labelColor=E5E7EB&color=FDE68A)](https://github.com/microsoft/CopilotAdventures?WT.mc_id=academic-105485-koreyst)

## Pomoč

Če se zataknete ali imate kakršna koli vprašanja o gradnji AI aplikacij, se pridružite:

[![Azure AI Foundry Discord](https://img.shields.io/badge/Discord-Azure_AI_Foundry_Community_Discord-blue?style=for-the-badge&logo=discord&color=5865f2&logoColor=fff)](https://aka.ms/foundry/discord)

Če imate povratne informacije o izdelku ali naletite na napake med gradnjo, obiščite:

[![Azure AI Foundry Developer Forum](https://img.shields.io/badge/GitHub-Azure_AI_Foundry_Developer_Forum-blue?style=for-the-badge&logo=github&color=000000&logoColor=fff)](https://aka.ms/foundry/forum)

---

**Omejitev odgovornosti**:  
Ta dokument je bil preveden z uporabo storitve za prevajanje AI [Co-op Translator](https://github.com/Azure/co-op-translator). Čeprav si prizadevamo za natančnost, vas prosimo, da upoštevate, da lahko avtomatizirani prevodi vsebujejo napake ali netočnosti. Izvirni dokument v njegovem maternem jeziku je treba obravnavati kot avtoritativni vir. Za ključne informacije priporočamo profesionalni človeški prevod. Ne prevzemamo odgovornosti za morebitne nesporazume ali napačne razlage, ki izhajajo iz uporabe tega prevoda.