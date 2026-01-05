---
title: "Groq API - 极速免费 AI API 接口服务"
description: "Groq 提供业界最快推理速度 800+ tokens/秒的免费 API！每日 14,400 次免费请求，支持 Llama 3.3、Mixtral、Gemma 2 等模型。OpenAI 兼容接口，极速响应，详细代码示例。"
keywords:
  - Groq API
  - 极速 AI API
  - 免费 Llama API
  - 快速推理 API
  - Mixtral API
  - OpenAI 兼容 API
  - 免费 AI 接口
  - 超快 API 服务
image: /images/logo.svg
weight: 2
comments: true
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [Groq](/providers/groq)  
**服务类型：** API 服务  
**API 端点：** [https://api.groq.com/openai/v1](https://api.groq.com/openai/v1)  
**免费类型：** 永久免费（有使用限制）  
**API 兼容性：** 完全兼容 OpenAI API

---

## 🎯 服务简介

Groq API 提供业界最快的 LLM 推理服务，完全兼容 OpenAI API 格式，让您只需修改 `base_url` 即可将现有代码切换到 Groq。

**核心优势：**
- ⚡ **业界最快** - 800+ tokens/s 推理速度
- 🔄 **OpenAI 兼容** - 无缝迁移现有代码
- 🎁 **超高配额** - 14,400 请求/天
- 💰 **完全免费** - 无隐藏费用
- 🚀 **低延迟** - 毫秒级首 token 响应

---

## 🚀 快速开始

### 前提条件

**必需：**
- ✅ 已创建 API 密钥

详细步骤请参考：[Groq 注册指南](/providers/groq#注册和账号)

### 5 分钟快速示例

**方法 1：使用 Groq SDK（推荐）**

```bash {filename="Bash"}
pip install groq
```

```python {filename="Python"}
from groq import Groq

# 初始化客户端
client = Groq(api_key="YOUR_API_KEY")

# 发送请求
chat_completion = client.chat.completions.create(
    messages=[
        {
            "role": "user",
            "content": "解释一下 Groq 的 LPU 技术",
        }
    ],
    model="llama-3.3-70b-versatile",
)

# 打印响应
print(chat_completion.choices[0].message.content)
```

**方法 2：使用 OpenAI SDK（兼容模式）**

```python {filename="Python"}
from openai import OpenAI

# 只需修改 base_url 和 api_key
client = OpenAI(
    base_url="https://api.groq.com/openai/v1",
    api_key="YOUR_API_KEY"
)

# 其余代码与 OpenAI 完全相同
response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "user", "content": "你好"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 支持的模型

### Llama 系列（推荐）

| 模型 ID | 参数量 | 上下文 | 速度 | 适用场景 |
|---------|-------|--------|------|---------|
| `llama-3.3-70b-versatile` | 70B | 128K | ⚡⚡⚡ | 通用任务，最佳平衡 |
| `llama-3.1-70b-versatile` | 70B | 128K | ⚡⚡⚡ | 复杂任务 |
| `llama-3.1-8b-instant` | 8B | 128K | ⚡⚡⚡⚡ | 快速响应 |

### 其他模型

| 模型 ID | 参数量 | 上下文 | 特点 |
|---------|-------|--------|------|
| `mixtral-8x7b-32768` | 47B | 32K | Mistral 混合专家 |
| `gemma2-9b-it` | 9B | 8K | Google 开源 |
| `deepseek-r1-distill-llama-70b` | 70B | 32K | 推理专家 |

---

## 🔢 配额和限制

### API 配额

| 限制类型 | 免费层级 | 说明 |
|---------|---------|------|
| **每日请求数** | 14,400 requests | 所有模型共享 |
| **每分钟请求数** | 30 requests | 所有模型共享 |
| **每日 Tokens** | 20,000-1,000,000 | 视模型而定 |
| **每分钟 Tokens** | 6,000 tokens | 输入输出总和 |
| **最大上下文** | 128K tokens | Llama 3.x 系列 |
| **最大输出** | 8,192 tokens | 单次请求 |

### ⚠️ 重要限制

1. **配额共享：** 所有模型共享同一账户配额
2. **速率限制：** 超过限制返回 429 错误
3. **每日重置：** UTC 时间凌晨 00:00 重置
4. **并发限制：** 建议不超过 10 个并发请求

---

## 📖 API 使用示例

### 1. 基础对话

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "system", "content": "你是一个有帮助的AI助手"},
        {"role": "user", "content": "什么是机器学习？"}
    ]
)

print(response.choices[0].message.content)
```

### 2. 流式输出

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

stream = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "user", "content": "写一篇关于AI的文章"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

### 3. 多轮对话

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

messages = [
    {"role": "system", "content": "你是一个Python编程助手"}
]

# 第一轮
messages.append({"role": "user", "content": "如何读取文件？"})
response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=messages
)
messages.append({"role": "assistant", "content": response.choices[0].message.content})

# 第二轮（模型会记住上下文）
messages.append({"role": "user", "content": "那写入呢？"})
response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=messages
)
print(response.choices[0].message.content)
```

### 4. 调整生成参数

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "user", "content": "写一首诗"}
    ],
    temperature=0.9,        # 提高创造性
    max_tokens=1024,        # 限制输出长度
    top_p=0.95,            # 核采样
    frequency_penalty=0.5,  # 降低重复
    presence_penalty=0.5    # 增加话题多样性
)

print(response.choices[0].message.content)
```

