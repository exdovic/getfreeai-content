---
title: "Cloudflare Workers AI API - 边缘 AI 推理接口"
linkTitle: "API - Cloudflare Workers AI"
description: "Cloudflare Workers AI 提供全球边缘部署的 AI 推理 API，支持 50+ 开源模型，每日 10,000 神经元免费额度。无服务器架构，低延迟，OpenAI SDK 兼容，成本超低。"
keywords:
  - Cloudflare Workers AI API
  - Workers AI
  - 边缘 AI API
  - 无服务器 AI
  - 免费 AI API
  - Cloudflare AI
  - 低延迟 AI
  - OpenAI 兼容
image: /images/logo.svg
type: docs
weight: 16
comments: true
prev: /services/api/github-models
sidebar:
  open: true
---

## 📋 服务概览

**服务名称：** Cloudflare Workers AI API  
**所属提供者：** [Cloudflare Workers AI](/providers/cloudflare-workers-ai)  
**API 端点：** `https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/{model_name}`  
**服务类型：** 免费增值（每日 10,000 神经元免费）  
**注册要求：** 需要注册 Cloudflare 账户，无需信用卡

---

## ✅ 服务说明

Cloudflare Workers AI API 是基于 Cloudflare 全球网络的边缘 AI 推理服务。与传统的集中式 AI API 不同，Workers AI 将模型部署在全球 300+ 个数据中心，让 AI 推理在离用户最近的地方执行，显著降低延迟并提升用户体验。

### 主要特点

- **🌍 全球边缘部署：** 在全球 300+ 城市运行，提供最低延迟（通常 < 50ms）
- **🎁 慷慨免费额度：** 每日 10,000 个神经元免费，无需信用卡
- **⚡ 超低成本：** 超出免费额度后仅 $0.011/1000 神经元，比传统云服务便宜 80%+
- **🤖 丰富模型库：** 支持 50+ 开源模型，涵盖 LLM、图像、语音、嵌入等
- **🔌 开发者友好：** REST API + Workers 绑定，兼容 OpenAI SDK
- **🔧 深度集成：** 与 Cloudflare Workers、Pages、AI Gateway、Vectorize 无缝集成

---

## 🎁 可用模型

### 文本生成模型（LLM）

| 模型名称 | 参数量 | 上下文长度 | 特点 | 适用场景 |
|---------|--------|-----------|------|---------|
| **@cf/meta/llama-3.1-8b-instruct** | 8B | 8K | Meta 最新，平衡性能 | 通用对话、代码生成 |
| **@cf/meta/llama-3-8b-instruct** | 8B | 8K | Meta Llama 3，速度快 | 实时对话、摘要 |
| **@cf/mistral/mistral-7b-instruct-v0.2** | 7B | 32K | Mistral AI，长上下文 | 文档分析、长文本 |
| **@cf/qwen/qwen1.5-7b-chat-awq** | 7B | 32K | 阿里通义千问，中文优化 | 中文对话、翻译 |
| **@cf/google/gemma-7b-it** | 7B | 8K | Google Gemma，开源 | 通用任务 |
| **@cf/deepseek-ai/deepseek-math-7b-instruct** | 7B | 4K | DeepSeek 数学专家 | 数学推理、解题 |

### 图像生成模型

| 模型名称 | 特点 | 适用场景 |
|---------|------|---------|
| **@cf/stabilityai/stable-diffusion-xl-base-1.0** | SDXL，高质量图像 | 艺术创作、设计 |
| **@cf/lykon/dreamshaper-8-lcm** | LCM，快速生成 | 快速原型、实时生成 |
| **@cf/bytedance/stable-diffusion-xl-lightning** | 超快速，4-8步生成 | 实时应用 |

### 图像分析模型

| 模型名称 | 特点 | 适用场景 |
|---------|------|---------|
| **@cf/unum/uform-gen2-qwen-500m** | 图像理解 + 文本生成 | 图像描述、VQA |
| **@cf/llava-hf/llava-1.5-7b-hf** | 多模态理解 | 图像问答、分析 |

### 语音识别模型

| 模型名称 | 特点 | 适用场景 |
|---------|------|---------|
| **@cf/openai/whisper** | OpenAI Whisper，多语言 | 语音转文字、字幕 |

