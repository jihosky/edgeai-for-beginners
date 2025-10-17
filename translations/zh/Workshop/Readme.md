<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b994c57f1207012e4d7f58b7c0d1ae7",
  "translation_date": "2025-10-17T09:13:29+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "zh"
}
-->
# EdgeAI 初学者工作坊

> **构建生产级边缘 AI 应用的实践学习路径**
>
> 通过 Microsoft Foundry Local，从首次聊天完成到多代理编排，掌握本地 AI 部署的技能，分为六个渐进式课程。

---

## 🎯 简介

欢迎参加 **EdgeAI 初学者工作坊**——这是一个实用的、动手操作的指南，帮助您构建完全在本地硬件上运行的智能应用程序。本次工作坊将理论性的边缘 AI 概念转化为现实世界的技能，通过使用 Microsoft Foundry Local 和小型语言模型（SLMs）完成逐步挑战的练习。

### 为什么选择这个工作坊？

**边缘 AI 革命已经到来**

全球组织正在从依赖云的 AI 转向边缘计算，主要原因有以下三点：

1. **隐私与合规性** - 在本地处理敏感数据，无需传输到云端（符合 HIPAA、GDPR、金融法规等）
2. **性能** - 消除网络延迟（本地延迟 50-500ms vs 云端往返 500-2000ms）
3. **成本控制** - 消除按令牌计费的 API 成本，并在无云费用的情况下扩展规模

**但边缘 AI 与众不同**

在本地运行 AI 需要新的技能：
- 针对资源限制选择和优化模型
- 本地服务管理和硬件加速
- 针对小型模型的提示工程
- 边缘设备的生产部署模式

**本次工作坊将传授这些技能**

通过 6 个专注的课程（总计约 3 小时），您将从“Hello World”进阶到部署生产级的多代理系统——所有内容均在您的机器上本地运行。

---

## 📚 学习目标

完成本次工作坊后，您将能够：

### 核心能力
1. **部署和管理本地 AI 服务**
   - 安装和配置 Microsoft Foundry Local
   - 为边缘部署选择合适的模型
   - 管理模型生命周期（下载、加载、缓存）
   - 监控资源使用并优化性能

2. **构建 AI 驱动的应用程序**
   - 本地实现兼容 OpenAI 的聊天完成
   - 为小型语言模型设计有效的提示
   - 处理流式响应以改善用户体验
   - 将本地模型集成到现有应用中

3. **创建 RAG（检索增强生成）系统**
   - 使用嵌入构建语义搜索
   - 将 LLM 响应与领域特定知识结合
   - 使用行业标准指标评估 RAG 质量
   - 从原型扩展到生产环境

4. **优化模型性能**
   - 为您的用例基准测试多个模型
   - 测量延迟、吞吐量和首令牌时间
   - 根据速度/质量权衡选择最佳模型
   - 在实际场景中比较 SLM 与 LLM 的权衡

5. **编排多代理系统**
   - 为不同任务设计专用代理
   - 实现代理记忆和上下文管理
   - 在复杂工作流中协调代理
   - 在多个模型之间智能路由请求

6. **部署生产级解决方案**
   - 实现错误处理和重试逻辑
   - 监控令牌使用和系统资源
   - 使用模型工具模式构建可扩展架构
   - 规划从边缘到混合（边缘+云）的迁移路径

---

## 🎓 学习成果

### 您将构建的内容

到工作坊结束时，您将完成以下内容：

| 课程 | 交付成果 | 展示的技能 |
|------|----------|-----------|
| **1** | 流式聊天应用 | 服务设置、基本完成、流式用户体验 |
| **2** | 带评估的 RAG 系统 | 嵌入、语义搜索、质量指标 |
| **3** | 多模型基准测试套件 | 性能测量、模型比较 |
| **4** | SLM 与 LLM 比较器 | 权衡分析、优化策略 |
| **5** | 多代理编排器 | 代理设计、记忆管理、协调 |
| **6** | 智能路由系统 | 意图检测、模型选择、可扩展性 |

### 能力矩阵

| 技能水平 | 课程 1-2 | 课程 3-4 | 课程 5-6 |
|----------|----------|----------|----------|
| **初学者** | ✅ 设置与基础 | ⚠️ 有挑战性 | ❌ 太高级 |
| **中级** | ✅ 快速回顾 | ✅ 核心学习 | ⚠️ 拉伸目标 |
| **高级** | ✅ 轻松完成 | ✅ 精炼 | ✅ 生产模式 |

