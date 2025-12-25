---
title: DeepSeek
type: docs
weight: 4
comments: true
prev: /providers/openrouter
next: /providers/cohere
sidebar:
  open: true
---

## 🏢 Provider Information

**Provider Name:** DeepSeek (Deep Seek)  
**Official Website:** https://www.deepseek.com  
**Console:** https://platform.deepseek.com  
**Type:** Freemium - Provides 9 million Tokens per month + 50 million Bonus Tokens

---

## 📋 Product Overview

DeepSeek is an AI company from China, focusing on developing powerful open-source large language models. DeepSeek's models excel in Chinese understanding, programming, and reasoning, especially the DeepSeek R1 series which has outstanding reasoning capabilities and is completely free to use.

**Core Advantages:**
- 🇨🇳 **Chinese Optimization** - Understanding and generating Chinese text better than most international models
- 💻 **Programming Expert** - Outstanding code generation and explanation capabilities
- 🧠 **Reasoning Capabilities** - R1 series has powerful logical reasoning abilities
- 🎁 **Extremely Generous Free Tier** - 9M tokens/month + 50M bonus tokens
- 🌍 **Fully Open-Source** - Model architecture and weights fully open

**Rating:** ⭐⭐⭐⭐⭐ (Best for Chinese!)

---

## 🔐 Registration and Account

### Registration Requirements

| Requirement | Required | Notes |
|------------|----------|-------|
| Account Registration | ✅ Required | Supports email, phone, WeChat |
| Email/Phone Verification | ✅ Required | Choose one to verify |
| Credit Card Binding | ❌ Not Required | Completely free, no payment info needed |
| Real-Name Verification | ❌ Not Required | No real-name authentication needed |

### Registration Steps

{{% steps %}}

#### Visit Official Website

