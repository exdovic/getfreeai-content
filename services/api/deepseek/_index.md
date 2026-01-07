---
title: "DeepSeek API - 中文优化超低价 AI API 服务"
linkTitle: "API - DeepSeek"
description: "DeepSeek 提供中文顶尖 AI API 服务，支持 DeepSeek V3.2 最新旗舰模型、思维链模式推理。中文优化，超低价格 $0.28/百万 tokens，¥5 免费试用，OpenAI 兼容接口。"
keywords:
  - DeepSeek API
  - 中文 AI API
  - 超低价 API
  - DeepSeek R1 API
  - 思维链 API
  - 中文优化 API
  - 国产 AI 接口
  - 透明推理 API
image: /images/logo.svg
weight: 4
comments: true
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [DeepSeek](/providers/deepseek)  
**服务类型：** API 服务  
**API 端点：** [https://api.deepseek.com](https://api.deepseek.com)  
**免费类型：** 试用积分（¥5，7天有效，可能因活动调整）  
**API 兼容性：** 完全兼容 OpenAI API

---

## 🎯 服务简介

DeepSeek API 提供强大的 AI 能力，完全兼容 OpenAI API 格式，价格比 GPT-4 便宜 97%，特别适合预算有限但需要高性能的开发者。

**核心优势：**
- 💰 **超低价格** - 比 GPT-4 便宜 95%+
- 🔄 **OpenAI 兼容** - 无缝迁移现有代码
- 🧠 **思维链模式** - 推理过程透明可见
- 🆕 **最新 V3.2** - 强化 Agent 能力
- 🇨🇳 **中文优化** - 中文性能顶尖
- 🎁 **试用积分** - 新用户赠送 ¥5（7天有效，可能因活动调整）

---

## 🚀 快速开始

### 前提条件

**必需：**
- ✅ 已注册开发者账户
- ✅ 已完成实名认证（API 充值必需）
- ✅ 已创建 API 密钥

详细步骤请参考：[DeepSeek 注册指南](/providers/deepseek#注册和账号)

### 5 分钟快速示例

**使用 OpenAI SDK（推荐）**

```python {filename="Python"}
from openai import OpenAI

# 配置 DeepSeek
client = OpenAI(
    api_key="YOUR_DEEPSEEK_API_KEY",
    base_url="https://api.deepseek.com"
)

# 使用 DeepSeek Chat
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "system", "content": "你是一个有帮助的助手"},
        {"role": "user", "content": "解释一下什么是深度学习"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 支持的模型

### 模型列表

| Model ID | 版本 | 上下文 | 价格（/百万tokens）|
|----------|------|--------|-------------------|
| `deepseek-chat` | V3.2 | 128K | $0.28(in)/$0.42(out) |
| `deepseek-reasoner` | V3.2 | 128K | $0.28(in)/$0.42(out) |

**注意：** 
- deepseek-chat：标准模式，默认输出 4K（最大 8K）
- deepseek-reasoner：思维链模式，默认输出 32K（最大 64K）
- 支持上下文缓存，命中时输入价格降至 $0.028/M

---

## 🔢 试用积分和价格

### 试用积分

| 项目 | 详情 |
|------|------|
| **赠送金额** | ¥5 人民币（可能因活动调整）|
| **有效期** | 注册后 7 天 |
| **获取方式** | 注册并实名认证后自动获得 |

### 充值后价格

**所有模型（V3.2）：**
- 输入（缓存未命中）：$0.28 / 百万 tokens
- 输入（缓存命中）：$0.028 / 百万 tokens  
- 输出：$0.42 / 百万 tokens

**换算参考：** $1 ≈ ¥7.2

### 价格对比

| 模型 | 输入 | 输出 | 相对便宜 |
|------|------|------|---------|
| **DeepSeek V3.2** | $0.28 | $0.42 | 基准 |
| GPT-4 Turbo | $10 | $30 | **36-71倍** |
| GPT-4o | $5 | $15 | **18-36倍** |
| Claude 3.5 | $3 | $15 | **11-36倍** |

---

## 📖 API 使用示例

### 1. 基础对话

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_DEEPSEEK_API_KEY",
    base_url="https://api.deepseek.com"
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "system", "content": "你是一个有帮助的AI助手"},
        {"role": "user", "content": "什么是机器学习？"}
    ]
)

print(response.choices[0].message.content)
```

### 2. 流式输出

```python {filename="Python"}
stream = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "user", "content": "写一篇关于AI的文章"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

### 3. 使用推理模型（R1）

```python {filename="Python"}
# 使用 DeepSeek R1 推理模型
response = client.chat.completions.create(
    model="deepseek-reasoner",
    messages=[
        {
            "role": "user",
            "content": "有100个球，每次拿走一半再放回1个，重复这个过程，最后会剩几个球？"
        }
    ]
)

# 查看推理过程
print("=== 思维过程 ===")
print(response.choices[0].message.reasoning_content)

# 查看最终答案
print("\n=== 最终答案 ===")
print(response.choices[0].message.content)
```

### 4. 代码生成（Coder）

```python {filename="Python"}
response = client.chat.completions.create(
    model="deepseek-coder",
    messages=[
        {
            "role": "system",
            "content": "你是一个专业的编程助手"
        },
        {
            "role": "user",
            "content": "用 Python 实现快速排序算法"
        }
    ]
)

print(response.choices[0].message.content)
```

### 5. cURL 示例

```bash {filename="Bash"}
curl https://api.deepseek.com/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_DEEPSEEK_API_KEY" \
  -d '{
    "model": "deepseek-chat",
    "messages": [
      {
        "role": "system",
        "content": "你是一个有帮助的助手"
      },
      {
        "role": "user",
        "content": "你好，介绍一下你自己"
      }
    ]
  }'
```

### 6. 多轮对话

```python {filename="Python"}
messages = [
    {"role": "system", "content": "你是一个Python编程助手"}
]

# 第一轮
messages.append({"role": "user", "content": "如何读取文件？"})
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=messages
)
messages.append({"role": "assistant", "content": response.choices[0].message.content})

