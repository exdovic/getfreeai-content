---
title: OpenRouter - API
weight: 3
comments: true
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [OpenRouter](/providers/openrouter)  
**服务类型：** API 服务  
**API 端点：** [https://openrouter.ai/api/v1](https://openrouter.ai/api/v1)  
**免费类型：** 永久免费（有使用限制）  
**API 兼容性：** 完全兼容 OpenAI API

---

## 🎯 服务简介

OpenRouter API 通过统一的接口提供 47+ 个免费 AI 模型，完全兼容 OpenAI API 格式，让您可以轻松切换和测试不同的模型。

**核心优势：**
- 🎯 **一站式访问** - 一个 API 密钥访问 47+ 模型
- 🔄 **OpenAI 兼容** - 无缝迁移现有代码
- 🎁 **大量免费模型** - 包括 Llama 3.1 405B 等顶级模型
- 🚀 **智能路由** - 自动选择最优提供者
- 💰 **灵活定价** - 免费模型永不扣费

---

## 🚀 快速开始

### 前提条件

**必需：**
- ✅ 已创建 API 密钥

详细步骤请参考：[OpenRouter 注册指南](/providers/openrouter#注册和账号)

### 5 分钟快速示例

**使用 OpenAI SDK（推荐）**

```python {filename="Python"}
from openai import OpenAI

# 配置 OpenRouter
client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY",
)

# 调用免费模型
response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=[
        {"role": "user", "content": "介绍一下 OpenRouter"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 免费模型列表

### 如何识别免费模型

免费模型的 model ID 以 `:free` 结尾：
- ✅ `meta-llama/llama-3.3-70b-instruct:free`
- ❌ `meta-llama/llama-3.3-70b-instruct`（付费）

### 顶级免费模型

| Model ID | 参数量 | 上下文 | 特点 |
|----------|-------|--------|------|
| `meta-llama/llama-3.3-70b-instruct:free` | 70B | 128K | Meta 最新 |
| `meta-llama/llama-3.1-405b-instruct:free` | 405B | 128K | 超大参数 |
| `deepseek/deepseek-r1-0528:free` | - | 64K | 推理专家 |
| `qwen/qwen-3-235b-a22b:free` | 235B | 128K | 阿里旗舰 |
| `mistralai/mistral-small-3.1-24b:free` | 24B | 32K | Mistral 高效 |

### 轻量快速模型

| Model ID | 参数量 | 上下文 | 特点 |
|----------|-------|--------|------|
| `meta-llama/llama-3.2-3b-instruct:free` | 3B | 128K | 轻量快速 |
| `google/gemma-3-4b-instruct:free` | 4B | 8K | 小而强大 |
| `mistralai/mistral-7b-instruct:free` | 7B | 32K | 经典高效 |

### 代码专用模型

| Model ID | 特点 |
|----------|------|
| `mistralai/devstral-2512:free` | Mistral 代码专家 |
| `qwen/qwen-3-coder:free` | 通义千问代码版 |

---

## 🔢 配额和限制

### API 配额

| 限制类型 | 基础层 | 升级层（$10） |
|---------|--------|-------------|
| **每日请求数** | 50 requests | 1,000 requests |
| **每分钟请求数** | 20 requests | 20 requests |
| **免费模型** | 47+ | 47+ |
| **费用** | $0 | $10 一次性 |

### ⚠️ 重要限制

1. **模型标识：** 必须使用 `:free` 后缀的模型 ID
2. **配额共享：** 所有免费模型共享配额
3. **速率限制：** 超过限制返回 429 错误
4. **余额保护：** 可设置信用限额为 $0 避免误用付费模型

---

## 📖 API 使用示例

### 1. 基础对话

**Python（OpenAI SDK）：**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=[
        {"role": "system", "content": "你是一个有帮助的AI助手"},
        {"role": "user", "content": "什么是机器学习？"}
    ]
)

print(response.choices[0].message.content)
```

### 2. 流式输出

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

stream = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=[
        {"role": "user", "content": "写一篇关于AI的文章"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

### 3. 使用 requests 库

```python {filename="Python"}
import requests

url = "https://openrouter.ai/api/v1/chat/completions"
headers = {
    "Authorization": "Bearer YOUR_OPENROUTER_API_KEY",
    "Content-Type": "application/json"
}
data = {
    "model": "meta-llama/llama-3.3-70b-instruct:free",
    "messages": [
        {"role": "user", "content": "你好"}
    ]
}

response = requests.post(url, headers=headers, json=data)
print(response.json()["choices"][0]["message"]["content"])
```

### 4. cURL 示例

```bash {filename="Bash"}
curl https://openrouter.ai/api/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_OPENROUTER_API_KEY" \
  -d '{
    "model": "meta-llama/llama-3.3-70b-instruct:free",
    "messages": [
      {
        "role": "user",
        "content": "介绍一下 OpenRouter"
      }
    ]
  }'
```

### 5. Node.js 示例

```javascript {filename="JavaScript"}
const fetch = require('node-fetch');

async function chat() {
    const response = await fetch('https://openrouter.ai/api/v1/chat/completions', {
        method: 'POST',
        headers: {
            'Authorization': 'Bearer YOUR_OPENROUTER_API_KEY',
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({
            model: 'meta-llama/llama-3.3-70b-instruct:free',
            messages: [
                { role: 'user', content: '你好' }
            ]
        })
    });
    
    const data = await response.json();
    console.log(data.choices[0].message.content);
}

chat();
```

### 6. 多轮对话

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

messages = [
    {"role": "system", "content": "你是一个Python编程助手"}
]

# 第一轮
messages.append({"role": "user", "content": "如何读取文件？"})
response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=messages
)
messages.append({"role": "assistant", "content": response.choices[0].message.content})

# 第二轮
messages.append({"role": "user", "content": "那写入呢？"})
response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=messages
)
print(response.choices[0].message.content)
```

---

## 💡 最佳实践

### ✅ 推荐做法

1. **选择合适的模型**
   ```python
   # 快速任务
   model = "meta-llama/llama-3.2-3b-instruct:free"
   
   # 通用任务
   model = "meta-llama/llama-3.3-70b-instruct:free"
   
   # 复杂任务
   model = "meta-llama/llama-3.1-405b-instruct:free"
   
   # 中文任务
   model = "qwen/qwen-3-235b-a22b:free"
   
   # 代码任务
   model = "mistralai/devstral-2512:free"
   ```

2. **设置余额限制**
   ```python
   # 在 OpenRouter 控制台设置
   # Settings → Credits → Monthly Limit → $0
   # 这样可以防止误用付费模型
   ```

3. **实现错误处理和重试**
   ```python
   import time
   from openai import OpenAI, RateLimitError
   
   client = OpenAI(
       base_url="https://openrouter.ai/api/v1",
       api_key="YOUR_OPENROUTER_API_KEY"
   )
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="meta-llama/llama-3.3-70b-instruct:free",
                   messages=messages
               )
           except RateLimitError:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"速率限制，等待 {wait_time} 秒...")
                   time.sleep(wait_time)
               else:
                   raise
   ```

4. **监控使用情况**
   ```python
   # 访问 https://openrouter.ai/activity
   # 查看详细的使用统计和成本
   ```

5. **安全管理 API 密钥**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('OPENROUTER_API_KEY')
   
   client = OpenAI(
       base_url="https://openrouter.ai/api/v1",
       api_key=api_key
   )
   ```

