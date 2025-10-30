<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "45923ada94573fee7c82cc4f0c3bb344",
  "translation_date": "2025-10-28T22:33:40+00:00",
  "source_file": "Workshop/Readme.md",
  "language_code": "vi"
}
-->
# EdgeAI cho Người Mới Bắt Đầu - Workshop

> **Lộ trình học thực hành để xây dựng ứng dụng Edge AI sẵn sàng sản xuất**
>
> Làm chủ triển khai AI cục bộ với Microsoft Foundry Local, từ hoàn thành chat đầu tiên đến điều phối đa tác nhân trong 6 buổi học tiến bộ.

---

## 🎯 Giới thiệu

Chào mừng bạn đến với **Workshop EdgeAI cho Người Mới Bắt Đầu** - hướng dẫn thực hành để xây dựng các ứng dụng thông minh hoạt động hoàn toàn trên phần cứng cục bộ. Workshop này biến các khái niệm lý thuyết về Edge AI thành kỹ năng thực tế thông qua các bài tập ngày càng thách thức sử dụng Microsoft Foundry Local và Small Language Models (SLMs).

### Tại sao nên tham gia Workshop này?

**Cuộc cách mạng Edge AI đã đến**

Các tổ chức trên toàn thế giới đang chuyển từ AI phụ thuộc vào đám mây sang điện toán biên vì ba lý do quan trọng:

1. **Bảo mật & Tuân thủ** - Xử lý dữ liệu nhạy cảm cục bộ mà không cần truyền lên đám mây (HIPAA, GDPR, quy định tài chính)
2. **Hiệu suất** - Loại bỏ độ trễ mạng (50-500ms cục bộ so với 500-2000ms vòng lặp đám mây)
3. **Kiểm soát chi phí** - Loại bỏ chi phí API theo token và mở rộng quy mô mà không cần chi phí đám mây

**Nhưng Edge AI thì khác**

Chạy AI tại chỗ yêu cầu các kỹ năng mới:
- Lựa chọn và tối ưu hóa mô hình cho các hạn chế tài nguyên
- Quản lý dịch vụ cục bộ và tăng tốc phần cứng
- Kỹ thuật prompt cho các mô hình nhỏ hơn
- Mẫu triển khai sản xuất cho các thiết bị biên

**Workshop này cung cấp những kỹ năng đó**

Trong 6 buổi học tập trung (~3 giờ tổng cộng), bạn sẽ tiến từ "Hello World" đến triển khai hệ thống đa tác nhân sẵn sàng sản xuất - tất cả đều chạy cục bộ trên máy của bạn.

---

## 📚 Mục tiêu học tập

Hoàn thành workshop này, bạn sẽ có thể:

### Năng lực cốt lõi
1. **Triển khai và Quản lý Dịch vụ AI Cục bộ**
   - Cài đặt và cấu hình Microsoft Foundry Local
   - Lựa chọn mô hình phù hợp cho triển khai biên
   - Quản lý vòng đời mô hình (tải xuống, tải lên, lưu trữ)
   - Giám sát sử dụng tài nguyên và tối ưu hóa hiệu suất

2. **Xây dựng Ứng dụng AI**
   - Triển khai hoàn thành chat tương thích OpenAI cục bộ
   - Thiết kế prompt hiệu quả cho Small Language Models
   - Xử lý phản hồi streaming để cải thiện UX
   - Tích hợp mô hình cục bộ vào các ứng dụng hiện có

3. **Tạo Hệ thống RAG (Retrieval Augmented Generation)**
   - Xây dựng tìm kiếm ngữ nghĩa với embeddings
   - Cung cấp phản hồi LLM dựa trên kiến thức chuyên ngành
   - Đánh giá chất lượng RAG với các chỉ số tiêu chuẩn ngành
   - Mở rộng từ nguyên mẫu đến sản xuất

4. **Tối ưu hóa Hiệu suất Mô hình**
   - Đánh giá nhiều mô hình cho trường hợp sử dụng của bạn
   - Đo lường độ trễ, thông lượng và thời gian token đầu tiên
   - Lựa chọn mô hình tối ưu dựa trên sự cân bằng tốc độ/chất lượng
   - So sánh trade-offs giữa SLM và LLM trong các tình huống thực tế

