---
title: "GitHub Models API - 免费 AI 模型 API 接口服务"
linkTitle: "API - GitHub Models"
description: "GitHub Models API 提供免费的 AI 模型 API 接口！兼容 OpenAI 规范，支持 GPT-4o、Llama 3.1、Phi-3、DeepSeek-R1 等 10+ 模型。每个模型有独立的免费配额。"
keywords:
  - GitHub Models API
  - GitHub API
  - 免费AI API
  - GPT-4o API
  - Llama 3.1 API
  - Phi-3 API
  - DeepSeek-R1 API
  - OpenAI兼容
  - 免费LLM API
  - GitHub开发者API
image: /images/logo.svg
type: docs
weight: 14
comments: true
prev: /services/api/cerebras
next: /services/chatbot
sidebar:
  open: true
---

## 📋 服务概览

**服务名称：** GitHub Models API  
**所属提供者：** [GitHub Models](/providers/github-models)  
**API 端点：** `https://models.github.ai/inference`  
**服务类型：** 免费使用（有速率限制）  
**注册要求：** 需要 GitHub 账户和 Personal Access Token

---

## ✅ 服务说明

GitHub Models API 是 GitHub 提供的开发者 API 接口，允许开发者通过编程方式调用多种主流 AI 模型。API 完全兼容 OpenAI 规范，可以使用 OpenAI SDK 直接调用。

### 主要特点

- **🔌 OpenAI 兼容** - 完全兼容 OpenAI API 规范，易于集成
- **🆓 完全免费** - 所有模型提供免费访问，有速率限制
- **🤖 多模型支持** - 支持 10+ 主流 AI 模型
- **🔒 安全可靠** - 基于 GitHub Personal Access Token 认证
- **🚀 易于使用** - 可使用 OpenAI SDK 或任何 HTTP 客户端
- **📚 完善文档** - 提供详细的官方文档和示例

---

## 🎁 可用模型

### 免费模型列表

| 模型名称 | 提供商 | 上下文长度 | 特点 | 适用场景 |
|---------|--------|-----------|------|---------|
| **gpt-4o** | OpenAI | 128K | 最强综合能力 | 复杂推理、创意写作 |
| **gpt-4o-mini** | OpenAI | 128K | 快速轻量 | 日常对话、高频调用 |
| **Llama-3.1-405B** | Meta | 128K | 超大开源模型 | 复杂任务 |
| **Llama-3.1-70B** | Meta | 128K | 平衡性能 | 通用任务 |
| **Llama-3.1-8B** | Meta | 128K | 快速响应 | 轻量应用 |
| **Phi-3.5-mini** | Microsoft | 128K | 小而精 | 效率优先 |
| **Phi-3-medium** | Microsoft | 128K | 平衡型 | 中等复杂度 |
| **DeepSeek-R1** | DeepSeek | 64K | 推理能力强 | 逻辑推理、中文 |
| **Mistral-Large** | Mistral | 128K | 欧洲领先 | 多语言任务 |
| **Mistral-Nemo** | Mistral | 128K | 轻量快速 | 实时应用 |
| **Command-R+** | Cohere | 128K | RAG 专家 | 知识检索 |

### 模型详细说明

#### GPT-4o（推荐）
- **上下文窗口：** 128K tokens
- **主要用途：** 复杂推理、创意写作、专业任务
- **优势：** 全球领先的 AI 能力，多模态支持
- **速率限制：** 10 RPM，50 RPD

#### Llama-3.1-405B
- **上下文窗口：** 128K tokens
- **主要用途：** 复杂推理、专业领域应用
- **优势：** 最强大的开源模型
- **速率限制：** 10 RPM，50 RPD

#### DeepSeek-R1
- **上下文窗口：** 64K tokens
- **主要用途：** 逻辑推理、中文任务
- **优势：** 中文优化，推理能力强
- **速率限制：** 15 RPM，150 RPD

---

## 🔢 配额和限制

### 免费层级限制

不同模型有不同的速率限制。以下是典型限制示例：

**High 级别模型（GPT-4o, Llama-3.1-405B）：**

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每分钟请求数** | 10 | RPM (Requests Per Minute) |
| **每天请求数** | 50 | RPD (Requests Per Day) |
| **每次最大输入 Token** | 8,000 | 单次请求输入上限 |
| **每次最大输出 Token** | 4,000 | 单次请求输出上限 |
| **最大并发请求** | 2 | 同时进行的请求数 |
| **需要信用卡** | ❌ | 完全免费 |