### 嵌入模型

| 模型名称 | 维度 | 特点 | 适用场景 |
|---------|-----|------|---------|
| **@cf/baai/bge-base-en-v1.5** | 768 | 英文嵌入，高性能 | 语义搜索、RAG |
| **@cf/baai/bge-large-en-v1.5** | 1024 | 英文嵌入，更高精度 | 精确匹配 |
| **@cf/baai/bge-small-en-v1.5** | 384 | 英文嵌入，轻量级 | 快速检索 |

### 完整模型列表

查看 [Cloudflare Workers AI 模型目录](https://developers.cloudflare.com/workers-ai/models/) 获取最新的模型列表。

---

## 🔢 配额和限制

### 免费层级限制

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每日神经元数** | 10,000 neurons/day | 所有模型共享 |
| **请求速率** | 无硬性限制 | 受神经元配额约束 |
| **单次请求大小** | 依模型而定 | 通常 1-10MB |
| **并发请求** | 无限制 | 受 Workers 限制 |
| **需要信用卡** | ❌ 不需要 | 免费额度无需绑卡 |

### ⚠️ 重要限制

1. **神经元计算：** 不同模型每次推理消耗的神经元数量不同：
   - 小型 LLM（如 Llama-3-8B）：约 5-10 neurons/请求
   - 图像生成（如 SDXL）：约 50-100 neurons/张图
   - 语音识别：约 1 neuron/秒音频

2. **每日重置：** 免费配额在每天 UTC 00:00 重置

3. **超出计费：** 超出免费额度后，按 $0.011/1000 neurons 计费

### 配额重置时间

- **每日配额：** UTC 时间 00:00 重置
- **实时监控：** 在 Cloudflare Dashboard 中查看使用情况

---

## 💰 价格说明

### 免费额度

- **免费配额：** 每日 10,000 个神经元
- **获取方式：** 注册 Cloudflare 账户即可使用
- **有效期：** 永久有效，每日重置

### 付费定价

超出免费额度后的计费：

| 项目 | 价格 | 说明 |
|------|------|------|
| **神经元** | $0.011/1000 neurons | 按实际使用量计费 |
| **最低消费** | 无 | 真正按需付费 |

### 成本对比

| 服务 | 典型成本（1000次 LLM 推理） | 相对便宜 |
|------|---------------------------|---------|
| **Cloudflare Workers AI** | ~$0.05-0.10 | 基准 |
| OpenAI GPT-3.5 | ~$0.50-1.00 | 5-20倍 |
| OpenAI GPT-4 | ~$10-30 | 100-600倍 |
| AWS Bedrock | ~$0.30-2.00 | 3-40倍 |

---

## 🚀 如何使用

### 前提条件

**1. 注册 Cloudflare 账户**

请参考：[Cloudflare Workers AI 注册指南](/providers/cloudflare-workers-ai#注册账户)

**2. 获取 API Token**

{{% steps %}}

##### 访问 API Tokens 页面

登录 Cloudflare Dashboard，进入 [API Tokens 页面](https://dash.cloudflare.com/profile/api-tokens)

##### 创建 Token

1. 点击"Create Token"
2. 选择"Edit Cloudflare Workers"模板
3. 或自定义权限，确保包含 Workers AI 权限

##### 保存 Token

复制生成的 Token 并安全保存（只显示一次）

{{% /steps %}}

**3. 获取 Account ID**

在 Cloudflare Dashboard 的任何页面右侧，可以找到您的 Account ID。

---

## 💻 代码示例

### 方法 1：使用 REST API（任何语言）

#### Python 示例

**安装依赖：**

```bash {filename="Bash"}
pip install requests
```

**基本使用（文本生成）：**

```python {filename="Python"}
import requests
import os

# 配置
CLOUDFLARE_ACCOUNT_ID = "your-account-id"
CLOUDFLARE_API_TOKEN = "your-api-token"

# API 端点
url = f"https://api.cloudflare.com/client/v4/accounts/{CLOUDFLARE_ACCOUNT_ID}/ai/run/@cf/meta/llama-3.1-8b-instruct"

# 请求头
headers = {
    "Authorization": f"Bearer {CLOUDFLARE_API_TOKEN}",
    "Content-Type": "application/json"
}

# 请求数据
data = {
    "messages": [
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "What is Cloudflare Workers AI?"}
    ]
}

# 发送请求
response = requests.post(url, headers=headers, json=data)
result = response.json()

# 打印结果
print(result["result"]["response"])
```

**流式输出：**

```python {filename="Python"}
import requests
import json

# 启用流式响应
data = {
    "messages": [
        {"role": "user", "content": "Write a short story about AI"}
    ],
    "stream": True
}

response = requests.post(url, headers=headers, json=data, stream=True)

# 处理流式数据
for line in response.iter_lines():
    if line:
        line = line.decode('utf-8')
        if line.startswith('data: '):
            try:
                data = json.loads(line[6:])
                if 'response' in data:
                    print(data['response'], end='', flush=True)
            except:
                pass
```

**图像生成示例：**

```python {filename="Python"}
import requests
import base64

# 图像生成 API
url = f"https://api.cloudflare.com/client/v4/accounts/{CLOUDFLARE_ACCOUNT_ID}/ai/run/@cf/stabilityai/stable-diffusion-xl-base-1.0"

data = {
    "prompt": "A beautiful sunset over mountains, digital art style"
}

response = requests.post(url, headers=headers, json=data)
result = response.json()

# 保存图片
image_data = base64.b64decode(result["result"]["image"])
with open("output.png", "wb") as f:
    f.write(image_data)
print("Image saved as output.png")
```

---

### 方法 2：使用 Cloudflare Workers（推荐）

在 Cloudflare Workers 中使用 Workers AI 更简单，无需管理 API Token。

**步骤 1：配置 wrangler.toml**

```toml {filename="wrangler.toml"}
name = "my-ai-worker"
main = "src/index.js"
compatibility_date = "2024-01-01"

[ai]
binding = "AI"
```

**步骤 2：编写 Worker 代码**

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    // 使用 AI 绑定
    const response = await env.AI.run("@cf/meta/llama-3.1-8b-instruct", {
      messages: [
        { role: "system", content: "You are a helpful assistant." },
        { role: "user", content: "Explain Workers AI in one sentence." }
      ]
    });

    return new Response(JSON.stringify(response), {
      headers: { "content-type": "application/json" }
    });
  }
};
```

**步骤 3：部署**

```bash {filename="Bash"}
npx wrangler deploy
```

**更多示例：**

```javascript {filename="JavaScript"}
// 文本嵌入
const embeddings = await env.AI.run("@cf/baai/bge-base-en-v1.5", {
  text: "Cloudflare Workers AI is amazing"
});

// 图像生成
const imageResponse = await env.AI.run("@cf/stabilityai/stable-diffusion-xl-base-1.0", {
  prompt: "A futuristic city"
});

// 语音转文字
const transcription = await env.AI.run("@cf/openai/whisper", {
  audio: audioArrayBuffer
});
```

---

### 方法 3：使用 OpenAI SDK（兼容）

Cloudflare Workers AI 部分兼容 OpenAI SDK：

```python {filename="Python"}
from openai import OpenAI

# 配置 Workers AI
client = OpenAI(
    api_key=CLOUDFLARE_API_TOKEN,
    base_url=f"https://api.cloudflare.com/client/v4/accounts/{CLOUDFLARE_ACCOUNT_ID}/ai/v1"
)

# 使用类似 OpenAI 的 API
response = client.chat.completions.create(
    model="@cf/meta/llama-3.1-8b-instruct",
    messages=[
        {"role": "user", "content": "Hello, how are you?"}
    ]
)

print(response.choices[0].message.content)
```

---

### cURL 示例

**基本请求：**

```bash {filename="Bash"}
curl https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/@cf/meta/llama-3.1-8b-instruct \
  -H "Authorization: Bearer {api_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "messages": [
      {"role": "system", "content": "You are a helpful assistant."},
      {"role": "user", "content": "What is edge computing?"}
    ]
  }'
