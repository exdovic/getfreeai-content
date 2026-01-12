---
title: "Vercel AI Gateway API - 统一 AI 模型访问接口"
linkTitle: "API - Vercel AI Gateway"
description: "Vercel AI Gateway API 提供统一接口访问数百种 AI 模型！每月 $5 免费额度，支持 OpenAI、Anthropic、Google 等提供商，自动故障转移，透明定价无加价，支持 BYOK，OpenAI 兼容格式。"
keywords:
  - Vercel AI Gateway API
  - AI Gateway
  - 统一AI接口
  - 多模型API
  - 免费AI API
  - OpenAI代理
  - AI聚合服务
  - BYOK
  - 自动故障转移
  - 免费AI额度
image: /images/logo.svg
type: docs
weight: 12
comments: true
prev: /services/api/nvidia-nim
next: /contribute
sidebar:
  open: true
---

## 📋 服务概览

**服务名称：** Vercel AI Gateway API  
**所属提供者：** [Vercel](/providers/vercel-ai-gateway)  
**API 端点：** 统一网关端点（通过 Vercel AI SDK 访问）  
**服务类型：** 免费试用（每月 $5 免费额度）+ 付费使用  
**注册要求：** 需要 Vercel 账户

---

## ✅ 服务说明

Vercel AI Gateway API 是 Vercel 提供的统一 AI 模型访问网关，通过单一接口让开发者访问来自多个提供商的数百种 AI 模型。

### 主要特点

- **🌐 统一接口：** 一个端点访问所有提供商的模型
- **🔄 自动故障转移：** 提供商故障时自动切换到备用提供商
- **💰 透明定价：** 按上游提供商列表价格，零加价
- **🔑 支持 BYOK：** 可使用自己的 API 密钥，完全无加价
- **⚡ 高性能：** Vercel 不设速率限制，由上游提供商决定
- **📊 统一计费：** 所有费用通过 Vercel 统一结算

---

## 🎁 支持的提供商

Vercel AI Gateway 支持多家主流 AI 提供商：

### 提供商列表

| 提供商 | 支持状态 | 主要模型 | 特点 |
|--------|---------|---------|------|
| **OpenAI** | ✅ | GPT-4o, GPT-4, GPT-3.5 | 业界领先 |
| **Anthropic** | ✅ | Claude 3.5, Claude 3 | 长上下文 |
| **Google** | ✅ | Gemini 系列 | 多模态 |
| **Meta** | ✅ | Llama 系列 | 开源模型 |
| **xAI** | ✅ | Grok | 实时信息 |
| **其他** | ✅ | 更多模型持续添加中 | 多样选择 |

**注意：** 具体可用模型列表请参考 [Vercel AI SDK 文档](https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway)。

---

## 🔢 配额和限制

### 免费层级限制

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每月免费额度** | $5 | 每个团队账户每月自动刷新 |
| **可用模型** | 全部模型 | 所有提供商的模型都可使用 |
| **速率限制** | 上游决定 | Vercel 不设限制，由上游提供商决定 |
| **并发请求** | 上游决定 | 取决于上游提供商 |
| **需要信用卡** | ❌ | 免费额度不需要信用卡 |

### ⚠️ 重要限制

1. **免费额度限制：** 一旦购买 AI Gateway Credits，账户将转为付费模式，不再每月获得 $5 免费额度。
2. **上游速率限制：** Vercel 不设速率限制，但各提供商有自己的限制，需遵守上游提供商的政策。
3. **模型可用性：** 模型可用性取决于上游提供商，可能因地区或账户类型而异。

### 配额重置时间

- **免费额度：** 每 30 天自动刷新
- **付费使用：** 按实际使用量计费，无重置周期

---

## 💰 价格说明

### 免费试用

- **免费额度：** 每个团队账户每月 $5
- **有效期：** 每 30 天自动刷新
- **获取方式：** 注册 Vercel 账户后自动获得

### 付费定价

| 模式 | 定价规则 | 加价比例 | 说明 |
|------|---------|---------|------|
| **使用 Gateway Credits** | 上游列表价格 | 0% | 通过 Vercel 统一计费 |
| **BYOK 模式** | 上游列表价格 | 0% | 使用自己的 API 密钥 |

