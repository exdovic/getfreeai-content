---
title: "Baidu 千帆 API - 永久免费国产 AI API 服务"
linkTitle: "API - Baidu"
description: "百度千帆大模型平台提供永久免费 API 服务！ERNIE-3.5-8K 和 ERNIE-Speed-8K 永久免费不限量，性能超越 GPT-3.5，支持 OpenAI SDK，中文优化，国内访问快速。"
keywords:
  - 百度千帆 API
  - 文心一言 API
  - ERNIE API
  - 免费中文 API
  - 国产 AI API
  - 永久免费 API
  - OpenAI 兼容
  - 百度智能云
image: /images/logo.svg
type: docs
weight: 8
comments: true
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [Baidu（百度）](/providers/baidu)  
**服务类型：** API 服务  
**API 端点：** `https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop/chat/`  
**免费类型：** 永久免费（部分模型） + 新用户赠送  
**API 兼容性：** 支持 OpenAI SDK

---

## 🎯 服务简介

百度千帆大模型平台提供强大的 AI API 服务，特色是提供**永久免费**的高性能模型，完全兼容 OpenAI SDK，为开发者提供零成本的 AI 能力。

**核心优势：**
- 🎁 **永久免费模型** - ERNIE-3.5-8K、ERNIE-Speed-8K 永久免费
- 💰 **超高性价比** - 免费模型性能超越 GPT-3.5 Turbo
- 🔄 **OpenAI 兼容** - 支持 OpenAI SDK，一行代码迁移
- 🇨🇳 **中文优化** - 专为中文优化，中文性能顶尖
- 🚀 **国内访问快** - 服务器在国内，响应速度快
- 🎁 **新用户赠送** - ERNIE-4.0-8K 100万 tokens/月（首月）
- 🔒 **合规商用** - 国内备案合规，商用无风险

---

## 🚀 快速开始

### 前提条件

**必需：**
- ✅ 已注册百度智能云账户
- ✅ 已完成实名认证
- ✅ 已创建应用并获取 API Key

详细步骤请参考：[百度注册指南](/providers/baidu#注册和账号)

### 5 分钟快速示例

**使用 OpenAI SDK（推荐）**

```python {filename="Python"}
from openai import OpenAI

# 配置百度千帆（使用 OpenAI SDK）
client = OpenAI(
    api_key="YOUR_BAIDU_API_KEY",
    base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
)

# 调用永久免费的 ERNIE-3.5-8K
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=[
        {"role": "system", "content": "你是一个有帮助的助手"},
        {"role": "user", "content": "介绍一下量子计算"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 支持的模型

### 永久免费模型

| Model ID | 上下文 | 特点 | QPS | 价格 |
|----------|--------|------|-----|------|
| `ernie-3.5-8k` | 8K | 🏆 性能超越 GPT-3.5 | 50 | **永久免费** |
| `ernie-speed-8k` | 8K | ⚡ 极速响应 | 50 | **永久免费** |

### 新用户赠送

| Model ID | 上下文 | 特点 | QPS | 免费额度 |
|----------|--------|------|-----|---------|
| `ernie-4.0-8k` | 8K | 🆕 最新旗舰模型 | 5 | 100万 tokens/月（首月） |

### 付费模型

| Model ID | 上下文 | 特点 | 价格（输入/输出） |
|----------|--------|------|------------------|
| `ernie-4.0-turbo-8k` | 8K | 高性能旗舰 | ¥12/M / ¥12/M |
| `ernie-4.0-turbo-128k` | 128K | 超长上下文 | ¥20/M / ¥20/M |
| `ernie-lite-8k` | 8K | 轻量快速 | ¥0/M / ¥0/M（试用期） |

⚠️ **重要说明：**
- ERNIE-3.5-8K 和 ERNIE-Speed-8K **永久免费，不限 token 数量**
- QPS 限制：每秒最多请求次数（可通过付费提高）
- 新用户首月赠送 ERNIE-4.0-8K 100万 tokens
- 详细价格请查看 [官方定价](https://cloud.baidu.com/doc/qianfan/s/Blfmc9dlf)

---

## 🔢 配额和限制

### 永久免费模型限制

| 限制项 | ERNIE-3.5-8K | ERNIE-Speed-8K |
|--------|--------------|----------------|
| **Token 限制** | 无限制 | 无限制 |
| **每秒请求数（QPS）** | 50 | 50 |
| **并发请求** | 50 | 50 |
| **上下文长度** | 8K tokens | 8K tokens |
| **有效期** | 永久 | 永久 |

### 新用户赠送限制

| 限制项 | ERNIE-4.0-8K |
|--------|--------------|
| **免费额度** | 100万 tokens/月 |
| **有效期** | 注册后首月 |
| **QPS** | 5 |

### 配额查询

- 实时查看配额：[控制台配额页面](https://console.bce.baidu.com/qianfan/ais/console/quota)
- 查看使用统计：控制台 → 千帆平台 → 用量统计

---

## 💻 代码示例

### 1. 基础对话（OpenAI SDK）

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_BAIDU_API_KEY",
    base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
)

# 使用永久免费的 ERNIE-3.5
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=[
        {"role": "user", "content": "什么是人工智能？"}
    ]
)

print(response.choices[0].message.content)
```

### 2. 流式输出

```python {filename="Python"}
# 流式输出（适合实时显示）
stream = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=[
        {"role": "user", "content": "写一篇关于 AI 的文章"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

### 3. 多轮对话

```python {filename="Python"}
messages = [
    {"role": "system", "content": "你是一个 Python 编程助手"}
]

# 第一轮对话
messages.append({"role": "user", "content": "如何读取 CSV 文件？"})
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=messages
)
messages.append({
    "role": "assistant", 
    "content": response.choices[0].message.content
})

