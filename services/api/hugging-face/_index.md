---
title: "Hugging Face Inference API - 免费测试数千个开源模型"
linkTitle: "API - Hugging Face"
description: "Hugging Face Inference API 提供免费 API 服务，支持数千个开源模型。免费层每小时数百次请求，PRO 账户 $9/月提供更高配额。支持文本生成、图像生成、语音识别等多种任务，简单易用。"
keywords:
  - Hugging Face API
  - Inference API
  - 免费 AI API
  - 开源模型 API
  - Llama API
  - Mistral API
  - 免费大模型 API
  - Transformers API
image: /images/logo.svg
type: docs
weight: 21
comments: true
prev: /services/api/anthropic
next: /services/api
sidebar:
  open: true
---

## 📋 服务概览

**服务名称:** Hugging Face Inference API  
**所属提供者:** [Hugging Face](/providers/hugging-face)  
**API 端点:** `https://api-inference.huggingface.co/models/{model_id}`  
**服务类型:** 免费增值（Free 约 $0.10/月 + PRO $9/月含 $2/月）  
**注册要求:** 需要注册并获取 API Token

---

## ✅ 服务说明

Hugging Face Inference API 是一个无服务器推理 API 服务，允许开发者通过简单的 HTTP 请求调用数千个托管在 Hugging Face Hub 上的开源模型。无需自己部署模型，即可快速测试和集成各种 AI 功能。

### 主要特点

- **模型丰富:** 支持数千个公开模型，涵盖各种 AI 任务
- **免费配额:** Free 账户约 $0.10/月，PRO 账户约 $2/月（参考值）
- **即用即走:** 无需部署，API 调用即可使用
- **支持多任务:** 文本生成、图像生成、语音识别、图像分类等

---

## 🎁 可用模型

### 免费可用的模型类型

Hugging Face Inference API 支持以下任务类型的模型：

#### 自然语言处理（NLP）

| 任务类型 | 说明 | 示例模型 |
|---------|------|---------|
| **Text Generation** | 文本生成 | Llama, Mistral, Qwen, DeepSeek |
| **Text Classification** | 文本分类 | BERT, RoBERTa |
| **Token Classification** | 命名实体识别 | BERT-NER |
| **Question Answering** | 问答系统 | BERT-QA |
| **Translation** | 机器翻译 | MarianMT, T5 |
| **Summarization** | 文本摘要 | BART, T5 |
| **Fill-Mask** | 填空 | BERT, RoBERTa |

#### 计算机视觉（CV）

| 任务类型 | 说明 | 示例模型 |
|---------|------|---------|
| **Image Classification** | 图像分类 | ResNet, ViT |
| **Object Detection** | 目标检测 | DETR, YOLO |
| **Image Segmentation** | 图像分割 | SegFormer |
| **Image-to-Image** | 图像转换 | Stable Diffusion |
| **Text-to-Image** | 文本生成图像 | Stable Diffusion, DALL-E mini |

#### 音频处理

| 任务类型 | 说明 | 示例模型 |
|---------|------|---------|
| **Automatic Speech Recognition** | 语音识别 | Whisper |
| **Audio Classification** | 音频分类 | Wav2Vec2 |
| **Text-to-Speech** | 语音合成 | FastSpeech |

### 热门模型示例

- **Llama 3.1 8B / 70B** - Meta 的开源大语言模型
- **Mistral 7B / Mixtral 8x7B** - Mistral AI 的高性能模型
- **Qwen 2.5** - 阿里云的多语言模型
- **FLUX.1** - 高质量图像生成模型
- **Whisper** - OpenAI 的语音识别模型
- **Stable Diffusion** - 图像生成模型

---

## 🔢 配额和限制

### 免费层级限制

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **月度配额** | Free 约 $0.10/月 | PRO 约 $2/月（参考值，以官网为准） |
| **速率限制** | 视账户等级 | Free/PRO/Team/Enterprise 有不同限制 |
| **并发请求** | 有限制 | 避免短时间内大量请求 |
| **冷启动时间** | 可能较长 | 首次请求可能需要等待模型加载 |
| **响应时间** | 无保证 | 尽力而为，无 SLA |
| **需要信用卡** | ❌ 不需要 | 免费配额无需信用卡 |

### PRO 账户（$9/月）

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **月度配额** | 约 $2/月 | 包含在 $9/月订阅中，支持按量付费 |
| **速率限制** | 更高限制 | 显著提升速率限制 |
| **优先处理** | ✅ | 请求优先处理，减少等待 |
| **冷启动** | 更快 | 模型保持活跃状态 |
| **提前访问** | ✅ | 提前访问新功能和模型 |