**注意：** 
- Vercel AI Gateway 对所有模式都不加价（0% markup）
- 实际费用取决于使用的模型和上游提供商定价
- 具体价格请参考各提供商的官方定价页面

---

## 🚀 如何使用

### 前提条件

**1. 注册 Vercel 账户**

请先 [注册 Vercel 账户](/providers/vercel-ai-gateway#注册步骤)

**2. 选择使用模式**

Vercel AI Gateway 支持两种使用模式：

**模式 1：使用 Gateway Credits（推荐新手）**
- 无需管理多个 API 密钥
- 统一计费，便于管理
- 每月 $5 免费额度

**模式 2：BYOK（自带密钥）**
- 使用自己的 API 密钥
- Vercel 零加价（0%）
- 适合已有 API 密钥的用户

---

## 💻 代码示例

### 安装依赖

```bash {filename="Bash"}
npm install ai @ai-sdk/openai @vercel/ai-gateway
```

### Python 示例（使用 OpenAI SDK）

**基本使用（Gateway Credits 模式）：**

```python {filename="Python"}
from openai import OpenAI

# 初始化客户端
client = OpenAI(
    base_url="https://gateway.ai.cloudflare.com/v1/{account_id}/{gateway_id}/openai",
    api_key="YOUR_VERCEL_API_KEY"  # ⬅️ 替换为您的 Vercel API 密钥
)

# 发送请求
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "介绍一下 Vercel AI Gateway 的优势"}
    ],
    max_tokens=1000
)

# 打印响应
print(response.choices[0].message.content)

# 查看 Token 使用情况
print(f"\n使用 Tokens: {response.usage.total_tokens}")
```

**流式输出示例：**

```python {filename="Python"}
# 流式输出
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "user", "content": "写一首关于云计算的诗"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

---

### Node.js 示例（使用 Vercel AI SDK）

**基本使用：**

```javascript {filename="JavaScript"}
import { createAI } from '@ai-sdk/openai';
import { generateText } from 'ai';

// 配置 AI Gateway
const ai = createAI({
  apiKey: process.env.VERCEL_API_KEY,
  // 启用 Gateway
  gateway: {
    enabled: true
  }
});

async function main() {
  // 使用 OpenAI 模型
  const { text } = await generateText({
    model: ai('gpt-4o'),
    prompt: '介绍一下 Vercel AI Gateway 的优势',
  });

  console.log(text);
}

main();
```

**使用多个提供商（故障转移）：**

```javascript {filename="JavaScript"}
import { createAI } from '@ai-sdk/openai';
import { createAnthropic } from '@ai-sdk/anthropic';
import { generateText } from 'ai';

// 配置主提供商
const openai = createAI({
  apiKey: process.env.OPENAI_API_KEY,
  gateway: { enabled: true }
});

// 配置备用提供商
const anthropic = createAnthropic({
  apiKey: process.env.ANTHROPIC_API_KEY,
  gateway: { enabled: true }
});

async function generateWithFallback() {
  try {
    // 首先尝试 OpenAI
    const { text } = await generateText({
      model: openai('gpt-4o'),
      prompt: 'Hello, world!',
    });
    return text;
  } catch (error) {
    console.log('OpenAI 失败，切换到 Anthropic');
    // 失败时自动切换到 Anthropic
    const { text } = await generateText({
      model: anthropic('claude-3-5-sonnet-20241022'),
      prompt: 'Hello, world!',
    });
    return text;
  }
}

generateWithFallback();
```

---

### BYOK 模式示例

```javascript {filename="JavaScript"}
import { createAI } from '@ai-sdk/openai';
import { generateText } from 'ai';

// 使用自己的 OpenAI API 密钥
const openai = createAI({
  apiKey: process.env.OPENAI_API_KEY,  // 您自己的密钥
  gateway: {
    enabled: true,
    byok: true  // 启用 BYOK 模式
  }
});

async function main() {
  const { text } = await generateText({
    model: openai('gpt-4o'),
    prompt: '使用 BYOK 模式调用',
  });

  console.log(text);
}

main();
```

---

### cURL 示例

**基本请求（需根据具体配置调整）：**

```bash {filename="Bash"}
curl https://api.vercel.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_VERCEL_API_KEY" \
  -d '{
    "model": "openai:gpt-4o",
    "messages": [
      {
        "role": "user",
        "content": "Hello, Vercel AI Gateway!"
      }
    ]
  }'