**Low 级别模型（Phi-3, Llama-3.1-8B, DeepSeek-R1）：**

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每分钟请求数** | 15 | RPM |
| **每天请求数** | 150 | RPD |
| **每次最大输入 Token** | 8,000 | 单次请求输入上限 |
| **每次最大输出 Token** | 4,000 | 单次请求输出上限 |
| **最大并发请求** | 5 | 同时进行的请求数 |
| **需要信用卡** | ❌ | 完全免费 |

### ⚠️ 重要限制

1. **速率限制：** 超出限制会返回 429 错误，建议实现指数退避重试机制。
2. **每日重置：** 每日配额在 UTC 0:00 重置。
3. **并发限制：** 超出最大并发数的请求会被拒绝。
4. **Token 限制：** 单次请求的输入和输出 Token 都有上限。
5. **配额示例：** 以上配额为参考示例，实际限制可能因模型和账户而异，请查看 [模型详情页](https://github.com/marketplace/models) 获取实时信息。

### 配额重置时间

- **每日配额：** UTC 0:00 重置
- **每分钟配额：** 滚动窗口，持续重置
- **并发限制：** 实时计算，请求完成后立即释放

---

## 💰 价格说明

### 免费配额

- **免费使用：** 所有模型完全免费
- **无需信用卡：** 不需要绑定信用卡
- **速率限制：** 每个模型有独立的速率限制
- **获取方式：** 注册 GitHub 账户并创建 PAT 即可

### 付费选项

目前 GitHub Models API 完全免费，暂无付费选项。如需更高配额，建议：
- 使用多个模型分散负载
- 优化请求频率
- 或考虑各模型提供商的官方 API

---

## 🚀 如何使用

### 前提条件

**1. 注册 GitHub 账户**

如果还没有 GitHub 账户，请先 [注册账户](/providers/github-models#注册账户)。

**2. 创建 Personal Access Token**

{{% steps %}}

##### 访问 GitHub Settings

1. 登录 GitHub
2. 点击右上角头像 > Settings
3. 左侧菜单选择 Developer settings

##### 创建 Token

1. 点击 Personal access tokens > Tokens (classic)
2. 点击"Generate new token" > "Generate new token (classic)"
3. 设置 Token 名称（例如：GitHub Models API）
4. 设置过期时间（建议选择合适的期限）

##### 选择权限范围

1. **重要：** 勾选 `models` 作用域
2. 这是使用 GitHub Models API 的必需权限
3. 不需要勾选其他权限

##### 生成并保存 Token

1. 点击页面底部的"Generate token"
2. **立即复制并安全保存** Token（只显示一次！）
3. 将 Token 保存到安全的地方（推荐使用密码管理器）

{{% /steps %}}

---

## 💻 代码示例

### Python 示例

**安装依赖：**

```bash {filename="Bash"}
pip install openai
```

**基本使用：**

```python {filename="Python"}
from openai import OpenAI

# 初始化客户端
client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key="YOUR_GITHUB_PAT"  # 替换为您的 GitHub Personal Access Token
)

# 发送请求
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "你好，请介绍一下 GitHub Models。"}
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

**流式输出示例：**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key="YOUR_GITHUB_PAT"
)

# 流式输出（适合实时显示）
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "user", "content": "写一首关于编程的诗"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)

print()  # 换行
```

---

### cURL 示例

**基本请求：**

```bash {filename="Bash"}
curl -X POST "https://models.github.ai/inference/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_GITHUB_PAT" \
  -d '{
    "model": "gpt-4o",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "你好，请介绍一下 GitHub Models。"
      }
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**流式输出：**

```bash {filename="Bash"}
curl -X POST "https://models.github.ai/inference/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_GITHUB_PAT" \
  -d '{
    "model": "gpt-4o",
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
  baseURL: 'https://models.github.ai/inference',
  apiKey: process.env.GITHUB_PAT,  // 使用环境变量
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'gpt-4o',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: '你好，请介绍一下 GitHub Models。' }
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

## 🌟 核心优势

### 技术优势

1. **OpenAI 兼容性：**
   - 完全兼容 OpenAI API 规范
   - 可直接使用 OpenAI SDK
   - 易于从其他平台迁移
   - 降低学习成本

2. **多模型访问：**
   - 一个 API 访问多家提供商的模型
   - 便于对比选择最佳模型
   - 不同模型有不同优势
   - 灵活切换满足不同需求

3. **GitHub 生态集成：**
   - 与 GitHub 深度集成
   - 可用于 GitHub Actions
   - 方便在开发流程中使用
   - 统一的身份认证

### 与其他 API 对比

| 特性 | GitHub Models | Google AI Studio | Groq |
|------|---------------|------------------|------|
| 免费配额 | 因模型而异 | 完全免费 | 约14,400次/天 |
| 模型数量 | 🏆 10+ 模型 | 5+ 模型 | 5+ 模型 |
| OpenAI 兼容 | ✅ 完全兼容 | ❌ 需适配 | ✅ 完全兼容 |
| 上下文长度 | 最高128K | 最高2M | 最高128K |
| GitHub 集成 | 🏆 深度集成 | ❌ 无 | ❌ 无 |
| 需要信用卡 | ❌ | ❌ | ⚠️ 部分需要 |

---

## 💡 实用建议

### ✅ 推荐做法

1. **安全管理 Token：**
   ```python
   import os
   from dotenv import load_dotenv
   
   # 使用环境变量
   load_dotenv()
   api_key = os.getenv('GITHUB_PAT')
   
   # 不要硬编码 Token
   # ❌ api_key = "github_pat_xxxx"  # 不要这样做！
   ```

2. **选择合适的模型：**
   - 复杂任务：GPT-4o 或 Llama-3.1-405B
   - 日常任务：GPT-4o-mini 或 Llama-3.1-8B
   - 中文任务：DeepSeek-R1
   - 知识检索：Cohere Command-R+

3. **实现错误处理：**
   ```python
   from openai import OpenAI, RateLimitError, APIError
   import time
   
   client = OpenAI(
       base_url="https://models.github.ai/inference",
       api_key=os.getenv('GITHUB_PAT')
   )
   
   def call_api_with_retry(messages, model="gpt-4o", max_retries=3):
       """带重试机制的 API 调用"""
       for attempt in range(max_retries):
           try:
               response = client.chat.completions.create(
                   model=model,
                   messages=messages
               )
               return response
           except RateLimitError:
               if attempt < max_retries - 1:
                   wait_time = 2 ** attempt  # 指数退避
                   print(f"达到速率限制，等待 {wait_time} 秒后重试...")
                   time.sleep(wait_time)
               else:
                   print("达到最大重试次数")
                   raise
           except APIError as e:
               print(f"API 错误: {e}")
               if attempt == max_retries - 1:
                   raise
       return None
   ```

### 🎯 最佳实践

**充分利用免费配额：**
- 根据任务复杂度选择合适的模型
- 使用缓存避免重复请求
- 批量处理相似任务
- 优化提示词减少 Token 使用

**优化 Token 使用：**
```python
# ✅ 精简提示词
messages = [
    {"role": "user", "content": "总结这段文字的要点：[文字内容]"}
]

# ❌ 避免冗余
messages = [
    {"role": "system", "content": "你是一个很厉害的助手，擅长总结..."},
    {"role": "user", "content": "请你帮我总结一下这段文字，注意要抓住重点..."}
]
```

**监控使用情况：**
```python
def log_usage(response):
    """记录 Token 使用情况"""
    usage = response.usage
    print(f"输入: {usage.prompt_tokens} tokens")
    print(f"输出: {usage.completion_tokens} tokens")
    print(f"总计: {usage.total_tokens} tokens")
    
    # 可以保存到文件或数据库
    with open('usage_log.txt', 'a') as f:
        f.write(f"{usage.total_tokens}\n")
```

### ⚠️ 注意事项

1. **速率限制：** 不同模型有不同限制，注意选择和分配。
2. **Token 安全：** 不要将 PAT 提交到公开仓库，使用环境变量。
3. **错误处理：** 实现完善的错误处理和重试机制。
4. **成本控制：** 虽然免费，但要合理使用，避免浪费配额。
5. **数据隐私：** 请勿在 API 请求中包含敏感信息（密码、密钥、个人隐私等）。

---

## 🎯 实际应用案例

### 案例 1：智能代码审查

**场景描述：** 使用 AI 自动审查代码并提供改进建议。

```python {filename="Python"}
from openai import OpenAI
import os

client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key=os.getenv('GITHUB_PAT')
)

def review_code(code):
    """AI 代码审查"""
    response = client.chat.completions.create(
        model="gpt-4o",
        messages=[
            {"role": "system", "content": "你是一个专业的代码审查专家。"},
            {"role": "user", "content": f"请审查以下代码并提供改进建议：\n\n{code}"}
        ]
    )
    return response.choices[0].message.content

# 使用示例
code = """
def calc(a, b):
    return a + b
"""

review = review_code(code)
print(review)
```

### 案例 2：文档自动生成

**场景描述：** 为函数自动生成文档注释。

```python {filename="Python"}
def generate_docstring(function_code):
    """为函数生成文档字符串"""
    response = client.chat.completions.create(
        model="gpt-4o",
        messages=[
            {"role": "system", "content": "生成 Python 函数的 docstring，使用 Google 风格。"},
            {"role": "user", "content": f"为以下函数生成 docstring：\n\n{function_code}"}
        ]
    )
    return response.choices[0].message.content

# 使用示例
function_code = """
def process_data(data, threshold=0.5):
    filtered = [x for x in data if x > threshold]
    return sum(filtered) / len(filtered) if filtered else 0
"""

docstring = generate_docstring(function_code)
print(docstring)
```

### 案例 3：多模型对比

**场景描述：** 对比不同模型的输出质量。

```python {filename="Python"}
def compare_models(prompt, models=["gpt-4o", "llama-3.1-70b", "deepseek-r1"]):
    """对比多个模型的输出"""
    results = {}
    
    for model in models:
        try:
            response = client.chat.completions.create(
                model=model,
                messages=[{"role": "user", "content": prompt}]
            )
            results[model] = {
                "response": response.choices[0].message.content,
                "tokens": response.usage.total_tokens
            }
        except Exception as e:
            results[model] = {"error": str(e)}
    
    return results

# 使用示例
prompt = "解释什么是递归，并给出一个 Python 例子。"
comparison = compare_models(prompt)

for model, result in comparison.items():
    print(f"\n{'='*50}")
    print(f"模型: {model}")
    print(f"{'='*50}")
    if "error" in result:
        print(f"错误: {result['error']}")
    else:
        print(result['response'])
        print(f"\n使用 Tokens: {result['tokens']}")
```

---

## 🔧 常见问题

**Q: 如何获取 GitHub Personal Access Token？**  
A: 访问 GitHub Settings > Developer settings > Personal access tokens，创建新 Token 并勾选 `models` 权限。详见 [注册步骤](/providers/github-models#注册步骤)。

**Q: API 端点地址是什么？**  
A: 基础 URL 为 `https://models.github.ai/inference`，Chat Completions 端点为 `https://models.github.ai/inference/chat/completions`。

**Q: 可以使用哪些模型？**  
A: 支持 GPT-4o、Llama 3.1、Phi-3、DeepSeek-R1、Mistral、Cohere 等 10+ 模型。完整列表请查看 [可用模型](#可用模型) 章节。

**Q: 速率限制是多少？**  
A: 不同模型有不同限制。例如 GPT-4o：10 RPM, 50 RPD；DeepSeek-R1：15 RPM, 150 RPD。详见 [配额和限制](#配额和限制) 章节。

**Q: 如何处理速率限制错误（429）？**  
A: 实现指数退避重试机制，或切换到其他模型。参考 [错误处理示例](#实用建议)。

**Q: 完全兼容 OpenAI API 吗？**  
A: 是的，完全兼容 OpenAI Chat Completions API 规范，可以直接使用 OpenAI SDK。

**Q: 需要付费吗？**  
A: 目前完全免费，但有速率限制。无需信用卡。

**Q: 如何保护 API Token？**  
A: 使用环境变量存储，不要提交到代码仓库，定期轮换 Token。

---

## 🔗 相关资源

- **API 端点：** `https://models.github.ai/inference`
- **官方文档：** [https://docs.github.com/zh/github-models](https://docs.github.com/zh/github-models)
- **快速入门：** [https://docs.github.com/zh/github-models/quickstart](https://docs.github.com/zh/github-models/quickstart)
- **提供者主页：** [GitHub Models](/providers/github-models)
- **对应的 Chatbot 服务：** [GitHub Models Playground](/services/chatbot/github-models)
- **GitHub Marketplace：** [https://github.com/marketplace/models](https://github.com/marketplace/models)

---

## 📝 更新日志

- **2024年9月：** GitHub Models API 公开测试上线
- **2024年10月：** 新增 DeepSeek-R1 等模型支持
- **2024年11月：** 优化 API 响应速度和稳定性
- **2025年：** 持续添加新模型，优化开发者体验

---

**服务提供者：** [GitHub Models](/providers/github-models)

