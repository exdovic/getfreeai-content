---
title: "Mistral API - 欧洲开源 AI 开发者接口"
linkTitle: "API - Mistral"
description: "Mistral API 提供多种开源和专有 AI 模型接口，支持文本生成、代码生成、嵌入等功能。灵活的按需付费定价，支持多云部署（AWS、Azure、Google Cloud）。提供 OpenAI 兼容的 API 格式，易于集成。"
keywords:
  - Mistral API
  - Mistral AI API
  - 欧洲AI API
  - 开源AI API
  - Pixtral API
  - Mistral Large API
  - 法国AI接口
  - 多云部署API
image: /images/logo.svg
type: docs
weight: 10
comments: true
prev: /services/api/hugging-face
next: /services/api/cohere
sidebar:
  open: true
---

## 📋 服务概览

**服务名称：** Mistral API  
**所属提供者：** [Mistral AI](/providers/mistral)  
**API 端点：** `https://api.mistral.ai/v1`  
**服务类型：** Experiment 免费试用 + Scale 按需付费  
**注册要求：** 需要注册账户；Experiment 计划仅需手机验证，Scale 计划需绑定支付方式

---

## ✅ 服务说明

Mistral API 是 Mistral AI 提供的开发者 API 接口，允许开发者将 Mistral 的先进 AI 模型集成到自己的应用中。API 采用 OpenAI 兼容的格式，易于从其他服务迁移。

### 主要特点

- **🔓 开源模型：** 部分模型开源，可下载本地部署
- **💰 灵活定价：** 按需付费，价格透明合理
- **☁️ 多云支持：** 支持在 AWS、Azure、Google Cloud 部署
- **🔄 OpenAI 兼容：** API 格式兼容 OpenAI，易于迁移
- **🎨 多模态能力：** Pixtral Large 支持图像理解
- **🇪🇺 数据主权：** 欧洲服务器，符合 GDPR

---

## 🎁 可用模型

### 免费/付费模型列表

|| 模型名称 | 上下文长度 | 特点 | 适用场景 | 定价 |
||---------|-----------|------|---------|------|
|| **Mistral Large 2** | 128K | 最强性能，多语言 | 复杂推理、长文本 | $2-6/M tokens |
|| **Pixtral Large** | 128K | 多模态，图像理解 | 视觉任务、OCR | $2-6/M tokens |
|| **Mistral Medium** | 32K | 平衡性能成本 | 日常应用 | $0.40-2/M tokens |
|| **Mistral Small** | 32K | 轻量高效 | 简单任务、高频调用 | $0.20-0.60/M tokens |
|| **Mixtral 8x7B** | 32K | 开源 MoE | 通用任务 | 开源免费/API付费 |
|| **Mistral 7B** | 8K | 开源基础 | 入门学习 | 开源免费 |

### 模型详细说明

#### Mistral Large 2
- **上下文窗口：** 128K tokens
- **主要用途：** 复杂推理、多语言任务、代码生成
- **优势：** 性能顶尖，支持 80+ 语言
- **定价：** 输入 $2/M，输出 $6/M

#### Pixtral Large
- **上下文窗口：** 128K tokens
- **主要用途：** 图像理解、文档分析、多模态任务
- **优势：** 欧洲首个多模态模型，视觉能力强
- **定价：** 输入 $2/M，输出 $6/M

#### Mistral Medium
- **上下文窗口：** 32K tokens
- **主要用途：** 日常对话、内容生成
- **优势：** 性能和成本平衡
- **定价：** 输入 $0.40/M，输出 $2/M

---

## 🔢 配额和限制

### 免费试用 (Experiment 计划)

| 项目 | 详情 |
|------|------|
| **试用方式** | Experiment 计划，免费试用（仅需手机验证，无需信用卡）|
| **速率限制** | 受限速率，适合实验和原型开发 |
| **获取方式** | 注册后在控制台 Subscription 中激活 Experiment 计划 |
| **升级选项** | 可升级到 Scale 计划（按需付费）获得更高配额 |

### 速率限制

|| 限制项 | 免费/试用 | 付费 |
||--------|----------|------|
|| **每分钟请求数** | 较低 | 根据套餐 |
|| **每分钟 Token 数** | 有限制 | 根据套餐 |
|| **并发请求** | 有限制 | 根据套餐 |

### ⚠️ 重要限制