```

**流式输出：**

```bash {filename="Bash"}
curl https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/@cf/meta/llama-3.1-8b-instruct \
  -H "Authorization: Bearer {api_token}" \
  -H "Content-Type: application/json" \
  -d '{
    "messages": [{"role": "user", "content": "Tell me a story"}],
    "stream": true
  }'
```

---

## 🌟 核心优势

### 技术优势

1. **超低延迟：**
   - 在全球 300+ 城市部署
   - 平均延迟 < 50ms（vs 传统云 100-300ms）
   - 就近响应，无跨区传输

2. **极致性价比：**
   - 每日 10,000 神经元免费
   - 超出后仅 $0.011/1000 neurons
   - 比 AWS、GCP 便宜 80%+

3. **无服务器架构：**
   - 无需管理 GPU 或服务器
   - 自动扩展，按需付费
   - 零运维成本

### 与其他 AI API 对比

| 特性 | Workers AI | OpenAI API | Google AI Studio | AWS Bedrock |
|------|----------|-----------|----------------|------------|
| 免费额度 | 10K neurons/天 | 试用积分 | 免费使用 | 试用积分 |
| 边缘部署 | ✅ 300+ 城市 | ❌ | ❌ | ❌ |
| 延迟 | < 50ms | 100-300ms | 100-300ms | 100-300ms |
| 成本（LLM） | ~$0.05/1K请求 | ~$0.50/1K请求 | 免费 | ~$0.30/1K请求 |
| 开源模型 | ✅ 50+ | ❌ | 部分 | 部分 |
| 无服务器 | ✅ | 需自行管理 | ❌ | 部分 |

---

## 💡 实用建议

### ✅ 推荐做法

1. **优先使用 Workers 绑定：**
   ```javascript
   // 在 Workers 中使用，更简单且无需管理 Token
   const response = await env.AI.run(model, input);
   ```

2. **结合 AI Gateway 使用：**
   ```javascript
   // 添加缓存、日志、重试等功能
   const response = await env.AI.run(model, input, {
     gateway: {
       id: "my-gateway",
       skipCache: false,
       cacheTtl: 3600
     }
   });
   ```

3. **选择合适的模型：**
   - 实时对话：Llama-3-8B（速度快）
   - 中文任务：Qwen-1.5-7B（中文优化）
   - 数学推理：DeepSeek-Math-7B（数学专家）
   - 快速图像生成：SD-XL-Lightning

4. **监控神经元使用：**
   ```javascript
   // 记录每个请求的消耗
   console.log(`Neurons used: ${response.neuronCount}`);
   ```

### 🎯 最佳实践

**充分利用免费配额：**
- 每日 10,000 神经元可以支持约 1,000-2,000 次 LLM 请求
- 合理选择模型大小和输入长度
- 使用缓存减少重复请求

**优化延迟：**
- 利用边缘部署优势，构建低延迟应用
- 使用流式输出提升用户体验
- 预加载常用模型

**错误处理：**

```python {filename="Python"}
import time