Open browser, visit [https://www.deepseek.com](https://www.deepseek.com), click **"开放平台"** (Open Platform) or directly visit [https://platform.deepseek.com](https://platform.deepseek.com)

#### Register Account

Click **"登录/注册"** (Login/Register) in the upper right corner. Choose registration method:
- **Email Registration** (recommended)
- **Phone Registration** (supports mainland China numbers)
- **WeChat Scan Login** (fastest, for WeChat users)

#### Verify Email/Phone

- If using email: Check inbox, click verification link
- If using phone: Enter received SMS code
- If using WeChat: Scan code to log in, no verification needed

#### Complete Account Setup

After first login, fill in basic information (optional). Go to console: [https://platform.deepseek.com](https://platform.deepseek.com)

#### Create API Key

1. In the console, click **"API Keys"**
2. Click **"创建 API Key"** (Create API Key) button
3. Name the key (e.g., "My Free API Key")
4. Click **"确定"** (Confirm)
5. ⚠️ **Important:** Immediately copy and save your API key, can't be viewed again

{{% /steps %}}

---

## 🎯 Provided Services

DeepSeek provides two main services:

### 1. [Chat Service](/services/chatbot/deepseek)
- **Type:** Web conversation interface
- **Access URL:** https://chat.deepseek.com
- **Features:** Direct conversation, no registration/API key needed
- **Supports:** DeepSeek V3, DeepSeek R1

### 2. [API Service](/services/api/deepseek-api)
- **Type:** RESTful API
- **Features:** OpenAI API compatible format
- **Models:** DeepSeek V3, DeepSeek R1 (Thinking), DeepSeek R1 (Fast)
- **Quota:** 9M tokens/month + 50M bonus tokens

---

## 📊 Quota Overview

### Basic Free Tier (New Users)

| Limit Type | Quota | Notes |
|-----------|-------|-------|
| **Monthly Input Tokens** | 9 million tokens | ~4.5 million Chinese characters |
| **Monthly Output Tokens** | 9 million tokens | ~4.5 million Chinese characters |
| **Requests Per Minute (RPM)** | 60 requests | All models combined |
| **Tokens Per Minute (TPM)** | 60,000 tokens | All models combined |
| **Tokens Per Request** | 10,000 tokens | Single request limit |
| **Cost** | $0 | Completely free |

### Bonus Tokens (One-Time)

| Limit Type | Quota | Notes |
|-----------|-------|-------|
| **Bonus Input Tokens** | 50 million tokens | ~25 million Chinese characters |
| **Bonus Output Tokens** | 50 million tokens | ~25 million Chinese characters |
| **Validity** | Unlimited | Never expires |
| **Purpose** | High-frequency usage | Testing, development, production all applicable |

⚠️ **Important Notes:**
- Basic quota resets every natural month (first day at 00:00)
- Bonus tokens don't expire and can be accumulated
- Bonus tokens are used after basic quota is exhausted
- RPM and TPM limits apply to all models combined

---

## 🤖 Model Overview

### DeepSeek V3

| Parameter | Value | Notes |
|----------|-------|-------|
| **Model Name** | `deepseek-chat` | General chat model |
| **Parameters** | 671B (Mixture of Experts) | 671 billion parameters, only 37B activated per request |
| **Context Length** | 128K tokens | Approximately 64,000 Chinese characters |
| **Capabilities** | General capabilities | Excels at Chinese, coding, reasoning |
| **Update Time** | December 2024 | Latest version |

**Excels At:**
- 📝 Chinese text understanding and generation
- 💻 Code writing and explanation
- 🔍 Information extraction and summarization
- 🧮 Mathematical and logical reasoning
- 📚 Long text processing

### DeepSeek R1 (Thinking Mode)

| Parameter | Value | Notes |
|----------|-------|-------|
| **Model Name** | `deepseek-reasoner` | Reasoning-specialized model |
| **Parameters** | Same as V3 | 671B MoE architecture |
| **Context Length** | 64K tokens | Approximately 32,000 Chinese characters |
| **Capabilities** | Deep reasoning | Displays reasoning process |
| **Features** | Thinking chain visible | Can see model's reasoning steps |

**Excels At:**
- 🧠 Complex logical reasoning
- 🔬 Mathematical problem solving
- 💡 Creative problem-solving
- 📊 Data analysis and interpretation
- 🎯 Multi-step task planning

**Special Note:**
- R1 model displays reasoning process when answering, consumes more tokens
- Suitable for tasks requiring high reasoning capabilities
- Response time may be longer than V3

---

## 🌟 Core Advantages

### 1. Chinese Optimization

**Superior Chinese Understanding:**
- Training data includes large amounts of high-quality Chinese text
- Better understanding of Chinese context and cultural nuances
- More accurate Chinese idioms and colloquialisms

**Chinese-English Bilingual:**
- Supports seamless Chinese-English mixing
- Accurate translation results
- Preserves semantic and emotional nuances in translation

### 2. Programming Capabilities

**Code Generation:**
- Supports 20+ programming languages
- Complete project-level code
- Code comments and documentation

**Code Understanding:**
- Code interpretation and explanation
- Bug location and fixes
- Code refactoring suggestions

### 3. Reasoning Capabilities

**Deep Reasoning:**
- R1 model has powerful reasoning chain capabilities
- Can handle complex logical problems
- Visible reasoning process, high transparency

**Multi-step Task:**
- Automatic task decomposition
- Step-by-step execution plan
- Clear thinking logic

### 4. Extremely Generous Free Tier

**Monthly Quota:**
- 9M tokens/month, equal to about 4.5M Chinese characters
- Can handle approximately 150 long conversations (30,000 chars each)
- Sufficient for individual developer daily usage

**Bonus Tokens:**
- One-time 50M tokens, never expires
- Can process approximately 25M Chinese characters
- Suitable for high-frequency usage scenarios

---

## ⚠️ Usage Notes

### Quota Management

- Monthly basic quota resets on the 1st of each month
- Bonus tokens don't expire, use with confidence
- Monitor token consumption in console to avoid overuse

### Model Selection

- **General tasks:** Use DeepSeek V3 (`deepseek-chat`), fast and comprehensive
- **Complex reasoning:** Use DeepSeek R1 (`deepseek-reasoner`), powerful reasoning but higher token consumption
- **Long text processing:** V3 supports 128K context, more suitable for long texts

### Rate Limits

- **RPM (Requests Per Minute):** 60 requests, sufficient for most applications
- **TPM (Tokens Per Minute):** 60,000 tokens, be mindful in high-frequency scenarios
- **Request Token Limit:** Single request maximum 10,000 tokens

### API Key Security

- Don't expose keys in public code
- Can create different keys for different projects
- Regularly check usage statistics, promptly detect abnormal usage

---

## 📊 Comparison with Other Services

| Feature | DeepSeek | Google AI Studio | OpenRouter |
|---------|----------|------------------|------------|
| Free Quota | 🏆 9M/month + 50M bonus | 1,500 times/day | 50-1,000 times/day |
| Chinese Optimization | 🏆 Excellent | Good | Varies |
| Reasoning Capability | 🏆 Excellent (R1) | Good (Gemini) | Varies |
| Code Generation | 🏆 Excellent | Good | Varies |
| Context Length | 128K | 1M | Varies |
| OpenAI Compatible | ✅ | ❌ | ✅ |
| Mainland China Access | 🏆 Very Good | 🔧 VPN Required | 🔧 Stable Network Required |

---

## 💡 Selection Suggestions

### Reasons to Choose DeepSeek

✅ **Highly Recommended:**
- Primary language is Chinese
- Need powerful Chinese text processing capabilities
- Focus on programming and code generation
- Need deep reasoning capabilities
- Mainly use from mainland China

✅ **Suitable Scenarios:**
- Chinese chatbot development
- Code generation and interpretation
- Chinese text analysis
- Logical reasoning tasks
- Long text processing

❌ **Not Suitable For:**
- Need multimodal features (images, audio) - choose Google AI Studio
- Need extremely high request frequency - choose Groq
- Need access to various different models - choose OpenRouter

---

## 🔗 Related Links

- **Official Website:** [https://www.deepseek.com](https://www.deepseek.com)
- **Open Platform:** [https://platform.deepseek.com](https://platform.deepseek.com)
- **Chat Page:** [https://chat.deepseek.com](https://chat.deepseek.com)
- **API Documentation:** [https://platform.deepseek.com/api-docs](https://platform.deepseek.com/api-docs)
- **Model Details:** [https://platform.deepseek.com/docs](https://platform.deepseek.com/docs)
- **GitHub:** [https://github.com/deepseek-ai](https://github.com/deepseek-ai)

---

## 📝 Changelog

- **January 2025:** DeepSeek R1 officially released, powerful reasoning capabilities
- **December 2024:** DeepSeek V3 released, significant performance improvement
- **2024:** Continuously optimizing Chinese and code generation capabilities
- **2024:** Increasing free quota, adding bonus tokens

---

## 📧 Support & Feedback

- **Official Documentation:** [https://platform.deepseek.com/docs](https://platform.deepseek.com/docs)
- **API Consultation:** Contact via open platform
- **Issue Reporting:** Submit issues on GitHub
- **Community Discussion:** Join DeepSeek user community

