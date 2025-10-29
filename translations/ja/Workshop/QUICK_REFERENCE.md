<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "93615ab69c8773b52c4437d537f6acea",
  "translation_date": "2025-10-28T20:54:59+00:00",
  "source_file": "Workshop/QUICK_REFERENCE.md",
  "language_code": "ja"
}
-->
# ワークショップサンプル - クイックリファレンスカード

**最終更新日**: 2025年10月8日

---

## 🚀 クイックスタート

```bash
# 1. Ensure Foundry Local is running
foundry service status
foundry model run phi-4-mini

# 2. Install dependencies
pip install -r Workshop/requirements.txt

# 3. Run a sample
cd Workshop/samples
python -m session01.chat_bootstrap "What is edge AI?"
```

---

## 📂 サンプル概要

| セッション | サンプル | 目的 | 時間 |
|------------|----------|------|------|
| 01 | `chat_bootstrap.py` | 基本的なチャット + ストリーミング | 約30秒 |
| 02 | `rag_pipeline.py` | 埋め込みを使用したRAG | 約45秒 |
| 02 | `rag_eval_ragas.py` | RAG評価 | 約60秒 |
| 03 | `benchmark_oss_models.py` | モデルベンチマーク | 約2分 |
| 04 | `model_compare.py` | SLMとLLMの比較 | 約45秒 |
| 05 | `agents_orchestrator.py` | マルチエージェントシステム | 約60秒 |
| 06 | `models_router.py` | インテントルーティング | 約45秒 |
| 06 | `models_pipeline.py` | マルチステップパイプライン | 約60秒 |

---

## 🛠️ 環境変数

### 必須
```bash
# Choose model
set FOUNDRY_LOCAL_ALIAS=phi-4-mini

# Override endpoint (optional)
set FOUNDRY_LOCAL_ENDPOINT=http://localhost:8000

# Show token usage
set SHOW_USAGE=1
```

### セッション固有
```bash
# Session 02: RAG
set RAG_QUESTION="What is local inference?"
set EMBED_MODEL=sentence-transformers/all-MiniLM-L6-v2

# Session 03: Benchmarking
set BENCH_MODELS=phi-4-mini,qwen2.5-0.5b
set BENCH_ROUNDS=3
set BENCH_STREAM=1

# Session 04: Comparison
set SLM_ALIAS=phi-4-mini
set LLM_ALIAS=qwen2.5-7b

# Session 05: Agents
set AGENT_MODEL_PRIMARY=phi-4-mini
set AGENT_QUESTION="Why use edge AI?"

# Session 06: Pipeline
set PIPELINE_TASK="Your task here"
```

---

## ✅ 検証とテスト

```bash
# Validate syntax and imports
python scripts/validate_samples.py

# Validate specific session
python scripts/validate_samples.py --session 01

# Run smoke tests
python scripts/test_samples.py --quick

# Verbose testing
python scripts/test_samples.py --verbose
```

---

## 🐛 トラブルシューティング

### 接続エラー
```bash
# Check Foundry Local
foundry service status

# Start if needed
foundry service start
foundry model run phi-4-mini
```

### インポートエラー
```bash
# Install missing dependencies
pip install sentence-transformers ragas datasets

# Or install all
pip install -r Workshop/requirements.txt
```

### モデルが見つからない
```bash
# List available models
foundry model ls

# Download model
foundry model download phi-4-mini
```

### パフォーマンスが遅い
```bash
# Use smaller model
set FOUNDRY_LOCAL_ALIAS=qwen2.5-0.5b

# Reduce benchmark rounds
set BENCH_ROUNDS=1
```

---

## 📖 よくあるパターン

### 基本的なチャット
```python
from workshop_utils import chat_once

text, usage = chat_once(
    'phi-4-mini',
    messages=[{"role": "user", "content": "Hello"}],
    max_tokens=100,
    temperature=0.7
)
```

### クライアント取得
```python
from workshop_utils import get_client

manager, client, model_id = get_client(
    alias='phi-4-mini',
    endpoint=None  # Auto-detect
)
```

### エラーハンドリング
```python
try:
    manager, client, model_id = get_client(alias)
except Exception as e:
    print(f"[ERROR] Failed: {e}")
    print("[INFO] Check: foundry service status")
    sys.exit(1)
```

### ストリーミング
```python
stream = client.chat.completions.create(
    model=model_id,
    messages=messages,
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

---

## 📊 モデル選択

| モデル | サイズ | 最適用途 | スピード |
|--------|--------|----------|----------|
| `qwen2.5-0.5b` | 0.5B | 高速分類 | ⚡⚡⚡ |
| `qwen2.5-coder-0.5b` | 0.5B | 素早いコード生成 | ⚡⚡⚡ |
| `gemma-2-2b` | 2B | 創造的な文章作成 | ⚡⚡ |
| `phi-3.5-mini` | 3.5B | コード、リファクタリング | ⚡⚡ |
| `phi-4-mini` | 4B | 一般用途、要約 | ⚡⚡ |
| `qwen2.5-7b` | 7B | 複雑な推論 | ⚡ |

---

## 🔗 リソース

- **SDKドキュメント**: https://github.com/microsoft/Foundry-Local/tree/main/sdk/python
- **クイックリファレンス**: `Workshop/FOUNDRY_SDK_QUICKREF.md`
- **更新概要**: `Workshop/SAMPLES_UPDATE_SUMMARY.md`
- **移行ノート**: `Workshop/SDK_MIGRATION_NOTES.md`

---

## 💡 ヒント

1. **クライアントのキャッシュ**: `workshop_utils`が自動でキャッシュします
2. **小型モデルを使用**: テストには`qwen2.5-0.5b`を使用
3. **使用状況統計を有効化**: `SHOW_USAGE=1`を設定してトークンを追跡
4. **バッチ処理**: 複数のプロンプトを順次処理
5. **max_tokensを減らす**: クイックレスポンスのためにレイテンシを削減

---

## 🎯 サンプルワークフロー

### 全てをテスト
```bash
python scripts/validate_samples.py
python scripts/test_samples.py --quick
```

### モデルのベンチマーク
```bash
cd samples
set BENCH_MODELS=phi-4-mini,qwen2.5-0.5b
set BENCH_ROUNDS=3
python -m session03.benchmark_oss_models
```

### RAGパイプライン
```bash
cd samples
set RAG_QUESTION="What is RAG?"
python -m session02.rag_pipeline
```

### マルチエージェントシステム
```bash
cd samples
set AGENT_QUESTION="Why edge AI for healthcare?"
python -m session05.agents_orchestrator
```

---

**クイックヘルプ**: `samples`ディレクトリから任意のサンプルを`--help`で実行するか、ドックストリングを確認してください:
```bash
python -c "import session01.chat_bootstrap; help(session01.chat_bootstrap)"
```

---

**すべてのサンプルは2025年10月にFoundry Local SDKのベストプラクティスで更新済み** ✨

---

**免責事項**:  
この文書はAI翻訳サービス[Co-op Translator](https://github.com/Azure/co-op-translator)を使用して翻訳されています。正確性を追求しておりますが、自動翻訳には誤りや不正確な部分が含まれる可能性があります。元の言語で記載された文書を正式な情報源としてご参照ください。重要な情報については、専門の人間による翻訳を推奨します。この翻訳の使用に起因する誤解や誤認について、当方は一切の責任を負いません。