### 5. 使用 cURL

```bash {filename="Bash"}
curl "https://api.groq.com/openai/v1/chat/completions" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "llama-3.3-70b-versatile",
    "messages": [
      {
        "role": "user",
        "content": "你好，介绍一下 Groq"
      }
    ]
  }'
```

### 6. Node.js 示例

```bash {filename="Bash"}
npm install groq-sdk
```

```javascript {filename="JavaScript"}
const Groq = require("groq-sdk");

const groq = new Groq({
  apiKey: "YOUR_API_KEY"
});

async function main() {
  const chatCompletion = await groq.chat.completions.create({
    messages: [
      { role: "user", content: "介绍一下 Groq 的 LPU 技术" }
    ],
    model: "llama-3.3-70b-versatile",
  });

  console.log(chatCompletion.choices[0].message.content);
}

main();
```

---

## 💡 最佳实践

### ✅ 推荐做法

1. **选择合适的模型**
   ```python
   # 快速任务
   model = "llama-3.1-8b-instant"
   
   # 平衡性能
   model = "llama-3.3-70b-versatile"
   
   # 数学/代码推理
   model = "deepseek-r1-distill-llama-70b"
   ```

2. **实现错误处理和重试**
   ```python
   import time
   from groq import Groq, RateLimitError
   
   client = Groq(api_key="YOUR_API_KEY")
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="llama-3.3-70b-versatile",
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

3. **监控配额使用**
   ```python
   import logging
   
   logging.basicConfig(level=logging.INFO)
   logger = logging.getLogger(__name__)
   
   def track_usage(response):
       usage = response.usage
       logger.info(f"Tokens使用: "
                   f"输入={usage.prompt_tokens}, "
                   f"输出={usage.completion_tokens}, "
                   f"总计={usage.total_tokens}")
       return response
   ```

4. **使用流式输出优化体验**
   ```python
   def stream_chat(prompt):
       stream = client.chat.completions.create(
           model="llama-3.3-70b-versatile",
           messages=[{"role": "user", "content": prompt}],
           stream=True
       )
       
       full_response = ""
       for chunk in stream:
           if chunk.choices[0].delta.content:
               content = chunk.choices[0].delta.content
               print(content, end="", flush=True)
               full_response += content
       
       return full_response
   ```

5. **安全管理 API 密钥**
   ```python
   import os
   from dotenv import load_dotenv
   
   # 使用环境变量
   load_dotenv()
   api_key = os.getenv('GROQ_API_KEY')
   
   client = Groq(api_key=api_key)
   ```

---

## 🔧 常见问题

### 1. 429 错误：Rate Limit Exceeded

**原因：** 超过速率限制

**解决：**
```python {filename="Python"}
import time
from groq import RateLimitError

try:
    response = client.chat.completions.create(...)
except RateLimitError as e:
    print(f"速率限制: {e}")
    print("等待后重试...")
    time.sleep(60)  # 等待1分钟
    response = client.chat.completions.create(...)