5. **Điều phối Hệ thống Đa Tác Nhân**
   - Thiết kế tác nhân chuyên biệt cho các nhiệm vụ khác nhau
   - Triển khai quản lý bộ nhớ và ngữ cảnh của tác nhân
   - Điều phối tác nhân trong các quy trình làm việc phức tạp
   - Điều hướng yêu cầu một cách thông minh qua nhiều mô hình

6. **Triển khai Giải pháp Sẵn Sàng Sản Xuất**
   - Triển khai xử lý lỗi và logic thử lại
   - Giám sát sử dụng token và tài nguyên hệ thống
   - Xây dựng kiến trúc mở rộng với mẫu mô hình như công cụ
   - Lập kế hoạch đường dẫn di chuyển từ biên đến hybrid (biên + đám mây)

---

## 🎓 Kết quả học tập

### Những gì bạn sẽ xây dựng

Kết thúc workshop này, bạn sẽ tạo được:

| Buổi học | Thành phẩm | Kỹ năng thể hiện |
|----------|------------|------------------|
| **1** | Ứng dụng chat với streaming | Cài đặt dịch vụ, hoàn thành cơ bản, UX streaming |
| **2** | Hệ thống RAG với đánh giá | Embeddings, tìm kiếm ngữ nghĩa, chỉ số chất lượng |
| **3** | Bộ công cụ đánh giá đa mô hình | Đo lường hiệu suất, so sánh mô hình |
| **4** | Bộ so sánh SLM vs LLM | Phân tích trade-offs, chiến lược tối ưu hóa |
| **5** | Bộ điều phối đa tác nhân | Thiết kế tác nhân, quản lý bộ nhớ, điều phối |
| **6** | Hệ thống điều hướng thông minh | Phát hiện ý định, lựa chọn mô hình, khả năng mở rộng |

### Ma trận năng lực

| Mức độ kỹ năng | Buổi 1-2 | Buổi 3-4 | Buổi 5-6 |
|----------------|----------|----------|----------|
| **Người mới bắt đầu** | ✅ Cài đặt & cơ bản | ⚠️ Thách thức | ❌ Quá nâng cao |
| **Trung cấp** | ✅ Xem nhanh | ✅ Học cốt lõi | ⚠️ Mục tiêu mở rộng |
| **Nâng cao** | ✅ Dễ dàng vượt qua | ✅ Tinh chỉnh | ✅ Mẫu sản xuất |

### Kỹ năng sẵn sàng nghề nghiệp

**Sau workshop này, bạn sẽ sẵn sàng để:**

✅ **Xây dựng Ứng dụng Ưu tiên Bảo mật**
- Ứng dụng chăm sóc sức khỏe xử lý PHI/PII cục bộ
- Dịch vụ tài chính với yêu cầu tuân thủ
- Hệ thống chính phủ với yêu cầu chủ quyền dữ liệu

✅ **Tối ưu hóa cho Môi trường Biên**
- Thiết bị IoT với tài nguyên hạn chế
- Ứng dụng di động ưu tiên offline
- Hệ thống thời gian thực độ trễ thấp

✅ **Thiết kế Kiến trúc Thông minh**
- Hệ thống đa tác nhân cho quy trình làm việc phức tạp
- Triển khai hybrid biên-đám mây
- Hạ tầng AI tối ưu chi phí

✅ **Dẫn dắt Các Sáng kiến Edge AI**
- Đánh giá khả năng Edge AI cho dự án
- Lựa chọn mô hình và framework phù hợp
- Kiến trúc giải pháp AI cục bộ mở rộng

---

## 🗺️ Cấu trúc Workshop

### Tổng quan buổi học (6 buổi × 30 phút = 3 giờ)

| Buổi học | Chủ đề | Trọng tâm | Thời lượng |
|----------|--------|----------|------------|
| **1** | Bắt đầu với Foundry Local | Cài đặt, xác minh, hoàn thành đầu tiên | 30 phút |
| **2** | Xây dựng Giải pháp AI với RAG | Kỹ thuật prompt, embeddings, đánh giá | 30 phút |
| **3** | Mô hình Mã nguồn Mở | Khám phá mô hình, đánh giá, lựa chọn | 30 phút |
| **4** | Mô hình Tiên tiến | SLM vs LLM, tối ưu hóa, framework | 30 phút |
| **5** | Tác nhân AI | Thiết kế tác nhân, điều phối, bộ nhớ | 30 phút |
| **6** | Mô hình như Công cụ | Điều hướng, chuỗi, chiến lược mở rộng | 30 phút |

