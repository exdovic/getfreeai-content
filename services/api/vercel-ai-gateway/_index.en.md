---
title: "Vercel AI Gateway API - Unified AI Model Access Interface"
linkTitle: "API - Vercel AI Gateway"
description: "Vercel AI Gateway API provides unified interface to access hundreds of AI models! $5 free credits per month, supports OpenAI, Anthropic, Google and more, automatic failover, transparent pricing with no markup, BYOK support, OpenAI-compatible format."
keywords:
  - Vercel AI Gateway API
  - AI Gateway
  - Unified AI Interface
  - Multi-Model API
  - Free AI API
  - OpenAI Proxy
  - AI Aggregation Service
  - BYOK
  - Automatic Failover
  - Free AI Credits
image: /images/logo.svg
type: docs
weight: 12
comments: true
prev: /services/api/nvidia-nim
next: /contribute
sidebar:
  open: true
---

## 📋 Service Overview

**Service Name:** Vercel AI Gateway API  
**Provider:** [Vercel](/providers/vercel-ai-gateway)  
**API Endpoint:** Unified gateway endpoint (accessed via Vercel AI SDK)  
**Service Type:** Free Trial ($5 monthly credits) + Paid Usage  
**Registration Requirements:** Vercel account required

---

## ✅ Service Description

Vercel AI Gateway API is a unified AI model access gateway provided by Vercel, allowing developers to access hundreds of AI models from multiple providers through a single interface.

### Key Features

- **🌐 Unified Interface:** Access all provider models through one endpoint
- **🔄 Automatic Failover:** Automatically switches to backup provider when failures occur
- **💰 Transparent Pricing:** Based on upstream provider list prices with zero markup
- **🔑 BYOK Support:** Use your own API keys with zero markup
- **⚡ High Performance:** Vercel sets no rate limits; determined by upstream providers
- **📊 Unified Billing:** All costs settled through Vercel billing

---

## 🎁 Supported Providers

Vercel AI Gateway supports multiple mainstream AI providers:

### Provider List

| Provider | Support Status | Main Models | Features |
|----------|---------------|-------------|----------|
| **OpenAI** | ✅ | GPT-4o, GPT-4, GPT-3.5 | Industry-leading |
| **Anthropic** | ✅ | Claude 3.5, Claude 3 | Long context |
| **Google** | ✅ | Gemini series | Multimodal |
| **Meta** | ✅ | Llama series | Open-source |
| **xAI** | ✅ | Grok | Real-time info |
| **Others** | ✅ | More models being added | Diverse options |

**Note:** For the complete list of available models, please refer to the [Vercel AI SDK Documentation](https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway).

---

## 🔢 Quotas and Limits

### Free Tier Limits

| Limit Item | Quota | Description |
|------------|-------|-------------|
| **Monthly Free Credits** | $5 | Auto-refreshes monthly for each team account |
| **Available Models** | All models | All provider models can be used |
| **Rate Limits** | Upstream decides | Vercel sets no limits; determined by upstream providers |
| **Concurrent Requests** | Upstream decides | Depends on upstream providers |
| **Credit Card Required** | ❌ | No credit card needed for free credits |

### ⚠️ Important Limitations

1. **Free Credit Limitations:** Once you purchase AI Gateway Credits, your account converts to paid status and no longer receives $5 monthly free credits.
2. **Upstream Rate Limits:** Vercel sets no rate limits, but each provider has their own restrictions. Must comply with upstream provider policies.
3. **Model Availability:** Model availability depends on upstream providers and may vary by region or account type.
4. **BYOK Usage:** When using BYOK (Bring Your Own Key), you theoretically bypass Gateway Credits billing, but thorough testing before production is recommended.

### Quota Reset Time

- **Free Credits:** Auto-refreshes every 30 days
- **Paid Usage:** Billed based on actual usage; no reset cycle

---

## 💰 Pricing

### Free Trial

- **Free Credits:** $5 per team account per month
- **Validity:** Auto-refreshes every 30 days
- **How to Get:** Automatically granted when you first use AI Gateway after registration
- **Note:** Once you purchase AI Gateway Credits (top-up), you'll switch to paid mode and no longer receive the monthly free $5

### Paid Pricing

| Mode | Pricing Rule | Markup | Description |
|------|-------------|---------|-------------|
| **Using Gateway Credits** | Upstream list price | 0% | Unified billing through Vercel |
| **BYOK Mode** | Upstream list price | 0% | Use your own API keys |

**Note:** 
- Vercel AI Gateway adds zero markup (0%) for all modes
- Actual costs depend on models used and upstream provider pricing
- For specific prices, please refer to each provider's official pricing page

---

## 🚀 How to Use

### Prerequisites

**1. Register Vercel Account**

