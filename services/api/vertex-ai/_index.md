---
title: Google Vertex AI - API
weight: 6
comments: true
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [Google Vertex AI](/providers/google-vertex-ai)  
**服务类型：** API 服务  
**API 端点：** `https://[REGION]-aiplatform.googleapis.com`（需替换 `[REGION]`，如 `us-central1`）  
**免费类型：** 试用积分（$300，90天）

---

## 🎯 服务简介

Vertex AI API 提供企业级 AI 能力，支持 Gemini 系列模型，特别适合大规模生产部署和与 Google Cloud 服务集成。

**核心优势：**
- 💰 **$300 试用积分** - 90天有效
- 🌟 **Gemini 1.5 Pro** - 2M 超长上下文
- 🏢 **企业级** - 完整 MLOps 工具
- 🔐 **安全合规** - Google Cloud 标准
- 🌐 **全球部署** - 多区域可用
- 📊 **监控完善** - 完整日志和指标

---

## 🚀 快速开始

### 前提条件

**必需：**
- ✅ 已创建 Google Cloud 账户
- ✅ 已激活 $300 试用积分
- ✅ 已启用 Vertex AI API
- ✅ 已创建服务账号或 API 密钥

详细步骤请参考：[Vertex AI 注册指南](/providers/google-vertex-ai#注册和账号)

### 5 分钟快速示例

**安装 SDK：**
```bash {filename="Bash"}
pip install google-cloud-aiplatform
```

**使用示例：**
```python {filename="Python"}
import vertexai
from vertexai.generative_models import GenerativeModel

# 初始化
vertexai.init(project="YOUR_PROJECT_ID", location="us-central1")

# 创建模型实例
model = GenerativeModel("gemini-1.5-pro")

# 生成内容
response = model.generate_content("解释一下什么是 Vertex AI")
print(response.text)
```

---

## 🤖 支持的模型

### Gemini 1.5 Pro

**Model ID:** `gemini-1.5-pro`

| 特性 | 详情 |
|------|------|
| **上下文** | 2M tokens |
| **多模态** | 文本、图像、音频、视频 |
| **价格** | $1.25-2.50/M (in), $5-10/M (out) |

### Gemini 1.5 Flash

**Model ID:** `gemini-1.5-flash`

| 特性 | 详情 |
|------|------|
| **上下文** | 1M tokens |
| **速度** | 极快 |
| **价格** | $0.075-0.15/M (in), $0.30-0.60/M (out) |

---

## 📖 API 使用示例

### 1. 基础对话

```python {filename="Python"}
import vertexai
from vertexai.generative_models import GenerativeModel

vertexai.init(project="YOUR_PROJECT_ID", location="us-central1")

model = GenerativeModel("gemini-1.5-flash")

response = model.generate_content("你好，介绍一下 Gemini")
print(response.text)
```

### 2. 流式输出

```python {filename="Python"}
model = GenerativeModel("gemini-1.5-flash")

response = model.generate_content(
    "写一篇关于AI的文章",
    stream=True
)

for chunk in response:
    print(chunk.text, end="", flush=True)
```

### 3. 多模态输入（图像）

```python {filename="Python"}
from vertexai.generative_models import GenerativeModel, Part

model = GenerativeModel("gemini-1.5-pro")

# 从本地加载图像
image = Part.from_uri(
    "gs://your-bucket/image.jpg",
    mime_type="image/jpeg"
)

response = model.generate_content([
    "这张图片里有什么？",
    image
])

print(response.text)
```

### 4. 长上下文处理

```python {filename="Python"}
# 处理超长文本（例如整本书）
with open("long_document.txt", "r") as f:
    long_text = f.read()  # 可以是几百万字

model = GenerativeModel("gemini-1.5-pro")

response = model.generate_content(
    f"总结以下文档的核心要点：\n\n{long_text}"
)

print(response.text)
```

### 5. 函数调用

```python {filename="Python"}
from vertexai.generative_models import (
    GenerativeModel,
    Tool,
    FunctionDeclaration
)

# 定义函数
get_weather_func = FunctionDeclaration(
    name="get_weather",
    description="获取指定城市的天气",
    parameters={
        "type": "object",
        "properties": {
            "city": {
                "type": "string",
                "description": "城市名称"
            }
        },
        "required": ["city"]
    }
)

# 创建工具
weather_tool = Tool(function_declarations=[get_weather_func])

# 使用
model = GenerativeModel(
    "gemini-1.5-pro",
    tools=[weather_tool]
)

response = model.generate_content("上海今天天气怎么样？")
print(response)
```

---

## 🔢 成本和配额

### 定价

**Gemini 1.5 Pro：**
| 上下文 | 输入 | 输出 |
|--------|------|------|
| ≤ 128K | $1.25/M | $5/M |
| > 128K | $2.50/M | $10/M |

**Gemini 1.5 Flash：**
| 上下文 | 输入 | 输出 |
|--------|------|------|
| ≤ 128K | $0.075/M | $0.30/M |
| > 128K | $0.15/M | $0.60/M |

### 试用积分使用示例

**$300 可以：**
- Gemini Pro: 处理 240M input tokens
- Gemini Flash: 处理 4B input tokens
- 或任意组合

---

## 💡 最佳实践

### ✅ 推荐做法

1. **使用 Flash 优先**
   ```python
   # Flash 便宜 16 倍，大部分场景够用
   model = GenerativeModel("gemini-1.5-flash")
   ```

2. **批量处理**
   ```python
   # 批量处理多个请求
   responses = []
   for prompt in prompts:
       response = model.generate_content(prompt)
       responses.append(response.text)
   ```

3. **成本监控**
   ```python
   # 在 GCP Console 设置预算警报
   # Billing → Budgets & alerts
   ```

4. **错误处理**
   ```python
   from google.api_core import exceptions
   
   try:
       response = model.generate_content(prompt)
   except exceptions.ResourceExhausted:
       print("配额用完")
   except exceptions.InvalidArgument:
       print("参数错误")
   ```

---

## 🔧 常见问题

### 1. 如何认证？

**方法：**
```bash {filename="Bash"}
# 设置环境变量
export GOOGLE_APPLICATION_CREDENTIALS="path/to/service-account-key.json"

# 或在代码中
import os
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "key.json"
```

### 2. 如何选择区域？

**可用区域：**
- `us-central1`（推荐）
- `europe-west1`
- `asia-southeast1`

### 3. 如何监控使用量？

**方法：**
1. GCP Console → Billing
2. 查看 Vertex AI 使用情况
3. 设置预算警报

---

## 📚 相关资源

### 官方文档
- [Vertex AI 完整介绍](/providers/google-vertex-ai)
- [Studio 使用指南](/services/chatbot/vertex-ai-studio)
- [API 官方文档](https://cloud.google.com/vertex-ai/docs)

### SDK 和工具
- [Python SDK](https://cloud.google.com/python/docs/reference/aiplatform/latest)
- [示例代码](https://github.com/GoogleCloudPlatform/vertex-ai-samples)
- [教程](https://cloud.google.com/vertex-ai/docs/tutorials)

---

## 🌟 实战案例

### 案例：长文档分析系统

```python {filename="Python"}
import vertexai
from vertexai.generative_models import GenerativeModel

vertexai.init(project="YOUR_PROJECT_ID", location="us-central1")

class DocumentAnalyzer:
    def __init__(self):
        self.model = GenerativeModel("gemini-1.5-pro")
    
    def analyze(self, document_text):
        """分析长文档"""
        prompt = f"""
        请分析以下文档并提供：
        1. 核心主题
        2. 关键要点（5-10个）
        3. 总结（200字内）
        
        文档内容：
        {document_text}
        """
        
        response = self.model.generate_content(prompt)
        return response.text

# 使用
analyzer = DocumentAnalyzer()
with open("long_doc.txt") as f:
    result = analyzer.analyze(f.read())
    print(result)
```

---

**服务提供者：** [Google Vertex AI](/providers/google-vertex-ai)