# 第二轮
messages.append({"role": "user", "content": "那写入呢？"})
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=messages
)
print(response.choices[0].message.content)
```

---

## 💡 最佳实践

### ✅ 推荐做法

1. **选择合适的模型**
   ```python
   # 通用任务 - 最便宜
   model = "deepseek-chat"
   
   # 代码任务 - 编程专家
   model = "deepseek-coder"
   
   # 复杂推理 - 数学、逻辑
   model = "deepseek-reasoner"
   ```

2. **错误处理和重试**
   ```python
   import time
   from openai import OpenAI, APIError
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="deepseek-chat",
                   messages=messages
               )
           except APIError as e:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"API 错误，等待 {wait_time} 秒...")
                   time.sleep(wait_time)
               else:
                   raise
   ```

3. **监控使用情况**
   ```python
   # 访问 https://platform.deepseek.com
   # 费用中心 → 查看详细使用统计
   ```

4. **安全管理 API 密钥**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('DEEPSEEK_API_KEY')
   
   client = OpenAI(
       api_key=api_key,
       base_url="https://api.deepseek.com"
   )
   ```

---

## 🔧 常见问题

### 1. 如何实名认证？

**步骤：**
1. 登录 https://platform.deepseek.com
2. 头像 → 账户设置 → 实名认证
3. 上传身份证（正反面）
4. 等待审核（1-24小时）

### 2. 试用积分用完了怎么办？

**解决：**
- 可以充值继续使用
- 价格极低（¥1-2/M tokens）
- 支持支付宝、微信支付

### 3. 支持哪些支付方式？

**支持：**
- 支付宝
- 微信支付
- 对公转账

### 4. 如何查看余额？

**方法：**
- 登录控制台
- 费用中心 → 余额查询

---

## 📊 性能优化

### 1. 选择合适的模型

```python {filename="Python"}
def select_model(task_type):
    if task_type == "code":
        return "deepseek-coder"
    elif task_type == "reasoning":
        return "deepseek-reasoner"
    else:
        return "deepseek-chat"  # 最便宜
```

### 2. 结果缓存

```python {filename="Python"}
import hashlib
import json

cache = {}

def cached_completion(model, messages):
    key = hashlib.md5(
        json.dumps({"model": model, "messages": messages}).encode()
    ).hexdigest()
    
    if key in cache:
        return cache[key]
    
    response = client.chat.completions.create(
        model=model,
        messages=messages
    )
    
    cache[key] = response
    return response
```

---

## 📚 相关资源

### 官方文档
- [DeepSeek 完整介绍](/providers/deepseek)
- [Chatbot 使用指南](/services/chatbot/deepseek-chat)
- [API 官方文档](https://platform.deepseek.com/api-docs)

### 工具和资源
- [定价说明](https://platform.deepseek.com/pricing)
- [开发者控制台](https://platform.deepseek.com)
- [帮助中心](https://platform.deepseek.com/docs)

---

## 🌟 实战案例

### 案例 1：学术论文助手

```python {filename="Python"}
def analyze_paper(paper_text):
    """分析学术论文"""
    response = client.chat.completions.create(
        model="deepseek-chat",
        messages=[
            {
                "role": "system",
                "content": "你是一个学术论文分析专家"
            },
            {
                "role": "user",
                "content": f"请分析以下论文的核心贡献和创新点：\n\n{paper_text}"
            }
        ]
    )
    return response.choices[0].message.content
```

### 案例 2：代码审查助手

```python {filename="Python"}
def code_review(code):
    """代码审查和优化建议"""
    response = client.chat.completions.create(
        model="deepseek-coder",
        messages=[
            {
                "role": "system",
                "content": "你是一个代码审查专家"
            },
            {
                "role": "user",
                "content": f"请审查以下代码：\n\n```python\n{code}\n```"
            }
        ]
    )
    return response.choices[0].message.content
```

### 案例 3：数学解题助手

```python {filename="Python"}
def solve_math_problem(problem):
    """使用 R1 模型解决数学问题"""
    response = client.chat.completions.create(
        model="deepseek-reasoner",
        messages=[
            {
                "role": "user",
                "content": f"请解决以下数学问题：{problem}"
            }
        ]
    )
    
    print("=== 思维过程 ===")
    print(response.choices[0].message.reasoning_content)
    print("\n=== 最终答案 ===")
    print(response.choices[0].message.content)
```

---

**服务提供者：** [DeepSeek](/providers/deepseek)
