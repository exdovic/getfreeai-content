---
title: "Cerebras Inference API - 极速 AI 推理 API 服务"
linkTitle: "API - Cerebras"
description: "Cerebras Inference API 提供全球最快的 AI 推理服务，每日 100 万 Token 免费额度，推理速度比 GPU 快 20 倍，支持 Llama 4、Qwen 3 等主流模型。基于晶圆级引擎 WSE 技术，OpenAI 兼容接口。"
keywords:
  - Cerebras API
  - Cerebras Inference
  - 极速推理 API
  - 晶圆级引擎 API
  - 免费 AI API
  - Llama API
  - 超快推理
  - OpenAI 兼容
image: /images/logo.svg
type: docs
weight: 13
comments: true
sidebar:
  open: true
---

## 📋 服务概览

**服务名称：** Cerebras Inference API  
**所属提供者：** [Cerebras Systems](/providers/cerebras)  
**API 端点：** `https://api.cerebras.ai/v1`  
**服务类型：** 免费额度（每日 100 万 Token）  
**注册要求：** 仅需邮箱注册，无需信用卡

---

## ✅ 服务说明

Cerebras Inference API 是 Cerebras Systems 提供的超高性能 AI 推理服务，基于革命性的晶圆级引擎 (WSE) 技术，提供比传统 GPU 快 20 倍的推理速度。

### 主要特点

- **🚀 极速推理：** Llama 4 Scout 可达 2,600+ tokens/s，比 GPU 快 20 倍
- **🎁 免费额度：** 每日 100 万 Token 免费使用
- **🔌 OpenAI 兼容：** 完全兼容 OpenAI API 格式，无缝迁移现有代码
- **🤖 主流模型：** 支持 Llama 3.1/4、Qwen 3 等开源大模型

---

## 🎁 可用模型

### 免费/试用模型列表

| 模型名称 | 上下文长度 | 输出长度 | 特点 | 适用场景 |
|---------|-----------|---------|------|---------|
| **llama-4-scout** | 8K | 2K | 🏆 极速 (2,600+ tokens/s) | 实时应用、聊天机器人 |
| **llama-3.1-70b** | 128K | 4K | 高性能、大上下文 | 长文档处理、复杂任务 |
| **llama-3.1-8b** | 128K | 4K | 快速、轻量 | 快速响应、边缘部署 |
| **qwen-3-32b** | 128K | 4K | 中文优化 | 中文应用 |

### 模型详细说明

#### Llama 4 Scout
- **上下文窗口：** 8K tokens
- **主要用途：** 实时对话、快速问答
- **优势：** 业界最快推理速度，达到 2,600+ tokens/s

#### Llama 3.1 70B
- **上下文窗口：** 128K tokens
- **主要用途：** 复杂任务、长文档处理
- **优势：** 高性能与超长上下文兼顾

#### Llama 3.1 8B
- **上下文窗口：** 128K tokens
- **主要用途：** 快速响应场景
- **优势：** 轻量快速，成本更低

#### Qwen 3-32B
- **上下文窗口：** 128K tokens
- **主要用途：** 中文对话和任务
- **优势：** 中文性能优秀

---

## 🔢 配额和限制

### 免费层级限制

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每日 Token 数** | 100 万 tokens/day | 多数主流模型，每日重置 |
| **速率限制** | 视模型而定 | 建议实现重试机制 |
| **最大上下文长度** | 最高 128K tokens | 取决于具体模型 |
| **最大输出长度** | 最高 4K tokens | 取决于具体模型 |
| **并发请求** | 合理范围内 | 具体限制请参考官方文档 |
| **需要信用卡** | ❌ | 完全免费，无需绑卡 |

