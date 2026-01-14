---
title: "NVIDIA NIM API - Enterprise GPU-Accelerated Inference API Service"
linkTitle: "API - NVIDIA NIM"
description: "NVIDIA NIM provides optimized GPU-accelerated inference APIs with free hosted trials and self-hosted deployment. OpenAI-compatible interface supporting Llama 3, Mistral, Phi and other mainstream models, offering low-latency, high-throughput enterprise-grade inference capabilities."
keywords:
  - NVIDIA NIM API
  - GPU-accelerated API
  - Free AI API
  - Enterprise Inference API
  - OpenAI Compatible API
  - Llama 3 API
  - Mistral API
  - Self-hosted AI API
image: /images/logo.svg
type: docs
weight: 11
comments: true
prev: /services/api/mistral
next: /services/chatbot
sidebar:
  open: true
---

## 📋 Service Overview

**Service Name:** NVIDIA NIM API  
**Provider:** [NVIDIA NIM](/providers/nvidia-nim)  
**API Endpoint:** `https://integrate.api.nvidia.com/v1`  
**Service Type:** Free Hosted Trial + Self-hosted Download  
**Registration Requirement:** NVIDIA developer account required

---

## ✅ Service Description

NVIDIA NIM API is an enterprise-grade AI inference API service provided by NVIDIA, delivering high-performance model inference capabilities through GPU acceleration. NIM (NVIDIA Inference Microservices) simplifies complex model deployment processes into ready-to-use microservices, fully compatible with the OpenAI API format.

### Key Features

- **🚀 GPU Acceleration:** Leveraging powerful NVIDIA GPU computing power for industry-leading inference performance
- **📦 Ready to Use:** Pre-optimized model containers that can be used without complex configuration
- **🔄 OpenAI Compatible:** Fully compatible with OpenAI API, just change the base_url to switch
- **🏭 Enterprise Features:** Supports Kubernetes deployment, auto-scaling, multi-tenant isolation
- **🌐 Flexible Deployment:** Supports both cloud-hosted trials and local self-hosting

---

## 🎁 Available Models

### Large Language Models (LLM)

| Model Name | Parameters | Context Length | Features | Use Cases |
|-----------|-----------|---------------|----------|-----------|
| **meta/llama-3.1-405b-instruct** | 405B | 128K | Meta's strongest model | Complex reasoning, professional tasks |
| **meta/llama-3.1-70b-instruct** | 70B | 128K | Performance-efficiency balance | General dialogue, content generation |
| **meta/llama-3.1-8b-instruct** | 8B | 128K | Lightweight and efficient | Quick response, high-frequency calls |
| **mistralai/mistral-large** | 123B | 128K | Mistral flagship model | Multilingual, code generation |
| **mistralai/mixtral-8x7b-instruct** | 47B | 32K | Mixture of Experts | Professional domains, multi-task |
| **microsoft/phi-3-medium-4k-instruct** | 14B | 4K | Microsoft small model | Edge devices, fast inference |

### Vision-Language Models

| Model Name | Features | Use Cases |
|-----------|----------|-----------|
| **meta/llama-3.2-90b-vision-instruct** | Vision understanding | Image analysis, OCR |
| **meta/llama-3.2-11b-vision-instruct** | Lightweight vision | Fast image processing |

### Reasoning Expert Models

| Model Name | Features | Use Cases |
|-----------|----------|-----------|
| **deepseek-ai/deepseek-r1** | Chain-of-thought reasoning | Math, logical reasoning |
| **nvidia/llama-3.1-nemotron-70b-instruct** | NVIDIA optimized | High-performance inference |