Please first [register a Vercel account](/providers/vercel-ai-gateway#registration-steps)

**2. Choose Usage Mode**

Vercel AI Gateway supports two usage modes:

**Mode 1: Using Gateway Credits (Recommended for beginners)**
- No need to manage multiple API keys
- Unified billing for easy management
- $5 monthly free credits

**Mode 2: BYOK (Bring Your Own Key)**
- Use your own API keys
- Vercel zero markup (0%)
- Suitable for users who already have API keys

---

## 💻 Code Examples

### Install Dependencies

```bash {filename="Bash"}
npm install ai @ai-sdk/openai @vercel/ai-gateway
```

### Python Example (Using OpenAI SDK)

**Basic Usage (Gateway Credits Mode):**

```python {filename="Python"}
from openai import OpenAI

# Initialize client
# Note: Use the actual base_url from your Vercel Dashboard AI Gateway settings
client = OpenAI(
    base_url="https://gateway.vercel.ai/v1",  # Example endpoint, replace with actual
    api_key="YOUR_VERCEL_API_KEY"  # ⬅️ Replace with your Vercel API key
)

# Send request
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain the advantages of Vercel AI Gateway"}
    ],
    max_tokens=1000
)

# Print response
print(response.choices[0].message.content)

# Check token usage
print(f"\nTokens used: {response.usage.total_tokens}")
```

**Streaming Output Example:**

```python {filename="Python"}
# Streaming output
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "user", "content": "Write a poem about cloud computing"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

---

### Node.js Example (Using Vercel AI SDK)

**Basic Usage:**

```javascript {filename="JavaScript"}
import { createAI } from '@ai-sdk/openai';
import { generateText } from 'ai';

// Configure AI Gateway
const ai = createAI({
  apiKey: process.env.VERCEL_API_KEY,
  // Enable Gateway
  gateway: {
    enabled: true
  }
});

async function main() {
  // Use OpenAI model
  const { text } = await generateText({
    model: ai('gpt-4o'),
    prompt: 'Explain the advantages of Vercel AI Gateway',
  });

  console.log(text);
}

main();
```

**Using Multiple Providers (Failover):**

```javascript {filename="JavaScript"}
import { createAI } from '@ai-sdk/openai';
import { createAnthropic } from '@ai-sdk/anthropic';
import { generateText } from 'ai';

// Configure primary provider
const openai = createAI({
  apiKey: process.env.OPENAI_API_KEY,
  gateway: { enabled: true }
});

// Configure backup provider
const anthropic = createAnthropic({
  apiKey: process.env.ANTHROPIC_API_KEY,
  gateway: { enabled: true }
});

async function generateWithFallback() {
  try {
    // First try OpenAI
    const { text } = await generateText({
      model: openai('gpt-4o'),
      prompt: 'Hello, world!',
    });
    return text;
  } catch (error) {
    console.log('OpenAI failed, switching to Anthropic');
    // Automatically switch to Anthropic on failure
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

### BYOK Mode Example

```javascript {filename="JavaScript"}
import { createAI } from '@ai-sdk/openai';
import { generateText } from 'ai';

// Use your own OpenAI API key
const openai = createAI({
  apiKey: process.env.OPENAI_API_KEY,  // Your own key
  gateway: {
    enabled: true,
    byok: true  // Enable BYOK mode
  }
});

async function main() {
  const { text } = await generateText({
    model: openai('gpt-4o'),
    prompt: 'Call using BYOK mode',
  });

  console.log(text);
}

main();
```

---

### cURL Example

**Basic Request (adjust based on specific configuration):**

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

**Note:** Specific endpoint and request format may vary by configuration. Please refer to the [official documentation](https://vercel.com/docs/ai-gateway) for the latest information.

---

## 🌟 Core Advantages

### Technical Advantages

1. **Simplified Integration:**
   - No need to manage multiple API keys and accounts
   - Unified interface reduces learning curve
   - Quick switching between different providers

2. **High Availability:**
   - Automatic failover mechanism
   - Multi-provider redundancy
   - Improved service stability

3. **Cost Optimization:**
   - Zero markup strategy
   - BYOK support to reduce costs
   - Transparent pricing mechanism

### Comparison with Other Solutions

| Feature | Vercel AI Gateway | Direct Provider Use | Other Gateways |
|---------|------------------|-------------------|----------------|
| Unified Interface | ✅ | ❌ | ✅ |
| Auto Failover | ✅ | ❌ | Partial |
| Pricing Markup | 0% | 0% | 5-20% |
| Free Credits | $5/month | Varies by provider | Usually none |
| BYOK Support | ✅ | N/A | Partial |
| Unified Billing | ✅ | ❌ | ✅ |

---

## 💡 Best Practices

### ✅ Recommended Approaches

1. **Maximize Free Credits:**
   - Use free credits to test different provider models
   - Evaluate model performance and costs
   - Find the best model for your needs

2. **Configure Failover:**
   - Configure multiple providers for critical services
   - Set reasonable timeout and retry strategies
   - Monitor provider availability

3. **Use BYOK to Reduce Costs:**
   - Use BYOK mode if you already have API keys
   - Enjoy Vercel Gateway convenience without extra cost
   - Flexibly control usage across providers

### 🎯 Best Practices

**Optimize Requests:**
- Set reasonable max_tokens to avoid waste
- Use streaming output for better UX
- Cache common query results

**Error Handling:**

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
      console.error(`Attempt ${i + 1} failed:`, error.message);
      
      if (i === maxRetries - 1) {
        throw new Error('All retries failed');
      }
      
      // Exponential backoff
      await new Promise(resolve => 
        setTimeout(resolve, Math.pow(2, i) * 1000)
      );
    }
  }
}
```

**Monitor Usage:**
- Regularly check Vercel Dashboard usage statistics
- Set budget alerts to avoid overspending
- Analyze cost-effectiveness of each model

### ⚠️ Considerations

1. **Free Credit Management:** Avoid exhausting all free credits before month-end; allocate usage wisely.
2. **Provider Limits:** Understand rate limits and usage policies of upstream providers.
3. **Data Privacy:** Confirm data usage policies of each provider; choose models that meet requirements.
4. **Regional Restrictions:** Some provider models may be unavailable in certain regions.

---

## 🎯 Real-World Use Cases

### Case 1: Multi-Model Comparison Application

**Scenario:** Build an application that calls multiple models simultaneously and compares results.

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

// Usage example
const results = await compareModels('Explain the basic principles of quantum computing');
results.forEach(({ name, text, duration }) => {
  console.log(`\n=== ${name} (${duration}ms) ===`);
  console.log(text);
});
```

### Case 2: High-Availability Chatbot

**Scenario:** Build a chatbot with automatic failover.

```javascript {filename="JavaScript"}
import { generateText } from 'ai';

const providers = [
  { name: 'OpenAI', model: openai('gpt-4o'), priority: 1 },
  { name: 'Anthropic', model: anthropic('claude-3-5-sonnet-20241022'), priority: 2 },
  { name: 'Google', model: google('gemini-pro'), priority: 3 }
];

async function chatWithFallback(message) {
  // Sort by priority
  const sortedProviders = providers.sort((a, b) => a.priority - b.priority);

  for (const provider of sortedProviders) {
    try {
      console.log(`Trying ${provider.name}...`);
      
      const { text } = await generateText({
        model: provider.model,
        prompt: message,
      });

      console.log(`✅ ${provider.name} succeeded`);
      return {
        text,
        provider: provider.name
      };
    } catch (error) {
      console.error(`❌ ${provider.name} failed: ${error.message}`);
      continue;
    }
  }

  throw new Error('All providers unavailable');
}

// Usage example
const response = await chatWithFallback('Hello, introduce yourself');
console.log(`Response from ${response.provider}:`, response.text);
```

---

## 🔧 FAQ

**Q: What's the difference between Vercel AI Gateway and other AI Gateway services?**  
A: Vercel AI Gateway's core advantages are zero markup, automatic failover, and unified billing. Many other Gateway services charge 5-20% markup.

**Q: Will I be charged automatically when free credits run out?**  
A: No. When free credits are exhausted, requests will fail if you haven't purchased Gateway Credits. You need to actively purchase credits to continue.

**Q: Do I still get failover functionality in BYOK mode?**  
A: Yes, but you need to configure keys for multiple providers yourself. Vercel won't automatically transfer between different providers.

**Q: Which programming languages are supported?**  
A: Vercel AI SDK primarily supports JavaScript/TypeScript. For other languages, use standard HTTP requests or official SDKs from each provider.

**Q: Can I use AI Gateway outside Vercel platform?**  
A: Yes, Vercel AI Gateway doesn't restrict deployment platforms and can be used in any environment that supports HTTP requests.

**Q: What are the rate limits?**  
A: Vercel sets no rate limits; specific limits depend on upstream providers. When using Gateway Credits, Vercel is negotiating higher limits with providers.

---

## 🔗 Related Resources

- **API Documentation:** [https://vercel.com/docs/ai-gateway](https://vercel.com/docs/ai-gateway)
- **AI SDK Documentation:** [https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway](https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway)
- **Pricing Page:** [https://vercel.com/docs/ai-gateway/pricing](https://vercel.com/docs/ai-gateway/pricing)
- **Provider Homepage:** [Vercel AI Gateway](/providers/vercel-ai-gateway)
- **Open-source Chatbot Template:** [https://github.com/vercel-labs/ai-chatbot-gateway](https://github.com/vercel-labs/ai-chatbot-gateway)
- **Vercel Dashboard:** [https://vercel.com/dashboard](https://vercel.com/dashboard)

---

## 📝 Changelog

- **January 2026:** Continuing to provide $5 monthly free credits
- **December 2024:** Vercel AI Gateway officially launched
- **2024:** Continuously adding support for more AI providers

---

**Service Provider:** [Vercel AI Gateway](/providers/vercel-ai-gateway)