### 职业技能

**完成工作坊后，您将能够：**

✅ **构建隐私优先的应用**
- 本地处理 PHI/PII 的医疗应用
- 符合合规要求的金融服务
- 数据主权需求的政府系统

✅ **优化边缘环境**
- 资源有限的物联网设备
- 离线优先的移动应用
- 低延迟实时系统

✅ **设计智能架构**
- 用于复杂工作流的多代理系统
- 混合边缘-云部署
- 成本优化的 AI 基础设施

✅ **领导边缘 AI 项目**
- 评估项目的边缘 AI 可行性
- 选择合适的模型和框架
- 构建可扩展的本地 AI 解决方案

---

## 🗺️ 工作坊结构

### 课程概览（6 节课 × 30 分钟 = 3 小时）

| 课程 | 主题 | 重点 | 时长 |
|------|------|------|------|
| **1** | 开始使用 Foundry Local | 安装、验证、首次完成 | 30 分钟 |
| **2** | 构建 RAG 的 AI 解决方案 | 提示工程、嵌入、评估 | 30 分钟 |
| **3** | 开源模型 | 模型发现、基准测试、选择 | 30 分钟 |
| **4** | 前沿模型 | SLM 与 LLM、优化、框架 | 30 分钟 |
| **5** | AI 驱动的代理 | 代理设计、编排、记忆 | 30 分钟 |
| **6** | 模型作为工具 | 路由、链式调用、扩展策略 | 30 分钟 |

---

## 🚀 快速开始

### 前提条件

**系统要求：**
- **操作系统**：Windows 10/11、macOS 11+ 或 Linux（Ubuntu 20.04+）
- **内存**：最低 8GB，推荐 16GB+
- **存储**：模型需要 10GB+ 可用空间
- **处理器**：支持 AVX2 的现代处理器
- **GPU**（可选）：支持 CUDA 的 GPU 或 Qualcomm NPU 加速