**Note:** Above are example models. Actual available models are continuously updated and may vary by region. Visit [build.nvidia.com/explore](https://build.nvidia.com/explore/discover) for the latest, complete model list.

---

## 🔢 Quotas and Limits

### Hosted API Trial

| Limit Item | Quota | Description |
|-----------|-------|-------------|
| **Free Credits** | ~1,000 credits | Reference value, granted after registration |
| **Daily Requests** | Based on credit consumption | Different models consume different amounts |
| **Rate Limits** | Model-specific | See individual model card descriptions |
| **Max Context** | Varies by model | Example: Llama 3.1 supports 128K |
| **Max Output** | Varies by model | Typically 4K-8K tokens |
| **Credit Card Required** | ❌ Not required | Completely free trial |

### Self-hosted Deployment

| Limit Item | Requirement | Description |
|-----------|------------|-------------|
| **GPU Required** | NVIDIA GPU | Model and memory depend on model size |
| **Minimum VRAM** | 24GB+ | Small models (8B) |
| **Recommended VRAM** | 80GB+ | Large models (70B+) |
| **License** | NVIDIA AI Enterprise | Required for production (90-day free trial) |
| **Download Access** | Developer account | Free registration |

### ⚠️ Important Limitations

1. **Credit Nature:** Free credits are for development/testing, policies may change. Request more or switch to self-hosting when exhausted
2. **Billing Details:** Remote API calls consume credits, web Playground interactions typically don't
3. **Model Availability:** Model list updates, some models may vary by region or partnership
4. **Production Use:** Hosted API trial is for development/testing; recommend self-hosting or enterprise license for production

---

## 💰 Pricing

### Free/Trial

- **Hosted API Trial:** New users typically receive initial trial credits (reference: ~1,000 credits)
- **Validity:** Credit policy controlled by NVIDIA, recommend using promptly. Request more on Build platform if needed
- **How to Get:** Register for NVIDIA developer account and generate API Key on Build platform
- **Billing Details:** Remote API calls consume credits, web Playground typically doesn't

### Self-hosted (Free Download)

- **Download:** Free download of NIM microservices through NVIDIA Developer Program
- **Usage Restrictions:** Free for development, testing, and research
- **Production Deployment:** Requires NVIDIA AI Enterprise license (~$4,500/GPU/year starting)

### Paid Options

| Plan | Price | Description |
|------|-------|-------------|
| **Hosted API Paid** | Pay-as-you-go | Purchase after credits exhausted |
| **AI Enterprise** | From $4,500/GPU/year | Enterprise license with support |
| **Cloud Provider Deployment** | Varies by platform | AWS, Azure, GCP, etc. |

---

## 🚀 How to Use

### Prerequisites

**1. Register NVIDIA Developer Account**

See: [NVIDIA NIM Registration Guide](/providers/nvidia-nim#account-registration)

**2. Get API Key**

{{% steps %}}

#### Visit build.nvidia.com

After logging in, go to [https://build.nvidia.com](https://build.nvidia.com)

#### Select a Model

Browse and select the model you want to use in the API Catalog

#### Get API Key

1. Click on your profile picture in the top right
2. Select **"Get API Key"** or **"API Keys"**
3. Click **"Generate API Key"** to create a new key
4. Copy and save the API key (format: `nvapi-xxx`)

⚠️ **Important:** Keep your API key secure and don't expose it in public code.

{{% /steps %}}

---

## 💻 Code Examples

### Python Examples

**Install Dependencies:**

```bash {filename="Bash"}
pip install openai
```

**Basic Usage:**

```python {filename="Python"}
from openai import OpenAI

# Initialize client (using NVIDIA NIM API)
client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"  # Replace with your API key
)

# Send request
response = client.chat.completions.create(
    model="meta/llama-3.1-70b-instruct",
    messages=[
        {"role": "system", "content": "You are a helpful AI assistant."},
        {"role": "user", "content": "Explain what GPU-accelerated inference is?"}
    ],
    max_tokens=1024,
    temperature=0.7
)

# Print response
print(response.choices[0].message.content)

# Check token usage
print(f"\nTokens used: {response.usage.total_tokens}")
```

**Streaming Example:**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

# Streaming output (for real-time display)
stream = client.chat.completions.create(
    model="meta/llama-3.1-70b-instruct",
    messages=[
        {"role": "user", "content": "Write a poem about artificial intelligence"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

**Using Vision Models:**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

# Image analysis
response = client.chat.completions.create(
    model="meta/llama-3.2-90b-vision-instruct",
    messages=[
        {
            "role": "user",
            "content": [
                {"type": "text", "text": "What's in this image?"},
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

### cURL Examples

**Basic Request:**

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
        "content": "Hello, please introduce NVIDIA NIM."
      }
    ],
    "max_tokens": 1024,
    "temperature": 0.7
  }'
```

**Streaming:**

```bash {filename="Bash"}
curl https://integrate.api.nvidia.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer nvapi-YOUR_API_KEY" \
  -d '{
    "model": "meta/llama-3.1-70b-instruct",
    "messages": [{"role": "user", "content": "Hello"}],
    "stream": true
  }'
```

---

### Node.js Example

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
      { role: 'user', content: 'Introduce the advantages of NVIDIA GPUs.' }
    ],
    max_tokens: 1024,
    temperature: 0.7,
  });

  console.log(completion.choices[0].message.content);
  console.log(`\nTokens used: ${completion.usage.total_tokens}`);
}

main();
```

---

## 🌟 Core Advantages

### Technical Advantages

1. **GPU-Accelerated Performance:**
   - Deeply optimized for NVIDIA GPUs
   - 10-100x speedup compared to CPU inference
   - Supports advanced optimizations like tensor parallelism, pipeline parallelism

2. **Enterprise-Grade Reliability:**
   - Production-validated inference engine
   - Supports high-concurrency, low-latency scenarios
   - SLA guarantees (enterprise version)

3. **Flexible Deployment Options:**
   - Cloud-hosted: No infrastructure management
   - On-premises: Full data control
   - Hybrid: Flexible combination

### Comparison with Other APIs

| Feature | NVIDIA NIM | Groq | OpenRouter |
|---------|-----------|------|------------|
| Free Quota | 1,000 credits | 14,400 req/day | 50-1,000 req/day |
| GPU Acceleration | ✅ NVIDIA GPU | ✅ LPU chip | ❌ Hosted models |
| Self-hosting | ✅ Supported | ❌ Not supported | ❌ Not supported |
| Enterprise Features | ✅ Complete | ❌ Basic | ❌ Basic |
| OpenAI Compatible | ✅ Fully compatible | ✅ Fully compatible | ✅ Fully compatible |
| Vision Models | ✅ Supported | ❌ Not supported | ✅ Partial support |

---

## 💡 Practical Suggestions

### ✅ Recommended Practices

1. **Choose the Right Model:**
   ```python
   # Fast response scenarios
   model = "meta/llama-3.1-8b-instruct"
   
   # Balance performance and quality
   model = "meta/llama-3.1-70b-instruct"
   
   # Maximum performance needs
   model = "meta/llama-3.1-405b-instruct"
   
   # Vision tasks
   model = "meta/llama-3.2-90b-vision-instruct"
   ```

2. **Implement Error Handling:**
   ```python
   import time
   from openai import OpenAI, RateLimitError, APIError
   
   client = OpenAI(
       base_url="https://integrate.api.nvidia.com/v1",
       api_key="nvapi-YOUR_API_KEY"
   )
   
   def call_with_retry(messages, max_retries=3):
       """API call with retry mechanism"""
       for attempt in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="meta/llama-3.1-70b-instruct",
                   messages=messages
               )
           except RateLimitError:
               if attempt < max_retries - 1:
                   wait_time = 2 ** attempt
                   print(f"Rate limit reached, waiting {wait_time} seconds...")
                   time.sleep(wait_time)
               else:
                   raise
           except APIError as e:
               print(f"API error: {e}")
               if attempt == max_retries - 1:
                   raise
       return None
   ```

3. **Monitor Credit Usage:**
   ```python
   def track_usage(response):
       """Track token usage"""
       usage = response.usage
       print(f"Input tokens: {usage.prompt_tokens}")
       print(f"Output tokens: {usage.completion_tokens}")
       print(f"Total tokens: {usage.total_tokens}")
       
       # Estimate credit consumption (check official docs for exact ratio)
       estimated_credits = usage.total_tokens / 1000
       print(f"Estimated credits used: {estimated_credits:.2f}")
   ```

4. **Optimize Token Usage:**
   - Use system prompts to guide model behavior
   - Limit max_tokens appropriately to avoid overly long outputs
   - Use smaller models for simple tasks
   - Cache responses to common questions

5. **Secure API Key Management:**
   ```python
   import os
   from dotenv import load_dotenv
   
   # Use environment variables
   load_dotenv()
   api_key = os.getenv('NVIDIA_API_KEY')
   
   client = OpenAI(
       base_url="https://integrate.api.nvidia.com/v1",
       api_key=api_key
   )
   ```

### ⚠️ Precautions

1. **Credit Management:** Use trial credits wisely, different models consume different amounts. Only remote API calls consume credits
2. **API Endpoint:** Example uses `https://integrate.api.nvidia.com/v1`, please refer to individual model card instructions
3. **Network Connection:** Accessing NVIDIA services may require stable international network
4. **Troubleshooting:** When encountering credit or permission errors, check balance in Build console or request more

---

## 🎯 Practical Use Cases

### Case 1: Intelligent Customer Service Assistant

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

def customer_service_bot(user_question, context=""):
    """Intelligent customer service assistant"""
    system_prompt = f"""You are a professional customer service assistant.
Please answer user questions based on the following knowledge base:

{context}

Requirements:
- Professional, friendly, concise
- If unsure, suggest contacting human support
- Provide specific solutions
"""
    
    response = client.chat.completions.create(
        model="meta/llama-3.1-70b-instruct",
        messages=[
            {"role": "system", "content": system_prompt},
            {"role": "user", "content": user_question}
        ],
        temperature=0.3  # Lower temperature for more deterministic answers
    )
    
    return response.choices[0].message.content

# Usage example
knowledge_base = """
Product Info:
- 24/7 online customer service
- 30-day no-questions-asked return policy
- Free nationwide shipping, except remote areas
"""

answer = customer_service_bot("How do I return a product?", knowledge_base)
print(answer)
```

### Case 2: Code Review Assistant

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

def code_review(code, language="Python"):
    """Code review assistant"""
    response = client.chat.completions.create(
        model="meta/llama-3.1-70b-instruct",
        messages=[
            {
                "role": "system",
                "content": f"You are a professional {language} code review expert. "
                           "Please review code from these perspectives:\n"
                           "1. Code quality and readability\n"
                           "2. Potential bugs and security issues\n"
                           "3. Performance optimization suggestions\n"
                           "4. Best practice recommendations"
            },
            {
                "role": "user",
                "content": f"Please review the following code:\n\n```{language.lower()}\n{code}\n```"
            }
        ],
        temperature=0.2
    )
    
    return response.choices[0].message.content

# Usage example
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

### Case 3: Image Understanding Application

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://integrate.api.nvidia.com/v1",
    api_key="nvapi-YOUR_API_KEY"
)

def analyze_image(image_url, question="Describe this image"):
    """Image analysis"""
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

# Usage example
result = analyze_image(
    "https://example.com/product.jpg",
    "What are the features of this product?"
)
print(result)
```

---

## 🔧 Common Questions

**Q: How do I check remaining credits?**  
A: Log into build.nvidia.com and check your current API credits balance and usage in your profile or Usage page.

**Q: What happens after free credits run out?**  
A: You can: 1) Click "Request More" on the Build platform to request additional credits; 2) Download NIM microservices for self-hosting; 3) Purchase NVIDIA AI Enterprise license for production environments.

**Q: Why am I getting 402/403 errors?**  
A: This may be due to insufficient credits or permission issues. Check: 1) Credit balance in Build console; 2) Confirm using remote API calls (which consume credits); 3) Try requesting more credits or contact NVIDIA support.

