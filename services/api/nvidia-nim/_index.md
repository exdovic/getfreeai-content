---
title: "NVIDIA NIM API - 企业级 GPU 加速推理 API 服务"
linkTitle: "API - NVIDIA NIM"
description: "NVIDIA NIM 提供优化的 GPU 加速推理 API，支持免费托管试用和自托管部署。OpenAI 兼容接口，支持 Llama 3、Mistral、Phi 等主流模型，提供低延迟、高吞吐量的企业级推理能力。"
keywords:
  - NVIDIA NIM API
  - GPU 加速 API
  - 免费 AI API
  - 企业级推理 API
  - OpenAI 兼容 API
  - Llama 3 API
  - Mistral API
  - 自托管 AI API
image: /images/logo.svg
type: docs
weight: 11
comments: true
prev: /services/api/mistral
next: /services/chatbot
sidebar:
  open: true
---

## 📋 服务概览

**服务名称：** NVIDIA NIM API  
**所属提供者：** [NVIDIA NIM](/providers/nvidia-nim)  
**API 端点：** `https://integrate.api.nvidia.com/v1`  
**服务类型：** 免费托管试用 + 自托管下载  
**注册要求：** 需要 NVIDIA 开发者账户

---

## ✅ 服务说明

NVIDIA NIM API 是 NVIDIA 提供的企业级 AI 推理 API 服务，通过 GPU 加速提供高性能的模型推理能力。NIM（NVIDIA Inference Microservices）将复杂的模型部署过程简化为开箱即用的微服务，完全兼容 OpenAI API 格式。

### 主要特点

- **🚀 GPU 加速：** 利用 NVIDIA GPU 的强大算力，提供业界领先的推理性能
- **📦 开箱即用：** 预先优化的模型容器，无需复杂配置即可使用
- **🔄 OpenAI 兼容：** 完全兼容 OpenAI API，只需修改 base_url 即可切换
- **🏭 企业级功能：** 支持 Kubernetes 部署、自动扩展、多租户隔离
- **🌐 灵活部署：** 支持云端托管试用和本地自托管两种方式

---

## 🎁 可用模型

### 大语言模型（LLM）

| 模型名称 | 参数量 | 上下文长度 | 特点 | 适用场景 |
|---------|-------|-----------|------|---------|
| **meta/llama-3.1-405b-instruct** | 405B | 128K | Meta 最强模型 | 复杂推理、专业任务 |
| **meta/llama-3.1-70b-instruct** | 70B | 128K | 性能与效率平衡 | 通用对话、内容生成 |
| **meta/llama-3.1-8b-instruct** | 8B | 128K | 轻量高效 | 快速响应、高频调用 |
| **mistralai/mistral-large** | 123B | 128K | Mistral 旗舰模型 | 多语言、代码生成 |
| **mistralai/mixtral-8x7b-instruct** | 47B | 32K | 混合专家架构 | 专业领域、多任务 |
| **microsoft/phi-3-medium-4k-instruct** | 14B | 4K | 微软小模型 | 边缘设备、快速推理 |

### 视觉语言模型

| 模型名称 | 特点 | 适用场景 |
|---------|------|---------|
| **meta/llama-3.2-90b-vision-instruct** | 视觉理解 | 图像分析、OCR |
| **meta/llama-3.2-11b-vision-instruct** | 轻量视觉 | 快速图像处理 |

### 推理专家模型

| 模型名称 | 特点 | 适用场景 |
|---------|------|---------|
| **deepseek-ai/deepseek-r1** | 思维链推理 | 数学、逻辑推理 |
| **nvidia/llama-3.1-nemotron-70b-instruct** | NVIDIA 优化 | 高性能推理 |

