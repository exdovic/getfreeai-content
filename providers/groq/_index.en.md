---
title: Groq
type: docs
weight: 2
comments: true
prev: /providers/google-ai-studio
next: /providers/openrouter
sidebar:
  open: true
---

## 🏢 Provider Information

**Provider Name:** Groq  
**Official Website:** https://groq.com  
**Developer Console:** https://console.groq.com  
**Type:** Free Service (Permanently free with usage limits)

---

## 📋 Product Overview

Groq is a company providing ultra-high-speed AI inference services, based on its self-developed **LPU (Language Processing Unit)** chip technology, offering the industry's fastest AI inference speed.

**Core Features:**
- ⚡ **Industry's Fastest Inference Speed** - 800+ tokens/s
- 🔧 **LPU Chip Powered** - Hardware optimized for language models
- 🎁 **Ultra-High Free Quota** - 14,400 requests/day
- 🔄 **OpenAI API Compatible** - Seamlessly switch existing code
- 🚀 **Real-time Response** - Extremely low latency conversation experience

**Rating:** ⭐⭐⭐⭐⭐ (Speed King!)

---

## 🔐 Registration and Account

### Registration Requirements

| Requirement | Required | Notes |
|------------|----------|-------|
| Account Registration | ✅ Required | Email or Google/GitHub account |
| Email Verification | ✅ Required | Need to verify email |
| Phone Verification | ❌ Not Required | Usually not needed |
| Credit Card Binding | ✅ Required | For identity verification, no charges |

### Registration Steps

{{% steps %}}

#### Register Account

