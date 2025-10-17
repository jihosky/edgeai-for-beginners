<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b994c57f1207012e4d7f58b7c0d1ae7",
  "translation_date": "2025-10-17T09:30:18+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "pa"
}
-->
# EdgeAI ਸ਼ੁਰੂਆਤੀ ਲਈ - ਵਰਕਸ਼ਾਪ

> **ਪ੍ਰੋਡਕਸ਼ਨ-ਤਿਆਰ ਐਜ AI ਐਪਲੀਕੇਸ਼ਨ ਬਣਾਉਣ ਲਈ ਹੈਂਡਸ-ਆਨ ਲਰਨਿੰਗ ਪਾਥ**
>
> Microsoft Foundry Local ਨਾਲ ਸਥਾਨਕ AI ਡਿਪਲੌਇਮੈਂਟ ਵਿੱਚ ਮਾਹਰ ਬਣੋ, ਪਹਿਲੀ ਚੈਟ ਕਮਪਲੀਸ਼ਨ ਤੋਂ ਲੈ ਕੇ 6 ਤਰੱਕੀਸ਼ੀਲ ਸੈਸ਼ਨਾਂ ਵਿੱਚ ਮਲਟੀ-ਏਜੰਟ ਆਰਕੇਸਟ੍ਰੇਸ਼ਨ ਤੱਕ।

---

## 🎯 ਪਰਿਚਯ

**ਐਜ AI ਸ਼ੁਰੂਆਤੀ ਲਈ ਵਰਕਸ਼ਾਪ** ਵਿੱਚ ਤੁਹਾਡਾ ਸਵਾਗਤ ਹੈ - ਸਥਾਨਕ ਹਾਰਡਵੇਅਰ 'ਤੇ ਪੂਰੀ ਤਰ੍ਹਾਂ ਚੱਲਣ ਵਾਲੀਆਂ ਬੁੱਧੀਮਾਨ ਐਪਲੀਕੇਸ਼ਨ ਬਣਾਉਣ ਲਈ ਤੁਹਾਡਾ ਪ੍ਰੈਕਟਿਕਲ, ਹੈਂਡਸ-ਆਨ ਗਾਈਡ। ਇਹ ਵਰਕਸ਼ਾਪ ਸਿਧਾਂਤਕ ਐਜ AI ਧਾਰਨਾਵਾਂ ਨੂੰ ਵਾਸਤਵਿਕ ਦੁਨੀਆ ਦੇ ਹੁਨਰਾਂ ਵਿੱਚ ਬਦਲ ਦਿੰਦੀ ਹੈ, ਜੋ ਕਿ Microsoft Foundry Local ਅਤੇ Small Language Models (SLMs) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਤਰੱਕੀਸ਼ੀਲ ਚੁਣੌਤੀਪੂਰਨ ਅਭਿਆਸਾਂ ਰਾਹੀਂ।

### ਇਹ ਵਰਕਸ਼ਾਪ ਕਿਉਂ?

**ਐਜ AI ਇਨਕਲਾਬ ਆ ਗਿਆ ਹੈ**

ਸੰਸਾਰ ਭਰ ਵਿੱਚ ਸੰਗਠਨ ਤਿੰਨ ਮਹੱਤਵਪੂਰਨ ਕਾਰਨਾਂ ਲਈ ਕਲਾਉਡ-ਨਿਰਭਰ AI ਤੋਂ ਐਜ ਕੰਪਿਊਟਿੰਗ ਵੱਲ ਬਦਲ ਰਹੇ ਹਨ:

1. **ਪ੍ਰਾਈਵੇਸੀ ਅਤੇ ਕਾਨੂੰਨੀ ਪਾਲਣਾ** - ਸੰਵੇਦਨਸ਼ੀਲ ਡਾਟਾ ਨੂੰ ਸਥਾਨਕ ਤੌਰ 'ਤੇ ਪ੍ਰੋਸੈਸ ਕਰੋ ਬਿਨਾਂ ਕਲਾਉਡ ਟ੍ਰਾਂਸਮਿਸ਼ਨ ਦੇ (HIPAA, GDPR, ਵਿੱਤੀ ਨਿਯਮ)
2. **ਪ੍ਰਦਰਸ਼ਨ** - ਨੈਟਵਰਕ ਲੈਟੈਂਸੀ ਨੂੰ ਖਤਮ ਕਰੋ (50-500ms ਸਥਾਨਕ ਵਿਰੁੱਧ 500-2000ms ਕਲਾਉਡ ਰਾਊਂਡ-ਟ੍ਰਿਪ)
3. **ਲਾਗਤ ਦਾ ਨਿਯੰਤਰਣ** - ਪ੍ਰਤੀ-ਟੋਕਨ API ਲਾਗਤਾਂ ਨੂੰ ਹਟਾਓ ਅਤੇ ਕਲਾਉਡ ਖਰਚਿਆਂ ਤੋਂ ਬਿਨਾਂ ਸਕੇਲ ਕਰੋ

**ਪਰ ਐਜ AI ਵੱਖਰਾ ਹੈ**

ਸਥਾਨਕ ਤੌਰ 'ਤੇ AI ਚਲਾਉਣ ਲਈ ਨਵੇਂ ਹੁਨਰਾਂ ਦੀ ਲੋੜ ਹੁੰਦੀ ਹੈ:
- ਮਾਡਲ ਦੀ ਚੋਣ ਅਤੇ ਸੰਸਾਧਨ ਦੀਆਂ ਪਾਬੰਦੀਆਂ ਲਈ ਅਨੁਕੂਲਤਾ
- ਸਥਾਨਕ ਸੇਵਾ ਪ੍ਰਬੰਧਨ ਅਤੇ ਹਾਰਡਵੇਅਰ ਐਕਸਲੇਰੇਸ਼ਨ
- ਛੋਟੇ ਮਾਡਲਾਂ ਲਈ ਪ੍ਰੋਮਪਟ ਇੰਜੀਨੀਅਰਿੰਗ
- ਐਜ ਡਿਵਾਈਸਾਂ ਲਈ ਪ੍ਰੋਡਕਸ਼ਨ ਡਿਪਲੌਇਮੈਂਟ ਪੈਟਰਨ

**ਇਹ ਵਰਕਸ਼ਾਪ ਉਹ ਹੁਨਰ ਪ੍ਰਦਾਨ ਕਰਦਾ ਹੈ**

6 ਕੇਂਦਰਿਤ ਸੈਸ਼ਨਾਂ (~3 ਘੰਟੇ ਕੁੱਲ), ਤੁਸੀਂ "ਹੈਲੋ ਵਰਲਡ" ਤੋਂ ਪ੍ਰੋਡਕਸ਼ਨ-ਤਿਆਰ ਮਲਟੀ-ਏਜੰਟ ਸਿਸਟਮਾਂ ਨੂੰ ਡਿਪਲੌਇ ਕਰਨ ਤੱਕ ਤਰੱਕੀ ਕਰੋਗੇ - ਸਾਰੇ ਤੁਹਾਡੇ ਮਸ਼ੀਨ 'ਤੇ ਸਥਾਨਕ ਤੌਰ 'ਤੇ ਚੱਲ ਰਹੇ ਹਨ।

