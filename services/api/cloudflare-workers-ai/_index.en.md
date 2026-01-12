---
title: "Cloudflare Workers AI API - Edge AI Inference Interface"
linkTitle: "API - Cloudflare Workers AI"
description: "Cloudflare Workers AI provides globally deployed edge AI inference API with 50+ open-source models and 10,000 neurons free daily. Serverless architecture, low latency, OpenAI SDK compatible, ultra-low cost."
keywords:
  - Cloudflare Workers AI API
  - Workers AI
  - Edge AI API
  - Serverless AI
  - Free AI API
  - Cloudflare AI
  - Low Latency AI
  - OpenAI Compatible
image: /images/logo.svg
type: docs
weight: 16
comments: true
prev: /services/api/github-models
sidebar:
  open: true
---

## 📋 Service Overview

**Service Name:** Cloudflare Workers AI API  
**Provider:** [Cloudflare Workers AI](/providers/cloudflare-workers-ai)  
**API Endpoint:** `https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/{model_name}`  
**Service Type:** Freemium (10,000 neurons free daily)  
**Registration Requirements:** Cloudflare account required, no credit card needed

---

## ✅ Service Description

Cloudflare Workers AI API is an edge AI inference service based on Cloudflare's global network. Unlike traditional centralized AI APIs, Workers AI deploys models across 300+ data centers globally, executing AI inference closest to users, significantly reducing latency and improving user experience.

### Key Features

- **🌍 Global Edge Deployment:** Runs in 300+ cities worldwide, providing minimum latency (typically < 50ms)
- **🎁 Generous Free Tier:** 10,000 neurons free daily, no credit card required
- **⚡ Ultra-Low Cost:** Only $0.011/1000 neurons when exceeding free tier, 80%+ cheaper than traditional cloud services
- **🤖 Rich Model Library:** 50+ open-source models covering LLM, image, speech, embeddings, and more
- **🔌 Developer Friendly:** REST API + Workers bindings, compatible with OpenAI SDK
- **🔧 Deep Integration:** Seamlessly integrates with Cloudflare Workers, Pages, AI Gateway, and Vectorize

---

## 🎁 Available Models

### Text Generation Models (LLM)

| Model Name | Parameters | Context Length | Features | Use Cases |
|-----------|-----------|---------------|----------|-----------|
| **@cf/meta/llama-3.1-8b-instruct** | 8B | 8K | Meta's latest, balanced | General chat, code generation |
| **@cf/meta/llama-3-8b-instruct** | 8B | 8K | Meta Llama 3, fast | Real-time chat, summarization |
| **@cf/mistral/mistral-7b-instruct-v0.2** | 7B | 32K | Mistral AI, long context | Document analysis, long text |
| **@cf/qwen/qwen1.5-7b-chat-awq** | 7B | 32K | Alibaba Qwen, Chinese optimized | Chinese chat, translation |
| **@cf/google/gemma-7b-it** | 7B | 8K | Google Gemma, open source | General tasks |
| **@cf/deepseek-ai/deepseek-math-7b-instruct** | 7B | 4K | DeepSeek math expert | Math reasoning, problem solving |

### Image Generation Models

| Model Name | Features | Use Cases |
|-----------|----------|-----------|
| **@cf/stabilityai/stable-diffusion-xl-base-1.0** | SDXL, high-quality images | Art creation, design |
| **@cf/lykon/dreamshaper-8-lcm** | LCM, fast generation | Quick prototyping, real-time |
| **@cf/bytedance/stable-diffusion-xl-lightning** | Ultra-fast, 4-8 steps | Real-time applications |

### Image Analysis Models

| Model Name | Features | Use Cases |
|-----------|----------|-----------|
| **@cf/unum/uform-gen2-qwen-500m** | Image understanding + text generation | Image captioning, VQA |
| **@cf/llava-hf/llava-1.5-7b-hf** | Multimodal understanding | Image Q&A, analysis |

### Speech Recognition Models

| Model Name | Features | Use Cases |
|-----------|----------|-----------|
| **@cf/openai/whisper** | OpenAI Whisper, multilingual | Speech-to-text, subtitles |

### Embedding Models

| Model Name | Dimensions | Features | Use Cases |
|-----------|-----------|----------|-----------|
| **@cf/baai/bge-base-en-v1.5** | 768 | English embeddings, high performance | Semantic search, RAG |
| **@cf/baai/bge-large-en-v1.5** | 1024 | English embeddings, higher accuracy | Precise matching |
| **@cf/baai/bge-small-en-v1.5** | 384 | English embeddings, lightweight | Fast retrieval |

### Complete Model List