```

**注意：** 具体的端点和请求格式可能因配置而异，请参考 [官方文档](https://vercel.com/docs/ai-gateway) 了解最新信息。

---

## 🌟 核心优势

### 技术优势

1. **简化集成：**
   - 无需管理多个 API 密钥和账户
   - 统一的接口降低学习成本
   - 快速在不同提供商之间切换

2. **高可用性：**
   - 自动故障转移机制
   - 多提供商冗余
   - 提高服务稳定性

3. **成本优化：**
   - 零加价策略
   - 支持 BYOK 降低成本
   - 透明的定价机制

### 与其他方案对比

| 特性 | Vercel AI Gateway | 直接使用提供商 | 其他 Gateway |
|------|------------------|---------------|--------------|
| 统一接口 | ✅ | ❌ | ✅ |
| 自动故障转移 | ✅ | ❌ | 部分支持 |
| 定价加价 | 0% | 0% | 5-20% |
| 免费额度 | $5/月 | 各提供商不同 | 通常无 |
| 支持 BYOK | ✅ | N/A | 部分支持 |
| 统一计费 | ✅ | ❌ | ✅ |

---

## 💡 实用建议

### ✅ 推荐做法

1. **充分利用免费额度：**
   - 使用免费额度测试不同提供商的模型
   - 评估各模型的性能和成本
   - 找到最适合您需求的模型

2. **配置故障转移：**
   - 为关键服务配置多个提供商
   - 设置合理的超时和重试策略
   - 监控各提供商的可用性

3. **使用 BYOK 降低成本：**
   - 如果已有 API 密钥，使用 BYOK 模式
   - 享受 Vercel Gateway 的便利，无需额外成本
   - 灵活控制各提供商的使用

### 🎯 最佳实践

**优化请求：**
- 合理设置 max_tokens 避免浪费
- 使用流式输出提升用户体验
- 缓存常见查询结果

**错误处理：**

```javascript {filename="JavaScript"}
import { generateText } from 'ai';

async function robustGenerate(model, prompt, maxRetries = 3) {
  for (let i = 0; i < maxRetries; i++) {
    try {
      const { text } = await generateText({
        model,
        prompt,
      });
      return text;
    } catch (error) {
      console.error(`尝试 ${i + 1} 失败:`, error.message);
      
      if (i === maxRetries - 1) {
        throw new Error('所有重试均失败');
      }
      
      // 指数退避
      await new Promise(resolve => 
        setTimeout(resolve, Math.pow(2, i) * 1000)
      );
    }
  }
}
```

**监控使用情况：**
- 定期检查 Vercel Dashboard 的使用统计
- 设置预算警报避免超支
- 分析各模型的成本效益

### ⚠️ 注意事项

1. **免费额度管理：** 避免在月底前用完所有免费额度，合理分配使用。
2. **提供商限制：** 了解各上游提供商的速率限制和使用政策。
3. **数据隐私：** 确认各提供商的数据使用政策，选择符合要求的模型。
4. **地区限制：** 部分提供商的模型可能在某些地区不可用。

---

## 🎯 实际应用案例

### 案例 1：多模型对比应用

**场景描述：** 构建一个应用，同时调用多个模型并对比结果。

```javascript {filename="JavaScript"}
import { createAI } from '@ai-sdk/openai';
import { createAnthropic } from '@ai-sdk/anthropic';
import { generateText } from 'ai';

const openai = createAI({
  apiKey: process.env.OPENAI_API_KEY,
  gateway: { enabled: true }
});

const anthropic = createAnthropic({
  apiKey: process.env.ANTHROPIC_API_KEY,
  gateway: { enabled: true }
});