**软件要求：**
- **Python 3.8+** ([下载](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([安装指南](../../../Workshop))
- **Git** ([下载](https://git-scm.com/downloads))
- **Visual Studio Code**（推荐）([下载](https://code.visualstudio.com/))

### 三步设置

#### 1. 安装 Foundry Local

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**验证安装：**
```bash
foundry --version
foundry service status
```

**确保 Azure AI Foundry Local 使用固定端口运行**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**验证运行情况：**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**查找可用模型**
要查看 Foundry Local 实例中的可用模型，可以查询模型端点：

```bash
# cmd/bash/powershell
foundry model list
```

使用 Web 端点 

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### 2. 克隆仓库并安装依赖项

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

#### 3. 运行您的第一个示例

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples/session01
python chat_bootstrap.py "What is edge AI?"
```

**✅ 成功！** 您应该看到关于边缘 AI 的流式响应。

---

## 📦 工作坊资源

### Python 示例

逐步动手示例，展示每个概念：

| 课程 | 示例 | 描述 | 运行时间 |
|------|------|------|----------|
| 1 | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | 基础与流式聊天 | ~30秒 |
| 2 | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | 带嵌入的 RAG | ~45秒 |
| 2 | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | RAG 质量评估 | ~60秒 |
| 3 | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | 多模型基准测试 | ~2-3分钟 |
| 4 | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | SLM 与 LLM 比较 | ~45秒 |
| 5 | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | 多代理系统 | ~60秒 |
| 6 | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | 基于意图的路由 | ~45秒 |
| 6 | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | 多步骤管道 | ~60秒 |

### Jupyter Notebooks

带有解释和可视化的交互式探索：

| 课程 | Notebook | 描述 | 难度 |
|------|----------|------|------|
| 1 | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | 聊天基础与流式 | ⭐ 初学者 |
| 2 | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline.ipynb) | 构建 RAG 系统 | ⭐⭐ 中级 |
| 2 | [`session02_rag_eval_ragas.ipynb`](./notebooks/session02_rag_eval_ragas.ipynb) | 评估 RAG 质量 | ⭐⭐ 中级 |
| 3 | [`session03_benchmark_oss_models.ipynb`](./notebooks/session03_benchmark_oss_models.ipynb) | 模型基准测试 | ⭐⭐ 中级 |
| 4 | [`session04_model_compare.ipynb`](./notebooks/session04_model_compare.ipynb) | 模型比较 | ⭐⭐ 中级 |
| 5 | [`session05_agents_orchestrator.ipynb`](./notebooks/session05_agents_orchestrator.ipynb) | 代理编排 | ⭐⭐⭐ 高级 |
| 6 | [`session06_models_router.ipynb`](./notebooks/session06_models_router.ipynb) | 意图路由 | ⭐⭐⭐ 高级 |
| 6 | [`session06_models_pipeline.ipynb`](./notebooks/session06_models_pipeline.ipynb) | 管道编排 | ⭐⭐⭐ 高级 |

### 文档

全面的指南和参考：

| 文档 | 描述 | 使用场景 |
|------|------|----------|
| [QUICK_START.md](./QUICK_START.md) | 快速设置指南 | 从零开始 |
| [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) | 命令与 API 速查表 | 需要快速答案时 |
| [FOUNDRY_SDK_QUICKREF.md](./FOUNDRY_SDK_QUICKREF.md) | SDK 模式与示例 | 编写代码时 |
| [ENV_CONFIGURATION.md](./ENV_CONFIGURATION.md) | 环境变量指南 | 配置示例时 |
| [SAMPLES_UPDATE_SUMMARY.md](./SAMPLES_UPDATE_SUMMARY.md) | 最新示例改进 | 理解变化时 |
| [SDK_MIGRATION_NOTES.md](./SDK_MIGRATION_NOTES.md) | 迁移指南 | 升级代码时 |
| [notebooks/TROUBLESHOOTING.md](./notebooks/TROUBLESHOOTING.md) | 常见问题与解决方法 | 调试问题时 |

---

## 🎓 学习路径推荐

### 初学者（3-4 小时）
1. ✅ 课程 1：入门（专注于设置和基础聊天）
2. ✅ 课程 2：RAG 基础（初期可跳过评估）
3. ✅ 课程 3：简单基准测试（仅测试 2 个模型）
4. ⏭️ 暂时跳过课程 4-6
5. 🔄 在构建第一个应用后返回课程 4-6

### 中级开发者（3 小时）
1. ⚡ 课程 1：快速设置验证
2. ✅ 课程 2：完整 RAG 管道及评估
3. ✅ 课程 3：完整基准测试套件
4. ✅ 课程 4：模型优化
5. ✅ 课程 5-6：专注于架构模式

### 高级实践者（2-3 小时）
1. ⚡ 课程 1-3：快速回顾与验证
2. ✅ 课程 4：深入优化
3. ✅ 课程 5：多代理架构
4. ✅ 课程 6：生产模式与扩展
5. 🚀 扩展：构建自定义路由逻辑和混合部署

---

## 工作坊课程包（专注的 30 分钟实验）

如果您正在遵循浓缩的 6 节课工作坊格式，请使用这些专用指南（每个指南与更广泛的模块文档相辅相成）：

| 工作坊课程 | 指南 | 核心重点 |
|-----------|------|----------|
| 1 | [Session01-GettingStartedFoundryLocal](./Session01-GettingStartedFoundryLocal.md) | 安装、验证、运行 phi 和 GPT-OSS-20B、加速 |
| 2 | [Session02-BuildAISolutionsRAG](./Session02-BuildAISolutionsRAG.md) | 提示工程、RAG 模式、CSV 和文档基础、迁移 |
| 3 | [Session03-OpenSourceModels](./Session03-OpenSourceModels.md) | Hugging Face 集成、基准测试、模型选择 |
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | SLM与LLM对比，WebGPU，Chainlit RAG，ONNX加速 |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | 代理角色、记忆、工具、编排 |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | 路由、链式调用、扩展到Azure的路径 |

每个课程文件包括：摘要、学习目标、30分钟演示流程、入门项目、验证清单、故障排除以及对官方Foundry Local Python SDK的参考。

### 示例脚本

安装工作坊依赖项（Windows）：

```powershell
cd Workshop
py -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

macOS / Linux：

```bash
cd Workshop
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

如果Foundry Local服务运行在不同的（Windows）机器或虚拟机上，从macOS导出端点：

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| 课程 | 脚本 | 描述 |
|------|------|------|
| 1 | `samples/session01/chat_bootstrap.py` | 启动服务并进行流式聊天 |
| 2 | `samples/session02/rag_pipeline.py` | 最小化RAG（内存嵌入） |
|   | `samples/session02/rag_eval_ragas.py` | 使用ragas指标进行RAG评估 |
| 3 | `samples/session03/benchmark_oss_models.py` | 多模型延迟与吞吐量基准测试 |
| 4 | `samples/session04/model_compare.py` | SLM与LLM对比（延迟与样本输出） |
| 5 | `samples/session05/agents_orchestrator.py` | 双代理研究→编辑流程 |
| 6 | `samples/session06/models_router.py` | 基于意图的路由演示 |
|   | `samples/session06/models_pipeline.py` | 多步骤计划/执行/优化链 |

### 环境变量（样本通用）

| 变量 | 用途 | 示例 |
|------|------|------|
| `FOUNDRY_LOCAL_ALIAS` | 基本样本的默认单模型别名 | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | 明确的SLM与较大模型对比 | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | 基准测试的模型别名列表 | `qwen2.5-0.5b,gemma-2-2b,mistral-7b` |
| `BENCH_ROUNDS` | 每个模型的基准测试重复次数 | `3` |
| `BENCH_PROMPT` | 基准测试中使用的提示 | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | Sentence-transformers嵌入模型 | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | 覆盖RAG管道的测试查询 | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | 覆盖代理管道查询 | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | 研究代理的模型别名 | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | 编辑代理的模型别名（可不同） | `gpt-oss-20b` |
| `SHOW_USAGE` | 当值为`1`时，打印每次完成的令牌使用情况 | `1` |
| `RETRY_ON_FAIL` | 当值为`1`时，在临时聊天错误时重试一次 | `1` |
| `RETRY_BACKOFF` | 重试前等待的秒数 | `1.0` |

如果变量未设置，脚本会回退到合理的默认值。对于单模型演示，通常只需要设置`FOUNDRY_LOCAL_ALIAS`。

### 工具模块

所有样本现在共享一个辅助模块`samples/workshop_utils.py`，提供：

* 缓存的`FoundryLocalManager`和OpenAI客户端创建
* 带可选重试和使用打印的`chat_once()`辅助函数
* 简单的令牌使用报告（通过`SHOW_USAGE=1`启用）

这减少了重复，并突出了高效本地模型编排的最佳实践。

## 可选增强功能（跨课程）

| 主题 | 增强功能 | 课程 | 环境变量/开关 |
|------|----------|------|--------------|
| 确定性 | 固定温度+稳定提示集 | 1–6 | 设置`temperature=0`，`top_p=1` |
| 令牌使用可见性 | 一致的成本/效率教学 | 1–6 | `SHOW_USAGE=1` |
| 流式首令牌 | 感知延迟指标 | 1,3,4,6 | `BENCH_STREAM=1`（基准测试） |
| 重试弹性 | 处理临时冷启动 | 全部 | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| 多模型代理 | 异构角色专门化 | 5 | `AGENT_MODEL_PRIMARY`，`AGENT_MODEL_EDITOR` |
| 自适应路由 | 意图+成本启发式 | 6 | 扩展路由器，添加升级逻辑 |
| 向量记忆 | 长期语义回忆 | 2,5,6 | 集成FAISS/Chroma嵌入索引 |
| 跟踪导出 | 审计与评估 | 2,5,6 | 每步追加JSON行 |
| 质量标准 | 定性跟踪 | 3–6 | 次级评分提示 |
| 烟雾测试 | 快速工作坊前验证 | 全部 | `python Workshop/tests/smoke.py` |

### 确定性快速启动

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

期望在重复相同输入时令牌计数稳定。

### RAG评估（课程2）

使用`rag_eval_ragas.py`计算答案相关性、真实性和上下文精度，基于一个小型合成数据集：

```powershell
python samples/session02/rag_eval_ragas.py
```

通过提供更大的问题、上下文和真实值的JSONL文件扩展，然后转换为Hugging Face `Dataset`。

## CLI命令准确性附录

工作坊仅使用当前文档化/稳定的Foundry Local CLI命令。

### 参考的稳定命令

| 类别 | 命令 | 用途 |
|------|------|------|
| 核心 | `foundry --version` | 显示已安装版本 |
| 核心 | `foundry init` | 初始化配置 |
| 服务 | `foundry service start` | 启动本地服务（如果未自动启动） |
| 服务 | `foundry status` | 显示服务状态 |
| 模型 | `foundry model list` | 列出目录/可用模型 |
| 模型 | `foundry model download <alias>` | 下载模型权重到缓存 |
| 模型 | `foundry model run <alias>` | 本地启动（加载）模型；结合`--prompt`进行一次性调用 |
| 模型 | `foundry model unload <alias>` / `foundry model stop <alias>` | 从内存中卸载模型（如果支持） |
| 缓存 | `foundry cache list` | 列出已缓存（下载）的模型 |
| 系统 | `foundry system info` | 硬件与加速能力快照 |
| 系统 | `foundry system gpu-info` | GPU诊断信息 |
| 配置 | `foundry config list` | 显示当前配置值 |
| 配置 | `foundry config set <key> <value>` | 更新配置 |

### 一次性提示模式

替代已弃用的`model chat`子命令，使用：

```powershell
foundry model run <alias> --prompt "Your question here"
```

这执行一个提示/响应周期后退出。

### 已移除/避免的模式

| 已弃用/未文档化 | 替代/指导 |
|-----------------|----------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | 使用普通`foundry model list` + 最近活动/日志 |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | 使用基准测试Python脚本+操作系统工具（任务管理器/`nvidia-smi`） |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### 基准测试与遥测

- 延迟、p95、令牌/秒：`samples/session03/benchmark_oss_models.py`
- 首令牌延迟（流式）：设置`BENCH_STREAM=1`
- 资源使用：操作系统监控（任务管理器、活动监视器、`nvidia-smi`）+ `foundry system info`。

随着新的CLI遥测命令在上游稳定，它们可以通过最小编辑集成到课程markdown中。

### 自动Lint守护

一个自动化的linter防止在markdown文件的代码块中重新引入已弃用的CLI模式：

脚本：`Workshop/scripts/lint_markdown_cli.py`

在代码块内阻止已弃用模式。

推荐替代：
| 已弃用 | 替代 |
|--------|------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | 基准测试脚本+系统工具 |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

本地运行：
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

GitHub Action：`.github/workflows/markdown-cli-lint.yml`在每次推送和PR时运行。

可选的预提交钩子：
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## 快速CLI→SDK迁移表

| 任务 | CLI单行命令 | SDK（Python）等效 | 备注 |
|------|------------|------------------|------|
| 一次运行模型（提示） | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK自动启动服务与缓存 |
| 下载（缓存）模型 | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # 触发下载/加载` | 管理器在别名映射到多个版本时选择最佳版本 |
| 列出目录 | `foundry model list` | `# 使用管理器处理每个别名或维护已知列表` | CLI聚合；SDK当前每个别名实例化 |
| 列出已缓存模型 | `foundry cache list` | `manager.list_cached_models()` | 在管理器初始化后（任何别名） |
| 启用GPU加速 | `foundry config set compute.onnx.enable_gpu true` | `# CLI操作；SDK假定配置已应用` | 配置是外部副作用 |
| 获取端点URL | （隐式） | `manager.endpoint` | 用于创建OpenAI兼容客户端 |
| 预热模型 | `foundry model run <alias>`然后首次提示 | `chat_once(alias, messages=[...])`（工具） | 工具处理初始冷启动延迟预热 |
| 测量延迟 | `python benchmark_oss_models.py` | `import benchmark_oss_models`（或新的导出脚本） | 优先使用脚本以确保一致的指标 |
| 停止/卸载模型 | `foundry model unload <alias>` | （未公开——重启服务/进程） | 通常不需要工作坊流程 |
| 检索令牌使用情况 | （查看输出） | `resp.usage.total_tokens` | 如果后端返回使用对象则提供 |

## 基准测试Markdown导出

使用脚本`Workshop/scripts/export_benchmark_markdown.py`运行新的基准测试（逻辑与`samples/session03/benchmark_oss_models.py`相同），并生成GitHub友好的Markdown表格和原始JSON。

### 示例

```powershell
python Workshop\scripts\export_benchmark_markdown.py --models "qwen2.5-0.5b,gemma-2-2b,mistral-7b" --prompt "Explain retrieval augmented generation briefly." --rounds 3 --output benchmark_report.md
```

生成的文件：
| 文件 | 内容 |
|------|------|
| `benchmark_report.md` | Markdown表格+解释提示 |
| `benchmark_report.json` | 原始指标数组（用于差异/趋势跟踪） |

在环境中设置`BENCH_STREAM=1`以包含首令牌延迟（如果支持）。

---

**免责声明**：  
本文档使用AI翻译服务[Co-op Translator](https://github.com/Azure/co-op-translator)进行翻译。尽管我们努力确保翻译的准确性，但请注意，自动翻译可能包含错误或不准确之处。原始语言的文档应被视为权威来源。对于重要信息，建议使用专业人工翻译。我们对因使用此翻译而产生的任何误解或误读不承担责任。