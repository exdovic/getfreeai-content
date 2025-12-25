---
title: Google AI Studio
type: docs
weight: 1
comments: true
prev: /providers
next: /providers/groq
sidebar:
  open: true
---

## 🏢 Provider Information

**Provider Name:** Google  
**Product Name:** Google AI Studio  
**Official Website:** https://aistudio.google.com  
**Type:** Free Service (Permanently free with usage limits)

---

## 📋 Product Overview

Google AI Studio is Google's official AI development platform, providing convenient access to Gemini models for developers and researchers.

**Core Features:**
- 🎁 **Industry's Highest Free Quota** - 15M tokens/day
- 🌟 **Gemini Series Models** - Latest AI models
- 🎨 **Multimodal Support** - Text, images, audio, video
- 📱 **2M Ultra-Long Context** - Handle massive information
- 🔍 **Google Search Grounding** - Search the web for latest information
- ⚡ **High-Speed Inference** - Flash series models provide extremely fast responses

**Rating:** ⭐⭐⭐⭐⭐

---

## 🔐 Registration and Account

### Registration Requirements

| Requirement | Required | Notes |
|------------|----------|-------|
| Google Account | ✅ Required | Gmail, YouTube, etc. all work |
| Email Verification | ✅ Required | Built into Google Account |
| Phone Verification | ❌ Not Required | May be required in some regions |
| Credit Card | ❌ Not Required | Completely free, no payment info needed |

### Registration Steps

{{% steps %}}

#### Visit Google AI Studio

Open your browser, visit [https://aistudio.google.com](https://aistudio.google.com), and click the **"Get started"** button in the upper right corner.

#### Login to Google Account

Login with your Google account (Gmail, YouTube, etc. all work). If you don't have a Google account, click **"Create account"** to create one.

#### Agree to Terms of Service

Read and agree to Google AI Studio's terms of service, select your data usage preferences (whether to allow use for training).

#### Create API Key (if using API)

1. Click **"Get API key"** in the left menu
2. Select or create a Google Cloud project (free)
3. Click **"Create API key"** to generate the key
4. ⚠️ **Important:** Immediately copy and save your API key, keep it secure

{{% /steps %}}

---

## 🎯 Provided Services

Google AI Studio provides two main services:

### 1. [Chatbot Service](/services/chatbot/google-ai-studio)
- **Type:** Web conversation interface
- **Access URL:** https://aistudio.google.com
- **Features:** No programming required, use directly on the web
- **Supports:** Multimodal input (text, images, audio, video)

### 2. [API Service](/services/api/google-ai-studio-api)
- **Type:** RESTful API
- **Features:** Compatible with OpenAI API format
- **Models:** Gemini 3/2.5 Flash, Gemma 3 series
- **Quota:** 15M tokens/day (Flash series)

---

## 📊 Quota Overview

### Total Quota

| Model Series | Daily Tokens | Daily Requests |
|-------------|--------------|----------------|
| Gemini Flash Series | 15M tokens | 1,500 requests |
| Gemini Pro Series | 3M tokens | 1,500 requests |
| Gemma Series | 4M tokens | 14,400 requests |

⚠️ **Important:** All models share a total quota of 1,500 daily requests (except Gemma)

---

## 💡 General Features

### 1. Multimodal Support
- **Text:** Ultra-long text understanding and generation (up to 2M tokens)
- **Images:** Image recognition and analysis
- **Audio:** Audio transcription and understanding
- **Video:** Video content analysis

### 2. Google Search Grounding
- Models can search the web for latest information
- Provides source citations
- Ensures timeliness and accuracy of answers

### 3. Function Calling
- Support for defining and calling external functions
- Can be integrated into your applications for complex functionality
- Suitable for building AI Agents and tool chains

### 4. Prompt Management
- Save and manage your Prompt templates
- Support for parameterized Prompts
- Convenient for team collaboration and version control

---

## ⚠️ Usage Notes

### Data Privacy
- In regions outside the EU/EEA/UK/Switzerland, your data may be used for Google model training
- You can opt out of data training in settings

### Regional Restrictions
- Some regions (like mainland China) may require VPN access

### API Key Security
- Don't expose API keys in public code
- All API keys share the same project quota

---

## 📊 Comparison with Other Services

| Feature | Google AI Studio | OpenRouter | Groq |
|---------|-----------------|------------|------|
| Daily Requests | 1,500 | 50-1,000 | 14,400 |
| Daily Tokens | 15M (Flash) | Unlimited | 20K-1M |
| Context Length | 2M | Varies by model | 32K-128K |
| Multimodal Support | ✅ Strong | Some models | ❌ |
| Web Search | ✅ | ❌ | ❌ |
| Credit Card Required | ❌ | ❌ | ✅ (Verification) |
| Mainland China Access | 🔧 VPN Required | ✅ | 🔧 VPN Required |

---

## 🔗 Related Links

- **Official Documentation:** [https://ai.google.dev/docs](https://ai.google.dev/docs)
- **API Reference:** [https://ai.google.dev/api](https://ai.google.dev/api)
- **Pricing Information:** [https://ai.google.dev/pricing](https://ai.google.dev/pricing)
- **Community Forum:** [https://discuss.ai.google.dev](https://discuss.ai.google.dev)
- **Sample Code:** [GitHub - generative-ai-docs](https://github.com/google/generative-ai-docs)
- **Status Page:** [https://status.cloud.google.com](https://status.cloud.google.com)

---

## 📝 Changelog

- **December 2024:** Gemini 2.5 Flash released, providing faster inference speed
- **November 2024:** Gemma 3 series released, open-source model support
- **2024:** Continuously increasing free quotas, adding multimodal features

---

## 📧 Support & Feedback

- **Official Support:** Submit support tickets through Google Cloud Console
- **Community Discussion:** https://discuss.ai.google.dev
- **Issue Reporting:** Through the feedback button in official documentation