---

## 🔧 常见问题

### 1. 如何查看所有免费模型？

**方法：**
- 访问：https://openrouter.ai/models?free=true
- 或使用 API：
  ```python
  response = requests.get(
      "https://openrouter.ai/api/v1/models",
      headers={"Authorization": f"Bearer {api_key}"}
  )
  free_models = [m for m in response.json()["data"] if ":free" in m["id"]]
  ```

### 2. 429 错误：Rate Limit Exceeded

**原因：** 超过每日或每分钟限制

**解决：**
- 等待配额重置（每日UTC 00:00）
- 升级到 1000 requests/day（充值 $10）
- 实现请求缓存和重试逻辑

### 3. 为什么会扣费？

**原因：** 使用了没有 `:free` 后缀的模型

**预防：**
```python {filename="Python"}
def ensure_free_model(model_id):
    if not model_id.endswith(":free"):
        raise ValueError(f"模型 {model_id} 不是免费模型！")
    return model_id

# 使用
model = ensure_free_model("meta-llama/llama-3.3-70b-instruct:free")
```

### 4. 如何切换不同模型？

**方法：**
```python {filename="Python"}
# 只需修改 model 参数
models_to_try = [
    "meta-llama/llama-3.3-70b-instruct:free",
    "meta-llama/llama-3.1-405b-instruct:free",
    "qwen/qwen-3-235b-a22b:free"
]

for model in models_to_try:
    response = client.chat.completions.create(
        model=model,
        messages=[{"role": "user", "content": "测试"}]
    )
    print(f"{model}: {response.choices[0].message.content[:50]}")
```

