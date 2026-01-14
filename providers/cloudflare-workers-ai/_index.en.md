---
title: "Cloudflare Workers AI - Edge AI Inference Platform"
linkTitle: "Cloudflare Workers AI"
description: "Cloudflare Workers AI is a serverless edge AI inference platform offering 10,000 free neurons daily and 50+ open-source models. Run AI models across 300+ global data centers with low latency, high availability, and no GPU management."
keywords:
  - Cloudflare Workers AI
  - Workers AI
  - Edge AI
  - Serverless AI
  - Free AI Inference
  - Cloudflare AI
  - Edge Computing
  - AI Gateway
  - LLM Inference
  - Open Source Models
image: /images/logo.svg
type: docs
weight: 16
comments: true
prev: /providers/github-models
sidebar:
  open: true
---

## 📋 Basic Information

**Provider Name:** Cloudflare Workers AI  
**Official Website:** [https://www.cloudflare.com/developer-platform/workers-ai/](https://www.cloudflare.com/developer-platform/workers-ai/)  
**Developer Docs:** [https://developers.cloudflare.com/workers-ai/](https://developers.cloudflare.com/workers-ai/)  
**Headquarters:** San Francisco, USA  
**Founded:** 2010 (Cloudflare), 2023 (Workers AI)

---

## 🏢 Provider Introduction

Cloudflare Workers AI is a serverless AI inference platform launched by Cloudflare, enabling developers to run machine learning models on Cloudflare's global network. Unlike traditional AI inference services, Workers AI deploys AI models across 300+ edge data centers worldwide, providing low-latency, high-availability AI inference services.

### Core Features

- **🌍 Global Edge Deployment:** Run AI models in 300+ cities worldwide for minimum latency
- **🎁 Generous Free Tier:** 10,000 neurons daily without credit card requirement
- **🤖 Rich Model Library:** 50+ open-source models covering text generation, image processing, speech recognition, and more
- **⚡ Serverless Architecture:** No GPU management, pay-per-use pricing, ultra-low cost
- **🔌 Developer Friendly:** REST API and Workers bindings, OpenAI SDK compatible
- **🔧 Cloudflare Ecosystem Integration:** Deep integration with Workers, Pages, AI Gateway, Vectorize, and more

**Recommendation:** ⭐⭐⭐⭐⭐ (Edge AI Pioneer! Low latency with generous free tier!)

### Technical Advantages

- **Edge Computing Benefits:** Execute AI inference at the nearest data center to users, significantly reducing latency
- **Serverless Architecture:** Auto-scaling, no resource reservation, true pay-as-you-go
- **Global Network:** Leverages Cloudflare's global network infrastructure for high availability
- **Cost Optimization:** $0.011/1000 neurons, 80%+ cheaper than traditional cloud services
- **Developer Experience:** Seamless integration with Cloudflare Workers, deployable in just a few lines of code

---

## 🎁 Available Services

Cloudflare Workers AI primarily provides API development interface services:

### API Services

{{< cards >}}
  {{< card link="/en/services/api/cloudflare-workers-ai" title="Cloudflare Workers AI API" subtitle="Edge AI inference API with 50+ models, 10,000 neurons free daily" >}}
{{< /cards >}}

**Features:**
- 10,000 neurons free daily quota
- 50+ open-source models (LLM, image, speech, etc.)
- REST API and Workers bindings
- OpenAI SDK compatible
- Global edge deployment with low latency

{{< callout type="info" >}}
**Note:** Cloudflare Workers AI currently focuses on API services and doesn't provide a standalone Web Chatbot interface. However, developers can quickly build their own Chatbot applications using the API.
{{< /callout >}}

---

## 🚀 Getting Started

### Account Registration

Cloudflare Workers AI uses the Cloudflare account system, with simple and quick registration.

#### Requirements

| Requirement | Necessary | Description |
|------------|----------|-------------|
| Account Registration | ✅ Required | Free Cloudflare account |
| Email Verification | ✅ Required | Email verification needed |
| Phone Verification | ❌ Not Required | Optional |
| Credit Card | ❌ Not Required | No credit card for free tier |
| Identity Verification | ❌ Not Required | Not required |

#### Registration Steps

{{% steps %}}

##### Visit Cloudflare Website

Go to [Cloudflare Sign Up](https://dash.cloudflare.com/sign-up) and click "Sign Up".

##### Create Account

1. Enter your email address
2. Set a password
3. Click "Create Account"

##### Verify Email

1. Check verification email in your inbox
2. Click the verification link to complete

##### Access Workers & Pages

1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Find "Workers & Pages" in the left menu
3. If first time, need to set a subdomain (free)

##### Get API Token

1. Go to "API Tokens" page
2. Click "Create Token"
3. Choose "Edit Cloudflare Workers" template or customize permissions
4. Create and save the Token

{{% /steps %}}

**Important Notes:**
- API Token is shown only once, save it securely
- Free quota resets daily, no credit card required
- Monitor usage in Dashboard

---

## 💡 General Notes

### ✅ Best Practices

1. **Leverage Edge Advantages:**
   - Workers AI deploys globally at the edge, ideal for low-latency applications
   - Combine with Cloudflare Workers to build full-stack edge applications

2. **Monitor Usage:**
   - Check neuron usage in Dashboard
   - Set usage alerts to avoid exceeding free tier

3. **Use AI Gateway:**
   - Combine with Cloudflare AI Gateway for caching, logging, retry features
   - Further reduce costs and improve reliability

4. **Choose Appropriate Models:**
   - Select models based on task requirements
   - Smaller models consume fewer neurons

### ⚠️ Important Reminders

1. **Free Tier Limit:** 10,000 neurons daily, charges $0.011/1000 neurons when exceeded
2. **Neuron Calculation:** Different models consume different amounts of neurons, see model documentation
3. **Daily Reset:** Free quota resets at UTC 00:00 daily
4. **Model Availability:** Some models may not be available in certain regions, check official docs

### 🔧 FAQ

**Q: What are "Neurons"?**  
A: Neurons are Cloudflare Workers AI's billing unit. Different models consume different amounts of neurons per inference, typically related to model size and input/output length. For example, a simple request to a small LLM might consume 5-10 neurons.

**Q: Is the free tier sufficient?**  
A: For small to medium applications and testing, 10,000 neurons daily is sufficient. For example, using small LLMs can process approximately 1,000-2,000 requests.

**Q: How do I check my usage?**  
A: Log in to Cloudflare Dashboard, you can view AI usage and neuron consumption in the Workers & Pages section.

**Q: How is Workers AI different from other AI services?**  
A: The biggest difference is edge deployment. Workers AI runs in 300+ data centers globally, providing lower latency. Traditional AI services are usually concentrated in a few regions.

**Q: Can I use my own models?**  
A: Currently, Workers AI only supports models provided by Cloudflare's open-source catalog and doesn't support custom model uploads.

---

## 🔗 Related Links

- **Official Website:** [https://www.cloudflare.com/developer-platform/workers-ai/](https://www.cloudflare.com/developer-platform/workers-ai/)
- **Developer Docs:** [https://developers.cloudflare.com/workers-ai/](https://developers.cloudflare.com/workers-ai/)
- **Model Catalog:** [https://developers.cloudflare.com/workers-ai/models/](https://developers.cloudflare.com/workers-ai/models/)
- **Pricing:** [https://developers.cloudflare.com/workers-ai/platform/pricing/](https://developers.cloudflare.com/workers-ai/platform/pricing/)
- **API Reference:** [https://developers.cloudflare.com/api/operations/workers-ai-post-run](https://developers.cloudflare.com/api/operations/workers-ai-post-run)
- **Discord Community:** [https://discord.cloudflare.com](https://discord.cloudflare.com)
- **Blog Post:** [https://blog.cloudflare.com/workers-ai/](https://blog.cloudflare.com/workers-ai/)
- **Status Page:** [https://www.cloudflarestatus.com/](https://www.cloudflarestatus.com/)

---

## 📈 Service Comparison

| Feature | Free Tier | Paid Tier |
|---------|-----------|-----------|
| Price | Free | $0.011/1000 neurons |
| Daily Quota | 10,000 neurons | Unlimited |
| Model Count | 50+ | 50+ |
| Edge Deployment | ✅ | ✅ |
| Global Available | ✅ | ✅ |
| Technical Support | Community | Enterprise (Optional) |

---

## 📝 Update Log

- **January 2024:** Added more open-source model support, including Llama 2, Mistral, etc.
- **September 2023:** Official launch of Workers AI with 10,000 neurons free daily
- **2023:** Beta testing phase, gradually opening to developers

---

## 📧 Support & Feedback

- **Official Support:** Submit support tickets through Cloudflare Dashboard
- **Community Forum:** [https://community.cloudflare.com/](https://community.cloudflare.com/)
- **Discord:** [https://discord.cloudflare.com](https://discord.cloudflare.com)
- **Issue Reporting:** Through Dashboard or community forum
