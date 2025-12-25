---
title: Google AI Studio - API
weight: 1
comments: true
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [Google AI Studio](/providers/google-ai-studio)  
**服务类型：** API 服务  
**API 端点：** [https://generativelanguage.googleapis.com](https://generativelanguage.googleapis.com)  
**免费类型：** 永久免费（有使用限制）

---

## 🎯 服务简介

Google AI Studio 的 API 服务提供了强大的 Gemini 模型访问能力，完全兼容 OpenAI API 格式，让开发者可以轻松集成到自己的应用中。

**核心优势：**
- 🎁 **超高免费配额** - 15M tokens/天（Flash 系列）
- ⚡ **极快响应速度** - Flash 系列优化
- 🔄 **OpenAI 兼容** - 无缝迁移现有代码
- 🎨 **多模态 API** - 支持文本、图像、音频、视频
- 📱 **超长上下文** - 最高 2M tokens
- 🔍 **联网搜索** - Google Search Grounding

---

## 🚀 快速开始

### 前提条件

**必需：**
- ✅ 已创建 API 密钥

详细步骤请参考：[Google AI Studio 注册指南](/providers/google-ai-studio#注册和账号)

### 获取 API 密钥

1. 访问：https://aistudio.google.com
2. 左侧菜单点击 "Get API key"
3. 选择或创建 Google Cloud 项目
4. 点击 "Create API key"
5. **立即复制并保存密钥**

### 5 分钟快速示例

**Python 示例：**

```python {filename="Python"}
import google.generativeai as genai

# 配置 API 密钥
genai.configure(api_key="YOUR_API_KEY")

# 创建模型实例
model = genai.GenerativeModel('gemini-2.5-flash')

# 发送请求
response = model.generate_content("你好，介绍一下你自己")
print(response.text)
```

**cURL 示例：**

```bash {filename="Bash"}
curl https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=YOUR_API_KEY \
  -H 'Content-Type: application/json' \
  -d '{
    "contents": [{
      "parts":[{"text": "你好，介绍一下你自己"}]
    }]
  }'
```

---

## 🤖 支持的模型

### Gemini Flash 系列（推荐）

| 模型名称 | 模型 ID | 特点 | 适用场景 |
|---------|---------|------|---------|
| **Gemini 3 Flash** | `gemini-3-flash` | 最快速度 | 高频调用、实时响应 |
| **Gemini 2.5 Flash** | `gemini-2.5-flash` | 新一代快速模型 | 日常任务、平衡性能 |
| **Gemini 2.5 Flash-Lite** | `gemini-2.5-flash-lite` | 轻量超快 | 简单任务、极速响应 |

### Gemini Pro 系列

| 模型名称 | 模型 ID | 特点 | 适用场景 |
|---------|---------|------|---------|
| **Gemini Pro** | `gemini-pro` | 更强理解 | 复杂任务、深度推理 |

### Gemma 开源系列

| 模型名称 | 模型 ID | 特点 | 适用场景 |
|---------|---------|------|---------|
| **Gemma 3 27B** | `gemma-3-27b-instruct` | 大参数量 | 复杂任务 |
| **Gemma 3 12B** | `gemma-3-12b-instruct` | 中等参数 | 平衡性能 |
| **Gemma 3 4B** | `gemma-3-4b-instruct` | 小型快速 | 轻量任务 |

---

## 🔢 配额和限制

### API 配额限制

| 模型名称 | 每日请求数 | 每分钟请求数 | 每分钟 Tokens |
|---------|-----------|-------------|--------------|
| Gemini 3 Flash | 20 requests/day | 5 requests/min | 250,000 tokens/min |
| Gemini 2.5 Flash | 20 requests/day | 5 requests/min | 250,000 tokens/min |
| Gemini 2.5 Flash-Lite | 20 requests/day | 10 requests/min | 250,000 tokens/min |
| Gemma 3 27B | 14,400 requests/day | 30 requests/min | 15,000 tokens/min |
| Gemma 3 12B | 14,400 requests/day | 30 requests/min | 15,000 tokens/min |
| Gemma 3 4B | 14,400 requests/day | 30 requests/min | 15,000 tokens/min |

### 每日总配额

| 模型系列 | 每日 Tokens 配额 |
|---------|----------------|
| Gemini Flash 系列 | 15M tokens |
| Gemini Pro 系列 | 3M tokens |
| Gemma 系列 | 4M tokens |

### 上下文长度

| 模型 | 输入上下文 | 输出长度 |
|------|-----------|---------|
| Gemini 系列 | 最高 2M tokens | 8,192 tokens |
| Gemma 系列 | 8K-128K tokens | 8,192 tokens |

### ⚠️ 重要限制

1. **总请求限制：** 所有 Gemini 模型共享每日 1500 次请求的总配额
2. **跨模型速率限制：** 60 requests/min（跨所有模型）
3. **配额共享：** 所有 API 密钥共享同一个 GCP 项目的配额

---

## 📖 API 使用示例

### 1. 基础文本生成

**Python SDK：**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# 简单对话
response = model.generate_content("解释一下什么是机器学习")
print(response.text)

# 带参数的请求
response = model.generate_content(
    "写一首关于秋天的诗",
    generation_config={
        "temperature": 0.9,
        "top_p": 0.95,
        "max_output_tokens": 1024,
    }
)
print(response.text)
```

**REST API：**

```bash {filename="Bash"}
curl https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=YOUR_API_KEY \
  -H 'Content-Type: application/json' \
  -d '{
    "contents": [{
      "parts":[{"text": "解释一下什么是机器学习"}]
    }],
    "generationConfig": {
      "temperature": 0.7,
      "maxOutputTokens": 1024
    }
  }'
```

### 2. 多轮对话

**Python SDK：**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# 创建对话会话
chat = model.start_chat(history=[])

# 第一轮对话
response = chat.send_message("你好，我想学习 Python")
print(response.text)

# 第二轮对话（模型会记住上下文）
response = chat.send_message("应该从哪里开始？")
print(response.text)

# 查看对话历史
print(chat.history)
```

### 3. 图像理解

**Python SDK：**

```python {filename="Python"}
import google.generativeai as genai
from PIL import Image

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# 加载图片
image = Image.open('example.jpg')

# 发送图片和问题
response = model.generate_content([
    "这张图片里有什么？请详细描述。",
    image
])
print(response.text)
```

**从 URL 加载图片：**

```python {filename="Python"}
import google.generativeai as genai
from PIL import Image
import requests
from io import BytesIO

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# 从 URL 加载图片
response = requests.get('https://example.com/image.jpg')
image = Image.open(BytesIO(response.content))

# 分析图片
response = model.generate_content(["分析这张图片", image])
print(response.text)
```

### 4. 流式输出

**Python SDK：**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# 流式输出
response = model.generate_content(
    "写一篇关于人工智能的文章",
    stream=True
)

for chunk in response:
    print(chunk.text, end='')
```

### 5. 函数调用（Function Calling）

**Python SDK：**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

# 定义函数
def get_weather(city: str):
    """获取指定城市的天气"""
    # 这里应该调用真实的天气 API
    return f"{city}的天气：晴天，25°C"

# 定义函数描述
tools = [{
    "function_declarations": [{
        "name": "get_weather",
        "description": "获取指定城市的天气信息",
        "parameters": {
            "type": "object",
            "properties": {
                "city": {
                    "type": "string",
                    "description": "城市名称"
                }
            },
            "required": ["city"]
        }
    }]
}]

model = genai.GenerativeModel(
    'gemini-2.5-flash',
    tools=tools
)

# 发送请求
chat = model.start_chat()
response = chat.send_message("上海今天天气怎么样？")

# 检查是否需要调用函数
if response.candidates[0].content.parts[0].function_call:
    function_call = response.candidates[0].content.parts[0].function_call
    
    # 调用函数
    if function_call.name == "get_weather":
        result = get_weather(function_call.args["city"])
        
        # 将结果返回给模型
        response = chat.send_message({
            "function_response": {
                "name": "get_weather",
                "response": {"result": result}
            }
        })
        print(response.text)
```

### 6. Google Search Grounding

**Python SDK：**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

# 启用 Google Search Grounding
model = genai.GenerativeModel('gemini-2.5-flash')

response = model.generate_content(
    "最新的 AI 技术发展趋势是什么？",
    tools=[{"google_search_retrieval": {}}]
)

print(response.text)

# 查看引用来源
for candidate in response.candidates:
    if hasattr(candidate, 'grounding_metadata'):
        print("\n引用来源：")
        for attribution in candidate.grounding_metadata.grounding_attributions:
            print(f"- {attribution.source_id.grounding_passage.url}")
```

---

## 🛠️ SDK 和客户端库

### 官方 SDK

**Python：**
```bash {filename="Bash"}
pip install google-generativeai
```

**Node.js：**
```bash {filename="Bash"}
npm install @google/generative-ai
```

**Go：**
```bash {filename="Bash"}
go get github.com/google/generative-ai-go
```

### OpenAI 兼容

Google AI Studio API 兼容 OpenAI 格式，可以直接使用 OpenAI SDK：

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_GOOGLE_API_KEY",
    base_url="https://generativelanguage.googleapis.com/v1beta/openai/"
)

response = client.chat.completions.create(
    model="gemini-2.5-flash",
    messages=[
        {"role": "user", "content": "你好"}
    ]
)

print(response.choices[0].message.content)
```

---

## 💡 最佳实践

### ✅ 推荐做法

1. **选择合适的模型**
   - 高频调用：Gemini 3 Flash（最快）
   - 日常任务：Gemini 2.5 Flash（平衡）
   - 复杂任务：Gemini Pro（更强）
   - 开源需求：Gemma 系列

2. **优化配额使用**
   ```python
   # 使用流式输出减少等待时间
   response = model.generate_content(prompt, stream=True)
   
   # 设置合理的 max_output_tokens
   generation_config = {"max_output_tokens": 512}
   
   # 批量处理请求
   prompts = ["问题1", "问题2", "问题3"]
   responses = [model.generate_content(p) for p in prompts]
   ```

3. **错误处理和重试**
   ```python
   import time
   from google.api_core import retry
   
   @retry.Retry(predicate=retry.if_exception_type(Exception))
   def call_api_with_retry(prompt):
       return model.generate_content(prompt)
   
   try:
       response = call_api_with_retry("你好")
   except Exception as e:
       print(f"API 调用失败: {e}")
   ```

4. **监控配额使用**
   ```python
   # 记录 API 调用
   import logging
   
   logging.basicConfig(level=logging.INFO)
   logger = logging.getLogger(__name__)
   
   def track_api_call(model, prompt):
       logger.info(f"调用模型: {model}")
       response = model.generate_content(prompt)
       logger.info(f"使用 tokens: {response.usage_metadata.total_token_count}")
       return response
   ```

5. **安全管理 API 密钥**
   ```python
   # 使用环境变量
   import os
   api_key = os.getenv('GOOGLE_AI_API_KEY')
   
   # 或使用配置文件
   import json
   with open('config.json') as f:
       config = json.load(f)
       api_key = config['api_key']
   ```

### ⚠️ 避免的做法

1. ❌ 在代码中硬编码 API 密钥
2. ❌ 频繁发送相同的请求（使用缓存）
3. ❌ 忽略速率限制（实现退避重试）
4. ❌ 不处理错误和异常
5. ❌ 使用过大的 max_output_tokens

---

## 🔧 常见问题

### 1. 403 错误：API key not valid

**原因：**
- API 密钥错误或过期
- API 未启用

**解决：**
```python {filename="Python"}
# 检查 API 密钥
import google.generativeai as genai
genai.configure(api_key="YOUR_API_KEY")

# 列出可用模型以验证
for model in genai.list_models():
    print(model.name)
```

### 2. 429 错误：Resource exhausted

**原因：**
- 超过速率限制
- 超过每日配额

**解决：**
```python {filename="Python"}
import time
from google.api_core.exceptions import ResourceExhausted

def call_with_backoff(prompt, max_retries=3):
    for i in range(max_retries):
        try:
            return model.generate_content(prompt)
        except ResourceExhausted:
            if i < max_retries - 1:
                wait_time = 2 ** i  # 指数退避
                print(f"速率限制，等待 {wait_time} 秒...")
                time.sleep(wait_time)
            else:
                raise
```

### 3. 网络超时

**原因：**
- 网络不稳定
- 请求内容过大

**解决：**
```python {filename="Python"}
from google.api_core import timeout

# 设置超时
timeout_config = timeout.ExponentialTimeout(initial=30, maximum=120)
response = model.generate_content(prompt, timeout=timeout_config)
```

### 4. 中国大陆访问问题

**解决方法：**
- 使用代理或 VPN
- 配置代理：
  ```python
  import os
  os.environ['HTTP_PROXY'] = 'http://your-proxy:port'
  os.environ['HTTPS_PROXY'] = 'https://your-proxy:port'
  ```

---

## 📊 性能优化

### 1. 使用缓存

```python {filename="Python"}
from functools import lru_cache

@lru_cache(maxsize=100)
def cached_api_call(prompt):
    return model.generate_content(prompt).text
```

### 2. 批量处理

```python {filename="Python"}
import asyncio
from google.generativeai import GenerativeModel

async def batch_generate(prompts):
    model = GenerativeModel('gemini-2.5-flash')
    tasks = [model.generate_content_async(p) for p in prompts]
    return await asyncio.gather(*tasks)

# 使用
prompts = ["问题1", "问题2", "问题3"]
responses = asyncio.run(batch_generate(prompts))
```

### 3. 流式处理大文本

```python {filename="Python"}
def process_large_text(text, chunk_size=10000):
    chunks = [text[i:i+chunk_size] for i in range(0, len(text), chunk_size)]
    results = []
    
    for chunk in chunks:
        response = model.generate_content(f"总结：{chunk}")
        results.append(response.text)
    
    return " ".join(results)
```

---

## 📚 相关资源

### 官方文档
- [Google AI Studio 完整介绍](/providers/google-ai-studio)
- [Chatbot 服务使用指南](/services/chatbot/google-ai-studio)
- [API 官方文档](https://ai.google.dev/docs)
- [API 参考手册](https://ai.google.dev/api)

### 代码示例
- [GitHub 示例库](https://github.com/google/generative-ai-docs)
- [Cookbook](https://github.com/google-gemini/cookbook)

### 学习资源
- [快速入门教程](https://ai.google.dev/tutorials/python_quickstart)
- [Prompt 工程](https://ai.google.dev/docs/prompt_best_practices)
- [函数调用指南](https://ai.google.dev/docs/function_calling)

---

**服务提供者：** [Google AI Studio](/providers/google-ai-studio)