async function compareModels(prompt) {
  const models = [
    { name: 'GPT-4o', provider: openai('gpt-4o') },
    { name: 'Claude 3.5 Sonnet', provider: anthropic('claude-3-5-sonnet-20241022') }
  ];

  const results = await Promise.all(
    models.map(async ({ name, provider }) => {
      const startTime = Date.now();
      const { text } = await generateText({
        model: provider,
        prompt,
      });
      const duration = Date.now() - startTime;

      return { name, text, duration };
    })
  );

  return results;
}

// 使用示例
const results = await compareModels('解释量子计算的基本原理');
results.forEach(({ name, text, duration }) => {
  console.log(`\n=== ${name} (${duration}ms) ===`);
  console.log(text);
});
```

### 案例 2：高可用聊天机器人

**场景描述：** 构建具有自动故障转移的聊天机器人。

```javascript {filename="JavaScript"}
import { generateText } from 'ai';

const providers = [
  { name: 'OpenAI', model: openai('gpt-4o'), priority: 1 },
  { name: 'Anthropic', model: anthropic('claude-3-5-sonnet-20241022'), priority: 2 },
  { name: 'Google', model: google('gemini-pro'), priority: 3 }
];

async function chatWithFallback(message) {
  // 按优先级排序
  const sortedProviders = providers.sort((a, b) => a.priority - b.priority);

  for (const provider of sortedProviders) {
    try {
      console.log(`尝试使用 ${provider.name}...`);
      
      const { text } = await generateText({
        model: provider.model,
        prompt: message,
      });

      console.log(`✅ ${provider.name} 成功`);
      return {
        text,
        provider: provider.name
      };
    } catch (error) {
      console.error(`❌ ${provider.name} 失败: ${error.message}`);
      continue;
    }
  }

  throw new Error('所有提供商均不可用');
}

// 使用示例
const response = await chatWithFallback('你好，介绍一下自己');
console.log(`回复来自 ${response.provider}:`, response.text);
```

---

## 🔧 常见问题

**Q: Vercel AI Gateway 与其他 AI Gateway 服务有什么区别？**  
A: Vercel AI Gateway 的核心优势是零加价、自动故障转移和统一计费。许多其他 Gateway 服务会收取 5-20% 的加价。

**Q: 免费额度用完后会自动扣费吗？**  
A: 不会。免费额度用完后，如果没有购买 Gateway Credits，请求将失败。您需要主动购买额度才能继续使用。

**Q: BYOK 模式下还享受故障转移功能吗？**  
A: 可以，但需要自己配置多个提供商的密钥。Vercel 不会自动在不同提供商之间转移。

**Q: 支持哪些编程语言？**  
A: Vercel AI SDK 主要支持 JavaScript/TypeScript。对于其他语言，可以使用标准的 HTTP 请求或各提供商的官方 SDK。

**Q: 可以在 Vercel 之外的平台使用 AI Gateway 吗？**  
A: 可以，Vercel AI Gateway 不限制部署平台，可以在任何支持 HTTP 请求的环境中使用。

**Q: 速率限制是多少？**  
A: Vercel 本身不设速率限制，具体限制取决于上游提供商。使用 Gateway Credits 时，Vercel 正在与提供商协商更高的限制。

---

## 🔗 相关资源

- **API 文档：** [https://vercel.com/docs/ai-gateway](https://vercel.com/docs/ai-gateway)
- **AI SDK 文档：** [https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway](https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway)
- **定价页面：** [https://vercel.com/docs/ai-gateway/pricing](https://vercel.com/docs/ai-gateway/pricing)
- **提供者主页：** [Vercel AI Gateway](/providers/vercel-ai-gateway)
- **开源 Chatbot 模板：** [https://github.com/vercel-labs/ai-chatbot-gateway](https://github.com/vercel-labs/ai-chatbot-gateway)
- **Vercel Dashboard：** [https://vercel.com/dashboard](https://vercel.com/dashboard)

---

## 📝 更新日志

- **2026年1月：** 继续提供每月 $5 免费额度
- **2024年12月：** Vercel AI Gateway 正式发布
- **2024年：** 持续添加更多 AI 提供商支持

---

**服务提供者：** [Vercel AI Gateway](/providers/vercel-ai-gateway)