```

### 2. 401 错误：Invalid API Key

**原因：** API 密钥无效或过期

**解决：**
1. 检查 API 密钥是否正确
2. 在 Console 重新生成密钥
3. 确保密钥没有多余的空格

### 3. 网络超时

**解决：**
```python {filename="Python"}
from groq import Groq

client = Groq(
    api_key="YOUR_API_KEY",
    timeout=60.0  # 设置60秒超时
)
```

### 4. 如何查看剩余配额？

**方法：**
1. 登录 https://console.groq.com
2. 访问 "Usage" 页面
3. 查看当前配额使用情况

---

## 📊 性能优化

### 1. 批量处理

```python {filename="Python"}
import asyncio
from groq import AsyncGroq

async def batch_process(questions):
    client = AsyncGroq(api_key="YOUR_API_KEY")
    
    tasks = []
    for q in questions:
        task = client.chat.completions.create(
            model="llama-3.1-8b-instant",
            messages=[{"role": "user", "content": q}]
        )
        tasks.append(task)
    
    return await asyncio.gather(*tasks)

# 使用
questions = ["问题1", "问题2", "问题3"]
responses = asyncio.run(batch_process(questions))
```

### 2. 缓存结果

```python {filename="Python"}
from functools import lru_cache
import hashlib
import json

def get_cache_key(messages):
    return hashlib.md5(
        json.dumps(messages, sort_keys=True).encode()
    ).hexdigest()

cache = {}

def cached_completion(messages):
    key = get_cache_key(messages)
    
    if key in cache:
        print("使用缓存结果")
        return cache[key]
    
    response = client.chat.completions.create(
        model="llama-3.3-70b-versatile",
        messages=messages
    )
    
    cache[key] = response
    return response
```

### 3. 选择合适的模型

```python {filename="Python"}
def select_model(task_complexity):
    if task_complexity == "simple":
        return "llama-3.1-8b-instant"  # 最快
    elif task_complexity == "medium":
        return "llama-3.3-70b-versatile"  # 平衡
    elif task_complexity == "complex":
        return "deepseek-r1-distill-llama-70b"  # 推理
```

---

## 📚 相关资源

### 官方文档
- [Groq 完整介绍](/providers/groq)
- [Playground 使用指南](/services/chatbot/groq)
- [API 官方文档](https://console.groq.com/docs)

### SDK 和工具
- [Python SDK](https://github.com/groq/groq-python)
- [Node.js SDK](https://github.com/groq/groq-typescript)
- [API 参考](https://console.groq.com/docs/api-reference)

### 示例代码
- [示例库](https://github.com/groq/groq-api-cookbook)
- [社区示例](https://discord.gg/groq)

---

## 🌟 实战案例

### 案例 1：实时聊天机器人

```python {filename="Python"}
import streamlit as st
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

st.title("Groq 超快聊天机器人")

if "messages" not in st.session_state:
    st.session_state.messages = []

# 显示历史消息
for message in st.session_state.messages:
    with st.chat_message(message["role"]):
        st.write(message["content"])

# 用户输入
if prompt := st.chat_input("输入您的问题..."):
    # 添加用户消息
    st.session_state.messages.append({"role": "user", "content": prompt})
    with st.chat_message("user"):
        st.write(prompt)
    
    # 生成回复
    with st.chat_message("assistant"):
        stream = client.chat.completions.create(
            model="llama-3.3-70b-versatile",
            messages=st.session_state.messages,
            stream=True
        )
        
        response = st.write_stream(
            (chunk.choices[0].delta.content for chunk in stream 
             if chunk.choices[0].delta.content)
        )
    
    # 添加助手消息
    st.session_state.messages.append({"role": "assistant", "content": response})
```

### 案例 2：代码助手

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

def code_assistant(language, task):
    response = client.chat.completions.create(
        model="llama-3.3-70b-versatile",
        messages=[
            {
                "role": "system",
                "content": f"你是一个专业的{language}编程助手。"
                           f"提供清晰的代码示例和解释。"
            },
            {
                "role": "user",
                "content": task
            }
        ],
        temperature=0.2  # 降低温度以获得更确定的代码
    )
    
    return response.choices[0].message.content

# 使用
result = code_assistant("Python", "实现一个二分查找算法")
print(result)
```

---

**服务提供者：** [Groq](/providers/groq)