Visit [https://console.groq.com](https://console.groq.com), click the **"Sign Up"** button. Choose registration method:
- Use Google account (recommended, fast)
- Use GitHub account
- Use email registration

#### Verify Email

If using email registration, check your inbox, click the verification link to complete email verification, return to Groq Console.

#### Verify Identity (Credit Card Binding)

After logging in, the system will prompt you to verify your identity:
1. Click the **"Verify Account"** button
2. Enter credit card information (supports Visa, MasterCard, AmEx, etc.)
3. ⚠️ **Important Note:** This is only for identity verification, no charges will occur
4. After successful verification, you can use the free service

#### Get API Key

1. Select **"API Keys"** in the left menu
2. Click the **"Create API Key"** button
3. Name your API key (e.g., "My First Key")
4. Click **"Submit"** to create
5. ⚠️ **Important:** Immediately copy and save your API key, you won't be able to view it again

{{% /steps %}}

---

## 🎯 Provided Services

Groq provides two main services:

### 1. [Playground Service](/services/chatbot/groq)
- **Type:** Web conversation interface
- **Access URL:** https://console.groq.com/playground
- **Features:** Real-time inference speed display, intuitive parameter adjustment
- **Supports:** All Groq models

### 2. [API Service](/services/api/groq-api)
- **Type:** RESTful API
- **Features:** Fully compatible with OpenAI API format
- **Models:** Llama 3.3/3.1, Mixtral, Gemma 2, DeepSeek R1, etc.
- **Quota:** 14,400 requests/day

---

## 📊 Quota Overview

### Free Tier Quota

| Limit Type | Quota | Notes |
|-----------|-------|-------|
| **Daily Requests** | 14,400 requests/day | Shared across all models |
| **Requests Per Minute** | 30 requests/min | Shared across all models |
| **Daily Tokens** | 20,000 tokens/day | Input + output total |
| **Tokens Per Minute** | 6,000 tokens/min | Input + output total |

⚠️ **Important Notes:**
- Shared quota: All models share the same account quota
- Daily reset: Quota resets daily at UTC midnight
- Token calculation: Both input and output tokens count toward quota

---

## 🤖 Supported Models

### Llama Series (Meta)

| Model Name | Parameters | Context Length | Use Cases |
|-----------|-----------|---------------|-----------|
| **Llama 3.3 70B** | 70B | 128K | Meta's latest model, powerful performance |
| **Llama 3.1 70B** | 70B | 128K | Complex tasks |
| **Llama 3.1 8B** | 8B | 128K | Lightweight and efficient |

### Other Open-Source Models

| Model Name | Parameters | Context Length | Features |
|-----------|-----------|---------------|----------|
| **Mixtral 8x7B** | 47B | 32K | Mistral mixture of experts model |
| **Gemma 2 9B** | 9B | 8K | Google open-source model |
| **DeepSeek R1 Distill Llama 70B** | 70B | 32K | Reasoning expert model |

---

## 🌟 Core Technical Advantages

### LPU Chip Technology

**Language Processing Unit:**
- Groq's self-developed specialized chip
- Optimized for sequential computation of language models
- Extremely low latency: over 10x lower than GPUs
- High throughput: Can achieve 800+ tokens/s generation speed

### Speed Comparison

| Provider | Typical Speed | Groq Advantage |
|---------|--------------|----------------|
| Groq | 800+ tokens/s | Baseline |
| OpenAI GPT-4 | 20-40 tokens/s | **20x Faster** |
| Anthropic Claude | 30-50 tokens/s | **16x Faster** |
| Other Cloud Services | 50-100 tokens/s | **8x Faster** |

### Real-time Application Scenarios

- **Chatbots:** Nearly zero-latency conversation experience
- **Code Assistants:** Real-time code completion and generation
- **Content Creation:** Rapid long-text generation
- **Data Analysis:** Real-time data interpretation

---

## ⚠️ Usage Notes

### Credit Card Verification

- Although the service is free, credit card binding is required for identity verification
- This is to prevent abuse, no charges will occur
- No automatic charges after free quota is exhausted

### Quota Management

- Pay attention to daily and per-minute limits to avoid exceeding quota
- View quota usage on the Usage page in Console
- Reasonably allocate quota for different applications

### API Key Security

- Don't expose API keys in public code repositories
- Use environment variables or config files to manage keys
- Regularly rotate API keys

### Network Requirements

- Groq supports most regions globally
- Mainland China may require stable network environment

---

## 📊 Comparison with Other Services

| Feature | Groq | Google AI Studio | OpenRouter |
|---------|------|------------------|------------|
| Inference Speed | 🏆 800+ tokens/s | 50-100 tokens/s | Varies by provider |
| Daily Requests | 14,400 | 1,500 | 50-1,000 |
| Daily Tokens | 20K-1M | 15M (Flash) | Unlimited |
| Credit Card Required | ✅ Verification | ❌ | ❌ |
| OpenAI Compatible | ✅ Fully Compatible | ❌ Not Compatible | ✅ Compatible |
| Multimodal Support | ❌ | ✅ | Some models |
| Mainland China Access | 🔧 Stable Network Required | 🔧 VPN Required | ✅ Good |

---

## 💡 Selection Suggestions

### Reasons to Choose Groq

✅ **Highly Recommended:**
- Need extremely fast response speed
- Building real-time conversation applications
- High-frequency calls (14,400 times/day)
- Need OpenAI API compatibility

❌ **Not Suitable For:**
- Need multimodal support (images, audio)
- Need ultra-long context (>128K)
- Cannot provide credit card verification

---

## 📈 Paid Plans (Optional)

If free quota isn't enough, Groq offers flexible paid options:

| Plan | Price | Features |
|------|-------|----------|
| Free | $0 | 14,400 req/day |
| Pay-as-you-go | Pay by usage | Higher quotas, billed by tokens |
| Enterprise | Custom | Dedicated support, SLA guarantee |

**Pricing Examples:**
- Llama 3.3 70B: ~$0.59/M tokens
- Llama 3.1 8B: ~$0.05/M tokens

---

## 🔗 Related Links

- **Official Website:** [https://groq.com](https://groq.com)
- **Developer Console:** [https://console.groq.com](https://console.groq.com)
- **API Documentation:** [https://console.groq.com/docs](https://console.groq.com/docs)
- **Python SDK:** [GitHub - groq-python](https://github.com/groq/groq-python)
- **Node.js SDK:** [GitHub - groq-typescript](https://github.com/groq/groq-typescript)
- **Community Discussion:** [Discord - Groq](https://discord.gg/groq)
- **Status Page:** [https://status.groq.com](https://status.groq.com)
- **Blog:** [https://groq.com/blog](https://groq.com/blog)

---

## 📝 Changelog

- **December 2024:** Support for DeepSeek R1 Distill series reasoning models
- **November 2024:** Released Llama 3.3 70B support
- **October 2024:** Increased free tier quota to 14,400 requests/day
- **2024:** Continuously optimizing LPU performance, improving inference speed

---

## 📧 Support & Feedback

- **Official Support:** support@groq.com
- **Discord Community:** [https://discord.gg/groq](https://discord.gg/groq)
- **Issue Reporting:** [https://console.groq.com/support](https://console.groq.com/support)
- **Feature Requests:** Contact via Discord or email

