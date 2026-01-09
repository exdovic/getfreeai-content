---
title: "Anthropic API - Claude 安全可靠的 AI API 接口服务"
linkTitle: "API - Anthropic"
description: "Anthropic API 提供 Claude 模型的开发者接口，支持 200K 超长上下文、强大推理能力。预付费模式，最低充值 $5，Claude 3.5 Sonnet 输入 $3/M、输出 $15/M，AI 安全优先，适合企业应用。"
keywords:
  - Anthropic API
  - Claude API
  - 免费 AI API
  - Claude 开发接口
  - 200K 上下文
  - AI API
  - Claude Sonnet API
  - 安全 AI API
image: /images/logo.svg
type: docs
weight: 20
comments: true
prev: /services/api/vertex-ai
next: /services/api
sidebar:
  open: true
---

## 📋 服务概览

**服务名称：** Anthropic API  
**所属提供者：** [Anthropic](/providers/anthropic)  
**API 端点：** `https://api.anthropic.com/v1`  
**服务类型：** 预付费（最低充值 $5）  
**注册要求：** 需要注册账户并购买使用额度

---

## ✅ 服务说明

Anthropic API 是 Anthropic 提供的开发者 API 接口服务，允许开发者将 Claude 模型集成到自己的应用程序中。API 采用预付费模式，支持多种 Claude 模型，以强大的推理能力、超长上下文和 AI 安全性著称。

### 主要特点

- **超长上下文：** 支持最高 200K tokens 的上下文窗口
- **强大推理：** 在复杂推理、代码生成、逻辑分析等任务上表现出色
- **AI 安全：** 专注于提供安全可靠的 AI 服务，减少有害内容生成
- **灵活定价：** 按使用量付费，不同模型不同价格

---

## 🎁 可用模型

### 免费/试用模型列表

| 模型名称 | 上下文长度 | 输入价格 | 输出价格 | 特点 | 适用场景 |
|---------|-----------|---------|---------|------|---------|
| **claude-3-5-sonnet-20241022** | 200K | $3/M | $15/M | 最新最强，性能优异 | 通用任务、复杂推理 |
| **claude-3-opus-20240229** | 200K | $15/M | $75/M | 最高性能和智能 | 复杂任务、深度分析 |
| **claude-3-haiku-20240307** | 200K | $0.25/M | $1.25/M | 快速响应，高性价比 | 简单任务、高频调用 |