Visit [Cloudflare Workers AI Model Catalog](https://developers.cloudflare.com/workers-ai/models/) for the latest model list.

---

## 🔢 Quotas and Limits

### Free Tier Limits

| Limit Item | Quota | Description |
|-----------|-------|-------------|
| **Daily Neurons** | 10,000 neurons/day | Shared across all models |
| **Request Rate** | No hard limit | Constrained by neuron quota |
| **Single Request Size** | Model dependent | Usually 1-10MB |
| **Concurrent Requests** | Unlimited | Subject to Workers limits |
| **Credit Card Required** | ❌ No | No card needed for free tier |

### ⚠️ Important Limits

1. **Neuron Calculation:** Different models consume different amounts of neurons per inference:
   - Small LLM (e.g., Llama-3-8B): ~5-10 neurons/request
   - Image generation (e.g., SDXL): ~50-100 neurons/image
   - Speech recognition: ~1 neuron/second of audio

2. **Daily Reset:** Free quota resets at UTC 00:00 daily

3. **Excess Billing:** When exceeding free tier, charges $0.011/1000 neurons

### Quota Reset Time

- **Daily Quota:** Resets at UTC 00:00
- **Real-time Monitoring:** Check usage in Cloudflare Dashboard

---

## 💰 Pricing

### Free Tier

- **Free Quota:** 10,000 neurons daily
- **How to Get:** Available immediately upon Cloudflare account registration
- **Validity:** Permanent, resets daily

### Paid Pricing

Billing after exceeding free tier:

| Item | Price | Description |
|------|-------|-------------|
| **Neurons** | $0.011/1000 neurons | Pay per actual usage |
| **Minimum Spend** | None | True pay-as-you-go |

### Cost Comparison

| Service | Typical Cost (1000 LLM Inferences) | Relative Savings |
|---------|----------------------------------|-----------------|
| **Cloudflare Workers AI** | ~$0.05-0.10 | Baseline |
| OpenAI GPT-3.5 | ~$0.50-1.00 | 5-20x |
| OpenAI GPT-4 | ~$10-30 | 100-600x |
| AWS Bedrock | ~$0.30-2.00 | 3-40x |

---

## 🚀 How to Use

### Prerequisites

**1. Register Cloudflare Account**

See: [Cloudflare Workers AI Registration Guide](/providers/cloudflare-workers-ai#account-registration)

**2. Get API Token**

{{% steps %}}

##### Access API Tokens Page

Log in to Cloudflare Dashboard and go to [API Tokens page](https://dash.cloudflare.com/profile/api-tokens)

##### Create Token

1. Click "Create Token"
2. Select "Edit Cloudflare Workers" template
3. Or customize permissions, ensure Workers AI permission is included

##### Save Token

Copy the generated Token and save securely (shown only once)

{{% /steps %}}

**3. Get Account ID**

Find your Account ID on the right side of any page in Cloudflare Dashboard.

---

## 💻 Code Examples

### Method 1: Using REST API (Any Language)

#### Python Example

**Install Dependencies:**

```bash {filename="Bash"}
pip install requests
```

**Basic Usage (Text Generation):**

```python {filename="Python"}
import requests
import os

# Configuration
CLOUDFLARE_ACCOUNT_ID = "your-account-id"
CLOUDFLARE_API_TOKEN = "your-api-token"

# API endpoint
url = f"https://api.cloudflare.com/client/v4/accounts/{CLOUDFLARE_ACCOUNT_ID}/ai/run/@cf/meta/llama-3.1-8b-instruct"

# Request headers
headers = {
    "Authorization": f"Bearer {CLOUDFLARE_API_TOKEN}",
    "Content-Type": "application/json"
}

# Request data
data = {
    "messages": [
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "What is Cloudflare Workers AI?"}
    ]
}

# Send request
response = requests.post(url, headers=headers, json=data)
result = response.json()

# Print result
print(result["result"]["response"])
```

**Streaming Output:**

```python {filename="Python"}
import requests
import json

# Enable streaming response
data = {
    "messages": [
        {"role": "user", "content": "Write a short story about AI"}
    ],
    "stream": True
}

response = requests.post(url, headers=headers, json=data, stream=True)

# Handle streaming data
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

**Image Generation Example:**

```python {filename="Python"}
import requests
import base64

# Image generation API
url = f"https://api.cloudflare.com/client/v4/accounts/{CLOUDFLARE_ACCOUNT_ID}/ai/run/@cf/stabilityai/stable-diffusion-xl-base-1.0"

data = {
    "prompt": "A beautiful sunset over mountains, digital art style"
}

response = requests.post(url, headers=headers, json=data)
result = response.json()

# Save image
image_data = base64.b64decode(result["result"]["image"])
with open("output.png", "wb") as f:
    f.write(image_data)
print("Image saved as output.png")
```

---

### Method 2: Using Cloudflare Workers (Recommended)

Using Workers AI in Cloudflare Workers is simpler without managing API Tokens.

**Step 1: Configure wrangler.toml**

```toml {filename="wrangler.toml"}
name = "my-ai-worker"
main = "src/index.js"
compatibility_date = "2024-01-01"

[ai]
binding = "AI"
```

**Step 2: Write Worker Code**

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    // Use AI binding
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

**Step 3: Deploy**

```bash {filename="Bash"}
npx wrangler deploy
```

**More Examples:**

```javascript {filename="JavaScript"}
// Text embeddings
const embeddings = await env.AI.run("@cf/baai/bge-base-en-v1.5", {
  text: "Cloudflare Workers AI is amazing"
});

// Image generation
const imageResponse = await env.AI.run("@cf/stabilityai/stable-diffusion-xl-base-1.0", {
  prompt: "A futuristic city"
});

// Speech-to-text
const transcription = await env.AI.run("@cf/openai/whisper", {
  audio: audioArrayBuffer
});
```

---

### Method 3: Using OpenAI SDK (Compatible)

Cloudflare Workers AI is partially compatible with OpenAI SDK:

```python {filename="Python"}
from openai import OpenAI

# Configure Workers AI
client = OpenAI(
    api_key=CLOUDFLARE_API_TOKEN,
    base_url=f"https://api.cloudflare.com/client/v4/accounts/{CLOUDFLARE_ACCOUNT_ID}/ai/v1"
)

# Use OpenAI-like API
response = client.chat.completions.create(
    model="@cf/meta/llama-3.1-8b-instruct",
    messages=[
        {"role": "user", "content": "Hello, how are you?"}
    ]
)

print(response.choices[0].message.content)
```

---

### cURL Examples

**Basic Request:**

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

**Streaming Output:**

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

## 🌟 Core Advantages

### Technical Advantages

1. **Ultra-Low Latency:**
   - Deployed in 300+ cities globally
   - Average latency < 50ms (vs traditional cloud 100-300ms)
   - Nearby response, no cross-region transmission

2. **Excellent Cost-Performance:**
   - 10,000 neurons free daily
   - Only $0.011/1000 neurons when exceeded
   - 80%+ cheaper than AWS and GCP

3. **Serverless Architecture:**
   - No GPU or server management
   - Auto-scaling, pay-per-use
   - Zero operational costs

### Comparison with Other AI APIs

| Feature | Workers AI | OpenAI API | Google AI Studio | AWS Bedrock |
|---------|-----------|-----------|----------------|------------|
| Free Tier | 10K neurons/day | Trial credits | Free usage | Trial credits |
| Edge Deployment | ✅ 300+ cities | ❌ | ❌ | ❌ |
| Latency | < 50ms | 100-300ms | 100-300ms | 100-300ms |
| Cost (LLM) | ~$0.05/1K requests | ~$0.50/1K requests | Free | ~$0.30/1K requests |
| Open Source Models | ✅ 50+ | ❌ | Partial | Partial |
| Serverless | ✅ | Self-managed | ❌ | Partial |

---

## 💡 Practical Recommendations

### ✅ Best Practices

1. **Prioritize Workers Bindings:**
   ```javascript
   // Use in Workers, simpler without managing Tokens
   const response = await env.AI.run(model, input);
   ```

2. **Combine with AI Gateway:**
   ```javascript
   // Add caching, logging, retry features
   const response = await env.AI.run(model, input, {
     gateway: {
       id: "my-gateway",
       skipCache: false,
       cacheTtl: 3600
     }
   });
   ```

3. **Choose Appropriate Models:**
   - Real-time chat: Llama-3-8B (fast)
   - Chinese tasks: Qwen-1.5-7B (Chinese optimized)
   - Math reasoning: DeepSeek-Math-7B (math expert)
   - Fast image generation: SD-XL-Lightning

4. **Monitor Neuron Usage:**
   ```javascript
   // Log consumption per request
   console.log(`Neurons used: ${response.neuronCount}`);
   ```

### 🎯 Best Practices

**Maximize Free Tier:**
- Daily 10,000 neurons can support ~1,000-2,000 LLM requests
- Choose appropriate model size and input length
- Use caching to reduce redundant requests

**Optimize Latency:**
- Leverage edge deployment for low-latency apps
- Use streaming output to improve UX
- Preload commonly used models

**Error Handling:**

```python {filename="Python"}
import time

def call_workers_ai_with_retry(url, headers, data, max_retries=3):
    """API call with retry mechanism"""
    for attempt in range(max_retries):
        try:
            response = requests.post(url, headers=headers, json=data, timeout=30)
            response.raise_for_status()
            return response.json()
        except requests.exceptions.RequestException as e:
            if attempt < max_retries - 1:
                wait_time = 2 ** attempt
                print(f"Request failed, retrying in {wait_time}s... ({attempt + 1}/{max_retries})")
                time.sleep(wait_time)
            else:
                raise Exception(f"Request failed: {e}")
```

### ⚠️ Cautions

1. **Neuron Consumption:** Different models consume different amounts; larger models and longer inputs consume more
2. **Model Availability:** Some models may not be available in certain regions
3. **Input Limits:** Note input length limits for each model
4. **Billing Cycle:** Billing starts immediately when free tier is exceeded, monitor usage

---

## 🎯 Practical Use Cases

### Case 1: Smart Customer Service Chatbot

Build a low-latency global customer service system:

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    const { message } = await request.json();
    
    // Use Llama 3 for fast response
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

### Case 2: Document Semantic Search

Build semantic search using embedding models:

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    const { query } = await request.json();
    
    // Generate query embeddings
    const embeddings = await env.AI.run(
      "@cf/baai/bge-base-en-v1.5",
      { text: query }
    );
    
    // Use Vectorize for similarity search
    const results = await env.VECTORIZE.query(embeddings.data[0], {
      topK: 5
    });
    
    return Response.json(results);
  }
};
```

### Case 3: Automated Image Generation

API receives text description and generates image:

```python {filename="Python"}
import requests
import base64

def generate_image(prompt, account_id, api_token):
    """Generate image"""
    url = f"https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/@cf/bytedance/stable-diffusion-xl-lightning"
    
    headers = {
        "Authorization": f"Bearer {api_token}",
        "Content-Type": "application/json"
    }
    
    data = {
        "prompt": prompt,
        "num_steps": 4  # Lightning model, 4 steps sufficient
    }
    
    response = requests.post(url, headers=headers, json=data)
    result = response.json()
    
    # Save image
    image_data = base64.b64decode(result["result"]["image"])
    filename = f"generated_{hash(prompt)}.png"
    with open(filename, "wb") as f:
        f.write(image_data)
    
    return filename

# Usage example
image_path = generate_image(
    "A futuristic cityscape at sunset, cyberpunk style",
    "your-account-id",
    "your-api-token"
)
print(f"Image saved to: {image_path}")
```

### Case 4: Speech-to-Text Service

```javascript {filename="JavaScript"}
export default {
  async fetch(request, env) {
    // Receive audio file
    const formData = await request.formData();
    const audioFile = formData.get('audio');
    const audioBuffer = await audioFile.arrayBuffer();
    
    // Use Whisper for transcription
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

## 🔧 FAQ

**Q: How do I check my neuron usage?**  
A: Log in to [Cloudflare Dashboard](https://dash.cloudflare.com), check AI usage and neuron consumption in the Workers & Pages section.

**Q: When am I charged?**  
A: Only when you exceed the daily 10,000 neurons free tier, charged at $0.011/1000 neurons.

**Q: Can I use my own models?**  
A: Currently, Workers AI only supports models from Cloudflare's open-source catalog and doesn't support custom model uploads.

**Q: Which regions does Workers AI support?**  
A: Workers AI runs on Cloudflare's global network, covering 300+ cities and is available almost globally. However, some models may be restricted in certain regions.

**Q: How do I get the best performance?**  
A: 1) Use Workers bindings instead of REST API; 2) Choose appropriately sized models; 3) Enable streaming output; 4) Use AI Gateway caching.

**Q: What's the difference between Workers AI and OpenAI API?**  
A: Workers AI uses open-source models deployed at the edge with lower latency and cost. OpenAI API uses proprietary models (like GPT-4) with stronger capabilities but higher cost.

---

## 🔗 Related Resources

- **API Endpoint:** `https://api.cloudflare.com/client/v4/accounts/{account_id}/ai/run/{model}`
- **Developer Docs:** [https://developers.cloudflare.com/workers-ai/](https://developers.cloudflare.com/workers-ai/)
- **Model Catalog:** [https://developers.cloudflare.com/workers-ai/models/](https://developers.cloudflare.com/workers-ai/models/)
- **Provider Homepage:** [Cloudflare Workers AI](/providers/cloudflare-workers-ai)
- **API Reference:** [https://developers.cloudflare.com/api/operations/workers-ai-post-run](https://developers.cloudflare.com/api/operations/workers-ai-post-run)
- **Example Code:** [https://developers.cloudflare.com/workers-ai/examples/](https://developers.cloudflare.com/workers-ai/examples/)
- **Discord Community:** [https://discord.cloudflare.com](https://discord.cloudflare.com)

---

## 📝 Update Log

- **January 2024:** Added support for more Llama 3.1 and Mistral models
- **December 2023:** Launched image generation and speech recognition models
- **September 2023:** Official Workers AI launch with 10,000 neurons free daily

---

**Service Provider:** [Cloudflare Workers AI](/providers/cloudflare-workers-ai)