### ⚠️ 重要限制

1. **月度配额限制:** Free 约 $0.10/月，PRO 约 $2/月，配额耗尽后会受限（数值以官网为准）
2. **冷启动延迟:** 模型首次请求或长时间未使用后，需要加载时间（可能 10-30 秒）
3. **速率限制:** 不同账户等级有不同的速率限制，超过会返回 429 错误
4. **模型可用性:** 部分模型可能需要 PRO 账户或特殊权限
5. **无 SLA 保证:** 免费层不提供服务水平协议保证
6. **生产使用限制:** 不建议免费层用于生产环境，建议使用专用推理端点

---

## 💰 价格说明

### 免费层

- **价格:** 完全免费
- **月度配额:** 约 $0.10/月（参考值，以官网为准）
- **适用场景:** 测试、学习、小规模应用

### PRO 账户

- **价格:** $9/月
- **包含配额:** 约 $2/月的 Inference credits
- **特点:**
  - 更高的速率限制
  - 优先处理请求
  - 更快的冷启动
  - 支持按量付费（超出配额后）
  - 提前访问新功能
- **适用场景:** 个人项目、中小规模应用

### 专用推理端点（Dedicated Inference Endpoints）

- **价格:** 按使用量计费，从 $0.06/小时起
- **特点:**
  - 专用计算资源
  - 无冷启动
  - 自动扩缩容
  - SLA 保证
- **适用场景:** 生产环境、企业应用

---

## 🚀 如何使用

### 前提条件

**1. 注册账户**