**注意：** 不同模型的具体限制可能有所不同，建议查看 [官方 Rate Limits 文档](https://inference-docs.cerebras.ai/support/rate-limits) 获取最新信息。

### ⚠️ 重要限制

1. **每日配额：** 100 万 Token/天，UTC 时区 00:00 重置
2. **模型可用性：** 模型列表可能随时更新，以官方文档为准
3. **商业使用：** 免费层级仅供开发测试，生产环境建议联系商务

### 配额重置时间

- **每日配额：** UTC 00:00（北京时间 08:00）
- **监控使用：** 可通过 API 响应头或控制台查看剩余配额

---

## 💰 价格说明

### 免费/试用

- **免费配额：** 每日 100 万 Token
- **获取方式：** 注册账户即可获得
- **使用期限：** 持续免费（政策可能调整）

### 付费定价

付费价格请联系 Cerebras 商务团队获取报价：sales@cerebras.ai

---

## 🚀 如何使用

### 前提条件

**1. 注册账户**

请先按照 [Cerebras 注册指南](/providers/cerebras#注册账户) 完成账户注册。

**2. 获取 API 密钥**

{{% steps %}}

##### 登录开发者平台

访问 [Cerebras Cloud](https://cloud.cerebras.ai) 并登录您的账户。

##### 创建 API 密钥

1. 在左侧菜单找到"API Keys"
2. 点击"Create API Key"
3. 为密钥命名（可选）
4. 点击"Create"

##### 保存 API 密钥

1. **重要：** 复制显示的 API 密钥
2. API 密钥只显示一次，请立即保存到安全位置
3. 推荐使用环境变量存储密钥

{{% /steps %}}

---

## 💻 代码示例

### Python 示例

#### 方式 1：使用 OpenAI 客户端（兼容模式）

**安装依赖：**

```bash {filename="Bash"}
pip install openai
```

**基本使用：**

```python {filename="Python"}
from openai import OpenAI

# 初始化客户端（使用 Cerebras API）
client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"  # 替换为您的 API 密钥
)

# 发送请求
response = client.chat.completions.create(
    model="llama-4-scout",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "解释一下什么是晶圆级引擎"}
    ],
    max_tokens=1000,
    temperature=0.7
)

# 打印响应
print(response.choices[0].message.content)

# 查看 Token 使用情况
print(f"\n使用 Tokens: {response.usage.total_tokens}")
print(f"输入 Tokens: {response.usage.prompt_tokens}")
print(f"输出 Tokens: {response.usage.completion_tokens}")
```

#### 方式 2：使用官方 SDK（推荐）

**安装依赖：**

```bash {filename="Bash"}
pip install cerebras_cloud_sdk
```

**基本使用：**

```python {filename="Python"}
from cerebras.cloud.sdk import Cerebras
import os

# 初始化客户端
client = Cerebras(
    api_key=os.environ.get("CEREBRAS_API_KEY")
)

# 发送请求
response = client.chat.completions.create(
    model="llama-3.3-70b",
    messages=[
        {"role": "user", "content": "解释一下什么是晶圆级引擎"}
    ],
)

# 打印响应
print(response.choices[0].message.content)
```

**流式输出示例：**

```python {filename="Python"}
# 流式输出（实时显示）
stream = client.chat.completions.create(
    model="llama-4-scout",
    messages=[
        {"role": "user", "content": "写一首关于人工智能的诗"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

**使用环境变量：**

```python {filename="Python"}
import os
from openai import OpenAI

# 从环境变量读取 API 密钥
client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key=os.getenv("CEREBRAS_API_KEY")
)

response = client.chat.completions.create(
    model="llama-3.1-70b",
    messages=[
        {"role": "user", "content": "什么是机器学习？"}
    ]
)

print(response.choices[0].message.content)
```

---

### cURL 示例

**基本请求：**

```bash {filename="Bash"}
curl https://api.cerebras.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_CEREBRAS_API_KEY" \
  -d '{
    "model": "llama-4-scout",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "你好，请介绍一下 Cerebras"
      }
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**流式输出：**

```bash {filename="Bash"}
curl https://api.cerebras.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_CEREBRAS_API_KEY" \
  -d '{
    "model": "llama-4-scout",
    "messages": [
      {"role": "user", "content": "你好"}
    ],
    "stream": true
  }'
```

---

### Node.js 示例

**安装依赖：**

```bash {filename="Bash"}
npm install openai
```

**基本使用：**

```javascript {filename="JavaScript"}
import OpenAI from 'openai';

const client = new OpenAI({
  baseURL: 'https://api.cerebras.ai/v1',
  apiKey: process.env.CEREBRAS_API_KEY,
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'llama-4-scout',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: '什么是人工智能？' }
    ],
    max_tokens: 1000,
    temperature: 0.7,
  });

  console.log(completion.choices[0].message.content);
  console.log(`\n使用 Tokens: ${completion.usage.total_tokens}`);
}

main();
```

**流式输出：**

```javascript {filename="JavaScript"}
async function streamExample() {
  const stream = await client.chat.completions.create({
    model: 'llama-4-scout',
    messages: [
      { role: 'user', content: '写一个简短的故事' }
    ],
    stream: true,
  });

  for await (const chunk of stream) {
    const content = chunk.choices[0]?.delta?.content || '';
    process.stdout.write(content);
  }
}

streamExample();
```

---

## 🌟 核心优势

### 技术优势

1. **极速推理：**
   - Llama 4 Scout: 2,600+ tokens/s
   - 比 GPU 快 20 倍
   - 毫秒级响应延迟

2. **晶圆级引擎 (WSE)：**
   - 900,000 个 AI 核心
   - 40 Pbits/s 片上带宽
   - 44 GB 高速 SRAM

3. **OpenAI 兼容：**
   - 无缝迁移现有代码
   - 支持流式输出
   - 标准 API 格式

### 与其他 API 对比

| 特性 | Cerebras | Groq | DeepSeek | Google AI Studio |
|------|----------|------|----------|------------------|
| 免费配额 | 100万 tokens/天 | 约14,400 req/天 | ¥5试用 | 免费使用 |
| 推理速度 | 🏆 2,600+ tokens/s | 800+ tokens/s | 快 | 快 |
| OpenAI 兼容 | ✅ | ✅ | ✅ | ❌ |
| 上下文长度 | 128K | 128K | 128K | 2M |
| 需要信用卡 | ❌ | ✅ | ❌ | ❌ |

---

## 💡 实用建议

### ✅ 推荐做法

1. **选择合适的模型：**
   ```python
   # 实时应用 - 追求极致速度
   model = "llama-4-scout"
   
   # 复杂任务 - 平衡性能和质量
   model = "llama-3.1-70b"
   
   # 中文应用 - 中文优化
   model = "qwen-3-32b"
   ```

2. **使用流式输出提升体验：**
   ```python
   # 流式输出让用户实时看到生成内容
   stream = client.chat.completions.create(
       model="llama-4-scout",
       messages=messages,
       stream=True
   )
   
   for chunk in stream:
       if chunk.choices[0].delta.content:
           print(chunk.choices[0].delta.content, end="", flush=True)
   ```

3. **实现请求缓存：**
   ```python
   import hashlib
   import json
   
   cache = {}
   
   def cached_request(model, messages):
       # 生成缓存键
       key = hashlib.md5(
           json.dumps({"model": model, "messages": messages}).encode()
       ).hexdigest()
       
       # 检查缓存
       if key in cache:
           return cache[key]
       
       # 调用 API
       response = client.chat.completions.create(
           model=model,
           messages=messages
       )
       
       # 存入缓存
       cache[key] = response
       return response
   ```

### 🎯 最佳实践

**充分利用免费配额：**
- 每日 100 万 Token 足够开发测试使用
- 监控每日使用情况，避免超额
- 开发环境和测试环境使用免费层级

**优化 Token 使用：**
- 精简 system prompt
- 控制对话历史长度
- 合理设置 max_tokens

**监控配额使用：**

```python {filename="Python"}
# 您可以在 Cerebras Cloud 控制台查看使用情况
# 访问: https://cloud.cerebras.ai
```

**错误处理：**

```python {filename="Python"}
import time
from openai import OpenAI, RateLimitError, APIError

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

def call_api_with_retry(messages, max_retries=3):
    """带重试机制的 API 调用"""
    for attempt in range(max_retries):
        try:
            response = client.chat.completions.create(
                model="llama-4-scout",
                messages=messages
            )
            return response
        except RateLimitError:
            print(f"达到速率限制，等待后重试... ({attempt + 1}/{max_retries})")
            time.sleep(2 ** attempt)  # 指数退避
        except APIError as e:
            print(f"API 错误: {e}")
            if attempt == max_retries - 1:
                raise
            time.sleep(1)
    
    return None
```

### ⚠️ 注意事项

1. **配额管理：** 每日 100 万 Token，UTC 00:00 重置，请合理安排使用
2. **速率限制：** 虽然速度极快，但仍有速率限制，建议实现重试机制
3. **模型选择：** 根据应用场景选择合适的模型，平衡速度和质量

---

## 🎯 实际应用案例

### 案例 1：实时聊天机器人

**场景描述：** 构建一个实时响应的聊天机器人

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

def chatbot():
    """实时聊天机器人"""
    messages = [
        {"role": "system", "content": "你是一个友好的AI助手"}
    ]
    
    print("聊天机器人已启动！输入 'quit' 退出。\n")
    
    while True:
        user_input = input("你: ")
        if user_input.lower() == 'quit':
            break
        
        messages.append({"role": "user", "content": user_input})
        
        # 使用流式输出实现实时响应
        print("AI: ", end="", flush=True)
        stream = client.chat.completions.create(
            model="llama-4-scout",
            messages=messages,
            stream=True
        )
        
        assistant_response = ""
        for chunk in stream:
            content = chunk.choices[0].delta.content or ""
            print(content, end="", flush=True)
            assistant_response += content
        
        print("\n")
        messages.append({"role": "assistant", "content": assistant_response})

# 运行聊天机器人
chatbot()
```

### 案例 2：批量文本处理

**场景描述：** 批量处理多个文本任务

```python {filename="Python"}
import asyncio
from openai import AsyncOpenAI

client = AsyncOpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

async def process_text(text):
    """处理单个文本"""
    response = await client.chat.completions.create(
        model="llama-4-scout",
        messages=[
            {"role": "system", "content": "你是一个文本摘要专家"},
            {"role": "user", "content": f"请总结以下文本：\n\n{text}"}
        ]
    )
    return response.choices[0].message.content

async def batch_process(texts):
    """批量处理文本"""
    tasks = [process_text(text) for text in texts]
    results = await asyncio.gather(*tasks)
    return results

# 使用示例
texts = [
    "这是第一段文本...",
    "这是第二段文本...",
    "这是第三段文本..."
]

results = asyncio.run(batch_process(texts))
for i, summary in enumerate(results, 1):
    print(f"摘要 {i}: {summary}\n")
```

### 案例 3：代码生成助手

**场景描述：** 使用 AI 辅助代码生成

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

def code_assistant(task_description):
    """代码生成助手"""
    response = client.chat.completions.create(
        model="llama-3.1-70b",
        messages=[
            {
                "role": "system",
                "content": "你是一个专业的编程助手，擅长生成高质量的代码"
            },
            {
                "role": "user",
                "content": f"请帮我编写代码：{task_description}"
            }
        ],
        temperature=0.3  # 降低温度以提高代码质量
    )
    
    return response.choices[0].message.content

# 使用示例
task = "用 Python 实现一个二叉树的前序遍历"
code = code_assistant(task)
print("生成的代码：")
print(code)
```

---

## 🔧 常见问题

**Q: 如何查看剩余配额？**  
A: 登录 [Cerebras Cloud 控制台](https://cloud.cerebras.ai) 可以查看 API 使用情况和剩余配额。建议在开发时定期检查使用量。

**Q: 超过每日配额会怎样？**  
A: API 将返回 429 错误，需要等待到 UTC 00:00 配额重置，或升级到付费计划。

**Q: 支持哪些编程语言？**  
A: 由于兼容 OpenAI API 格式，所有支持 OpenAI SDK 的语言都可以使用，包括 Python、Node.js、Go、Java 等。

**Q: 可以用于生产环境吗？**  
A: 免费层级主要用于开发测试，生产环境建议联系 Cerebras 商务团队获取企业方案。

**Q: 为什么这么快？**  
A: Cerebras 使用晶圆级引擎 (WSE)，单芯片拥有 900,000 个核心和 40 Pbits/s 带宽，消除了传统 GPU 的内存瓶颈。

---

## 🔗 相关资源

- **API 端点：** `https://api.cerebras.ai/v1`
- **开发者平台：** [https://cloud.cerebras.ai](https://cloud.cerebras.ai)
- **API 文档：** [https://inference-docs.cerebras.ai](https://inference-docs.cerebras.ai)
- **提供者主页：** [Cerebras Systems](/providers/cerebras)
- **SDK 文档：** [OpenAI Python SDK](https://github.com/openai/openai-python)
- **GitHub：** [https://github.com/Cerebras](https://github.com/Cerebras)

---

## 📝 更新日志

- **2024年1月：** Cerebras Inference API 公开发布，提供每日 100 万 Token 免费额度
- **2024年：** 新增 Llama 3 系列模型支持
- **2025年：** 新增 Llama 4 Scout、Qwen 3-32B 等模型

---

**服务提供者：** [Cerebras Systems](/providers/cerebras)