**注意：** 以上为示例模型，实际可用模型会持续更新并可能因地区而异。请访问 [build.nvidia.com/explore](https://build.nvidia.com/explore/discover) 查看最新、完整的模型列表。

---

## 🔢 配额和限制

### 托管 API 试用

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **免费积分** | 约 1,000 积分 | 参考值，新用户注册后获得 |
| **每日请求数** | 视积分消耗 | 不同模型消耗不同 |
| **速率限制** | 模型特定 | 详见各模型卡说明 |
| **最大上下文** | 视模型而定 | 示例：Llama 3.1 支持 128K |
| **最大输出** | 视模型而定 | 通常为 4K-8K tokens |
| **需要信用卡** | ❌ 不需要 | 完全免费试用 |

### 自托管部署

| 限制项 | 要求 | 说明 |
|--------|------|------|
| **GPU 要求** | NVIDIA GPU | 型号和显存视模型而定 |
| **最小显存** | 24GB+ | 小模型（8B） |
| **推荐显存** | 80GB+ | 大模型（70B+） |
| **许可证** | NVIDIA AI Enterprise | 生产环境需要（90天免费试用） |
| **下载权限** | 开发者账户 | 免费注册获取 |

### ⚠️ 重要限制

1. **额度性质：** 免费积分用于开发测试，额度政策可能调整。用完后可申请更多或转自托管
2. **计费说明：** 远程 API 调用消耗 credits，网页 Playground 交互通常不消耗
3. **模型可用性：** 模型列表会更新，部分模型可能因地区或合作方而异
4. **生产使用：** 托管 API 试用用于开发测试；生产环境建议自托管或购买企业许可证

---

## 💰 价格说明

### 免费/试用

- **托管 API 试用：** 新用户通常获得初始试用额度（参考值约 1,000 credits）
- **有效期：** 额度政策由 NVIDIA 控制，建议及时使用。如需更多可在 Build 平台申请
- **获取方式：** 注册 NVIDIA 开发者账户并在 Build 平台生成 API Key 后获得
- **计费说明：** 远程 API 调用消耗 credits，网页 Playground 通常不消耗

### 自托管（免费下载）

- **下载：** 通过 NVIDIA 开发者计划免费下载 NIM 微服务
- **用途限制：** 免费用于开发、测试和研究
- **生产部署：** 需要购买 NVIDIA AI Enterprise 许可证（约 $4,500/GPU/年起）

### 付费选项

| 方案 | 价格 | 说明 |
|------|------|------|
| **托管 API 付费** | 按使用量计费 | 积分消耗完后可购买 |
| **AI Enterprise** | $4,500/GPU/年起 | 企业许可证，包含支持 |
| **云服务商部署** | 视云平台定价 | AWS、Azure、GCP 等 |

---

## 🚀 如何使用

### 前提条件

**1. 注册 NVIDIA 开发者账户**

请参考：[NVIDIA NIM 注册指南](/providers/nvidia-nim#注册账户)

**2. 获取 API 密钥**

{{% steps %}}

#### 访问 build.nvidia.com

登录后访问 [https://build.nvidia.com](https://build.nvidia.com)

#### 选择模型

在 API Catalog 中浏览并选择您想使用的模型

#### 获取 API Key

1. 点击页面右上角的用户头像
2. 选择 **"Get API Key"** 或 **"API Keys"**
3. 点击 **"Generate API Key"** 创建新密钥
4. 复制并保存 API 密钥（格式：`nvapi-xxx`）

⚠️ **重要：** 请妥善保管您的 API 密钥，不要在公开代码中暴露。

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

# 初始化客户端（使用 NVIDIA NIM API）
client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"  # 替换为您的 API 密钥
)

# 发送请求
response = client.chat.completions.create(
    model="meta/llama-3.1-70b-instruct",
    messages=[
        {"role": "system", "content": "You are a helpful AI assistant."},
        {"role": "user", "content": "解释一下什么是 GPU 加速推理？"}
    ],
    max_tokens=1024,
    temperature=0.7
)

# 打印响应
print(response.choices[0].message.content)

# 查看 Token 使用情况
print(f"\n使用 Tokens: {response.usage.total_tokens}")
```

**流式输出示例：**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

# 流式输出（适合实时显示）
stream = client.chat.completions.create(
    model="meta/llama-3.1-70b-instruct",
    messages=[
        {"role": "user", "content": "写一首关于人工智能的诗"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

**使用视觉模型：**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

# 图像分析
response = client.chat.completions.create(
    model="meta/llama-3.2-90b-vision-instruct",
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

---

### cURL 示例

**基本请求：**

```bash {filename="Bash"}
curl https://integrate.api.nvidia.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer nvapi-YOUR_API_KEY" \
  -d '{
    "model": "meta/llama-3.1-70b-instruct",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful AI assistant."
      },
      {
        "role": "user",
        "content": "你好，请介绍一下 NVIDIA NIM。"
      }
    ],
    "max_tokens": 1024,
    "temperature": 0.7
  }'
```

**流式输出：**

```bash {filename="Bash"}
curl https://integrate.api.nvidia.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer nvapi-YOUR_API_KEY" \
  -d '{
    "model": "meta/llama-3.1-70b-instruct",
    "messages": [{"role": "user", "content": "你好"}],
    "stream": true
  }'
```

---

### Node.js 示例

```bash {filename="Bash"}
npm install openai
```

```javascript {filename="JavaScript"}
import OpenAI from 'openai';