**注：** 需要预先购买使用额度，最低充值 $5。科研人员可申请 [AI 科学计划](https://www.anthropic.com/ai-for-science) 获得免费额度。

### 模型详细说明

#### Claude 3.5 Sonnet（推荐）
- **上下文窗口：** 200,000 tokens
- **主要用途：** 通用对话、复杂推理、代码生成
- **优势：** 性能与成本的最佳平衡，在多项基准测试中表现出色
- **更新：** 2024年10月发布，相比前代性能显著提升

#### Claude 3 Opus
- **上下文窗口：** 200,000 tokens
- **主要用途：** 最复杂的任务、深度分析、高精度要求
- **优势：** Claude 3 系列中性能最强，智能水平最高
- **适合：** 对准确性和智能要求极高的场景

#### Claude 3 Haiku
- **上下文窗口：** 200,000 tokens
- **主要用途：** 日常对话、简单任务、高频调用
- **优势：** 响应速度快，价格最低，性价比高
- **适合：** 成本敏感的大规模部署

---

## 🔢 配额和限制

### 预付费模式

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **最低充值** | $5 | 首次购买最低金额 |
| **额度有效期** | 1 年 | 购买日期起 1 年后过期 |
| **最大上下文长度** | 200K tokens | 所有 Claude 3 系列模型 |
| **速率限制** | 根据账户等级 | 新账户有限制，随使用增加 |
| **并发请求** | 根据账户等级 | 付费用户有更高并发 |

### ⚠️ 重要限制

1. **预付费要求：** 必须先购买使用额度才能调用 API，不提供免费试用额度
2. **额度过期：** 购买的额度在 1 年后过期，且不可退款
3. **速率限制：** 新账户有较严格的速率限制，随着使用量增加会逐步提升
4. **区域限制：** 某些地区可能无法直接访问 API

### 速率限制示例

| 账户等级 | RPM | TPM | 说明 |
|---------|-----|-----|------|
| **新账户** | 5 | 20K | 初始限制较低 |
| **标准账户** | 50 | 100K | 使用一段时间后提升 |
| **高级账户** | 可协商 | 可协商 | 企业用户可联系销售 |

**注：** RPM = Requests Per Minute（每分钟请求数），TPM = Tokens Per Minute（每分钟 Token 数）

---

## 💰 价格说明

### 定价表

| 模型 | 输入价格 | 输出价格 | 说明 |
|------|---------|---------|------|
| **Claude 3.5 Sonnet** | $3/M tokens | $15/M tokens | 推荐首选 |
| **Claude 3 Opus** | $15/M tokens | $75/M tokens | 最高性能 |
| **Claude 3 Haiku** | $0.25/M tokens | $1.25/M tokens | 高性价比 |

### 成本估算示例

**示例 1：简单对话**
- 输入：1,000 tokens（约 750 字）
- 输出：500 tokens（约 375 字）
- 使用模型：Claude 3.5 Sonnet
- 成本：(1,000 × $3 + 500 × $15) / 1,000,000 = **$0.0105**

**示例 2：长文档分析**
- 输入：50,000 tokens（约 37,500 字）
- 输出：2,000 tokens（约 1,500 字）
- 使用模型：Claude 3.5 Sonnet
- 成本：(50,000 × $3 + 2,000 × $15) / 1,000,000 = **$0.18**

**示例 3：高频简单任务**
- 每次输入：500 tokens
- 每次输出：200 tokens
- 每天调用：1,000 次
- 使用模型：Claude 3 Haiku
- 每日成本：(500 × 1,000 × $0.25 + 200 × 1,000 × $1.25) / 1,000,000 = **$0.375**

---

## 🚀 如何使用

### 前提条件

**1. 注册账户**

请先 [注册账户](/providers/anthropic#注册和账号)：
- 访问 [https://console.anthropic.com](https://console.anthropic.com)
- 使用 Google 账户或邮箱注册
- 验证邮箱

**2. 购买使用额度**

{{% steps %}}

##### 登录控制台

访问 [https://console.anthropic.com](https://console.anthropic.com) 并登录

##### 进入 Billing 页面

点击左侧菜单的"Billing"或"账单"

##### 购买额度

1. 点击"Purchase Credits"或"购买额度"
2. 输入充值金额（最低 $5）
3. 输入信用卡信息
4. 确认购买

##### 创建 API 密钥

1. 点击左侧菜单的"API Keys"
2. 点击"Create Key"创建新密钥
3. 为密钥命名（例如：my-app-key）
4. **重要：** 复制并安全保存您的 API 密钥

{{% /steps %}}

---

## 💻 代码示例

### Python 示例

**安装依赖：**

```bash {filename="Bash"}
pip install anthropic
```

**基本使用：**

```python {filename="Python"}
import anthropic

# 初始化客户端（请替换为您的 API 密钥）
client = anthropic.Anthropic(
    api_key="your-api-key-here"
)

# 发送请求
response = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=1024,
    messages=[
        {
            "role": "user",
            "content": "你好，请介绍一下 Claude API 的主要特点。"
        }
    ]
)

# 打印响应
print(response.content[0].text)

# 查看 Token 使用情况
print(f"\n输入 Tokens: {response.usage.input_tokens}")
print(f"输出 Tokens: {response.usage.output_tokens}")
```

**使用系统提示词：**

```python {filename="Python"}
response = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=2048,
    system="你是一个专业的 Python 编程助手，擅长代码优化和最佳实践。",
    messages=[
        {
            "role": "user",
            "content": "请帮我优化这段代码：\n\n```python\ndef find_max(arr):\n    max_val = arr[0]\n    for i in range(len(arr)):\n        if arr[i] > max_val:\n            max_val = arr[i]\n    return max_val\n```"
        }
    ]
)

print(response.content[0].text)
```

**流式输出示例：**

```python {filename="Python"}
# 流式输出（适合实时显示）
with client.messages.stream(
    model="claude-3-5-sonnet-20241022",
    max_tokens=1024,
    messages=[
        {
            "role": "user",
            "content": "写一首关于 AI 的诗"
        }
    ]
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)
```

---

### cURL 示例

**基本请求：**

```bash {filename="Bash"}
curl https://api.anthropic.com/v1/messages \
  -H "Content-Type: application/json" \
  -H "x-api-key: your-api-key-here" \
  -H "anthropic-version: 2023-06-01" \
  -d '{
    "model": "claude-3-5-sonnet-20241022",
    "max_tokens": 1024,
    "messages": [
      {
        "role": "user",
        "content": "你好，请介绍一下 Claude API。"
      }
    ]
  }'
```

**带系统提示词：**

```bash {filename="Bash"}
curl https://api.anthropic.com/v1/messages \
  -H "Content-Type: application/json" \
  -H "x-api-key: your-api-key-here" \
  -H "anthropic-version: 2023-06-01" \
  -d '{
    "model": "claude-3-5-sonnet-20241022",
    "max_tokens": 1024,
    "system": "你是一个专业的技术顾问。",
    "messages": [
      {
        "role": "user",
        "content": "什么是微服务架构？"
      }
    ]
  }'
```

---

### Node.js 示例

```javascript {filename="JavaScript"}
import Anthropic from '@anthropic-ai/sdk';

const client = new Anthropic({
  apiKey: 'your-api-key-here',
});

async function main() {
  const message = await client.messages.create({
    model: 'claude-3-5-sonnet-20241022',
    max_tokens: 1024,
    messages: [
      {
        role: 'user',
        content: '你好，请介绍一下 Claude API 的主要特点。'
      }
    ],
  });

  console.log(message.content[0].text);
  console.log(`\n输入 Tokens: ${message.usage.input_tokens}`);
  console.log(`输出 Tokens: ${message.usage.output_tokens}`);
}

main();
```

---

## 🌟 核心优势

### 技术优势

1. **超长上下文处理：**
   - 200K tokens 上下文窗口
   - 可以处理约 150,000 字的文本
   - 适合长文档分析和复杂对话
   - 支持完整代码库理解

2. **强大的推理能力：**
   - 复杂逻辑推理
   - 多步骤问题求解
   - 代码生成和分析
   - 数学和科学计算

3. **AI 安全保障：**
   - 减少有害内容生成
   - 降低虚假信息（幻觉）概率
   - 更加准确可靠的输出
   - 符合企业级安全要求

### 与其他 API 对比

| 特性 | Anthropic API | OpenAI API | DeepSeek API |
|------|--------------|-----------|-------------|
| 免费额度 | 需付费（最低$5）| $18/3个月 | ¥5/7天 |
| 上下文长度 | 🏆 200K | 128K | 128K |
| 推理能力 | 🏆 极强 | 极强 | 强 |
| AI 安全 | 🏆 行业领先 | 优秀 | 良好 |
| 价格（标准模型）| $3-15/M | $2.5-10/M | $0.28-0.42/M |
| 需要信用卡 | ✅ | ✅ | ⚠️ 充值方式多样 |

---

## 💡 实用建议

### ✅ 推荐做法

1. **选择合适的模型：**
   - 简单任务使用 Haiku（成本低）
   - 通用任务使用 3.5 Sonnet（平衡性能和成本）
   - 复杂任务使用 Opus（性能最强）

2. **优化 Token 使用：**
   - 精简输入文本，去除冗余信息
   - 使用清晰简洁的提示词
   - 设置合理的 max_tokens 限制
   - 利用系统提示词提供持久性指令

3. **充分利用长上下文：**
   ```python
   # 一次性传入完整文档
   with open("long_document.txt", "r") as f:
       document = f.read()
   
   response = client.messages.create(
       model="claude-3-5-sonnet-20241022",
       max_tokens=2048,
       messages=[
           {
               "role": "user",
               "content": f"请分析以下文档:\n\n{document}\n\n总结主要观点。"
           }
       ]
   )
   ```

### 🎯 最佳实践

**错误处理和重试：**

```python {filename="Python"}
import time
from anthropic import Anthropic, APIError, RateLimitError

client = Anthropic(api_key="your-api-key-here")

def call_api_with_retry(messages, max_retries=3):
    """带重试机制的 API 调用"""
    for attempt in range(max_retries):
        try:
            response = client.messages.create(
                model="claude-3-5-sonnet-20241022",
                max_tokens=1024,
                messages=messages
            )
            return response
        except RateLimitError:
            wait_time = 2 ** attempt
            print(f"达到速率限制，等待 {wait_time} 秒后重试...")
            time.sleep(wait_time)
        except APIError as e:
            print(f"API 错误: {e}")
            if attempt == max_retries - 1:
                raise
    
    return None

# 使用示例
messages = [{"role": "user", "content": "你好"}]
response = call_api_with_retry(messages)
if response:
    print(response.content[0].text)
```

**成本监控：**

```python {filename="Python"}
def calculate_cost(input_tokens, output_tokens, model="claude-3-5-sonnet"):
    """计算 API 调用成本"""
    pricing = {
        "claude-3-5-sonnet": {"input": 3, "output": 15},
        "claude-3-opus": {"input": 15, "output": 75},
        "claude-3-haiku": {"input": 0.25, "output": 1.25}
    }
    
    price = pricing.get(model, pricing["claude-3-5-sonnet"])
    cost = (input_tokens * price["input"] + output_tokens * price["output"]) / 1_000_000
    
    return cost

# 使用示例
response = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    max_tokens=1024,
    messages=[{"role": "user", "content": "你好"}]
)

cost = calculate_cost(
    response.usage.input_tokens,
    response.usage.output_tokens
)
print(f"本次调用成本: ${cost:.6f}")
```

### ⚠️ 注意事项

1. **API 密钥安全：** 不要将 API 密钥硬编码在代码中，使用环境变量
2. **速率限制：** 新账户有较严格限制，需要逐步建立使用历史
3. **成本控制：** 监控使用量，避免意外高额账单
4. **区域限制：** 某些地区可能需要特殊网络环境

---

## 🎯 实际应用案例

### 案例 1：长文档分析

**场景描述：** 分析长篇技术文档，提取关键信息

```python {filename="Python"}
def analyze_long_document(document_path):
    """分析长文档"""
    with open(document_path, 'r', encoding='utf-8') as f:
        document = f.read()
    
    client = Anthropic(api_key="your-api-key-here")
    
    response = client.messages.create(
        model="claude-3-5-sonnet-20241022",
        max_tokens=4096,
        system="你是一个专业的文档分析专家。",
        messages=[
            {
                "role": "user",
                "content": f"""请分析以下技术文档:

{document}

请提供:
1. 文档主要内容概述
2. 关键技术点
3. 重要结论和建议
4. 潜在问题和风险"""
            }
        ]
    )
    
    return response.content[0].text

# 使用示例
result = analyze_long_document("technical_spec.txt")
print(result)
```

### 案例 2：代码审查助手

**场景描述：** 自动审查代码，提供优化建议

```python {filename="Python"}
def code_review(code, language="python"):
    """代码审查助手"""
    client = Anthropic(api_key="your-api-key-here")
    
    response = client.messages.create(
        model="claude-3-5-sonnet-20241022",
        max_tokens=2048,
        system=f"你是一个资深的 {language} 开发专家，擅长代码审查和优化。",
        messages=[
            {
                "role": "user",
                "content": f"""请审查以下代码:

```{language}
{code}
```

请提供:
1. 代码质量评估
2. 潜在的 bug 或问题
3. 性能优化建议
4. 最佳实践建议
5. 安全性检查"""
            }
        ]
    )
    
    return response.content[0].text

# 使用示例
code = """
def process_data(data):
    result = []
    for item in data:
        if item > 0:
            result.append(item * 2)
    return result
"""

review = code_review(code)
print(review)
```

### 案例 3：智能客服

**场景描述：** 构建智能客服系统

```python {filename="Python"}
class CustomerServiceBot:
    def __init__(self, api_key, knowledge_base):
        self.client = Anthropic(api_key=api_key)
        self.knowledge_base = knowledge_base
        self.conversation_history = []
    
    def chat(self, user_message):
        """处理用户消息"""
        # 添加用户消息到历史
        self.conversation_history.append({
            "role": "user",
            "content": user_message
        })
        
        # 调用 API
        response = self.client.messages.create(
            model="claude-3-5-sonnet-20241022",
            max_tokens=1024,
            system=f"""你是一个专业的客服助手。

知识库:
{self.knowledge_base}

请根据知识库信息回答用户问题，保持礼貌和专业。""",
            messages=self.conversation_history
        )
        
        assistant_message = response.content[0].text
        
        # 添加助手回复到历史
        self.conversation_history.append({
            "role": "assistant",
            "content": assistant_message
        })
        
        return assistant_message

# 使用示例
knowledge = """
产品: 智能手表 X1
价格: $299
功能: 健康监测、运动追踪、消息通知
保修: 1年保修
退换货: 30天无理由退货
"""

bot = CustomerServiceBot("your-api-key-here", knowledge)
print(bot.chat("你们的智能手表有什么功能？"))
print(bot.chat("价格是多少？"))
```

---

## 🔧 常见问题

**Q: 如何获取 API 密钥？**  
A: 登录 [https://console.anthropic.com](https://console.anthropic.com)，在"API Keys"页面创建新密钥。

**Q: 最低充值金额是多少？**  
A: 最低充值金额为 $5，购买的额度有效期为 1 年。

**Q: 是否有免费试用额度？**  
A: 一般用户需要付费购买额度。但科研人员可以申请 [AI 科学计划](https://www.anthropic.com/ai-for-science) 获得免费额度（最高 $20,000）。

**Q: API 支持流式输出吗？**  
A: 是的，Anthropic API 支持流式输出（Server-Sent Events），适合实时显示生成内容。

**Q: 如何处理速率限制？**  
A: 实现指数退避重试机制，或者联系 Anthropic 申请提高速率限制。

**Q: API 与 OpenAI 兼容吗？**  
A: 不完全兼容，但 API 设计类似。需要使用 Anthropic 官方 SDK 或参考其 API 文档。

---

## 🔗 相关资源

- **API 端点：** `https://api.anthropic.com/v1`
- **开发者控制台：** [https://console.anthropic.com](https://console.anthropic.com)
- **API 文档：** [https://docs.anthropic.com](https://docs.anthropic.com)
- **定价信息：** [https://www.anthropic.com/pricing](https://www.anthropic.com/pricing)
- **提供者主页：** [Anthropic](/providers/anthropic)
- **对应的 Chatbot 服务：** [Claude Chatbot](/services/chatbot/anthropic)
- **Python SDK：** [https://github.com/anthropics/anthropic-sdk-python](https://github.com/anthropics/anthropic-sdk-python)
- **TypeScript SDK：** [https://github.com/anthropics/anthropic-sdk-typescript](https://github.com/anthropics/anthropic-sdk-typescript)
- **API 状态：** [https://status.anthropic.com](https://status.anthropic.com)

---

## 📝 更新日志

- **2024年10月：** 推出 Claude 3.5 Sonnet，性能大幅提升
- **2024年3月：** 发布 Claude 3 系列 API
- **2023年：** Claude 2 API 支持 100K 上下文
- **2022年：** Claude API 正式发布

---

**服务提供者：** [Anthropic](/providers/anthropic)