# 第二轮对话
messages.append({"role": "user", "content": "如何处理缺失值？"})
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=messages
)
print(response.choices[0].message.content)
```

### 4. 使用官方 SDK

```python {filename="Python"}
# 安装官方 SDK
# pip install qianfan

import qianfan

# 通过 API Key 和 Secret Key 初始化
chat_comp = qianfan.ChatCompletion(
    api_key="YOUR_API_KEY",
    secret_key="YOUR_SECRET_KEY"
)

# 调用 ERNIE-3.5-8K
resp = chat_comp.do(
    model="ERNIE-3.5-8K",
    messages=[{
        "role": "user",
        "content": "你好，请介绍一下自己"
    }]
)

print(resp["result"])
```

### 5. cURL 示例

```bash {filename="Bash"}
# 获取 access_token
curl -X POST \
  'https://aip.baidubce.com/oauth/2.0/token?grant_type=client_credentials&client_id=YOUR_API_KEY&client_secret=YOUR_SECRET_KEY'

# 调用 API（使用获取的 access_token）
curl -X POST \
  'https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop/chat/ernie-3.5-8k?access_token=YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{
    "messages": [
      {
        "role": "user",
        "content": "你好，请介绍一下自己"
      }
    ]
  }'
```

---

## 💡 最佳实践

### ✅ 推荐做法

1. **选择合适的模型**
   ```python
   # 通用任务、成本优先 → ERNIE-3.5-8K（永久免费）
   model = "ernie-3.5-8k"
   
   # 速度优先 → ERNIE-Speed-8K（永久免费）
   model = "ernie-speed-8k"
   
   # 质量优先 → ERNIE-4.0-8K（新用户首月免费）
   model = "ernie-4.0-8k"
   ```

2. **错误处理和重试**
   ```python
   import time
   from openai import OpenAI, APIError
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="ernie-3.5-8k",
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

3. **安全管理密钥**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('BAIDU_API_KEY')
   secret_key = os.getenv('BAIDU_SECRET_KEY')
   
   client = OpenAI(
       api_key=api_key,
       base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
   )
   ```

4. **监控使用情况**
   - 定期访问 [控制台](https://console.bce.baidu.com/qianfan/ais/console/quota)
   - 查看剩余配额和使用统计
   - 设置配额警告

### 🎯 优化建议

**充分利用永久免费模型：**
- ERNIE-3.5-8K 性能已超越 GPT-3.5 Turbo
- 适合大部分应用场景
- 零成本开发和运营

**优化 QPS 使用：**
- 合理分配并发请求
- 超出 QPS 会排队等待
- 需要更高 QPS 可考虑付费升级

**结果缓存：**
```python
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

### ⚠️ 注意事项

1. **实名认证必需：** API 使用必须完成实名认证
2. **QPS 限制：** 免费模型 QPS 为 50，超出会排队
3. **内容审核：** 遵守中国法律法规，敏感内容会被拒绝
4. **Token 计算：** 中文按字符计算，约 1.5-2 个字符 = 1 token

---

## 🔧 常见问题

### 1. 如何获取 API Key？