const client = new OpenAI({
  baseURL: 'https://integrate.api.nvidia.com/v1',
  apiKey: 'nvapi-YOUR_API_KEY',
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'meta/llama-3.1-70b-instruct',
    messages: [
      { role: 'system', content: 'You are a helpful AI assistant.' },
      { role: 'user', content: '介绍一下 NVIDIA GPU 的优势。' }
    ],
    max_tokens: 1024,
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

1. **GPU 加速性能：**
   - 针对 NVIDIA GPU 深度优化
   - 相比 CPU 推理提速 10-100 倍
   - 支持张量并行、流水线并行等高级优化

2. **企业级可靠性：**
   - 经过生产验证的推理引擎
   - 支持高并发、低延迟场景
   - 提供 SLA 保障（企业版）

3. **灵活部署选项：**
   - 云端托管：无需管理基础设施
   - 本地部署：数据完全掌控
   - 混合部署：灵活组合

### 与其他 API 对比

| 特性 | NVIDIA NIM | Groq | OpenRouter |
|------|-----------|------|------------|
| 免费配额 | 1,000 积分 | 14,400 次/天 | 50-1,000 次/天 |
| GPU 加速 | ✅ NVIDIA GPU | ✅ LPU 芯片 | ❌ 托管模型 |
| 自托管 | ✅ 支持 | ❌ 不支持 | ❌ 不支持 |
| 企业功能 | ✅ 完整 | ❌ 基础 | ❌ 基础 |
| OpenAI 兼容 | ✅ 完全兼容 | ✅ 完全兼容 | ✅ 完全兼容 |
| 视觉模型 | ✅ 支持 | ❌ 不支持 | ✅ 部分支持 |

---

## 💡 实用建议

### ✅ 推荐做法

1. **选择合适的模型：**
   ```python
   # 快速响应场景
   model = "meta/llama-3.1-8b-instruct"
   
   # 平衡性能和质量
   model = "meta/llama-3.1-70b-instruct"
   
   # 最强性能需求
   model = "meta/llama-3.1-405b-instruct"
   
   # 视觉任务
   model = "meta/llama-3.2-90b-vision-instruct"
   ```

2. **实现错误处理：**
   ```python
   import time
   from openai import OpenAI, RateLimitError, APIError
   
   client = OpenAI(
       base_url="https://integrate.api.nvidia.com/v1",
       api_key="nvapi-YOUR_API_KEY"
   )
   
   def call_with_retry(messages, max_retries=3):
       """带重试机制的 API 调用"""
       for attempt in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="meta/llama-3.1-70b-instruct",
                   messages=messages
               )
           except RateLimitError:
               if attempt < max_retries - 1:
                   wait_time = 2 ** attempt
                   print(f"达到速率限制，等待 {wait_time} 秒...")
                   time.sleep(wait_time)
               else:
                   raise
           except APIError as e:
               print(f"API 错误: {e}")
               if attempt == max_retries - 1:
                   raise
       return None
   ```

3. **监控积分使用：**
   ```python
   def track_usage(response):
       """跟踪 Token 使用情况"""
       usage = response.usage
       print(f"输入 Tokens: {usage.prompt_tokens}")
       print(f"输出 Tokens: {usage.completion_tokens}")
       print(f"总计 Tokens: {usage.total_tokens}")
       
       # 估算积分消耗（具体比例请查看官方文档）
       estimated_credits = usage.total_tokens / 1000
       print(f"估算消耗积分: {estimated_credits:.2f}")
   ```

4. **优化 Token 使用：**
   - 使用系统提示词指导模型行为
   - 适当限制 max_tokens 避免过长输出
   - 对于简单任务使用小模型
   - 缓存常见问题的回答

5. **安全管理 API 密钥：**
   ```python
   import os
   from dotenv import load_dotenv
   
   # 使用环境变量
   load_dotenv()
   api_key = os.getenv('NVIDIA_API_KEY')
   
   client = OpenAI(
       base_url="https://integrate.api.nvidia.com/v1",
       api_key=api_key
   )
   ```

### ⚠️ 注意事项

1. **积分管理：** 合理使用试用额度，不同模型消耗不同。远程 API 调用才消耗 credits
2. **API 端点：** 示例使用 `https://integrate.api.nvidia.com/v1`，请以各模型卡中的说明为准
3. **网络连接：** 访问 NVIDIA 服务可能需要稳定的国际网络连接
4. **故障排查：** 遇到额度或权限错误时，可在 Build 控制台检查余额或申请更多

---

## 🎯 实际应用案例

### 案例 1：智能客服助手

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

def customer_service_bot(user_question, context=""):
    """智能客服助手"""
    system_prompt = f"""你是一个专业的客服助手。
请基于以下知识库回答用户问题：

{context}

回答要求：
- 专业、友好、简洁
- 如果不确定，建议联系人工客服
- 提供具体的解决方案
"""
    
    response = client.chat.completions.create(
        model="meta/llama-3.1-70b-instruct",
        messages=[
            {"role": "system", "content": system_prompt},
            {"role": "user", "content": user_question}
        ],
        temperature=0.3  # 降低温度以获得更确定的回答
    )
    
    return response.choices[0].message.content

# 使用示例
knowledge_base = """
产品信息：
- 支持 7x24 小时在线客服
- 提供 30 天无理由退换货
- 全国包邮，偏远地区除外
"""

answer = customer_service_bot("如何退货？", knowledge_base)
print(answer)
```

### 案例 2：代码审查助手

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

def code_review(code, language="Python"):
    """代码审查助手"""
    response = client.chat.completions.create(
        model="meta/llama-3.1-70b-instruct",
        messages=[
            {
                "role": "system",
                "content": f"你是一个专业的 {language} 代码审查专家。"
                           "请从以下方面审查代码：\n"
                           "1. 代码质量和可读性\n"
                           "2. 潜在的 bug 和安全问题\n"
                           "3. 性能优化建议\n"
                           "4. 最佳实践建议"
            },
            {
                "role": "user",
                "content": f"请审查以下代码：\n\n```{language.lower()}\n{code}\n```"
            }
        ],
        temperature=0.2
    )
    
    return response.choices[0].message.content

# 使用示例
code_to_review = """
def calculate_sum(numbers):
    sum = 0
    for i in range(len(numbers)):
        sum = sum + numbers[i]
    return sum
"""

review_result = code_review(code_to_review)
print(review_result)
```

### 案例 3：图像理解应用

```python {filename="Python"}
from openai import OpenAI
import base64

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

def analyze_image(image_url, question="描述这张图片"):
    """图像分析"""
    response = client.chat.completions.create(
        model="meta/llama-3.2-90b-vision-instruct",
        messages=[
            {
                "role": "user",
                "content": [
                    {"type": "text", "text": question},
                    {
                        "type": "image_url",
                        "image_url": {"url": image_url}
                    }
                ]
            }
        ]
    )
    
    return response.choices[0].message.content

# 使用示例
result = analyze_image(
    "https://example.com/product.jpg",
    "这个产品有什么特点？"
)
print(result)
```

---

## 🔧 常见问题

**Q: 如何查看剩余积分？**  
A: 登录 build.nvidia.com，在个人资料或 Usage 页面查看当前 API credits 余额和使用情况。

**Q: 免费积分用完后怎么办？**  
A: 可以：1) 在 Build 平台点击 "Request More" 申请更多额度；2) 下载 NIM 微服务自托管部署；3) 购买 NVIDIA AI Enterprise 许可证用于生产环境。