**Q: What hardware is needed for self-hosting?**  
A: Minimum one NVIDIA GPU required. Specific requirements depend on model size. For example, Llama 3.1 8B needs at least 24GB VRAM, 70B models need 80GB+ VRAM.

**Q: Which programming languages are supported?**  
A: Since it's OpenAI API compatible, all languages supporting OpenAI work, including Python, JavaScript/Node.js, Go, Java, C#, etc.

**Q: How do I get technical support?**  
A: Support available through NVIDIA developer forums, official documentation, GitHub Issues, etc. Enterprise users can purchase paid support services.

---

## 🔗 Related Resources

- **API Endpoint:** `https://integrate.api.nvidia.com/v1`
- **Developer Platform:** [https://build.nvidia.com](https://build.nvidia.com)
- **API Catalog:** [https://build.nvidia.com/explore/discover](https://build.nvidia.com/explore/discover)
- **Provider Homepage:** [NVIDIA NIM Overview](/providers/nvidia-nim)
- **Official Documentation:** [https://docs.nvidia.com/nim](https://docs.nvidia.com/nim)
- **Developer Forum:** [https://forums.developer.nvidia.com](https://forums.developer.nvidia.com)
- **GitHub:** [https://github.com/NVIDIA](https://github.com/NVIDIA)

---

## 📝 Update Log

- **January 2025:** Added more open-source model support, optimized API performance
- **December 2024:** Official release of NVIDIA NIM with hosted API and self-hosting options
- **October 2024:** build.nvidia.com developer platform launched

---

**Service Provider:** [NVIDIA NIM](/providers/nvidia-nim)