---

## 🚀 Bắt đầu nhanh

### Yêu cầu trước

**Yêu cầu hệ thống:**
- **Hệ điều hành**: Windows 10/11, macOS 11+, hoặc Linux (Ubuntu 20.04+)
- **RAM**: Tối thiểu 8GB, khuyến nghị 16GB+
- **Dung lượng lưu trữ**: Tối thiểu 10GB trống cho mô hình
- **CPU**: Bộ xử lý hiện đại hỗ trợ AVX2
- **GPU** (tùy chọn): Tương thích CUDA hoặc Qualcomm NPU để tăng tốc

**Yêu cầu phần mềm:**
- **Python 3.8+** ([Tải xuống](https://www.python.org/downloads/))
- **Microsoft Foundry Local** ([Hướng dẫn cài đặt](../../../Workshop))
- **Git** ([Tải xuống](https://git-scm.com/downloads))
- **Visual Studio Code** (khuyến nghị) ([Tải xuống](https://code.visualstudio.com/))

### Cài đặt trong 3 bước

#### 1. Cài đặt Foundry Local

**Windows:**
```powershell
winget install Microsoft.FoundryLocal
```

**macOS:**
```bash
brew tap microsoft/foundrylocal
brew install foundrylocal
```

**Xác minh cài đặt:**
```bash
foundry --version
foundry service status
```

**Đảm bảo Azure AI Foundry Local đang chạy với một cổng cố định**

```bash
# Set FoundryLocal to use port 58123 (default)
foundry service set --port 58123 --show

# Or use a different port
foundry service set --port 58000 --show
```

**Xác minh hoạt động:**
```bash
# Check service status
foundry service status

# Test the endpoint
curl http://127.0.0.1:58123/v1/models
```
**Tìm các mô hình có sẵn**
Để xem các mô hình có sẵn trong phiên bản Foundry Local của bạn, bạn có thể truy vấn endpoint mô hình:

```bash
# cmd/bash/powershell
foundry model list
```

Sử dụng Web Endpoint 

```bash
# Windows PowerShell
powershell -Command "Invoke-RestMethod -Uri 'http://127.0.0.1:58123/v1/models' -Method Get"

# Or using curl (if available)
curl http://127.0.0.1:58123/v1/models
```

#### 2. Clone Repository & Cài đặt Dependencies

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

#### 3. Chạy Mẫu Đầu Tiên của Bạn

```bash
# Start Foundry Local and load a model
foundry model run phi-4-mini

# Run the chat bootstrap sample
cd samples
python -m session01.chat_bootstrap "What is edge AI?"
```

**✅ Thành công!** Bạn sẽ thấy phản hồi streaming về edge AI.

---

## 📦 Tài nguyên Workshop

### Mẫu Python

Các ví dụ thực hành tiến bộ minh họa từng khái niệm:

| Buổi học | Mẫu | Mô tả | Thời gian chạy |
|----------|------|-------|----------------|
| 1 | [`chat_bootstrap.py`](../../../Workshop/samples/session01/chat_bootstrap.py) | Chat cơ bản & streaming | ~30s |
| 2 | [`rag_pipeline.py`](../../../Workshop/samples/session02/rag_pipeline.py) | RAG với embeddings | ~45s |
| 2 | [`rag_eval_ragas.py`](../../../Workshop/samples/session02/rag_eval_ragas.py) | Đánh giá chất lượng RAG | ~60s |
| 3 | [`benchmark_oss_models.py`](../../../Workshop/samples/session03/benchmark_oss_models.py) | Đánh giá đa mô hình | ~2-3m |
| 4 | [`model_compare.py`](../../../Workshop/samples/session04/model_compare.py) | So sánh SLM vs LLM | ~45s |
| 5 | [`agents_orchestrator.py`](../../../Workshop/samples/session05/agents_orchestrator.py) | Hệ thống đa tác nhân | ~60s |
| 6 | [`models_router.py`](../../../Workshop/samples/session06/models_router.py) | Điều hướng dựa trên ý định | ~45s |
| 6 | [`models_pipeline.py`](../../../Workshop/samples/session06/models_pipeline.py) | Pipeline nhiều bước | ~60s |

### Jupyter Notebooks

Khám phá tương tác với giải thích và hình ảnh hóa:

| Buổi học | Notebook | Mô tả | Độ khó |
|----------|----------|-------|--------|
| 1 | [`session01_chat_bootstrap.ipynb`](./notebooks/session01_chat_bootstrap.ipynb) | Cơ bản về chat & streaming | ⭐ Người mới bắt đầu |
| 2 | [`session02_rag_pipeline.ipynb`](./notebooks/session02_rag_pipeline.ipynb) | Xây dựng hệ thống RAG | ⭐⭐ Trung cấp |
| 2 | [`session02_rag_eval_ragas.ipynb`](./notebooks/session02_rag_eval_ragas.ipynb) | Đánh giá chất lượng RAG | ⭐⭐ Trung cấp |
| 3 | [`session03_benchmark_oss_models.ipynb`](./notebooks/session03_benchmark_oss_models.ipynb) | Đánh giá mô hình | ⭐⭐ Trung cấp |
| 4 | [`session04_model_compare.ipynb`](./notebooks/session04_model_compare.ipynb) | So sánh mô hình | ⭐⭐ Trung cấp |
| 5 | [`session05_agents_orchestrator.ipynb`](./notebooks/session05_agents_orchestrator.ipynb) | Điều phối tác nhân | ⭐⭐⭐ Nâng cao |
| 6 | [`session06_models_router.ipynb`](./notebooks/session06_models_router.ipynb) | Điều hướng ý định | ⭐⭐⭐ Nâng cao |
| 6 | [`session06_models_pipeline.ipynb`](./notebooks/session06_models_pipeline.ipynb) | Điều phối pipeline | ⭐⭐⭐ Nâng cao |

### Tài liệu

Hướng dẫn và tham khảo toàn diện:

| Tài liệu | Mô tả | Sử dụng khi |
|---------|-------|------------|
| [QUICK_START.md](./QUICK_START.md) | Hướng dẫn cài đặt nhanh | Bắt đầu từ đầu |
| [QUICK_REFERENCE.md](./QUICK_REFERENCE.md) | Cheat sheet lệnh & API | Cần câu trả lời nhanh |
| [FOUNDRY_SDK_QUICKREF.md](./FOUNDRY_SDK_QUICKREF.md) | Mẫu & ví dụ SDK | Viết mã |
| [ENV_CONFIGURATION.md](./ENV_CONFIGURATION.md) | Hướng dẫn biến môi trường | Cấu hình mẫu |
| [SAMPLES_UPDATE_SUMMARY.md](./SAMPLES_UPDATE_SUMMARY.md) | Cải tiến mẫu mới nhất | Hiểu thay đổi |
| [SDK_MIGRATION_NOTES.md](./SDK_MIGRATION_NOTES.md) | Hướng dẫn di chuyển | Nâng cấp mã |
| [notebooks/TROUBLESHOOTING.md](./notebooks/TROUBLESHOOTING.md) | Vấn đề thường gặp & cách khắc phục | Gỡ lỗi vấn đề |

---

## 🎓 Khuyến nghị Lộ trình Học tập

### Dành cho Người Mới Bắt Đầu (3-4 giờ)
1. ✅ Buổi 1: Bắt đầu (tập trung vào cài đặt và chat cơ bản)
2. ✅ Buổi 2: Cơ bản về RAG (bỏ qua đánh giá ban đầu)
3. ✅ Buổi 3: Đánh giá đơn giản (chỉ 2 mô hình)
4. ⏭️ Bỏ qua Buổi 4-6 lúc đầu
5. 🔄 Quay lại Buổi 4-6 sau khi xây dựng ứng dụng đầu tiên

### Dành cho Nhà Phát Triển Trung Cấp (3 giờ)
1. ⚡ Buổi 1: Xác minh cài đặt nhanh
2. ✅ Buổi 2: Hoàn thành pipeline RAG với đánh giá
3. ✅ Buổi 3: Bộ đánh giá đầy đủ
4. ✅ Buổi 4: Tối ưu hóa mô hình
5. ✅ Buổi 5-6: Tập trung vào mẫu kiến trúc

### Dành cho Người Thực Hành Nâng Cao (2-3 giờ)
1. ⚡ Buổi 1-3: Xem nhanh và xác minh
2. ✅ Buổi 4: Phân tích sâu về tối ưu hóa
3. ✅ Buổi 5: Kiến trúc đa tác nhân
4. ✅ Buổi 6: Mẫu sản xuất và mở rộng
5. 🚀 Mở rộng: Xây dựng logic điều hướng tùy chỉnh và triển khai hybrid

---

## Bộ Buổi Học Workshop (Labs Tập Trung 30 Phút)

Nếu bạn đang theo định dạng workshop 6 buổi học cô đọng, hãy sử dụng các hướng dẫn chuyên dụng này (mỗi hướng dẫn tương ứng và bổ sung cho tài liệu module rộng hơn ở trên):

| Buổi Workshop | Hướng dẫn | Trọng tâm cốt lõi |
|---------------|-----------|-------------------|
| 1 | [Session01-GettingStartedFoundryLocal](./Session01-GettingStartedFoundryLocal.md) | Cài đặt, xác minh, chạy phi & GPT-OSS-20B, tăng tốc |
| 2 | [Session02-BuildAISolutionsRAG](./Session02-BuildAISolutionsRAG.md) | Kỹ thuật prompt, mẫu RAG, CSV & tài liệu grounding, di chuyển |
| 3 | [Session03-OpenSourceModels](./Session03-OpenSourceModels.md) | Tích hợp Hugging Face, đánh giá, lựa chọn mô hình |
| 4 | [Session04-CuttingEdgeModels](./Session04-CuttingEdgeModels.md) | SLM so với LLM, WebGPU, Chainlit RAG, tăng tốc ONNX |
| 5 | [Session05-AIPoweredAgents](./Session05-AIPoweredAgents.md) | Vai trò của agent, bộ nhớ, công cụ, điều phối |
| 6 | [Session06-ModelsAsTools](./Session06-ModelsAsTools.md) | Định tuyến, chuỗi, mở rộng quy mô lên Azure |

Mỗi tệp phiên bao gồm: tóm tắt, mục tiêu học tập, luồng demo 30 phút, dự án khởi đầu, danh sách kiểm tra xác thực, xử lý sự cố và tham chiếu đến SDK Python Foundry Local chính thức.

### Mẫu Script

Cài đặt các phụ thuộc của workshop (Windows):

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

Nếu chạy dịch vụ Foundry Local trên một máy (Windows) hoặc VM khác từ macOS, xuất endpoint:

```bash
export FOUNDRY_LOCAL_ENDPOINT=http://<windows-host>:5273/v1
```

| Phiên | Script(s) | Mô tả |
|-------|-----------|-------|
| 1 | `samples/session01/chat_bootstrap.py` | Khởi động dịch vụ & chat streaming |
| 2 | `samples/session02/rag_pipeline.py` | RAG tối thiểu (embedding trong bộ nhớ) |
|   | `samples/session02/rag_eval_ragas.py` | Đánh giá RAG với các chỉ số ragas |
| 3 | `samples/session03/benchmark_oss_models.py` | Đánh giá độ trễ & thông lượng đa mô hình |
| 4 | `samples/session04/model_compare.py` | So sánh SLM và LLM (độ trễ & kết quả mẫu) |
| 5 | `samples/session05/agents_orchestrator.py` | Pipeline nghiên cứu → biên tập của hai agent |
| 6 | `samples/session06/models_router.py` | Demo định tuyến dựa trên ý định |
|   | `samples/session06/models_pipeline.py` | Chuỗi lập kế hoạch/thực hiện/tinh chỉnh nhiều bước |

### Biến Môi Trường (Chung cho các mẫu)

| Biến | Mục đích | Ví dụ |
|------|----------|-------|
| `FOUNDRY_LOCAL_ALIAS` | Alias mô hình đơn mặc định cho các mẫu cơ bản | `phi-4-mini` |
| `SLM_ALIAS` / `LLM_ALIAS` | SLM rõ ràng so với mô hình lớn hơn để so sánh | `phi-4-mini` / `gpt-oss-20b` |
| `BENCH_MODELS` | Danh sách alias để đánh giá | `qwen2.5-0.5b,mistral-7b` |
| `BENCH_ROUNDS` | Số lần lặp lại đánh giá mỗi mô hình | `3` |
| `BENCH_PROMPT` | Prompt sử dụng trong đánh giá | `Explain retrieval augmented generation briefly.` |
| `EMBED_MODEL` | Mô hình embedding của sentence-transformers | `sentence-transformers/all-MiniLM-L6-v2` |
| `RAG_QUESTION` | Ghi đè truy vấn kiểm tra cho pipeline RAG | `Why use RAG with local inference?` |
| `AGENT_QUESTION` | Ghi đè truy vấn pipeline của agent | `Explain why edge AI matters for compliance.` |
| `AGENT_MODEL_PRIMARY` | Alias mô hình cho agent nghiên cứu | `phi-4-mini` |
| `AGENT_MODEL_EDITOR` | Alias mô hình cho agent biên tập (có thể khác) | `gpt-oss-20b` |
| `SHOW_USAGE` | Khi `1`, in mức sử dụng token mỗi lần hoàn thành | `1` |
| `RETRY_ON_FAIL` | Khi `1`, thử lại một lần khi gặp lỗi chat tạm thời | `1` |
| `RETRY_BACKOFF` | Số giây chờ trước khi thử lại | `1.0` |

Nếu một biến không được đặt, các script sẽ sử dụng giá trị mặc định hợp lý. Đối với các demo mô hình đơn, bạn thường chỉ cần `FOUNDRY_LOCAL_ALIAS`.

### Mô-đun Tiện ích

Tất cả các mẫu hiện chia sẻ một helper `samples/workshop_utils.py` cung cấp:

* Tạo bộ nhớ cache `FoundryLocalManager` + client OpenAI
* Helper `chat_once()` với tùy chọn thử lại + in mức sử dụng
* Báo cáo mức sử dụng token đơn giản (kích hoạt qua `SHOW_USAGE=1`)

Điều này giúp giảm sự trùng lặp và làm nổi bật các thực hành tốt nhất để điều phối mô hình cục bộ hiệu quả.

## Các Nâng Cấp Tùy Chọn (Xuyên Suốt Các Phiên)

| Chủ đề | Nâng cấp | Phiên | Env / Toggle |
|--------|----------|-------|--------------|
| Tính xác định | Nhiệt độ cố định + bộ prompt ổn định | 1–6 | Đặt `temperature=0`, `top_p=1` |
| Hiển thị mức sử dụng token | Dạy về chi phí/hiệu quả nhất quán | 1–6 | `SHOW_USAGE=1` |
| Streaming Token Đầu Tiên | Thước đo độ trễ cảm nhận | 1,3,4,6 | `BENCH_STREAM=1` (đánh giá) |
| Khả năng chịu lỗi khi thử lại | Xử lý khởi động lạnh tạm thời | Tất cả | `RETRY_ON_FAIL=1` + `RETRY_BACKOFF` |
| Agent Đa Mô Hình | Chuyên môn hóa vai trò không đồng nhất | 5 | `AGENT_MODEL_PRIMARY`, `AGENT_MODEL_EDITOR` |
| Định tuyến thích ứng | Ý định + heuristic chi phí | 6 | Mở rộng router với logic leo thang |
| Bộ nhớ vector | Ghi nhớ ngữ nghĩa dài hạn | 2,5,6 | Tích hợp FAISS/Chroma embedding index |
| Xuất Trace | Kiểm tra & đánh giá | 2,5,6 | Thêm dòng JSON mỗi bước |
| Rubric Chất lượng | Theo dõi định tính | 3–6 | Prompt chấm điểm thứ cấp |
| Kiểm tra nhanh | Xác thực trước workshop nhanh | Tất cả | `python Workshop/tests/smoke.py` |

### Khởi Động Nhanh Tính Xác Định

```powershell
set FOUNDRY_LOCAL_ALIAS=phi-4-mini
set SHOW_USAGE=1
python Workshop\tests\smoke.py
```

Dự kiến số lượng token ổn định qua các đầu vào giống hệt nhau lặp lại.

### Đánh Giá RAG (Phiên 2)

Sử dụng `rag_eval_ragas.py` để tính toán mức độ liên quan của câu trả lời, độ chính xác và độ chính xác ngữ cảnh trên một tập dữ liệu tổng hợp nhỏ:

```powershell
cd Workshop/samples
python -m session02.rag_eval_ragas
```

Mở rộng bằng cách cung cấp một JSONL lớn hơn gồm các câu hỏi, ngữ cảnh và sự thật cơ bản, sau đó chuyển đổi sang một `Dataset` của Hugging Face.

## Phụ Lục Độ Chính Xác Lệnh CLI

Workshop chỉ sử dụng các lệnh CLI Foundry Local hiện được tài liệu hóa / ổn định.

### Các Lệnh Ổn Định Được Tham Chiếu

| Danh mục | Lệnh | Mục đích |
|----------|------|----------|
| Core | `foundry --version` | Hiển thị phiên bản đã cài đặt |
| Core | `foundry init` | Khởi tạo cấu hình |
| Dịch vụ | `foundry service start` | Khởi động dịch vụ cục bộ (nếu không tự động) |
| Dịch vụ | `foundry status` | Hiển thị trạng thái dịch vụ |
| Mô hình | `foundry model list` | Liệt kê danh mục / các mô hình có sẵn |
| Mô hình | `foundry model download <alias>` | Tải trọng lượng mô hình vào bộ nhớ cache |
| Mô hình | `foundry model run <alias>` | Khởi chạy (tải) một mô hình cục bộ; kết hợp với `--prompt` cho một lần |
| Mô hình | `foundry model unload <alias>` / `foundry model stop <alias>` | Dỡ một mô hình khỏi bộ nhớ (nếu được hỗ trợ) |
| Bộ nhớ cache | `foundry cache list` | Liệt kê các mô hình đã được cache (tải xuống) |
| Hệ thống | `foundry system info` | Snapshot khả năng phần cứng & tăng tốc |
| Hệ thống | `foundry system gpu-info` | Thông tin chẩn đoán GPU |
| Cấu hình | `foundry config list` | Hiển thị giá trị cấu hình hiện tại |
| Cấu hình | `foundry config set <key> <value>` | Cập nhật cấu hình |

### Mẫu Prompt Một Lần

Thay vì lệnh con `model chat` đã bị loại bỏ, sử dụng:

```powershell
foundry model run <alias> --prompt "Your question here"
```

Lệnh này thực hiện một chu kỳ prompt/response duy nhất rồi thoát.

### Các Mẫu Bị Loại Bỏ / Tránh

| Bị loại bỏ / Không được tài liệu hóa | Thay thế / Hướng dẫn |
|-------------------------------------|----------------------|
| `foundry model chat <model> "..."` | `foundry model run <model> --prompt "..."` |
| `foundry model list --running` | Sử dụng `foundry model list` thông thường + hoạt động gần đây / log |
| `foundry model list --cached` | `foundry cache list` |
| `foundry model stats <model>` | Sử dụng script đánh giá Python + công cụ hệ điều hành (Task Manager / `nvidia-smi`) |
| `foundry model benchmark ...` | `samples/session03/benchmark_oss_models.py` |

### Đánh Giá & Telemetry

- Độ trễ, p95, token/giây: `samples/session03/benchmark_oss_models.py`
- Độ trễ token đầu tiên (streaming): đặt `BENCH_STREAM=1`
- Sử dụng tài nguyên: công cụ giám sát hệ điều hành (Task Manager, Activity Monitor, `nvidia-smi`) + `foundry system info`.

Khi các lệnh telemetry CLI mới ổn định upstream, chúng có thể được tích hợp với các chỉnh sửa tối thiểu vào các tệp markdown của phiên.

### Lint Guard Tự Động

Một linter tự động ngăn chặn việc tái giới thiệu các mẫu CLI bị loại bỏ bên trong các khối mã của tệp markdown:

Script: `Workshop/scripts/lint_markdown_cli.py`

Các mẫu bị loại bỏ bị chặn bên trong các khối mã.

Các thay thế được khuyến nghị:
| Bị loại bỏ | Thay thế |
|-----------|----------|
| `foundry model chat <a> "..."` | `foundry model run <a> --prompt "..."` |
| `model list --running` | `model list` |
| `model list --cached` | `cache list` |
| `model stats` | Script đánh giá + công cụ hệ thống |
| `model benchmark` | `samples/session03/benchmark_oss_models.py` |
| `model list --available` | `model list` |

Chạy cục bộ:
```powershell
python Workshop\scripts\lint_markdown_cli.py --verbose
```

GitHub Action: `.github/workflows/markdown-cli-lint.yml` chạy trên mỗi lần đẩy & PR.

Hook pre-commit tùy chọn:
```bash
echo "python Workshop/scripts/lint_markdown_cli.py" > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

## Bảng Di Chuyển Nhanh CLI → SDK

| Nhiệm vụ | Lệnh CLI Một Dòng | Tương đương SDK (Python) | Ghi chú |
|----------|-------------------|--------------------------|---------|
| Chạy một mô hình một lần (prompt) | `foundry model run phi-4-mini --prompt "Hello"` | `manager=FoundryLocalManager("phi-4-mini"); client=OpenAI(base_url=manager.endpoint, api_key=manager.api_key or "not-needed"); client.chat.completions.create(model=manager.get_model_info("phi-4-mini").id, messages=[{"role":"user","content":"Hello"}])` | SDK tự động khởi động dịch vụ & caching |
| Tải xuống (cache) mô hình | `foundry model download qwen2.5-0.5b` | `FoundryLocalManager("qwen2.5-0.5b")  # triggers download/load` | Manager chọn biến thể tốt nhất nếu alias ánh xạ đến nhiều bản dựng |
| Liệt kê danh mục | `foundry model list` | `# use manager for each alias or maintain known list` | CLI tổng hợp; SDK hiện tại khởi tạo theo alias |
| Liệt kê các mô hình đã cache | `foundry cache list` | `manager.list_cached_models()` | Sau khi khởi tạo manager (bất kỳ alias nào) |
| Kích hoạt tăng tốc GPU | `foundry config set compute.onnx.enable_gpu true` | `# CLI action; SDK assumes config already applied` | Cấu hình là hiệu ứng bên ngoài |
| Lấy URL endpoint | (ngầm định) | `manager.endpoint` | Sử dụng để tạo client tương thích OpenAI |
| Làm nóng một mô hình | `foundry model run <alias>` sau đó prompt đầu tiên | `chat_once(alias, messages=[...])` (utility) | Các tiện ích xử lý khởi động lạnh ban đầu |
| Đo độ trễ | `python -m session03.benchmark_oss_models` | `import benchmark_oss_models` (hoặc script xuất mới) | Ưu tiên script để có các thước đo nhất quán |
| Dừng / dỡ mô hình | `foundry model unload <alias>` | (Không được cung cấp – khởi động lại dịch vụ / quy trình) | Thường không cần thiết cho luồng workshop |
| Lấy mức sử dụng token | (xem output) | `resp.usage.total_tokens` | Được cung cấp nếu backend trả về đối tượng usage |

## Xuất Markdown Đánh Giá

Sử dụng script `Workshop/scripts/export_benchmark_markdown.py` để chạy một đánh giá mới (logic tương tự như `samples/session03/benchmark_oss_models.py`) và xuất một bảng Markdown thân thiện với GitHub cùng với JSON thô.

### Ví dụ

```powershell
python Workshop\scripts\export_benchmark_markdown.py --models "qwen2.5-0.5b,mistral-7b" --prompt "Explain retrieval augmented generation briefly." --rounds 3 --output benchmark_report.md
```

Các tệp được tạo:
| Tệp | Nội dung |
|-----|----------|
| `benchmark_report.md` | Bảng Markdown + gợi ý diễn giải |
| `benchmark_report.json` | Mảng số liệu thô (để so sánh / theo dõi xu hướng) |

Đặt `BENCH_STREAM=1` trong môi trường để bao gồm độ trễ token đầu tiên nếu được hỗ trợ.

---

**Tuyên bố miễn trừ trách nhiệm**:  
Tài liệu này đã được dịch bằng dịch vụ dịch thuật AI [Co-op Translator](https://github.com/Azure/co-op-translator). Mặc dù chúng tôi cố gắng đảm bảo độ chính xác, xin lưu ý rằng các bản dịch tự động có thể chứa lỗi hoặc không chính xác. Tài liệu gốc bằng ngôn ngữ bản địa nên được coi là nguồn thông tin chính xác nhất. Đối với thông tin quan trọng, chúng tôi khuyến nghị sử dụng dịch vụ dịch thuật chuyên nghiệp từ con người. Chúng tôi không chịu trách nhiệm cho bất kỳ sự hiểu lầm hoặc diễn giải sai nào phát sinh từ việc sử dụng bản dịch này.