---

## 📚 ਸਿੱਖਣ ਦੇ ਉਦੇਸ਼

ਇਸ ਵਰਕਸ਼ਾਪ ਨੂੰ ਪੂਰਾ ਕਰਨ ਦੁਆਰਾ, ਤੁਸੀਂ ਇਹ ਕਰਨ ਦੇ ਯੋਗ ਹੋਵੋਗੇ:

### ਮੁੱਖ ਯੋਗਤਾਵਾਂ
1. **ਸਥਾਨਕ AI ਸੇਵਾਵਾਂ ਨੂੰ ਡਿਪਲੌਇ ਅਤੇ ਪ੍ਰਬੰਧਿਤ ਕਰੋ**
   - Microsoft Foundry Local ਨੂੰ ਇੰਸਟਾਲ ਅਤੇ ਕਨਫਿਗਰ ਕਰੋ
   - ਐਜ ਡਿਪਲੌਇਮੈਂਟ ਲਈ ਉਚਿਤ ਮਾਡਲ ਚੁਣੋ
   - ਮਾਡਲ ਲਾਈਫਸਾਈਕਲ ਦਾ ਪ੍ਰਬੰਧਨ ਕਰੋ (ਡਾਊਨਲੋਡ, ਲੋਡ, ਕੈਸ਼)
   - ਸੰਸਾਧਨ ਦੀ ਵਰਤੋਂ ਦੀ ਨਿਗਰਾਨੀ ਕਰੋ ਅਤੇ ਪ੍ਰਦਰਸ਼ਨ ਨੂੰ ਅਨੁਕੂਲ ਬਣਾਓ

2. **AI-ਚਾਲਤ ਐਪਲੀਕੇਸ਼ਨ ਬਣਾਓ**
   - ਸਥਾਨਕ ਤੌਰ 'ਤੇ OpenAI-ਅਨੁਕੂਲ ਚੈਟ ਕਮਪਲੀਸ਼ਨ ਲਾਗੂ ਕਰੋ
   - Small Language Models ਲਈ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਪ੍ਰੋਮਪਟ ਡਿਜ਼ਾਈਨ ਕਰੋ
   - ਵਧੀਆ UX ਲਈ ਸਟ੍ਰੀਮਿੰਗ ਜਵਾਬਾਂ ਨੂੰ ਸੰਭਾਲੋ
   - ਸਥਾਨਕ ਮਾਡਲਾਂ ਨੂੰ ਮੌਜੂਦਾ ਐਪਲੀਕੇਸ਼ਨਾਂ ਵਿੱਚ ਇੰਟੀਗਰੇਟ ਕਰੋ

3. **RAG (Retrieval Augmented Generation) ਸਿਸਟਮ ਬਣਾਓ**
   - ਐਮਬੈਡਿੰਗ ਨਾਲ ਸੈਮੈਂਟਿਕ ਖੋਜ ਬਣਾਓ
   - LLM ਜਵਾਬਾਂ ਨੂੰ ਡੋਮੇਨ-ਵਿਸ਼ੇਸ਼ ਗਿਆਨ ਵਿੱਚ ਜਮ੍ਹਾ ਕਰੋ
   - ਉਦਯੋਗ-ਮਿਆਰੀ ਮਾਪਦੰਡਾਂ ਨਾਲ RAG ਗੁਣਵੱਤਾ ਦਾ ਮੁਲਾਂਕਨ ਕਰੋ
   - ਪ੍ਰੋਟੋਟਾਈਪ ਤੋਂ ਪ੍ਰੋਡਕਸ਼ਨ ਤੱਕ ਸਕੇਲ ਕਰੋ

4. **ਮਾਡਲ ਪ੍ਰਦਰਸ਼ਨ ਨੂੰ ਅਨੁਕੂਲ ਬਣਾਓ**
   - ਤੁਹਾਡੇ ਉਪਯੋਗ ਮਾਮਲੇ ਲਈ ਕਈ ਮਾਡਲਾਂ ਦਾ ਬੈਂਚਮਾਰਕ ਕਰੋ
   - ਲੈਟੈਂਸੀ, ਥਰੂਪੁੱਟ, ਅਤੇ ਪਹਿਲੇ ਟੋਕਨ ਸਮੇਂ ਨੂੰ ਮਾਪੋ
   - ਗਤੀ/ਗੁਣਵੱਤਾ ਦੇ ਵਪਾਰ-ਅਫਸਰਾਂ ਦੇ ਆਧਾਰ 'ਤੇ ਉਚਿਤ ਮਾਡਲ ਚੁਣੋ
   - ਅਸਲ ਸਥਿਤੀਆਂ ਵਿੱਚ SLM ਵਿਰੁੱਧ LLM ਵਪਾਰ-ਅਫਸਰਾਂ ਦੀ ਤੁਲਨਾ ਕਰੋ

5. **ਮਲਟੀ-ਏਜੰਟ ਸਿਸਟਮਾਂ ਨੂੰ ਆਰਕੇਸਟ੍ਰੇਟ ਕਰੋ**
   - ਵੱਖ-ਵੱਖ ਕੰਮਾਂ ਲਈ ਵਿਸ਼ੇਸ਼ ਏਜੰਟਾਂ ਨੂੰ ਡਿਜ਼ਾਈਨ ਕਰੋ
   - ਏਜੰਟ ਮੈਮਰੀ ਅਤੇ ਸੰਦਰਭ ਪ੍ਰਬੰਧਨ ਲਾਗੂ ਕਰੋ
   - ਜਟਿਲ ਵਰਕਫਲੋਜ਼ ਵਿੱਚ ਏਜੰਟਾਂ ਨੂੰ ਸਮਨਵਿਤ ਕਰੋ
   - ਕਈ ਮਾਡਲਾਂ ਵਿੱਚ ਬੁੱਧੀਮਾਨੀ ਨਾਲ ਬੇਨਤੀਆਂ ਨੂੰ ਰੂਟ ਕਰੋ

6. **ਪ੍ਰੋਡਕਸ਼ਨ-ਤਿਆਰ ਹੱਲਾਂ ਨੂੰ ਡਿਪਲੌਇ ਕਰੋ**
   - ਗਲਤੀ ਸੰਭਾਲਣ ਅਤੇ ਰੀਟ੍ਰਾਈ ਲਾਜਿਕ ਲਾਗੂ ਕਰੋ
   - ਟੋਕਨ ਦੀ ਵਰਤੋਂ ਅਤੇ ਸਿਸਟਮ ਸੰਸਾਧਨਾਂ ਦੀ ਨਿਗਰਾਨੀ ਕਰੋ
   - ਮਾਡਲ-ਜਿਵੇਂ-ਟੂਲ ਪੈਟਰਨ ਨਾਲ ਸਕੇਲਯੋਗ ਆਰਕੀਟੈਕਚਰ ਬਣਾਓ
   - ਐਜ ਤੋਂ ਹਾਈਬ੍ਰਿਡ (ਐਜ + ਕਲਾਉਡ) ਤੱਕ ਮਾਈਗ੍ਰੇਸ਼ਨ ਪਾਥਾਂ ਦੀ ਯੋਜਨਾ ਬਣਾਓ