**Q: 为什么会遇到 402/403 错误？**  
A: 可能是积分不足或权限问题。请检查：1) Build 控制台的积分余额；2) 确认使用的是远程 API 调用（会消耗 credits）；3) 尝试申请更多额度或联系 NVIDIA 支持。

**Q: 自托管需要什么硬件？**  
A: 最低需要一块 NVIDIA GPU，具体要求取决于模型大小。例如 Llama 3.1 8B 需要至少 24GB 显存，70B 模型需要 80GB+ 显存。

**Q: 支持哪些编程语言？**  
A: 由于兼容 OpenAI API，所有支持 OpenAI 的语言都可以使用，包括 Python、JavaScript/Node.js、Go、Java、C# 等。

**Q: 如何获取技术支持？**  
A: 可以通过 NVIDIA 开发者论坛、官方文档、GitHub Issues 等渠道获取支持。企业用户可以购买付费支持服务。

---

## 🔗 相关资源

- **API 端点：** `https://integrate.api.nvidia.com/v1`
- **开发者平台：** [https://build.nvidia.com](https://build.nvidia.com)
- **API 目录：** [https://build.nvidia.com/explore/discover](https://build.nvidia.com/explore/discover)
- **提供者主页：** [NVIDIA NIM 介绍](/providers/nvidia-nim)
- **官方文档：** [https://docs.nvidia.com/nim](https://docs.nvidia.com/nim)
- **开发者论坛：** [https://forums.developer.nvidia.com](https://forums.developer.nvidia.com)
- **GitHub：** [https://github.com/NVIDIA](https://github.com/NVIDIA)

---

## 📝 更新日志

- **2025年1月：** 添加更多开源模型支持，优化 API 性能
- **2024年12月：** NVIDIA NIM 正式发布，提供托管 API 和自托管选项
- **2024年10月：** build.nvidia.com 开发者平台上线

---

**服务提供者：** [NVIDIA NIM](/providers/nvidia-nim)