def call_workers_ai_with_retry(url, headers, data, max_retries=3):
    """带重试机制的 API 调用"""
    for attempt in range(max_retries):
        try:
            response = requests.post(url, headers=headers, json=data, timeout=30)
            response.raise_for_status()
            return response.json()
        except requests.exceptions.RequestException as e:
            if attempt < max_retries - 1:
                wait_time = 2 ** attempt
                print(f"请求失败，{wait_time}秒后重试... ({attempt + 1}/{max_retries})")
                time.sleep(wait_time)
            else:
                raise Exception(f"请求失败: {e}")
```

### ⚠️ 注意事项

1. **神经元消耗：** 不同模型消耗不同，大模型和长输入会消耗更多神经元
2. **模型可用性：** 部分模型可能在某些区域不可用
3. **输入限制：** 注意各模型的输入长度限制
4. **计费周期：** 超出免费额度会立即开始计费，请监控使用情况

---

## 🎯 实际应用案例

### 案例 1：智能客服 Chatbot

构建一个低延迟的全球智能客服系统：

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    const { message } = await request.json();
    
    // 使用 Llama 3 快速响应
    const response = await env.AI.run(
      "@cf/meta/llama-3.1-8b-instruct",
      {
        messages: [
          {
            role: "system",
            content: "You are a helpful customer service agent."
          },
          { role: "user", content: message }
        ],
        stream: true
      }
    );

    return new Response(response, {
      headers: { "content-type": "text/event-stream" }
    });
  }
};
```

### 案例 2：文档语义搜索