---

## 🎓 ਸਿੱਖਣ ਦੇ ਨਤੀਜੇ

### ਤੁਸੀਂ ਕੀ ਬਣਾਓਗੇ

ਵਰਕਸ਼ਾਪ ਦੇ ਅੰਤ ਤੱਕ, ਤੁਸੀਂ ਇਹ ਬਣਾਉਣ ਵਿੱਚ ਸਫਲ ਹੋਵੋਗੇ:

| ਸੈਸ਼ਨ | ਡਿਲੀਵਰੇਬਲ | ਦਿਖਾਏ ਗਏ ਹੁਨਰ |
|---------|-------------|---------------------|
| **1** | ਸਟ੍ਰੀਮਿੰਗ ਨਾਲ ਚੈਟ ਐਪਲੀਕੇਸ਼ਨ | ਸੇਵਾ ਸੈਟਅਪ, ਬੁਨਿਆਦੀ ਕਮਪਲੀਸ਼ਨ, ਸਟ੍ਰੀਮਿੰਗ UX |
| **2** | RAG ਸਿਸਟਮ ਮੁਲਾਂਕਨ ਨਾਲ | ਐਮਬੈਡਿੰਗ, ਸੈਮੈਂਟਿਕ ਖੋਜ, ਗੁਣਵੱਤਾ ਮਾਪਦੰਡ |
| **3** | ਮਲਟੀ-ਮਾਡਲ ਬੈਂਚਮਾਰਕ ਸੂਟ | ਪ੍ਰਦਰਸ਼ਨ ਮਾਪ, ਮਾਡਲ ਤੁਲਨਾ |
| **4** | SLM ਵਿਰੁੱਧ LLM ਕੰਪੈਰੇਟਰ | ਵਪਾਰ-ਅਫਸਰ ਵਿਸ਼ਲੇਸ਼ਣ, ਅਨੁਕੂਲਤਾ ਰਣਨੀਤੀਆਂ |
| **5** | ਮਲਟੀ-ਏਜੰਟ ਆਰਕੇਸਟ੍ਰੇਟਰ | ਏਜੰਟ ਡਿਜ਼ਾਈਨ, ਮੈਮਰੀ ਪ੍ਰਬੰਧਨ, ਸਮਨਵਯ |
| **6** | ਬੁੱਧੀਮਾਨ ਰੂਟਿੰਗ ਸਿਸਟਮ | ਇਰਾਦਾ ਪਛਾਣ, ਮਾਡਲ ਚੋਣ, ਸਕੇਲਯੋਗਤਾ |

### ਯੋਗਤਾ ਮੈਟ੍ਰਿਕਸ

| ਹੁਨਰ ਪੱਧਰ | ਸੈਸ਼ਨ 1-2 | ਸੈਸ਼ਨ 3-4 | ਸੈਸ਼ਨ 5-6 |
|-------------|-------------|-------------|-------------|
| **ਸ਼ੁਰੂਆਤੀ** | ✅ ਸੈਟਅਪ ਅਤੇ ਬੁਨਿਆਦੀਆਂ | ⚠️ ਚੁਣੌਤੀਪੂਰਨ | ❌ ਬਹੁਤ ਅਗਰ |
| **ਮੱਧਮ** | ✅ ਤੇਜ਼ ਸਮੀਖਿਆ | ✅ ਮੁੱਖ ਸਿੱਖਣ | ⚠️ ਖਿੱਚ ਦੇ ਲਕਸ਼ |
| **ਅਗਰ** | ✅ ਆਸਾਨੀ ਨਾਲ | ✅ ਸੁਧਾਰ | ✅ ਪ੍ਰੋਡਕਸ਼ਨ ਪੈਟਰਨ |

### ਕਰੀਅਰ-ਤਿਆਰ ਹੁਨਰ

**ਇਸ ਵਰਕਸ਼ਾਪ ਦੇ ਬਾਅਦ, ਤੁਸੀਂ ਤਿਆਰ ਹੋਵੋਗੇ:**

✅ **ਪ੍ਰਾਈਵੇਸੀ-ਪਹਿਲਾਂ ਐਪਲੀਕੇਸ਼ਨ ਬਣਾਉਣ ਲਈ**
- ਸਥਾਨਕ ਤੌਰ 'ਤੇ PHI/PII ਨੂੰ ਸੰਭਾਲਣ ਵਾਲੀਆਂ ਹੈਲਥਕੇਅਰ ਐਪਸ
- ਕਾਨੂੰਨੀ ਪਾਲਣਾ ਦੀਆਂ ਲੋੜਾਂ ਵਾਲੀਆਂ ਵਿੱਤੀ ਸੇਵਾਵਾਂ
- ਡਾਟਾ ਸਵੈਰਾਜ ਦੀਆਂ ਲੋੜਾਂ ਵਾਲੇ ਸਰਕਾਰੀ ਸਿਸਟਮ

✅ **ਐਜ ਵਾਤਾਵਰਣਾਂ ਲਈ ਅਨੁਕੂਲਤਾ**
- ਸੀਮਿਤ ਸੰਸਾਧਨਾਂ ਵਾਲੇ IoT ਡਿਵਾਈਸ
- ਆਫਲਾਈਨ-ਪਹਿਲਾਂ ਮੋਬਾਈਲ ਐਪਲੀਕੇਸ਼ਨ
- ਘੱਟ-ਲੈਟੈਂਸੀ ਰੀਅਲ-ਟਾਈਮ ਸਿਸਟਮ

✅ **ਬੁੱਧੀਮਾਨ ਆਰਕੀਟੈਕਚਰ ਡਿਜ਼ਾਈਨ ਕਰੋ**
- ਜਟਿਲ ਵਰਕਫਲੋਜ਼ ਲਈ ਮਲਟੀ-ਏਜੰਟ ਸਿਸਟਮ
- ਹਾਈਬ੍ਰਿਡ ਐਜ-ਕਲਾਉਡ ਡਿਪਲੌਇਮੈਂਟ
- ਲਾਗਤ-ਅਨੁਕੂਲ AI ਇੰਫਰਾਸਟਰਕਚਰ

✅ **ਐਜ AI ਪਹਲਾਂ ਦੀ ਅਗਵਾਈ ਕਰੋ**
- ਪ੍ਰੋਜੈਕਟਾਂ ਲਈ ਐਜ AI ਸੰਭਾਵਨਾ ਦਾ ਮੁਲਾਂਕਨ ਕਰੋ
- ਉਚਿਤ ਮਾਡਲ ਅਤੇ ਫਰੇਮਵਰਕ ਚੁਣੋ
- ਸਕੇਲਯੋਗ ਸਥਾਨਕ AI ਹੱਲਾਂ ਦੀ ਆਰਕੀਟੈਕਚਰ ਬਣਾਓ

---