1. **Experiment vs Scale：** Experiment 计划免费但有速率限制，Scale 计划按需付费且配额更高
2. **速率限制：** 根据账户等级和计划有不同的速率限制
3. **数据使用：** Experiment 计划的请求可能用于模型改进，Scale 计划默认不会（可在控制台调整）

### 配额重置时间

- **按使用量计费：** 实时扣费，无固定重置时间
- **速率限制：** 每分钟滚动窗口

---

## 💰 价格说明

### 按需付费

|| 模型 | 输入价格 | 输出价格 | 说明 |
||------|---------|---------|------|
|| **Mistral Large 2** | $2/M tokens | $6/M tokens | 最强性能 |
|| **Pixtral Large** | $2/M tokens | $6/M tokens | 多模态 |
|| **Mistral Medium** | $0.40/M tokens | $2/M tokens | 性价比高 |
|| **Mistral Small** | $0.20/M tokens | $0.60/M tokens | 经济实惠 |

**注：** M = Million（百万）

### 多云部署价格

在 AWS、Azure、Google Cloud 等平台部署价格可能不同，请查看各平台定价。

---

## 🚀 如何使用

### 前提条件

**1. 注册账户**

请先 [注册 Mistral AI 账户](/providers/mistral#注册账户)

**2. 获取 API 密钥**

{{% steps %}}

##### 登录控制台

访问 [Mistral AI 控制台](https://console.mistral.ai) 并登录。

##### 选择计划

1. 进入 "Admin" → "Subscription" 部分
2. 选择 **Experiment**（免费试用）或 **Scale**（付费）
3. **Experiment：** 通常只需手机验证，无需信用卡
4. **Scale：** 需要在 Billing 中添加支付方式

##### 创建 API 密钥

1. 导航到 "API Keys" 页面
2. 点击 "Create API Key"
3. 为密钥命名（例如："My App API Key"）
4. 复制生成的 API 密钥
5. **重要：** 安全保存密钥，它只会显示一次

{{% /steps %}}

---

## 💻 代码示例

### Python 示例

**安装依赖：**

```bash {filename="Bash"}
pip install mistralai
# 或使用 OpenAI SDK（兼容）
pip install openai
```

**使用 Mistral 官方 SDK：**

```python {filename="Python"}
from mistralai.client import MistralClient
from mistralai.models.chat_completion import ChatMessage

# 初始化客户端
client = MistralClient(api_key="YOUR_API_KEY")

# 发送请求
messages = [
    ChatMessage(role="user", content="什么是机器学习？")
]

response = client.chat(
    model="mistral-large-latest",
    messages=messages
)

print(response.choices[0].message.content)
```

**使用 OpenAI SDK（兼容）：**

```python {filename="Python"}
from openai import OpenAI

# 初始化客户端（使用 Mistral API）
client = OpenAI(
    api_key="YOUR_MISTRAL_API_KEY",
    base_url="https://api.mistral.ai/v1"
)

# 发送请求
response = client.chat.completions.create(
    model="mistral-large-latest",
    messages=[
        {"role": "system", "content": "你是一个有帮助的助手。"},
        {"role": "user", "content": "解释一下深度学习的基本原理。"}
    ],
    max_tokens=1000,
    temperature=0.7
)

print(response.choices[0].message.content)
print(f"\n使用 Tokens: {response.usage.total_tokens}")
```

**流式输出示例：**

```python {filename="Python"}
# 流式输出（实时显示）
stream = client.chat.completions.create(
    model="mistral-large-latest",
    messages=[
        {"role": "user", "content": "写一首关于 AI 的诗"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

---

### cURL 示例

**基本请求：**

```bash {filename="Bash"}
curl https://api.mistral.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "mistral-large-latest",
    "messages": [
      {
        "role": "system",
        "content": "你是一个有帮助的助手。"
      },
      {
        "role": "user",
        "content": "你好，请介绍一下自己。"
      }
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**流式输出：**

```bash {filename="Bash"}
curl https://api.mistral.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "mistral-large-latest",
    "messages": [{"role": "user", "content": "你好"}],
    "stream": true
  }'
```

---

### Node.js 示例

```javascript {filename="JavaScript"}
import OpenAI from 'openai';

const client = new OpenAI({
  apiKey: 'YOUR_MISTRAL_API_KEY',
  baseURL: 'https://api.mistral.ai/v1',
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'mistral-large-latest',
    messages: [
      { role: 'system', content: '你是一个有帮助的助手。' },
      { role: 'user', content: '你好，请介绍一下自己。' }
    ],
    max_tokens: 1000,
    temperature: 0.7,
  });

  console.log(completion.choices[0].message.content);
  console.log(`\n使用 Tokens: ${completion.usage.total_tokens}`);
}

main();
```

---

### 多模态示例（Pixtral Large）

```python {filename="Python"}
from openai import OpenAI
import base64

client = OpenAI(
    api_key="YOUR_MISTRAL_API_KEY",
    base_url="https://api.mistral.ai/v1"
)

# 读取图片并转为 base64
def encode_image(image_path):
    with open(image_path, "rb") as image_file:
        return base64.b64encode(image_file.read()).decode('utf-8')

image_base64 = encode_image("path/to/your/image.jpg")

# 发送多模态请求
response = client.chat.completions.create(
    model="pixtral-large-latest",
    messages=[
        {
            "role": "user",
            "content": [
                {"type": "text", "text": "这张图片里有什么？"},
                {
                    "type": "image_url",
                    "image_url": {
                        "url": f"data:image/jpeg;base64,{image_base64}"
                    }
                }
            ]
        }
    ]
)

print(response.choices[0].message.content)
```

---

## 🌟 核心优势

### 技术优势

1. **开源透明：**
   - 多个模型开源（Mistral 7B, Mixtral 8x7B）
   - 可下载本地部署
   - 社区活跃

2. **多云灵活：**
   - AWS Sagemaker
   - Microsoft Azure AI
   - Google Cloud Vertex AI
   - 自建服务器

3. **欧洲数据主权：**
   - 数据存储在欧洲
   - 符合 GDPR
   - 隐私保护严格

### 与其他 API 对比

|| 特性 | Mistral API | OpenAI API | Google AI Studio | DeepSeek API |
||------|------------|-----------|-----------------|-------------|
|| 免费配额 | 试用额度 | 试用额度 | 高配额免费 | ¥5 试用 |
|| 开源模型 | ✅ 部分 | ❌ | ❌ | ✅ |
|| 多云部署 | ✅ | ❌ | ✅ | ❌ |
|| 欧洲服务器 | ✅ | ❌ | ❌ | ❌ |
|| OpenAI 兼容 | ✅ | ✅ | 部分 | ✅ |
|| 多模态 | ✅ Pixtral | ✅ GPT-4V | ✅ Gemini | ❌ |

---

## 💡 实用建议

### ✅ 推荐做法

1. **选择合适的模型：**
   ```python
   # 复杂任务 → Mistral Large
   model = "mistral-large-latest"
   
   # 图像任务 → Pixtral Large
   model = "pixtral-large-latest"
   
   # 经济实惠 → Mistral Small
   model = "mistral-small-latest"
   ```

2. **错误处理和重试：**
   ```python
   import time
   from openai import OpenAI, APIError
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="mistral-large-latest",
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

3. **安全管理 API 密钥：**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('MISTRAL_API_KEY')
   
   client = OpenAI(
       api_key=api_key,
       base_url="https://api.mistral.ai/v1"
   )
   ```

4. **监控使用情况：**
   - 定期检查 [控制台](https://console.mistral.ai) 的使用统计
   - 设置预算警报
   - 记录 API 调用和成本

### 🎯 最佳实践

**优化 Token 使用：**
- 使用简洁的 Prompt
- 避免重复的系统消息
- 设置合理的 max_tokens

**选择合适的温度：**
```python
# 创意任务（诗歌、故事）
temperature = 0.9

# 平衡（日常对话）
temperature = 0.7

# 精确任务（代码、翻译）
temperature = 0.3
```

**批量处理：**
```python
# 批量处理多个请求
requests = ["问题1", "问题2", "问题3"]
responses = []

for question in requests:
    response = client.chat.completions.create(
        model="mistral-large-latest",
        messages=[{"role": "user", "content": question}]
    )
    responses.append(response.choices[0].message.content)
```

### ⚠️ 注意事项

1. **成本控制：** API 按使用量付费，请监控成本
2. **速率限制：** 注意不要超过速率限制
3. **数据隐私：** 不要发送敏感信息到 API
4. **模型选择：** 根据任务选择合适的模型以优化成本

---

## 🎯 实际应用案例

### 案例 1：智能客服系统

```python {filename="Python"}
def customer_service_bot(user_message, conversation_history):
    """智能客服助手"""
    messages = [
        {"role": "system", "content": "你是一个专业的客服助手，友好且高效。"}
    ]
    
    # 添加对话历史
    messages.extend(conversation_history)
    
    # 添加用户消息
    messages.append({"role": "user", "content": user_message})
    
    response = client.chat.completions.create(
        model="mistral-medium-latest",  # 使用 Medium 平衡成本
        messages=messages,
        temperature=0.7
    )
    
    return response.choices[0].message.content

# 使用示例
history = []
user_msg = "我想了解你们的退货政策"
reply = customer_service_bot(user_msg, history)
print(reply)
```

### 案例 2：文档分析助手

```python {filename="Python"}
def analyze_document(image_path):
    """分析文档图片并提取信息"""
    import base64
    
    with open(image_path, "rb") as f:
        image_data = base64.b64encode(f.read()).decode()
    
    response = client.chat.completions.create(
        model="pixtral-large-latest",
        messages=[
            {
                "role": "user",
                "content": [
                    {"type": "text", "text": "请分析这份文档，提取关键信息。"},
                    {
                        "type": "image_url",
                        "image_url": {"url": f"data:image/jpeg;base64,{image_data}"}
                    }
                ]
            }
        ]
    )
    
    return response.choices[0].message.content

# 使用示例
result = analyze_document("invoice.jpg")
print(result)
```

### 案例 3：代码审查助手

```python {filename="Python"}
def code_review(code):
    """代码审查和优化建议"""
    response = client.chat.completions.create(
        model="mistral-large-latest",  # Large 模型更擅长代码
        messages=[
            {
                "role": "system",
                "content": "你是一个资深的代码审查专家，提供建设性的反馈。"
            },
            {
                "role": "user",
                "content": f"请审查以下代码并提供优化建议：\n\n```python\n{code}\n```"
            }
        ],
        temperature=0.3  # 低温度保证精确
    )
    
    return response.choices[0].message.content

# 使用示例
code = """
def calculate(a, b):
    return a + b
"""
review = code_review(code)
print(review)
```

---

## 🔧 常见问题

**Q: Mistral API 有免费额度吗？**  
A: 有。Mistral 提供 **Experiment 免费试用计划**，仅需手机验证即可使用（无需信用卡）。Experiment 计划适合实验和原型开发，有速率限制。如需更高配额可升级到 Scale 按需付费计划。详见 [官方定价页面](https://mistral.ai/pricing)。

**Q: 如何从 OpenAI API 迁移到 Mistral API？**  
A: 只需修改 `base_url` 和 `api_key`，代码其他部分无需改动：
```python
# 原 OpenAI
client = OpenAI(api_key="sk-...")

# 改为 Mistral
client = OpenAI(
    api_key="YOUR_MISTRAL_KEY",
    base_url="https://api.mistral.ai/v1"
)
```

**Q: 开源模型如何使用？**  
A: Mistral 的开源模型可以：
1. 通过 API 使用（付费）
2. 从 Hugging Face 下载本地部署（免费）
3. 在云平台部署（根据云平台收费）

**Q: Mistral API 支持函数调用吗？**  
A: 是的，Mistral API 支持函数调用（Function Calling），用法与 OpenAI 类似。详见 [官方文档](https://docs.mistral.ai)。

**Q: 如何在多云平台使用 Mistral？**  
A: Mistral 支持多云部署：
- **AWS:** 通过 Sagemaker
- **Azure:** 通过 Azure AI Foundry
- **Google Cloud:** 通过 Vertex AI
详见各平台文档。

---

## 🔗 相关资源

- **API 端点：** `https://api.mistral.ai/v1`
- **开发者控制台：** [https://console.mistral.ai](https://console.mistral.ai)
- **API 文档：** [https://docs.mistral.ai](https://docs.mistral.ai)
- **提供者主页：** [Mistral AI 完整介绍](/providers/mistral)
- **对应的 Chatbot 服务：** [Le Chat 使用指南](/services/chatbot/mistral)
- **SDK 仓库：** [https://github.com/mistralai/client-python](https://github.com/mistralai/client-python)
- **定价说明：** [https://mistral.ai/pricing](https://mistral.ai/pricing)

---

## 📝 更新日志

- **2025 年 1 月：** 更新价格和速率限制
- **2024 年 11 月：** 发布 Pixtral Large 多模态 API
- **2024 年 7 月：** 发布 Mistral Large 2
- **2024 年 5 月：** 支持函数调用功能
- **2024 年 3 月：** 推出 Mistral Medium
- **2023 年 12 月：** 发布 Mixtral 8x7B API
- **2023 年 9 月：** Mistral API 正式发布

---

**服务提供者：** [Mistral AI](/providers/mistral)