使用嵌入模型构建语义搜索：

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    const { query } = await request.json();
    
    // 生成查询嵌入
    const embeddings = await env.AI.run(
      "@cf/baai/bge-base-en-v1.5",
      { text: query }
    );
    
    // 使用 Vectorize 进行相似度搜索
    const results = await env.VECTORIZE.query(embeddings.data[0], {
      topK: 5
    });
    
    return Response.json(results);
  }
};
```

### 案例 3：自动图像生成

API 接收文本描述，生成图像：

```python {filename="Python"}
import requests
import base64

def generate_image(prompt, account_id, api_token):
    """生成图像"""
    url = f"https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/@cf/bytedance/stable-diffusion-xl-lightning"
    
    headers = {
        "Authorization": f"Bearer {api_token}",
        "Content-Type": "application/json"
    }
    
    data = {
        "prompt": prompt,
        "num_steps": 4  # Lightning 模型，4步即可
    }
    
    response = requests.post(url, headers=headers, json=data)
    result = response.json()
    
    # 保存图片
    image_data = base64.b64decode(result["result"]["image"])
    filename = f"generated_{hash(prompt)}.png"
    with open(filename, "wb") as f:
        f.write(image_data)
    
    return filename

# 使用示例
image_path = generate_image(
    "A futuristic cityscape at sunset, cyberpunk style",
    "your-account-id",
    "your-api-token"
)
print(f"Image saved to: {image_path}")
```

### 案例 4：语音转文字服务

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    // 接收音频文件
    const formData = await request.formData();
    const audioFile = formData.get('audio');
    const audioBuffer = await audioFile.arrayBuffer();
    
    // 使用 Whisper 转录
    const transcription = await env.AI.run(
      "@cf/openai/whisper",
      {
        audio: [...new Uint8Array(audioBuffer)]
      }
    );
    
    return Response.json({
      text: transcription.text,
      language: transcription.language
    });
  }
};
```

---

## 🔧 常见问题

**Q: 如何查看我使用了多少神经元？**  
A: 登录 [Cloudflare Dashboard](https://dash.cloudflare.com)，在 Workers & Pages 部分可以查看 AI 使用情况和神经元消耗。

**Q: 什么情况下会产生费用？**  
A: 只有当您超过每日 10,000 个神经元的免费额度时，才会按 $0.011/1000 neurons 计费。

**Q: 可以使用自己的模型吗？**  
A: 目前 Workers AI 只支持 Cloudflare 提供的开源模型目录，暂不支持上传自定义模型。

**Q: Workers AI 支持哪些地区？**  
A: Workers AI 在 Cloudflare 的全球网络上运行，覆盖 300+ 城市，几乎全球可用。但部分模型可能在某些地区受限。

**Q: 如何获得最佳性能？**  
A: 1) 使用 Workers 绑定而不是 REST API；2) 选择合适大小的模型；3) 启用流式输出；4) 使用 AI Gateway 缓存。

**Q: Workers AI 与 OpenAI API 有什么区别？**  
A: Workers AI 使用开源模型，部署在边缘，延迟更低，成本更低。OpenAI API 使用专有模型（如 GPT-4），能力更强但成本更高。

---

## 🔗 相关资源

- **API 端点：** `https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/{model}`
- **开发者文档：** [https://developers.cloudflare.com/workers-ai/](https://developers.cloudflare.com/workers-ai/)
- **模型目录：** [https://developers.cloudflare.com/workers-ai/models/](https://developers.cloudflare.com/workers-ai/models/)
- **提供者主页：** [Cloudflare Workers AI](/providers/cloudflare-workers-ai)
- **API 参考：** [https://developers.cloudflare.com/api/operations/workers-ai-post-run](https://developers.cloudflare.com/api/operations/workers-ai-post-run)
- **示例代码：** [https://developers.cloudflare.com/workers-ai/examples/](https://developers.cloudflare.com/workers-ai/examples/)
- **Discord 社区：** [https://discord.cloudflare.com](https://discord.cloudflare.com)

---

## 📝 更新日志

- **2024年1月：** 新增多个 Llama 3.1 和 Mistral 模型支持
- **2023年12月：** 推出图像生成和语音识别模型
- **2023年9月：** Workers AI 正式发布，提供每日 10,000 神经元免费额度

---

**服务提供者：** [Cloudflare Workers AI](/providers/cloudflare-workers-ai)