请先 [注册 Hugging Face 账户](/providers/hugging-face#注册账户)。

**2. 获取 Access Token**

{{% steps %}}

##### 登录 Hugging Face

访问 [https://huggingface.co](https://huggingface.co) 并登录您的账户

##### 进入设置页面

点击右上角头像 → Settings → Access Tokens

##### 创建新 Token

1. 点击"New token"按钮
2. 输入 Token 名称（如：my-api-token）
3. 选择权限类型（建议选择 Read）
4. 点击"Generate a token"
5. **重要：** 复制并安全保存您的 Token

{{% /steps %}}

---

## 💻 代码示例

### Python 示例

**安装依赖:**

```bash {filename="Bash"}
pip install requests
# 或使用官方库
pip install huggingface_hub
```

**使用 requests 库:**

```python {filename="Python"}
import requests

API_URL = "https://api-inference.huggingface.co/models/meta-llama/Llama-3.1-8B-Instruct"
headers = {"Authorization": "Bearer YOUR_HF_TOKEN"}

def query(payload):
    response = requests.post(API_URL, headers=headers, json=payload)
    return response.json()

# 调用 API
output = query({
    "inputs": "请介绍一下人工智能的发展历史。",
    "parameters": {
        "max_new_tokens": 500,
        "temperature": 0.7
    }
})

print(output)
```

**使用 huggingface_hub 库:**

```python {filename="Python"}
from huggingface_hub import InferenceClient

# 初始化客户端
client = InferenceClient(token="YOUR_HF_TOKEN")

# 文本生成
response = client.text_generation(
    "请介绍一下人工智能的发展历史。",
    model="meta-llama/Llama-3.1-8B-Instruct",
    max_new_tokens=500,
    temperature=0.7
)

print(response)
```

**流式输出:**

```python {filename="Python"}
from huggingface_hub import InferenceClient

client = InferenceClient(token="YOUR_HF_TOKEN")

# 流式文本生成
for token in client.text_generation(
    "写一首关于春天的诗",
    model="meta-llama/Llama-3.1-8B-Instruct",
    max_new_tokens=200,
    stream=True
):
    print(token, end="", flush=True)
```

---

### cURL 示例

**文本生成:**

```bash {filename="Bash"}
curl https://api-inference.huggingface.co/models/meta-llama/Llama-3.1-8B-Instruct \
  -X POST \
  -H "Authorization: Bearer YOUR_HF_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "inputs": "请介绍一下人工智能的发展历史。",
    "parameters": {
      "max_new_tokens": 500,
      "temperature": 0.7
    }
  }'
```

**图像生成:**

```bash {filename="Bash"}
curl https://api-inference.huggingface.co/models/stabilityai/stable-diffusion-2-1 \
  -X POST \
  -H "Authorization: Bearer YOUR_HF_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "inputs": "a beautiful sunset over the ocean, oil painting style"
  }' \
  --output image.jpg
```

---

### Node.js 示例

```javascript {filename="JavaScript"}
import { HfInference } from '@huggingface/inference'

const hf = new HfInference('YOUR_HF_TOKEN')

async function generateText() {
  const result = await hf.textGeneration({
    model: 'meta-llama/Llama-3.1-8B-Instruct',
    inputs: '请介绍一下人工智能的发展历史。',
    parameters: {
      max_new_tokens: 500,
      temperature: 0.7
    }
  })
  
  console.log(result.generated_text)
}

generateText()
```

---

## 🌟 核心优势

### 技术优势

1. **无需部署:**
   - 无需管理服务器和基础设施
   - 无需安装和配置模型
   - 开箱即用，专注于应用开发

2. **模型丰富:**
   - 超过 100 万个模型可选
   - 覆盖各种 AI 任务和场景
   - 持续更新最新模型

3. **快速迭代:**
   - 快速测试不同模型
   - 轻松切换模型
   - 加速原型开发

### 与其他 API 对比

| 特性 | Hugging Face API | OpenAI API | Google AI Studio API | DeepSeek API |
|------|-----------------|-----------|---------------------|-------------|
| 免费配额 | 约数百次/小时 | $18/3个月 | 免费使用 | ¥5/7天 |
| 模型数量 | 🏆 100万+ | 少数模型 | Gemini系列 | DeepSeek系列 |
| 开源模型 | 🏆 完全支持 | ❌ 不支持 | ❌ 不支持 | ✅ 部分开源 |
| 自带模型 | ✅ 可上传 | ❌ 不可 | ❌ 不可 | ❌ 不可 |
| 任务类型 | 🏆 最全面 | 主要NLP | 主要NLP | 主要NLP |
| 需要信用卡 | ❌ | ✅ | ❌ | ⚠️ 充值 |
| 冷启动 | ⚠️ 有 | ❌ 无 | ❌ 无 | ❌ 无 |

---

## 💡 实用建议

### ✅ 推荐做法

1. **选择合适的模型:**
   - 根据任务类型选择专门模型
   - 查看模型下载量和评分
   - 在 Playground 中测试后再集成

2. **处理冷启动:**
   ```python
   import time
   
   def query_with_retry(payload, max_retries=3):
       """带重试的 API 调用，处理冷启动"""
       for attempt in range(max_retries):
           try:
               response = requests.post(API_URL, headers=headers, json=payload)
               if response.status_code == 503:
                   # 模型加载中，等待后重试
                   wait_time = 10 + (attempt * 5)
                   print(f"模型加载中，等待 {wait_time} 秒...")
                   time.sleep(wait_time)
                   continue
               return response.json()
           except Exception as e:
               print(f"请求失败: {e}")
               if attempt == max_retries - 1:
                   raise
       return None
   ```

3. **缓存结果:**
   - 对相同输入缓存结果
   - 减少 API 调用次数
   - 提高应用响应速度

### 🎯 最佳实践

**速率限制处理:**

```python {filename="Python"}
import time
from requests.exceptions import HTTPError

def call_api_with_rate_limit(payload):
    """带速率限制处理的 API 调用"""
    max_retries = 5
    retry_delay = 1
    
    for attempt in range(max_retries):
        try:
            response = requests.post(API_URL, headers=headers, json=payload)
            response.raise_for_status()
            return response.json()
        except HTTPError as e:
            if e.response.status_code == 429:
                # 速率限制，指数退避重试
                wait_time = retry_delay * (2 ** attempt)
                print(f"速率限制，等待 {wait_time} 秒...")
                time.sleep(wait_time)
            else:
                raise
    
    raise Exception("达到最大重试次数")
```

**批量处理:**

```python {filename="Python"}
def batch_inference(inputs, batch_size=10):
    """批量推理，减少请求次数"""
    results = []
    
    for i in range(0, len(inputs), batch_size):
        batch = inputs[i:i+batch_size]
        payload = {"inputs": batch}
        
        try:
            response = requests.post(API_URL, headers=headers, json=payload)
            results.extend(response.json())
            
            # 避免速率限制
            time.sleep(1)
        except Exception as e:
            print(f"批次 {i//batch_size} 失败: {e}")
    
    return results
```

### ⚠️ 注意事项

1. **Token 安全:** 不要将 Token 硬编码在代码中，使用环境变量
2. **速率限制:** 注意免费层速率限制，避免频繁请求
3. **冷启动:** 首次请求可能较慢，做好超时处理
4. **生产环境:** 免费层不适合生产环境，考虑专用推理端点
5. **模型许可:** 注意查看模型的使用许可，确保符合您的使用场景

---

## 🎯 实际应用案例

### 案例 1：多模型对比工具

**场景描述:** 对比不同模型对同一问题的回答

```python {filename="Python"}
from huggingface_hub import InferenceClient

client = InferenceClient(token="YOUR_HF_TOKEN")

models = [
    "meta-llama/Llama-3.1-8B-Instruct",
    "mistralai/Mistral-7B-Instruct-v0.2",
    "Qwen/Qwen2.5-7B-Instruct"
]

def compare_models(prompt):
    """对比多个模型的输出"""
    results = {}
    
    for model in models:
        print(f"\n测试模型: {model}")
        try:
            response = client.text_generation(
                prompt,
                model=model,
                max_new_tokens=200
            )
            results[model] = response
            print(f"回答: {response[:100]}...")
        except Exception as e:
            results[model] = f"错误: {e}"
    
    return results

# 使用示例
prompt = "请用一句话解释什么是人工智能。"
results = compare_models(prompt)

for model, response in results.items():
    print(f"\n{model}:")
    print(response)
```

### 案例 2：文档摘要服务

**场景描述:** 自动生成文档摘要

```python {filename="Python"}
from huggingface_hub import InferenceClient

client = InferenceClient(token="YOUR_HF_TOKEN")

def summarize_document(document_text):
    """生成文档摘要"""
    # 使用摘要模型
    summary = client.summarization(
        document_text,
        model="facebook/bart-large-cnn",
        max_length=150,
        min_length=50
    )
    
    return summary['summary_text']

# 使用示例
document = """
人工智能（Artificial Intelligence，AI）是计算机科学的一个分支，
旨在创建能够执行通常需要人类智能的任务的系统。这些任务包括视觉感知、
语音识别、决策制定和语言翻译等。AI 的发展经历了多个阶段...
"""

summary = summarize_document(document)
print(f"摘要: {summary}")
```

### 案例 3：智能图像分类应用

**场景描述:** 图像分类和内容识别

```python {filename="Python"}
from huggingface_hub import InferenceClient
from PIL import Image

client = InferenceClient(token="YOUR_HF_TOKEN")

def classify_image(image_path):
    """图像分类"""
    with open(image_path, "rb") as f:
        data = f.read()
    
    result = client.image_classification(
        data,
        model="google/vit-base-patch16-224"
    )
    
    return result

# 使用示例
image_path = "photo.jpg"
results = classify_image(image_path)

print("图像分类结果:")
for item in results:
    print(f"- {item['label']}: {item['score']:.2%}")
```

---

## 🔧 常见问题

**Q: Inference API 完全免费吗？**  
A: 提供免费配额（Free 约 $0.10/月，PRO $9/月含 $2/月），配额耗尽后会受限。PRO 支持按量付费。

**Q: 什么是冷启动？**  
A: 模型首次请求或长时间未使用后需要加载时间，可能需要 10-30 秒。PRO 用户冷启动更快。

**Q: 可以使用自己上传的模型吗？**  
A: 可以！上传模型到 Hugging Face Hub 后，就可以通过 Inference API 调用。

**Q: 免费层适合生产环境吗？**  
A: 不建议。免费层没有 SLA 保证，有速率限制和冷启动。生产环境建议使用专用推理端点。

**Q: 如何处理速率限制错误？**  
A: 实现指数退避重试机制，或升级到 PRO 账户，或使用专用推理端点。

**Q: 支持哪些编程语言？**  
A: 官方支持 Python、JavaScript/TypeScript。其他语言可直接使用 HTTP 请求。

---

## 🔗 相关资源

- **API 文档：** [https://huggingface.co/docs/api-inference](https://huggingface.co/docs/api-inference)
- **模型库：** [https://huggingface.co/models](https://huggingface.co/models)
- **提供者主页：** [Hugging Face](/providers/hugging-face)
- **对应的 Chatbot 服务：** [HuggingChat](/services/chatbot/hugging-face)
- **Python SDK：** [https://github.com/huggingface/huggingface_hub](https://github.com/huggingface/huggingface_hub)
- **JavaScript SDK：** [https://github.com/huggingface/huggingface.js](https://github.com/huggingface/huggingface.js)
- **API 状态：** [https://status.huggingface.co](https://status.huggingface.co)
- **定价页面：** [https://huggingface.co/pricing](https://huggingface.co/pricing)

---

## 📝 更新日志

- **2024年：** 支持更多模型类型和任务
- **2023年：** 推出 PRO 账户计划
- **2022年：** Inference API 正式发布
- **2021年：** 开始提供托管推理服务

---

**服务提供者：** [Hugging Face](/providers/hugging-face)