## 🗺️ ਵਰਕਸ਼ਾਪ ਦੀ ਬਣਤਰ

### ਸੈਸ਼ਨ ਝਲਕ (6 ਸੈਸ਼ਨ × 30 ਮਿੰਟ = 3 ਘੰਟੇ)

| ਸੈਸ਼ਨ | ਵਿਸ਼ਾ | ਕੇਂਦਰ | ਅੰਤਰਾਲ |
|---------|-------|-------|----------|
| **1** | Foundry Local ਨਾਲ ਸ਼ੁਰੂਆਤ | ਇੰਸਟਾਲ, ਵੈਧਤਾ, ਪਹਿਲੀ ਕਮਪਲੀਸ਼ਨ | 30 ਮਿੰਟ |
| **2** | RAG ਨਾਲ AI ਹੱਲ ਬਣਾਉਣਾ | ਪ੍ਰੋਮਪਟ ਇੰਜੀਨੀਅਰਿੰਗ, ਐਮਬੈਡਿੰਗ, ਮੁਲਾਂਕਨ | 30 ਮਿੰਟ |
| **3** | ਖੁੱਲ੍ਹੇ ਸਰੋਤ ਮਾਡਲ | ਮਾਡਲ ਖੋਜ, ਬੈਂਚਮਾਰਕਿੰਗ, ਚੋਣ | 30 ਮਿੰਟ |
| **4** | ਕੱਟਿੰਗ ਐਜ ਮਾਡਲ | SLM ਵਿਰੁੱਧ LLM, ਅਨੁਕੂਲਤਾ, ਫਰੇਮਵਰਕ | 30 ਮਿੰਟ |
| **5** | AI-ਚਾਲਤ ਏਜੰਟ | ਏਜੰਟ ਡਿਜ਼ਾਈਨ, ਆਰਕੇਸਟ੍ਰੇਸ਼ਨ, ਮੈਮਰੀ | 30 ਮਿੰਟ |
| **6** | ਮਾਡਲ ਜਿਵੇਂ ਟੂਲ | ਰੂਟਿੰਗ, ਚੇਨਿੰਗ, ਸਕੇਲਿੰਗ ਰਣਨੀਤੀਆਂ | 30 ਮਿੰਟ |

---

## 🚀 ਤੇਜ਼ ਸ਼ੁਰੂਆਤ

### ਪੂਰਵ ਸ਼ਰਤਾਂ

**ਸਿਸਟਮ ਦੀਆਂ ਲੋੜਾਂ:**
- **OS**: Windows 10/11, macOS 11+, ਜਾਂ Linux (Ubuntu 20.04+)
- **RAM**: ਘੱਟੋ-ਘੱਟ 8GB, 16GB+ ਸਿਫਾਰਸ਼ੀ
- **ਸਟੋਰੇਜ**: ਮਾਡਲਾਂ ਲਈ 10GB+ ਖਾਲੀ ਸਥਾਨ
- **CPU**: AVX2 ਸਹਾਇਕ ਮਾਡਰਨ ਪ੍ਰੋਸੈਸਰ
- **GPU** (ਵਿਕਲਪਿਕ): CUDA-ਅਨੁਕੂਲ ਜਾਂ Qualcomm NPU ਐਕਸਲੇਰੇਸ਼ਨ ਲਈ