---

## 📊 性能优化

### 1. 模型选择策略

```python {filename="Python"}
def select_model(task_type, complexity):
    if task_type == "code":
        return "mistralai/devstral-2512:free"
    elif task_type == "chinese":
        return "qwen/qwen-3-235b-a22b:free"
    elif complexity == "high":
        return "meta-llama/llama-3.1-405b-instruct:free"
    else:
        return "meta-llama/llama-3.3-70b-instruct:free"
```

### 2. 结果缓存

```python {filename="Python"}
from functools import lru_cache
import hashlib
import json

cache = {}

def get_cache_key(model, messages):
    content = json.dumps({"model": model, "messages": messages}, sort_keys=True)
    return hashlib.md5(content.encode()).hexdigest()

def cached_completion(model, messages):
    key = get_cache_key(model, messages)
    
    if key in cache:
        print("使用缓存结果")
        return cache[key]
    
    response = client.chat.completions.create(
        model=model,
        messages=messages
    )
    
    cache[key] = response
    return response
```

### 3. 批量处理

```python {filename="Python"}
import asyncio
from openai import AsyncOpenAI

async def batch_process(questions):
    client = AsyncOpenAI(
        base_url="https://openrouter.ai/api/v1",
        api_key="YOUR_OPENROUTER_API_KEY"
    )
    
    tasks = []
    for q in questions:
        task = client.chat.completions.create(
            model="meta-llama/llama-3.3-70b-instruct:free",
            messages=[{"role": "user", "content": q}]
        )
        tasks.append(task)
    
    return await asyncio.gather(*tasks)

# 使用
questions = ["问题1", "问题2", "问题3"]
responses = asyncio.run(batch_process(questions))
```

---

## 📚 相关资源

### 官方文档
- [OpenRouter 完整介绍](/providers/openrouter)
- [Playground 使用指南](/services/chatbot/openrouter)
- [API 官方文档](https://openrouter.ai/docs)

### 工具和资源
- [免费模型列表](https://openrouter.ai/models?free=true)
- [API 参考](https://openrouter.ai/docs/api-reference)
- [使用统计](https://openrouter.ai/activity)
- [定价说明](https://openrouter.ai/docs/limits)

---

## 🌟 实战案例

### 案例 1：多模型对比工具

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

def compare_models(prompt, models):
    results = {}
    for model in models:
        response = client.chat.completions.create(
            model=model,
            messages=[{"role": "user", "content": prompt}]
        )
        results[model] = response.choices[0].message.content
    return results

# 使用
models = [
    "meta-llama/llama-3.3-70b-instruct:free",
    "qwen/qwen-3-235b-a22b:free",
    "mistralai/mistral-small-3.1-24b:free"
]

results = compare_models("解释量子计算", models)
for model, answer in results.items():
    print(f"\n{model}:\n{answer[:200]}...")
```

### 案例 2：智能模型路由

```python {filename="Python"}
def smart_router(task, content):
    if "代码" in task or "编程" in task:
        model = "mistralai/devstral-2512:free"
    elif "中文" in task or len(content) > len(content.encode('utf-8')) * 0.7:
        model = "qwen/qwen-3-235b-a22b:free"
    elif len(content) > 5000:
        model = "meta-llama/llama-3.1-405b-instruct:free"
    else:
        model = "meta-llama/llama-3.3-70b-instruct:free"
    
    return model

# 使用
task = "写一个Python函数"
model = smart_router(task, task)
print(f"选择模型: {model}")
```

---

**服务提供者：** [OpenRouter](/providers/openrouter)
