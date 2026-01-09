---
title: "OpenAI API - 行业标准 AI API 服务"
linkTitle: "API - OpenAI"
description: "OpenAI API 提供行业标准的 AI 接口服务，支持 GPT-4o、GPT-4o-mini 等顶尖模型。新用户赠送 $18 试用额度（3个月有效），完整的多模态支持，生态完善。"
keywords:
  - OpenAI API
  - GPT-4 API
  - GPT-4o API
  - ChatGPT API
  - OpenAI 免费额度
  - AI API 服务
  - 免费 GPT API
  - OpenAI 试用
image: /images/logo.svg
type: docs
weight: 1
comments: true
prev: /services/api
next: /services/api/google-ai-studio
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [OpenAI](/providers/openai)  
**服务类型：** API 服务  
**API 端点：** [https://api.openai.com/v1](https://api.openai.com/v1)  
**免费类型：** 试用积分（$18，3个月有效）  
**API 兼容性：** OpenAI 标准格式（行业标准）

---

## 🎯 服务简介

OpenAI API 是业界最完善的 AI API 服务，提供 GPT-4o、GPT-4o-mini、o1 等多个顶尖模型。新用户注册即可获得 $18 试用额度，支持文本生成、图像理解、语音识别等多模态功能。

**核心优势：**
- 🏆 **行业标准** - OpenAI API 格式是事实上的行业标准
- 💰 **试用政策** - 新用户可能获得试用额度（政策会调整）
- 🤖 **顶尖模型** - GPT-4o 等最强 AI 模型
- 🌐 **多模态** - 文本、图像、语音全面支持
- 🔌 **生态完善** - 大量第三方工具和集成
- 📚 **文档齐全** - 详细的官方文档和社区支持
- ⚡ **性能可靠** - 企业级稳定性和速度

> **更新说明：** 试用额度政策会随时间调整，请访问 [OpenAI Platform](https://platform.openai.com) 查看最新信息。

---

## 🚀 快速开始

### 前提条件

**必需：**
- ✅ 已注册 OpenAI 账户
- ✅ 已验证手机号
- ✅ 已创建 API 密钥
- ⚠️ 可访问的网络环境（中国大陆需科学上网）

详细步骤请参考：[OpenAI 注册指南](/providers/openai#注册和账号)

### 获取 API 密钥

{{% steps %}}

##### 登录开发者平台

1. 访问 [https://platform.openai.com](https://platform.openai.com)
2. 使用您的 OpenAI 账户登录

##### 创建 API 密钥

1. 点击左侧菜单的"API keys"
2. 点击"Create new secret key"
3. 输入密钥名称（可选）
4. 点击"Create secret key"

##### 保存密钥

1. **立即复制并保存**密钥（只显示一次）
2. 将密钥保存到安全的地方
3. ⚠️ **重要：** 不要分享或公开您的 API 密钥

##### 设置使用限额（可选）

1. 在"Usage"页面设置每月支出限额
2. 避免意外超支
3. 试用期建议设置 $20 限额

{{% /steps %}}

### 5 分钟快速示例

**使用 OpenAI Python SDK（推荐）**

```python {filename="Python"}
from openai import OpenAI

# 初始化客户端
client = OpenAI(
    api_key="YOUR_API_KEY"  # 替换为您的 API 密钥
)

# 发送请求
response = client.chat.completions.create(
    model="gpt-4o-mini",  # 使用经济实惠的模型
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "什么是机器学习？"}
    ]
)

# 打印响应
print(response.choices[0].message.content)

# 查看使用情况
print(f"\n使用 Tokens: {response.usage.total_tokens}")
```

---

## 🤖 可用模型

### 文本生成模型

| 模型 ID | 上下文 | 输入价格 | 输出价格 | 特点 | 适用场景 |
|---------|--------|---------|---------|------|---------|
| **gpt-4o** | 128K | $2.5/1M | $10/1M | 最强综合能力 | 复杂任务 |
| **gpt-4o-mini** | 128K | $0.15/1M | $0.6/1M | 🏆 高性价比 | 日常使用 |
| **gpt-3.5-turbo** | 16K | $0.5/1M | $1.5/1M | 快速经济 | 简单任务 |
| **o1-preview** | 128K | $15/1M | $60/1M | 推理能力强 | 数学、逻辑 |
| **o1-mini** | 128K | $3/1M | $12/1M | 代码推理 | 编程任务 |

### 模型详细说明

#### GPT-4o（推荐复杂任务）
- **上下文窗口：** 128K tokens
- **主要用途：** 复杂任务、创意写作、深度分析
- **优势：** 最强的综合能力，多模态支持
- **价格：** 输入 $2.5/1M, 输出 $10/1M

#### GPT-4o-mini（🏆 最推荐）
- **上下文窗口：** 128K tokens
- **主要用途：** 日常对话、代码生成、文本处理
- **优势：** 性价比极高，速度快，质量优秀
- **价格：** 输入 $0.15/1M, 输出 $0.6/1M

#### GPT-3.5-turbo
- **上下文窗口：** 16K tokens
- **主要用途：** 简单对话、快速响应
- **优势：** 便宜且快速
- **价格：** 输入 $0.5/1M, 输出 $1.5/1M

#### o1-preview / o1-mini（推理模型）
- **上下文窗口：** 128K tokens
- **主要用途：** 数学、逻辑推理、复杂问题
- **优势：** 推理能力强，适合需要深度思考的任务
- **价格：** o1-preview: $15/1M (输入), $60/1M (输出)

### 其他模型

**图像生成：**
- DALL·E 3：$0.040 - $0.120/图片（根据质量和尺寸）

**语音识别：**
- Whisper：$0.006/分钟

**文本转语音：**
- TTS：$15/1M 字符（标准）, $30/1M 字符（HD）

**嵌入模型：**
- text-embedding-3-small：$0.02/1M tokens
- text-embedding-3-large：$0.13/1M tokens

---

## 🔢 配额和限制

### 免费试用积分

| 项目 | 详情 |
|------|------|
| **试用政策** | 新用户可能获得试用额度（金额和条件因时期而异）|
| **历史额度** | 历史上曾有 $5-$18 等不同额度 |
| **获取方式** | 注册并验证后，查看 Billing 页面 |
| **使用范围** | 所有 API 服务 |

**注：** 试用额度政策会随时间调整，并非所有新用户都保证获得。请以官方 Billing 页面显示为准。

### 免费层级速率限制

| 限制项 | 说明 |
|--------|------|
| **速率限制** | 根据账户等级（Tier）动态设置 |
| **免费层示例** | 通常为较低的 RPM/TPM/RPD 限制 |
| **查看方式** | 登录 Platform → Account → Limits 页面 |
| **提升方法** | 充值并使用一段时间后自动升级 Tier |

**重要：** 具体速率限制因账户 Tier、模型和组织设置而异。请查看 [Rate Limits 文档](https://platform.openai.com/docs/guides/rate-limits) 和您的账户 Limits 页面获取准确信息。

### 付费后速率限制（Tier 1）

充值至少 $5 后，自动升级到 Tier 1：

| 限制项 | GPT-4o | GPT-4o-mini | GPT-3.5-turbo |
|--------|--------|-------------|---------------|
| **RPM** | 500 | 500 | 3,500 |
| **RPD** | - | - | 10,000 |
| **TPM** | 30,000 | 200,000 | 60,000 |

### ⚠️ 重要限制

1. **试用额度过期：** 3 个月后未使用的额度自动失效
2. **免费层限制低：** 仅 3 RPM，适合测试，不适合生产
3. **需要充值升级：** 生产环境建议充值到 Tier 1 或更高
4. **访问限制：** 中国大陆需要科学上网

---

## 💰 价格说明

### 试用政策

- **试用额度：** 新用户可能获得试用额度（金额因时期而异）
- **获取方式：** 注册并验证后查看 Billing 页面
- **使用建议：** 用于测试和小规模应用
- **注意：** 政策会调整，请以官方为准

### 充值后定价

**推荐模型定价：**

| 模型 | 输入 | 输出 | 1000 次对话成本* |
|------|------|------|-----------------|
| gpt-4o-mini | $0.15/1M | $0.6/1M | ~$0.15-0.30 |
| gpt-4o | $2.5/1M | $10/1M | ~$2.50-5.00 |
| o1-mini | $3/1M | $12/1M | ~$3.00-6.00 |

**\*假设平均每次对话 200 tokens 输入 + 200 tokens 输出**

**注：** 价格可能随时调整，最新价格请参考 [OpenAI Pricing](https://openai.com/api/pricing) 官方页面。

### 成本优化建议

1. **优先使用 gpt-4o-mini**
   - 性价比最高
   - 质量足够好
   - 速度快

2. **合理选择模型**
   - 简单任务用 gpt-3.5-turbo
   - 复杂任务才用 gpt-4o
   - 推理任务用 o1 系列

3. **优化 Token 使用**
   - 精简 system prompt
   - 避免重复上下文
   - 使用流式输出提升体验

---

## 💻 代码示例

### 1. 基础对话

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(api_key="YOUR_API_KEY")

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "你是一个专业的AI助手。"},
        {"role": "user", "content": "解释一下什么是深度学习"}
    ],
    max_tokens=500,
    temperature=0.7
)

print(response.choices[0].message.content)
```

### 2. 流式输出

```python {filename="Python"}
# 流式输出（实时显示）
stream = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "user", "content": "写一篇关于人工智能的文章"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

### 3. 图像理解（Vision）

```python {filename="Python"}
# 分析图片
response = client.chat.completions.create(
    model="gpt-4o",  # Vision 需要 gpt-4o
    messages=[
        {
            "role": "user",
            "content": [
                {"type": "text", "text": "这张图片里有什么？"},
                {
                    "type": "image_url",
                    "image_url": {
                        "url": "https://example.com/image.jpg"
                    }
                }
            ]
        }
    ]
)

print(response.choices[0].message.content)
```

### 4. 多轮对话

```python {filename="Python"}
# 保持对话历史
messages = [
    {"role": "system", "content": "你是一个Python编程助手"}
]

# 第一轮
messages.append({"role": "user", "content": "如何读取CSV文件？"})
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=messages
)
messages.append({"role": "assistant", "content": response.choices[0].message.content})

# 第二轮（带上下文）
messages.append({"role": "user", "content": "如何过滤数据？"})
response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=messages
)

print(response.choices[0].message.content)
```

### 5. Function Calling（函数调用）

```python {filename="Python"}
# 定义函数
tools = [
    {
        "type": "function",
        "function": {
            "name": "get_weather",
            "description": "获取指定城市的天气",
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
        }
    }
]

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "user", "content": "北京今天天气怎么样？"}
    ],
    tools=tools
)

# 检查是否需要调用函数
if response.choices[0].message.tool_calls:
    tool_call = response.choices[0].message.tool_calls[0]
    print(f"需要调用函数: {tool_call.function.name}")
    print(f"参数: {tool_call.function.arguments}")
```

### 6. cURL 示例

```bash {filename="Bash"}
curl https://api.openai.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "gpt-4o-mini",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "你好，介绍一下你自己"
      }
    ],
    "max_tokens": 500,
    "temperature": 0.7
  }'
```

### 7. Node.js 示例

```javascript {filename="JavaScript"}
import OpenAI from 'openai';

const client = new OpenAI({
  apiKey: process.env.OPENAI_API_KEY,
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'gpt-4o-mini',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: '什么是机器学习？' }
    ],
    max_tokens: 500,
    temperature: 0.7,
  });

  console.log(completion.choices[0].message.content);
  console.log(`\n使用 Tokens: ${completion.usage.total_tokens}`);
}

main();
```

---

## 🌟 核心优势

### 技术优势

1. **行业标准接口**
   - OpenAI API 格式是事实上的行业标准
   - 大量工具和库支持
   - 易于迁移和集成
   - 社区资源丰富

2. **模型质量顶尖**
   - GPT-4o 代表最高水平
   - 自然语言理解和生成出色
   - 多模态能力完整
   - 持续更新改进

3. **生态完善**
   - 官方 SDK（Python、Node.js等）
   - 第三方库和框架（LangChain、LlamaIndex等）
   - 大量教程和文档
   - 活跃的开发者社区

4. **企业级可靠**
   - 高可用性（99.9% SLA）
   - 稳定的性能
   - 完善的监控和日志
   - 专业的技术支持

### 与其他 API 对比

| 特性 | OpenAI | Google AI Studio | DeepSeek |
|------|--------|------------------|----------|
| 免费额度 | $18/3个月 | ✅ 完全免费 | ¥5/7天 |
| 模型质量 | 🏆 顶尖 | 优秀 | 优秀 |
| 生态系统 | 🏆 最完善 | 良好 | 成长中 |
| 文档质量 | 🏆 最详细 | 良好 | 良好 |
| 社区支持 | 🏆 最活跃 | 良好 | 成长中 |
| 价格 | 中等 | 免费 | 🏆 最便宜 |
| 中国访问 | ❌ 需科学上网 | ❌ 需科学上网 | ✅ 直接 |

---

## 💡 实用建议

### ✅ 推荐做法

1. **安全管理 API 密钥**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('OPENAI_API_KEY')
   
   client = OpenAI(api_key=api_key)
   ```

2. **错误处理和重试**
   ```python
   import time
   from openai import OpenAI, APIError, RateLimitError
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="gpt-4o-mini",
                   messages=messages
               )
           except RateLimitError:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"速率限制，等待 {wait_time} 秒...")
                   time.sleep(wait_time)
               else:
                   raise
           except APIError as e:
               print(f"API 错误: {e}")
               if i == max_retries - 1:
                   raise
       return None
   ```

3. **监控使用情况**
   ```python
   # 记录每次调用的 token 使用
   def track_usage(response):
       usage = response.usage
       print(f"输入 tokens: {usage.prompt_tokens}")
       print(f"输出 tokens: {usage.completion_tokens}")
       print(f"总计 tokens: {usage.total_tokens}")
       print(f"预估费用: ${usage.total_tokens * 0.0000015:.6f}")
   
   response = client.chat.completions.create(...)
   track_usage(response)
   ```

4. **优化 Token 使用**
   ```python
   # 精简 system prompt
   system_prompt = "你是AI助手"  # 简洁版
   
   # 而不是
   system_prompt = "你是一个非常有帮助的AI助手，总是提供详细和准确的回答..."  # 啰嗦版
   
   # 使用 max_tokens 限制输出
   response = client.chat.completions.create(
       model="gpt-4o-mini",
       messages=[...],
       max_tokens=200  # 限制输出长度
   )
   ```

5. **设置使用限额**
   - 在控制台设置每月支出限额
   - 避免意外超支
   - 建议初期设置较低限额

### 🎯 最佳实践

**选择合适的模型：**
```python
def select_model(task_complexity):
    if task_complexity == "simple":
        return "gpt-3.5-turbo"  # 快速且便宜
    elif task_complexity == "medium":
        return "gpt-4o-mini"  # 最推荐
    elif task_complexity == "complex":
        return "gpt-4o"  # 最强大
    elif task_complexity == "reasoning":
        return "o1-mini"  # 推理任务
```

**批量处理：**
```python
# 使用 Batch API 降低成本（50% 折扣）
# 适合非实时任务
```

**缓存结果：**
```python
import hashlib
import json

cache = {}

def cached_completion(messages):
    key = hashlib.md5(json.dumps(messages).encode()).hexdigest()
    
    if key in cache:
        return cache[key]
    
    response = client.chat.completions.create(
        model="gpt-4o-mini",
        messages=messages
    )
    
    cache[key] = response
    return response
```

### ⚠️ 注意事项

1. **密钥安全**
   - 永远不要硬编码 API 密钥
   - 使用环境变量或密钥管理服务
   - 定期轮换密钥
   - 为不同项目使用不同密钥

2. **速率限制**
   - 免费层只有 3 RPM，非常低
   - 建议充值到 Tier 1（$5）
   - 使用指数退避处理速率限制
   - 考虑使用队列系统

3. **成本控制**
   - 设置使用限额
   - 监控 API 调用
   - 优先使用 gpt-4o-mini
   - 避免过长的上下文

4. **错误处理**
   - 处理网络错误
   - 处理速率限制
   - 处理超时
   - 记录错误日志

5. **合规使用**
   - 遵守使用政策
   - 不生成有害内容
   - 尊重版权
   - 保护用户隐私

---

## 🔧 常见问题

### 1. 如何获取免费的 $18 额度？

**步骤：**
1. 注册 OpenAI 账户
2. 验证邮箱
3. 验证手机号（支持中国 +86）
4. 访问 [platform.openai.com](https://platform.openai.com)
5. 创建 API 密钥
6. 额度自动添加到账户

### 2. 试用额度用完了怎么办？

**解决方法：**
- 绑定支付方式（信用卡或借记卡）
- 充值继续使用
- 最低充值 $5
- 按实际使用量付费

### 3. 中国大陆如何使用？

**解决方法：**
- 需要稳定的科学上网工具
- 使用海外手机号验证（或中国 +86）
- API 访问需要稳定网络
- 建议使用香港/美国等地区的服务器

### 4. 如何监控使用情况？

**方法：**
- 登录 [platform.openai.com](https://platform.openai.com)
- 访问"Usage"页面
- 查看详细的使用统计
- 可以按日期、模型、项目查看

### 5. 速率限制太低怎么办？

**解决方法：**
- 充值至少 $5 升级到 Tier 1
- Tier 1: 500 RPM (gpt-4o-mini)
- 继续使用会自动升级到更高层级
- 企业用户可联系申请更高配额

### 6. 为什么 API 调用失败？

**常见原因：**
1. API 密钥错误或已撤销
2. 达到速率限制
3. 余额不足
4. 网络问题
5. 请求格式错误

**解决方法：**
- 检查 API 密钥是否正确
- 查看错误信息
- 检查余额和限额
- 查看官方状态页面
- 参考官方文档

---

## 🎯 实战案例

### 案例 1：智能客服机器人

```python {filename="Python"}
def customer_service_bot(user_message, chat_history=[]):
    """智能客服示例"""
    
    messages = [
        {
            "role": "system",
            "content": """你是一个专业的客服助手。
            - 礼貌友好
            - 提供准确信息
            - 如不确定，建议联系人工客服"""
        }
    ]
    
    # 添加对话历史
    messages.extend(chat_history)
    
    # 添加用户消息
    messages.append({"role": "user", "content": user_message})
    
    # 调用 API
    response = client.chat.completions.create(
        model="gpt-4o-mini",
        messages=messages,
        temperature=0.7
    )
    
    return response.choices[0].message.content

# 使用示例
answer = customer_service_bot("我的订单什么时候发货？")
print(answer)
```

### 案例 2：文档分析助手

```python {filename="Python"}
def document_analyzer(document_text):
    """文档分析和总结"""
    
    response = client.chat.completions.create(
        model="gpt-4o",  # 复杂任务用 GPT-4o
        messages=[
            {
                "role": "system",
                "content": "你是一个文档分析专家，擅长提取关键信息。"
            },
            {
                "role": "user",
                "content": f"""请分析以下文档并提供：
                1. 主要内容概述（3-5句话）
                2. 关键要点（列表形式）
                3. 重要数据和日期
                4. 建议的后续行动
                
                文档内容：
                {document_text}"""
            }
        ],
        temperature=0.3  # 较低温度，更准确
    )
    
    return response.choices[0].message.content
```

### 案例 3：代码审查助手

```python {filename="Python"}
def code_reviewer(code, language="python"):
    """代码审查和优化建议"""
    
    response = client.chat.completions.create(
        model="o1-mini",  # 代码任务用 o1-mini
        messages=[
            {
                "role": "user",
                "content": f"""请审查以下{language}代码：

                {code}

                提供：
                1. 潜在问题和bug
                2. 性能优化建议
                3. 代码风格改进
                4. 安全性建议
                5. 重构后的代码"""
            }
        ]
    )
    
    return response.choices[0].message.content
```

### 案例 4：内容生成器

```python {filename="Python"}
def content_generator(topic, style="professional", length="medium"):
    """内容生成"""
    
    length_map = {
        "short": "300-500字",
        "medium": "800-1000字",
        "long": "1500-2000字"
    }
    
    response = client.chat.completions.create(
        model="gpt-4o",
        messages=[
            {
                "role": "system",
                "content": f"你是一个{style}风格的内容创作者。"
            },
            {
                "role": "user",
                "content": f"""请写一篇关于"{topic}"的文章：
                - 风格：{style}
                - 长度：{length_map[length]}
                - 包含引言、正文、结论
                - 使用小标题组织内容"""
            }
        ],
        temperature=0.8  # 较高温度，更有创意
    )
    
    return response.choices[0].message.content
```

---

## 📚 相关资源

### 官方文档
- [OpenAI 完整介绍](/providers/openai)
- [ChatGPT 使用指南](/services/chatbot/openai)
- [API 官方文档](https://platform.openai.com/docs)
- [API 参考](https://platform.openai.com/docs/api-reference)

### 开发工具
- [Python SDK](https://github.com/openai/openai-python)
- [Node.js SDK](https://github.com/openai/openai-node)
- [OpenAI Cookbook](https://github.com/openai/openai-cookbook)
- [Postman Collection](https://www.postman.com/devrel/workspace/openai/overview)

### 社区资源
- [官方社区](https://community.openai.com)
- [GitHub Discussions](https://github.com/openai/openai-python/discussions)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/openai)

---

**服务提供者：** [OpenAI](/providers/openai)