**ਸੌਫਟਵੇਅਰ ਦੀਆਂ ਲੋੜਾਂ:**
- **Python 3.8+** ([ਡਾਊਨਲੋਡ](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([ਇੰਸਟਾਲੇਸ਼ਨ ਗਾਈਡ](../../../Workshop))
- **Git** ([ਡਾਊਨਲੋਡ](https://git-scm.com/downloads))
- **Visual Studio Code** (ਸਿਫਾਰਸ਼ੀ) ([ਡਾਊਨਲੋਡ](https://code.visualstudio.com/))

### 3 ਕਦਮਾਂ ਵਿੱਚ ਸੈਟਅਪ

#### 1. Foundry Local ਇੰਸਟਾਲ ਕਰੋ

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**ਇੰਸਟਾਲੇਸ਼ਨ ਦੀ ਪੁਸ਼ਟੀ ਕਰੋ:**
```bash
foundry --version
foundry service status
```

**ਯਕੀਨੀ ਬਣਾਓ ਕਿ Azure AI Foundry Local ਇੱਕ ਫਿਕਸਡ ਪੋਰਟ ਨਾਲ ਚੱਲ ਰਿਹਾ ਹੈ**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**ਇਸ ਦੀ ਪੁਸ਼ਟੀ ਕਰੋ ਕਿ ਇਹ ਕੰਮ ਕਰ ਰਿਹਾ ਹੈ:**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**ਉਪਲਬਧ ਮਾਡਲ ਲੱਭਣਾ**
ਤੁਹਾਡੇ Foundry Local ਇੰਸਟੈਂਸ ਵਿੱਚ ਕਿਹੜੇ ਮਾਡਲ ਉਪਲਬਧ ਹਨ, ਇਹ ਦੇਖਣ ਲਈ ਤੁਸੀਂ ਮਾਡਲ ਐਂਡਪੌਇੰਟ ਨੂੰ ਪੁੱਛ ਸਕਦੇ ਹੋ:

```bash
# cmd/bash/powershell
foundry model list
```

ਵੈੱਬ ਐਂਡਪੌਇੰਟ ਦੀ ਵਰਤੋਂ ਕਰਕੇ 

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### 2. ਰਿਪੋਜ਼ਟਰੀ ਕਲੋਨ ਕਰੋ ਅਤੇ ਡਿਪੈਂਡੈਂਸੀਜ਼ ਇੰਸਟਾਲ ਕਰੋ

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

#### 3. ਆਪਣਾ ਪਹਿਲਾ ਸੈਂਪਲ ਚਲਾਓ

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples/session01
python chat_bootstrap.py "What is edge AI?"
```

**✅ ਸਫਲਤਾ!** ਤੁਹਾਨੂੰ ਐਜ AI ਬਾਰੇ ਸਟ੍ਰੀਮਿੰਗ ਜਵਾਬ ਦੇਖਣਾ ਚਾਹੀਦਾ ਹੈ।

---

## 📦 ਵਰਕਸ਼ਾਪ ਸਰੋਤ

### Python ਸੈਂਪਲ

ਹਰ ਧਾਰਨਾ ਨੂੰ ਦਰਸਾਉਣ ਵਾਲੇ ਤਰੱਕੀਸ਼ੀਲ ਹੈਂਡਸ-ਆਨ ਉਦਾਹਰਨ:

| ਸੈਸ਼ਨ | ਸੈਂਪਲ | ਵੇਰਵਾ | ਚਲਾਉਣ ਦਾ ਸਮਾਂ |
|---------|--------|-------------|----------|
| 1 | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | ਬੁਨਿਆਦੀ ਅਤੇ ਸਟ੍ਰੀਮਿੰਗ ਚੈਟ | ~30ਸ |
| 2 | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | ਐਮਬੈਡਿੰਗ ਨਾਲ RAG | ~45ਸ |
| 2 | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | RAG ਗੁਣਵੱਤਾ ਮੁਲਾਂਕਨ | ~60ਸ |
| 3 | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | ਮਲਟੀ-ਮਾਡਲ ਬੈਂਚਮਾਰਕਿੰਗ | ~2-3ਮਿੰਟ |
| 4 | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | SLM ਵਿਰੁੱਧ LLM ਤੁਲਨਾ | ~45ਸ |
| 5 | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | ਮਲਟੀ-ਏਜੰਟ ਸਿਸਟਮ | ~60ਸ |
| 6 | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | ਇਰਾਦਾ-ਅਧਾਰਿਤ ਰੂਟਿੰਗ | ~45ਸ |
| 6 | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | ਮਲਟੀ-ਸਟੈਪ ਪਾਈਪਲਾਈਨ | ~60ਸ |

### Jupyter ਨੋਟਬੁੱਕ

ਵਿਆਖਿਆਵਾਂ ਅਤੇ ਵਿਜ਼ੁਅਲਾਈਜ਼ੇਸ਼ਨ ਨਾਲ ਇੰਟਰੈਕਟਿਵ ਖੋਜ:

| ਸੈਸ਼ਨ | ਨੋਟਬੁੱਕ | ਵੇਰਵਾ | ਮੁਸ਼ਕਲਤਾ |
|---------|----------|-------------|------------|
| 1 | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | ਚੈਟ ਬੁਨਿਆਦੀਆਂ ਅਤੇ ਸਟ੍ਰੀਮਿੰਗ | ⭐ ਸ਼ੁਰੂਆਤੀ |
| 2 | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | SLM ਅਤੇ LLM ਦੀ ਤੁਲਨਾ, WebGPU, Chainlit RAG, ONNX ਤੇਜ਼ੀ |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | ਏਜੰਟ ਦੀਆਂ ਭੂਮਿਕਾਵਾਂ, ਯਾਦ, ਟੂਲ, ਸੰਗਠਨ |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | ਰੂਟਿੰਗ, ਚੇਨਿੰਗ, Azure ਲਈ ਸਕੇਲਿੰਗ ਪਾਥ |

ਹਰ ਸੈਸ਼ਨ ਫਾਈਲ ਵਿੱਚ ਸ਼ਾਮਲ ਹੈ: ਸੰਖੇਪ, ਸਿੱਖਣ ਦੇ ਉਦੇਸ਼, 30‑ਮਿੰਟ ਡੈਮੋ ਫਲੋ, ਸ਼ੁਰੂਆਤੀ ਪ੍ਰੋਜੈਕਟ, ਵੈਧਤਾ ਚੈੱਕਲਿਸਟ, ਸਮੱਸਿਆ ਹੱਲ, ਅਤੇ Foundry Local Python SDK ਦੇ ਅਧਿਕਾਰਤ ਸੰਦਰਭ।

### ਨਮੂਨਾ ਸਕ੍ਰਿਪਟ

ਵਰਕਸ਼ਾਪ ਦੀਆਂ Dependencies ਇੰਸਟਾਲ ਕਰੋ (Windows):

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

ਜੇ macOS ਤੋਂ ਵੱਖਰੇ (Windows) ਮਸ਼ੀਨ ਜਾਂ VM 'ਤੇ Foundry Local ਸੇਵਾ ਚਲਾ ਰਹੇ ਹੋ, ਤਾਂ endpoint ਐਕਸਪੋਰਟ ਕਰੋ:

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| ਸੈਸ਼ਨ | ਸਕ੍ਰਿਪਟ(ਸ) | ਵੇਰਵਾ |
|---------|-----------|-------------|
| 1 | `samples/session01/chat_bootstrap.py` | ਸੇਵਾ ਸ਼ੁਰੂ ਕਰੋ ਅਤੇ ਸਟ੍ਰੀਮਿੰਗ ਚੈਟ |
| 2 | `samples/session02/rag_pipeline.py` | ਘੱਟੋ-ਘੱਟ RAG (ਇਨ-ਮੇਮੋਰੀ embeddings) |
|   | `samples/session02/rag_eval_ragas.py` | RAG ਮੁਲਾਂਕਣ ragas ਮੈਟ੍ਰਿਕਸ ਨਾਲ |
| 3 | `samples/session03/benchmark_oss_models.py` | ਬਹੁ-ਮਾਡਲ latency ਅਤੇ throughput ਬੈਂਚਮਾਰਕਿੰਗ |
| 4 | `samples/session04/model_compare.py` | SLM ਅਤੇ LLM ਦੀ ਤੁਲਨਾ (latency ਅਤੇ ਨਮੂਨਾ ਆਉਟਪੁੱਟ) |
| 5 | `samples/session05/agents_orchestrator.py` | ਦੋ-ਏਜੰਟ ਰਿਸਰਚ → ਐਡੀਟੋਰਿਅਲ ਪਾਈਪਲਾਈਨ |
| 6 | `samples/session06/models_router.py` | ਇਰਾਦੇ-ਅਧਾਰਿਤ ਰੂਟਿੰਗ ਡੈਮੋ |
|   | `samples/session06/models_pipeline.py` | ਬਹੁ-ਕਦਮ ਯੋਜਨਾ/ਅਮਲ/ਸੁਧਾਰ ਚੇਨ |

### ਵਾਤਾਵਰਣ ਵੈਰੀਏਬਲ (ਸਾਰੇ ਨਮੂਨਿਆਂ ਵਿੱਚ ਸਾਂਝੇ)

| ਵੈਰੀਏਬਲ | ਉਦੇਸ਼ | ਉਦਾਹਰਨ |
|----------|---------|---------|
| `FOUNDRY_LOCAL_ALIAS` | ਬੁਨਿਆਦੀ ਨਮੂਨਿਆਂ ਲਈ ਡਿਫਾਲਟ ਸਿੰਗਲ ਮਾਡਲ ਅਲਿਆਸ | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | SLM ਅਤੇ ਵੱਡੇ ਮਾਡਲ ਦੀ ਸਪਸ਼ਟ ਤੁਲਨਾ | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | ਬੈਂਚਮਾਰਕ ਕਰਨ ਲਈ ਅਲਿਆਸ ਦੀ ਕਾਮਾ ਸੂਚੀ | `qwen2.5-0.5b,gemma-2-2b,mistral-7b` |
| `BENCH_ROUNDS` | ਪ੍ਰਤੀ ਮਾਡਲ ਬੈਂਚਮਾਰਕ ਦੁਹਰਾਵਾਂ | `3` |
| `BENCH_PROMPT` | ਬੈਂਚਮਾਰਕਿੰਗ ਵਿੱਚ ਵਰਤਿਆ ਗਿਆ ਪ੍ਰੋਮਪਟ | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | Sentence-transformers embedding ਮਾਡਲ | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | RAG ਪਾਈਪਲਾਈਨ ਲਈ ਟੈਸਟ ਪ੍ਰਸ਼ਨ ਨੂੰ ਓਵਰਰਾਈਡ ਕਰੋ | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | ਏਜੰਟ ਪਾਈਪਲਾਈਨ ਪ੍ਰਸ਼ਨ ਨੂੰ ਓਵਰਰਾਈਡ ਕਰੋ | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | ਰਿਸਰਚ ਏਜੰਟ ਲਈ ਮਾਡਲ ਅਲਿਆਸ | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | ਐਡੀਟਰ ਏਜੰਟ ਲਈ ਮਾਡਲ ਅਲਿਆਸ (ਵੱਖਰਾ ਹੋ ਸਕਦਾ ਹੈ) | `gpt-oss-20b` |
| `SHOW_USAGE` | ਜਦੋਂ `1`, ਪ੍ਰਤੀ ਪੂਰਨ ਟੋਕਨ ਦੀ ਵਰਤੋਂ ਪ੍ਰਿੰਟ ਕਰਦਾ ਹੈ | `1` |
| `RETRY_ON_FAIL` | ਜਦੋਂ `1`, transient ਚੈਟ ਗਲਤੀਆਂ 'ਤੇ ਇੱਕ ਵਾਰ ਦੁਬਾਰਾ ਕੋਸ਼ਿਸ਼ ਕਰੋ | `1` |
| `RETRY_BACKOFF` | ਦੁਬਾਰਾ ਕੋਸ਼ਿਸ਼ ਕਰਨ ਤੋਂ ਪਹਿਲਾਂ ਰੁਕਣ ਲਈ ਸਕਿੰਟ | `1.0` |

ਜੇਕਰ ਕੋਈ ਵੈਰੀਏਬਲ ਸੈਟ ਨਹੀਂ ਹੈ, ਤਾਂ ਸਕ੍ਰਿਪਟ ਸੈਂਸਿਬਲ ਡਿਫਾਲਟ 'ਤੇ ਵਾਪਸ ਆ ਜਾਂਦੇ ਹਨ। ਸਿੰਗਲ-ਮਾਡਲ ਡੈਮੋਜ਼ ਲਈ ਤੁਹਾਨੂੰ ਆਮ ਤੌਰ 'ਤੇ ਸਿਰਫ `FOUNDRY_LOCAL_ALIAS` ਦੀ ਲੋੜ ਹੁੰਦੀ ਹੈ।

### ਯੂਟਿਲਿਟੀ ਮੋਡਿਊਲ

ਸਾਰੇ ਨਮੂਨੇ ਹੁਣ ਇੱਕ ਸਹਾਇਕ `samples/workshop_utils.py` ਸਾਂਝਾ ਕਰਦੇ ਹਨ ਜੋ ਪ੍ਰਦਾਨ ਕਰਦਾ ਹੈ:

* Cached `FoundryLocalManager` + OpenAI ਕਲਾਇੰਟ ਬਣਾਉਣ
* `chat_once()` ਸਹਾਇਕ, ਵਿਕਲਪਿਕ retry + ਵਰਤੋਂ ਪ੍ਰਿੰਟਿੰਗ ਨਾਲ
* ਸਧਾਰਨ ਟੋਕਨ ਵਰਤੋਂ ਰਿਪੋਰਟਿੰਗ (ਇਸ ਨੂੰ `SHOW_USAGE=1` ਨਾਲ ਐਨਬਲ ਕਰੋ)

ਇਹ ਨਕਲ ਨੂੰ ਘਟਾਉਂਦਾ ਹੈ ਅਤੇ ਕੁਸ਼ਲ ਸਥਾਨਕ ਮਾਡਲ ਸੰਗਠਨ ਲਈ ਵਧੀਆ ਅਭਿਆਸਾਂ ਨੂੰ ਉਜਾਗਰ ਕਰਦਾ ਹੈ।

## ਵਿਕਲਪਿਕ ਸੁਧਾਰ (ਕ੍ਰਾਸ-ਸੈਸ਼ਨ)

| ਥੀਮ | ਸੁਧਾਰ | ਸੈਸ਼ਨ | Env / Toggle |
|-------|-------------|----------|--------------|
| ਨਿਰਧਾਰਤਾ | ਫਿਕਸਡ ਟੈਂਪਰੇਚਰ + ਸਥਿਰ ਪ੍ਰੋਮਪਟ ਸੈੱਟ | 1–6 | `temperature=0`, `top_p=1` ਸੈਟ ਕਰੋ |
| ਟੋਕਨ ਵਰਤੋਂ ਦ੍ਰਿਸ਼ਤਾ | ਲਾਗਤ/ਕੁਸ਼ਲਤਾ ਸਿਖਲਾਈ | 1–6 | `SHOW_USAGE=1` |
| ਸਟ੍ਰੀਮਿੰਗ ਪਹਿਲਾ ਟੋਕਨ | ਧਾਰਨਾ latency ਮੈਟ੍ਰਿਕ | 1,3,4,6 | `BENCH_STREAM=1` (ਬੈਂਚਮਾਰਕ) |
| Retry ਲਚੀਲਾਪਨ | transient cold-start ਨੂੰ ਸੰਭਾਲਦਾ ਹੈ | ਸਾਰੇ | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| ਬਹੁ-ਮਾਡਲ ਏਜੰਟ | ਹੇਟਰੋਜੀਨੀਅਸ ਭੂਮਿਕਾ ਵਿਸ਼ੇਸ਼ਤਾ | 5 | `AGENT_MODEL_PRIMARY`, `AGENT_MODEL_EDITOR` |
| ਅਡਾਪਟਿਵ ਰੂਟਿੰਗ | ਇਰਾਦਾ + ਲਾਗਤ ਹਿਊਰਿਸਟਿਕ | 6 | escalation logic ਨਾਲ ਰੂਟਰ ਨੂੰ ਵਧਾਓ |
| ਵੇਕਟਰ ਯਾਦ | ਲੰਬੇ ਸਮੇਂ ਦੀ ਸੈਮੈਂਟਿਕ ਰੀਕਾਲ | 2,5,6 | FAISS/Chroma embedding index ਨੂੰ ਸ਼ਾਮਲ ਕਰੋ |
| ਟਰੇਸ ਐਕਸਪੋਰਟ | ਆਡਿਟਿੰਗ ਅਤੇ ਮੁਲਾਂਕਣ | 2,5,6 | ਪ੍ਰਤੀ ਕਦਮ JSON ਲਾਈਨ ਸ਼ਾਮਲ ਕਰੋ |
| ਗੁਣਵੱਤਾ ਰੂਬ੍ਰਿਕ | ਗੁਣਾਤਮਕ ਟ੍ਰੈਕਿੰਗ | 3–6 | ਸੈਕੰਡਰੀ ਸਕੋਰਿੰਗ ਪ੍ਰੋਮਪਟ |
| ਸਮੋਕ ਟੈਸਟ | ਵਰਕਸ਼ਾਪ ਤੋਂ ਪਹਿਲਾਂ ਤੇਜ਼ ਵੈਰੀਫਿਕੇਸ਼ਨ | ਸਾਰੇ | `python Workshop/tests/smoke.py` |

### ਨਿਰਧਾਰਤ Quick Start

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

ਇੱਕੋ ਜਿਹੇ ਇਨਪੁਟ ਦੁਹਰਾਉਣ 'ਤੇ ਸਥਿਰ ਟੋਕਨ ਗਿਣਤੀ ਦੀ ਉਮੀਦ ਕਰੋ।

### RAG ਮੁਲਾਂਕਣ (ਸੈਸ਼ਨ 2)

`rag_eval_ragas.py` ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਇੱਕ ਛੋਟੇ ਸਿੰਥੇਟਿਕ ਡੇਟਾਸੈਟ 'ਤੇ ਜਵਾਬ ਦੀ ਸਹੀਤਾ, ਸੱਚਾਈ ਅਤੇ ਸੰਦਰਭ ਸਹੀਤਾ ਦੀ ਗਣਨਾ ਕਰੋ:

```powershell
python samples/session02/rag_eval_ragas.py
```

ਇਸ ਨੂੰ ਪ੍ਰਸ਼ਨਾਂ, ਸੰਦਰਭਾਂ ਅਤੇ ਗਰਾਊਂਡ ਸੱਚਾਈਆਂ ਦੇ ਵੱਡੇ JSONL ਨੂੰ ਸਪਲਾਈ ਕਰਕੇ ਵਧਾਓ, ਫਿਰ ਇਸ ਨੂੰ Hugging Face `Dataset` ਵਿੱਚ ਰੂਪਾਂਤਰਿਤ ਕਰੋ।

## CLI ਕਮਾਂਡ ਸਹੀਤਾ ਐਪੈਂਡਿਕਸ

ਵਰਕਸ਼ਾਪ ਜ਼ਰੂਰਤਮੰਦ CLI ਕਮਾਂਡਾਂ ਦੀ ਵਰਤੋਂ ਕਰਦਾ ਹੈ ਜੋ ਇਸ ਸਮੇਂ ਦਸਤਾਵੇਜ਼ਬੱਧ / ਸਥਿਰ ਹਨ।

### ਸਥਿਰ ਕਮਾਂਡਾਂ ਦਾ ਹਵਾਲਾ

| ਸ਼੍ਰੇਣੀ | ਕਮਾਂਡ | ਉਦੇਸ਼ |
|----------|---------|---------|
| ਕੋਰ | `foundry --version` | ਇੰਸਟਾਲ ਕੀਤੀ ਵਰਜਨ ਦਿਖਾਓ |
| ਕੋਰ | `foundry init` | ਕਨਫਿਗਰੇਸ਼ਨ ਸ਼ੁਰੂ ਕਰੋ |
| ਸੇਵਾ | `foundry service start` | ਸਥਾਨਕ ਸੇਵਾ ਸ਼ੁਰੂ ਕਰੋ (ਜੇਕਰ ਆਟੋ ਨਹੀਂ) |
| ਸੇਵਾ | `foundry status` | ਸੇਵਾ ਦੀ ਸਥਿਤੀ ਦਿਖਾਓ |
| ਮਾਡਲ | `foundry model list` | ਕੈਟਾਲਾਗ / ਉਪਲਬਧ ਮਾਡਲਾਂ ਦੀ ਸੂਚੀ |
| ਮਾਡਲ | `foundry model download <alias>` | ਮਾਡਲ ਵਜ਼ਨ ਕੈਸ਼ ਵਿੱਚ ਡਾਊਨਲੋਡ ਕਰੋ |
| ਮਾਡਲ | `foundry model run <alias>` | ਇੱਕ ਮਾਡਲ ਨੂੰ ਸਥਾਨਕ ਤੌਰ 'ਤੇ ਚਲਾਓ; `--prompt` ਨਾਲ ਇੱਕ-ਸ਼ਾਟ ਨੂੰ ਜੋੜੋ |
| ਮਾਡਲ | `foundry model unload <alias>` / `foundry model stop <alias>` | ਮਾਡਲ ਨੂੰ ਮੈਮੋਰੀ ਤੋਂ ਬਾਹਰ ਕੱਢੋ (ਜੇਕਰ ਸਮਰਥਿਤ ਹੈ) |
| ਕੈਸ਼ | `foundry cache list` | ਕੈਸ਼ ਕੀਤੇ (ਡਾਊਨਲੋਡ ਕੀਤੇ) ਮਾਡਲਾਂ ਦੀ ਸੂਚੀ |
| ਸਿਸਟਮ | `foundry system info` | ਹਾਰਡਵੇਅਰ ਅਤੇ ਤੇਜ਼ੀ ਦੀ ਸਮਰੱਥਾ ਸਨੈਪਸ਼ਾਟ |
| ਸਿਸਟਮ | `foundry system gpu-info` | GPU ਡਾਇਗਨੋਸਟਿਕ ਜਾਣਕਾਰੀ |
| ਕਨਫਿਗ | `foundry config list` | ਮੌਜੂਦਾ ਕਨਫਿਗ ਵੇਲਿਊਜ਼ ਦਿਖਾਓ |
| ਕਨਫਿਗ | `foundry config set <key> <value>` | ਕਨਫਿਗਰੇਸ਼ਨ ਅਪਡੇਟ ਕਰੋ |

### ਇੱਕ-ਸ਼ਾਟ ਪ੍ਰੋਮਪਟ ਪੈਟਰਨ

ਪੁਰਾਣੇ `model chat` ਸਬਕਮਾਂਡ ਦੀ ਬਜਾਏ, ਇਸਦੀ ਵਰਤੋਂ ਕਰੋ:

```powershell
foundry model run <alias> --prompt "Your question here"
```

ਇਹ ਇੱਕ ਪ੍ਰੋਮਪਟ/ਰਿਸਪਾਂਸ ਸਾਈਕਲ ਨੂੰ ਚਲਾਉਂਦਾ ਹੈ ਅਤੇ ਫਿਰ ਬੰਦ ਕਰਦਾ ਹੈ।

### ਹਟਾਏ ਗਏ / ਬਚਾਏ ਗਏ ਪੈਟਰਨ

| ਪੁਰਾਣੇ / ਅਣਦਸਤਾਵੇਜ਼ | ਬਦਲਾਅ / ਮਾਰਗਦਰਸ਼ਨ |
|---------------------------|------------------------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | ਸਧਾਰਨ `foundry model list` + ਹਾਲੀਆ ਗਤੀਵਿਧੀ / ਲਾਗ |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | ਬੈਂਚਮਾਰਕ ਪਾਈਥਨ ਸਕ੍ਰਿਪਟ + OS ਟੂਲ (ਟਾਸਕ ਮੈਨੇਜਰ / `nvidia-smi`) |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### ਬੈਂਚਮਾਰਕਿੰਗ ਅਤੇ ਟੈਲੀਮੈਟਰੀ

- Latency, p95, tokens/sec: `samples/session03/benchmark_oss_models.py`
- ਪਹਿਲਾ-ਟੋਕਨ latency (streaming): `BENCH_STREAM=1` ਸੈਟ ਕਰੋ
- ਸਰੋਤ ਵਰਤੋਂ: OS ਮਾਨੀਟਰ (ਟਾਸਕ ਮੈਨੇਜਰ, ਐਕਟੀਵਿਟੀ ਮਾਨੀਟਰ, `nvidia-smi`) + `foundry system info`.

ਜਿਵੇਂ ਨਵੇਂ CLI ਟੈਲੀਮੈਟਰੀ ਕਮਾਂਡ ਉਪਰ ਸਥਿਰ ਹੁੰਦੇ ਹਨ, ਉਹਨਾਂ ਨੂੰ ਸੈਸ਼ਨ ਮਾਰਕਡਾਊਨ ਵਿੱਚ ਘੱਟ ਸੰਪਾਦਨ ਨਾਲ ਸ਼ਾਮਲ ਕੀਤਾ ਜਾ ਸਕਦਾ ਹੈ।

### ਆਟੋਮੈਟਿਕ ਲਿੰਟ ਗਾਰਡ

ਇੱਕ ਆਟੋਮੈਟਿਕ ਲਿੰਟਰ ਪੁਰਾਣੇ CLI ਪੈਟਰਨਾਂ ਨੂੰ ਮਾਰਕਡਾਊਨ ਫਾਈਲਾਂ ਦੇ ਫੈਂਸਡ ਕੋਡ ਬਲਾਕਾਂ ਵਿੱਚ ਮੁੜ-ਪੇਸ਼ ਕਰਨ ਤੋਂ ਰੋਕਦਾ ਹੈ:

ਸਕ੍ਰਿਪਟ: `Workshop/scripts/lint_markdown_cli.py`

ਪੁਰਾਣੇ ਪੈਟਰਨਾਂ ਨੂੰ ਕੋਡ ਫੈਂਸਾਂ ਵਿੱਚ ਰੋਕਿਆ ਜਾਂਦਾ ਹੈ।

ਸੁਝਾਏ ਬਦਲਾਅ:
| ਪੁਰਾਣੇ | ਬਦਲਾਅ |
|------------|-------------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | ਬੈਂਚਮਾਰਕ ਸਕ੍ਰਿਪਟ + ਸਿਸਟਮ ਟੂਲ |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

ਸਥਾਨਕ ਤੌਰ 'ਤੇ ਚਲਾਓ:
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

GitHub Action: `.github/workflows/markdown-cli-lint.yml` ਹਰ ਪੁਸ਼ ਅਤੇ PR 'ਤੇ ਚਲਦਾ ਹੈ।

ਵਿਕਲਪਿਕ ਪ੍ਰੀ-ਕਮਿਟ ਹੂਕ:
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## Quick CLI → SDK ਮਾਈਗ੍ਰੇਸ਼ਨ ਟੇਬਲ

| ਕੰਮ | CLI ਇੱਕ-ਲਾਈਨਰ | SDK (Python) ਸਮਕਾਲੀ | ਨੋਟ |
|------|---------------|-------------------------|-------|
| ਇੱਕ ਵਾਰ ਮਾਡਲ ਚਲਾਓ (ਪ੍ਰੋਮਪਟ) | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK ਸੇਵਾ ਅਤੇ ਕੈਸ਼ਿੰਗ ਨੂੰ ਆਪਣੇ ਆਪ ਸ਼ੁਰੂ ਕਰਦਾ ਹੈ |
| ਮਾਡਲ ਡਾਊਨਲੋਡ ਕਰੋ (ਕੈਸ਼) | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # triggers download/load` | ਮੈਨੇਜਰ ਵਧੀਆ ਵਰਜਨ ਚੁਣਦਾ ਹੈ ਜੇਕਰ ਅਲਿਆਸ ਕਈ ਬਿਲਡਾਂ ਨਾਲ ਮੈਪ ਕਰਦਾ ਹੈ |
| ਕੈਟਾਲਾਗ ਦੀ ਸੂਚੀ | `foundry model list` | `# use manager for each alias or maintain known list` | CLI ਇਕੱਠਾ ਕਰਦਾ ਹੈ; SDK ਵਰਤਮਾਨ ਵਿੱਚ ਪ੍ਰਤੀ-ਅਲਿਆਸ ਇਨਿਸਟੈਂਸ਼ਨ |
| ਕੈਸ਼ ਕੀਤੇ ਮਾਡਲਾਂ ਦੀ ਸੂਚੀ | `foundry cache list` | `manager.list_cached_models()` | ਮੈਨੇਜਰ ਸ਼ੁਰੂ ਕਰਨ ਤੋਂ ਬਾਅਦ (ਕੋਈ ਵੀ ਅਲਿਆਸ) |
| GPU ਤੇਜ਼ੀ ਨੂੰ ਐਨਬਲ ਕਰੋ | `foundry config set compute.onnx.enable_gpu true` | `# CLI action; SDK assumes config already applied` | ਕਨਫਿਗਰੇਸ਼ਨ ਬਾਹਰੀ ਸਾਈਡ ਇਫੈਕਟ ਹੈ |
| Endpoint URL ਪ੍ਰਾਪਤ ਕਰੋ | (implicit) | `manager.endpoint` | OpenAI-ਅਨੁਕੂਲ ਕਲਾਇੰਟ ਬਣਾਉਣ ਲਈ ਵਰਤਿਆ |
| ਮਾਡਲ ਨੂੰ ਗਰਮ ਕਰੋ | `foundry model run <alias>` ਫਿਰ ਪਹਿਲਾ ਪ੍ਰੋਮਪਟ | `chat_once(alias, messages=[...])` (utility) | ਯੂਟਿਲਿਟੀਜ਼ ਸ਼ੁਰੂਆਤੀ ਠੰਡੀ latency warmup ਨੂੰ ਸੰਭਾਲਦੇ ਹਨ |
| Latency ਮਾਪੋ | `python benchmark_oss_models.py` | `import benchmark_oss_models` (ਜਾਂ ਨਵਾਂ ਐਕਸਪੋਰਟਰ ਸਕ੍ਰਿਪਟ) | ਸਥਿਰ ਮੈਟ੍ਰਿਕਸ ਲਈ ਸਕ੍ਰਿਪਟ ਨੂੰ ਤਰਜੀਹ ਦਿਓ |
| ਮਾਡਲ ਨੂੰ ਰੋਕੋ / ਬਾਹਰ ਕੱਢੋ | `foundry model unload <alias>` | (Not exposed – restart service / process) | ਵਰਕਸ਼ਾਪ ਫਲੋ ਲਈ ਆਮ ਤੌਰ 'ਤੇ ਲੋੜੀਂਦਾ ਨਹੀਂ |
| ਟੋਕਨ ਵਰਤੋਂ ਪ੍ਰਾਪਤ

---

**ਅਸਵੀਕਰਤੀ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀ ਹੋਣ ਦੀ ਕੋਸ਼ਿਸ਼ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਦਿਓ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸੁਚੀਤਤਾਵਾਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਨੂੰ ਇਸਦੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਅਸੀਂ ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਪੈਦਾ ਹੋਣ ਵਾਲੇ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।