**步骤：**
1. 登录 [百度智能云千帆平台](https://qianfan.cloud.baidu.com)
2. 完成实名认证
3. 创建应用
4. 获取 API Key 和 Secret Key

### 2. 永久免费模型真的不限量吗？

**答：** 是的！ERNIE-3.5-8K 和 ERNIE-Speed-8K 永久免费，不限 token 数量，只有 QPS（每秒50次请求）限制。

### 3. 如何使用 OpenAI SDK？

**答：** 百度千帆支持 OpenAI SDK，只需修改 `base_url`：
```python
client = OpenAI(
    api_key="YOUR_BAIDU_API_KEY",
    base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
)
```

### 4. ERNIE-3.5 与 GPT-3.5 相比如何？

**答：** 根据官方数据和实测：
- 中文能力：ERNIE-3.5 > GPT-3.5 Turbo
- 英文能力：ERNIE-3.5 ≈ GPT-3.5 Turbo
- 价格：ERNIE-3.5 永久免费，GPT-3.5 付费

### 5. 新用户赠送如何获取？

**答：** 
- 注册百度智能云账户
- 完成实名认证
- 首月自动获得 ERNIE-4.0-8K 100万 tokens
- 有效期为注册后首月

### 6. 支持哪些支付方式？

**答：** 
- 支付宝
- 微信支付
- 对公转账
- 银行卡

---

## 📊 性能对比

### 与其他 API 对比

| API | 免费类型 | 配额 | 中文性能 | OpenAI 兼容 |
|-----|---------|------|---------|-------------|
| **百度千帆** | 🏆 永久免费 | 不限量 | 🏆 顶尖 | ✅ |
| Google AI Studio | 永久免费 | 免费使用 | 优秀 | ❌ |
| DeepSeek | 试用积分 | ¥5（7天） | 🏆 顶尖 | ✅ |
| Groq | 免费服务 | 约14,400次/天 | 良好 | ✅ |

### 价格优势

| 场景 | 百度千帆 | GPT-3.5 Turbo | 节省 |
|------|---------|---------------|------|
| 1M tokens | **免费** | ~$1.5 | 100% |
| 10M tokens | **免费** | ~$15 | 100% |
| 100M tokens | **免费** | ~$150 | 100% |

---

## 🌟 实战案例

### 案例 1：智能客服

```python {filename="Python"}
def ai_customer_service(user_question):
    """智能客服助手"""
    response = client.chat.completions.create(
        model="ernie-3.5-8k",  # 使用永久免费模型
        messages=[
            {
                "role": "system",
                "content": "你是一个专业的客服助手，负责回答用户关于产品的问题"
            },
            {
                "role": "user",
                "content": user_question
            }
        ]
    )
    return response.choices[0].message.content

# 使用
answer = ai_customer_service("你们的产品有什么特点？")
print(answer)
```

### 案例 2：文档摘要生成

```python {filename="Python"}
def summarize_document(document_text):
    """生成文档摘要"""
    response = client.chat.completions.create(
        model="ernie-3.5-8k",
        messages=[
            {
                "role": "system",
                "content": "你是一个文档分析专家，擅长提取关键信息"
            },
            {
                "role": "user",
                "content": f"请总结以下文档的核心内容：\n\n{document_text}"
            }
        ]
    )
    return response.choices[0].message.content
```

### 案例 3：内容审核

```python {filename="Python"}
def content_moderation(user_content):
    """内容审核"""
    response = client.chat.completions.create(
        model="ernie-speed-8k",  # 使用极速模型
        messages=[
            {
                "role": "system",
                "content": "你是一个内容审核专家，判断内容是否合规"
            },
            {
                "role": "user",
                "content": f"请判断以下内容是否合规：\n{user_content}"
            }
        ]
    )
    return response.choices[0].message.content
```

---

## 📚 相关资源

### 官方文档
- [百度完整介绍](/providers/baidu)
- [Chatbot 使用指南](/services/chatbot/baidu)
- [API 官方文档](https://cloud.baidu.com/doc/qianfan/index.html)

### 工具和资源
- [千帆控制台](https://console.bce.baidu.com/qianfan/overview)
- [配额查询](https://console.bce.baidu.com/qianfan/ais/console/quota)
- [定价说明](https://cloud.baidu.com/doc/qianfan/s/Blfmc9dlf)
- [实名认证](https://console.bce.baidu.com/idc/#/personal/verify)
- [官方 SDK（Python）](https://github.com/baidubce/bce-qianfan-sdk)

---

## 📝 更新日志

- **2025年：** ERNIE-3.5-8K 和 ERNIE-Speed-8K 永久免费
- **2025年3月：** 发布 ERNIE 4.5 和 ERNIE X1 新模型
- **持续更新：** 不断优化 API 性能和稳定性

---

**服务提供者：** [Baidu（百度）](/providers/baidu)
