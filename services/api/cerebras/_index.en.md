---
title: "Cerebras Inference API - Ultra-Fast AI Inference API Service"
linkTitle: "API - Cerebras"
description: "Cerebras Inference API offers the world's fastest AI inference service with 1 million free tokens daily, 20x faster than GPUs, supporting Llama 4, Qwen 3, and other mainstream models. Built on Wafer-Scale Engine WSE technology with OpenAI-compatible interface."
keywords:
  - Cerebras API
  - Cerebras Inference
  - Ultra-fast Inference API
  - Wafer-Scale Engine API
  - Free AI API
  - Llama API
  - Super-fast Inference
  - OpenAI Compatible
image: /images/logo.svg
type: docs
weight: 13
comments: true
sidebar:
  open: true
---

## 📋 Service Overview

**Service Name:** Cerebras Inference API  
**Provider:** [Cerebras Systems](/providers/cerebras)  
**API Endpoint:** `https://api.cerebras.ai/v1`  
**Service Type:** Free tier (1 million tokens daily)  
**Registration Requirements:** Email only, no credit card required

---

## ✅ Service Description

Cerebras Inference API is an ultra-high-performance AI inference service provided by Cerebras Systems, built on revolutionary Wafer-Scale Engine (WSE) technology, offering 20x faster inference speed than traditional GPUs.

### Key Features

- **🚀 Ultra-Fast Inference:** Llama 4 Scout achieves 2,600+ tokens/s, 20x faster than GPUs
- **🎁 Free Tier:** 1 million tokens free daily
- **🔌 OpenAI Compatible:** Fully compatible with OpenAI API format for seamless migration
- **🤖 Mainstream Models:** Supports Llama 3.1/4, Qwen 3, and other open-source large models

---

## 🎁 Available Models

### Free/Trial Model List

| Model Name | Context Length | Output Length | Features | Use Cases |
|-----------|----------------|---------------|----------|-----------|
| **llama-4-scout** | 8K | 2K | 🏆 Ultra-fast (2,600+ tokens/s) | Real-time apps, chatbots |
| **llama-3.1-70b** | 128K | 4K | High performance, large context | Long document processing, complex tasks |
| **llama-3.1-8b** | 128K | 4K | Fast, lightweight | Quick response, edge deployment |
| **qwen-3-32b** | 128K | 4K | Chinese optimized | Chinese applications |

### Detailed Model Information

#### Llama 4 Scout
- **Context Window:** 8K tokens
- **Primary Use:** Real-time conversation, quick Q&A
- **Advantage:** Industry-leading inference speed at 2,600+ tokens/s

#### Llama 3.1 70B
- **Context Window:** 128K tokens
- **Primary Use:** Complex tasks, long document processing
- **Advantage:** Balances high performance with ultra-long context

#### Llama 3.1 8B
- **Context Window:** 128K tokens
- **Primary Use:** Quick response scenarios
- **Advantage:** Lightweight and fast, more cost-effective

#### Qwen 3-32B
- **Context Window:** 128K tokens
- **Primary Use:** Chinese dialogue and tasks
- **Advantage:** Excellent Chinese language performance

---

## 🔢 Quotas and Limits

### Free Tier Limits

| Limit Item | Quota | Notes |
|-----------|-------|-------|
| **Daily Tokens** | 1M tokens/day | Most mainstream models, daily reset |
| **Rate Limits** | Varies by model | Retry mechanism recommended |
| **Max Context Length** | Up to 128K tokens | Depends on specific model |
| **Max Output Length** | Up to 4K tokens | Depends on specific model |
| **Concurrent Requests** | Within reason | See official docs for specifics |
| **Credit Card Required** | ❌ | Completely free, no card needed |

**Note:** Specific limits may vary by model. Please refer to the [official Rate Limits documentation](https://inference-docs.cerebras.ai/support/rate-limits) for the latest information.

### ⚠️ Important Limits

1. **Daily Quota:** 1 million tokens/day, resets at UTC 00:00
2. **Model Availability:** Model list may be updated anytime, refer to official documentation
3. **Commercial Use:** Free tier for development/testing only, contact sales for production

### Quota Reset Time

- **Daily Quota:** UTC 00:00 (Beijing time 08:00)
- **Usage Monitoring:** Check remaining quota via API response headers or console

---

## 💰 Pricing

### Free/Trial

- **Free Quota:** 1 million tokens daily
- **How to Get:** Simply register an account
- **Duration:** Continuously free (policy subject to change)

### Paid Pricing

For paid pricing, please contact Cerebras sales team: sales@cerebras.ai

---

## 🚀 Getting Started

### Prerequisites

**1. Register Account**

Please follow the [Cerebras Registration Guide](/providers/cerebras#account-registration) to complete account registration.

**2. Get API Key**

{{% steps %}}

##### Log in to Developer Platform

Visit [Cerebras Cloud](https://cloud.cerebras.ai) and log in to your account.

##### Create API Key

1. Find "API Keys" in the left menu
2. Click "Create API Key"
3. Name your key (optional)
4. Click "Create"

##### Save API Key

1. **Important:** Copy the displayed API key
2. API key is shown only once, save it immediately to a secure location
3. Recommended to store key in environment variables

{{% /steps %}}

---

## 💻 Code Examples

### Python Example

#### Method 1: Using OpenAI Client (Compatible Mode)

**Install Dependencies:**

```bash {filename="Bash"}
pip install openai
```

**Basic Usage:**

```python {filename="Python"}
from openai import OpenAI

# Initialize client (using Cerebras API)
client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"  # Replace with your API key
)

# Send request
response = client.chat.completions.create(
    model="llama-4-scout",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain what a Wafer-Scale Engine is"}
    ],
    max_tokens=1000,
    temperature=0.7
)

# Print response
print(response.choices[0].message.content)

# Check token usage
print(f"\nTokens Used: {response.usage.total_tokens}")
print(f"Prompt Tokens: {response.usage.prompt_tokens}")
print(f"Completion Tokens: {response.usage.completion_tokens}")
```

#### Method 2: Using Official SDK (Recommended)

**Install Dependencies:**

```bash {filename="Bash"}
pip install cerebras_cloud_sdk
```

**Basic Usage:**

```python {filename="Python"}
from cerebras.cloud.sdk import Cerebras
import os

# Initialize client
client = Cerebras(
    api_key=os.environ.get("CEREBRAS_API_KEY")
)

# Send request
response = client.chat.completions.create(
    model="llama-3.3-70b",
    messages=[
        {"role": "user", "content": "Explain what a Wafer-Scale Engine is"}
    ],
)

# Print response
print(response.choices[0].message.content)
```

**Streaming Output Example:**

```python {filename="Python"}
# Streaming output (real-time display)
stream = client.chat.completions.create(
    model="llama-4-scout",
    messages=[
        {"role": "user", "content": "Write a poem about artificial intelligence"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

**Using Environment Variables:**

```python {filename="Python"}
import os
from openai import OpenAI

# Read API key from environment variable
client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key=os.getenv("CEREBRAS_API_KEY")
)

response = client.chat.completions.create(
    model="llama-3.1-70b",
    messages=[
        {"role": "user", "content": "What is machine learning?"}
    ]
)

print(response.choices[0].message.content)
```

---

### cURL Example

**Basic Request:**

```bash {filename="Bash"}
curl https://api.cerebras.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_CEREBRAS_API_KEY" \
  -d '{
    "model": "llama-4-scout",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "Hello, tell me about Cerebras"
      }
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**Streaming Output:**

```bash {filename="Bash"}
curl https://api.cerebras.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_CEREBRAS_API_KEY" \
  -d '{
    "model": "llama-4-scout",
    "messages": [
      {"role": "user", "content": "Hello"}
    ],
    "stream": true
  }'
```

---

### Node.js Example

**Install Dependencies:**

```bash {filename="Bash"}
npm install openai
```

**Basic Usage:**

```javascript {filename="JavaScript"}
import OpenAI from 'openai';

const client = new OpenAI({
  baseURL: 'https://api.cerebras.ai/v1',
  apiKey: process.env.CEREBRAS_API_KEY,
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'llama-4-scout',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: 'What is artificial intelligence?' }
    ],
    max_tokens: 1000,
    temperature: 0.7,
  });

  console.log(completion.choices[0].message.content);
  console.log(`\nTokens Used: ${completion.usage.total_tokens}`);
}

main();
```

**Streaming Output:**

```javascript {filename="JavaScript"}
async function streamExample() {
  const stream = await client.chat.completions.create({
    model: 'llama-4-scout',
    messages: [
      { role: 'user', content: 'Write a short story' }
    ],
    stream: true,
  });

  for await (const chunk of stream) {
    const content = chunk.choices[0]?.delta?.content || '';
    process.stdout.write(content);
  }
}

streamExample();
```

---

## 🌟 Core Advantages

### Technical Advantages

1. **Ultra-Fast Inference:**
   - Llama 4 Scout: 2,600+ tokens/s
   - 20x faster than GPUs
   - Millisecond-level response latency

2. **Wafer-Scale Engine (WSE):**
   - 900,000 AI cores
   - 40 Pbits/s on-chip bandwidth
   - 44 GB high-speed SRAM

3. **OpenAI Compatible:**
   - Seamless migration of existing code
   - Supports streaming output
   - Standard API format

### Comparison with Other APIs

| Feature | Cerebras | Groq | DeepSeek | Google AI Studio |
|---------|----------|------|----------|------------------|
| Free Quota | 1M tokens/day | ~14,400 req/day | ¥5 trial | Free usage |
| Inference Speed | 🏆 2,600+ tokens/s | 800+ tokens/s | Fast | Fast |
| OpenAI Compatible | ✅ | ✅ | ✅ | ❌ |
| Context Length | 128K | 128K | 128K | 2M |
| Credit Card Required | ❌ | ✅ | ❌ | ❌ |

---

## 💡 Practical Recommendations

### ✅ Best Practices

1. **Choose the Right Model:**
   ```python
   # Real-time apps - ultimate speed
   model = "llama-4-scout"
   
   # Complex tasks - balanced performance and quality
   model = "llama-3.1-70b"
   
   # Chinese apps - Chinese optimized
   model = "qwen-3-32b"
   ```

2. **Use Streaming to Enhance UX:**
   ```python
   # Streaming lets users see content in real-time
   stream = client.chat.completions.create(
       model="llama-4-scout",
       messages=messages,
       stream=True
   )
   
   for chunk in stream:
       if chunk.choices[0].delta.content:
           print(chunk.choices[0].delta.content, end="", flush=True)
   ```

3. **Implement Request Caching:**
   ```python
   import hashlib
   import json
   
   cache = {}
   
   def cached_request(model, messages):
       # Generate cache key
       key = hashlib.md5(
           json.dumps({"model": model, "messages": messages}).encode()
       ).hexdigest()
       
       # Check cache
       if key in cache:
           return cache[key]
       
       # Call API
       response = client.chat.completions.create(
           model=model,
           messages=messages
       )
       
       # Store in cache
       cache[key] = response
       return response
   ```

### 🎯 Best Practices

**Maximize Free Quota:**
- 1 million tokens daily is sufficient for development and testing
- Monitor daily usage to avoid exceeding quota
- Use free tier for dev and test environments

**Optimize Token Usage:**
- Streamline system prompts
- Control conversation history length
- Set max_tokens appropriately

**Monitor Quota Usage:**

```python {filename="Python"}
# You can check usage in the Cerebras Cloud console
# Visit: https://cloud.cerebras.ai
```

**Error Handling:**

```python {filename="Python"}
import time
from openai import OpenAI, RateLimitError, APIError

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

def call_api_with_retry(messages, max_retries=3):
    """API call with retry mechanism"""
    for attempt in range(max_retries):
        try:
            response = client.chat.completions.create(
                model="llama-4-scout",
                messages=messages
            )
            return response
        except RateLimitError:
            print(f"Rate limit reached, retrying... ({attempt + 1}/{max_retries})")
            time.sleep(2 ** attempt)  # Exponential backoff
        except APIError as e:
            print(f"API error: {e}")
            if attempt == max_retries - 1:
                raise
            time.sleep(1)
    
    return None
```

### ⚠️ Important Notes

1. **Quota Management:** 1 million tokens daily, resets at UTC 00:00, plan usage accordingly
2. **Rate Limits:** Despite being very fast, rate limits exist, implement retry mechanism
3. **Model Selection:** Choose appropriate model based on use case, balance speed and quality

---

## 🎯 Real-World Use Cases

### Case 1: Real-Time Chatbot

**Scenario:** Building a real-time responsive chatbot

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

def chatbot():
    """Real-time chatbot"""
    messages = [
        {"role": "system", "content": "You are a friendly AI assistant"}
    ]
    
    print("Chatbot started! Type 'quit' to exit.\n")
    
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'quit':
            break
        
        messages.append({"role": "user", "content": user_input})
        
        # Use streaming for real-time response
        print("AI: ", end="", flush=True)
        stream = client.chat.completions.create(
            model="llama-4-scout",
            messages=messages,
            stream=True
        )
        
        assistant_response = ""
        for chunk in stream:
            content = chunk.choices[0].delta.content or ""
            print(content, end="", flush=True)
            assistant_response += content
        
        print("\n")
        messages.append({"role": "assistant", "content": assistant_response})

# Run chatbot
chatbot()
```

### Case 2: Batch Text Processing

**Scenario:** Process multiple text tasks in batch

```python {filename="Python"}
import asyncio
from openai import AsyncOpenAI

client = AsyncOpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

async def process_text(text):
    """Process single text"""
    response = await client.chat.completions.create(
        model="llama-4-scout",
        messages=[
            {"role": "system", "content": "You are a text summarization expert"},
            {"role": "user", "content": f"Please summarize the following text:\n\n{text}"}
        ]
    )
    return response.choices[0].message.content

async def batch_process(texts):
    """Batch process texts"""
    tasks = [process_text(text) for text in texts]
    results = await asyncio.gather(*tasks)
    return results

# Usage example
texts = [
    "This is the first text...",
    "This is the second text...",
    "This is the third text..."
]

results = asyncio.run(batch_process(texts))
for i, summary in enumerate(results, 1):
    print(f"Summary {i}: {summary}\n")
```

### Case 3: Code Generation Assistant

**Scenario:** Use AI to assist with code generation

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://api.cerebras.ai/v1",
    api_key="YOUR_CEREBRAS_API_KEY"
)

def code_assistant(task_description):
    """Code generation assistant"""
    response = client.chat.completions.create(
        model="llama-3.1-70b",
        messages=[
            {
                "role": "system",
                "content": "You are a professional programming assistant skilled at generating high-quality code"
            },
            {
                "role": "user",
                "content": f"Please help me write code: {task_description}"
            }
        ],
        temperature=0.3  # Lower temperature for better code quality
    )
    
    return response.choices[0].message.content

# Usage example
task = "Implement binary tree preorder traversal in Python"
code = code_assistant(task)
print("Generated code:")
print(code)
```

---

## 🔧 Common Questions

**Q: How do I check remaining quota?**  
A: Log in to [Cerebras Cloud console](https://cloud.cerebras.ai) to view API usage and remaining quota. It's recommended to check usage regularly during development.

**Q: What happens if I exceed daily quota?**  
A: API will return 429 error, need to wait until UTC 00:00 for quota reset, or upgrade to paid plan.

**Q: Which programming languages are supported?**  
A: Since it's OpenAI API compatible, all languages supporting OpenAI SDK can be used, including Python, Node.js, Go, Java, etc.

**Q: Can I use it in production?**  
A: Free tier is mainly for development/testing, contact Cerebras sales team for enterprise solutions for production.

**Q: Why is it so fast?**  
A: Cerebras uses Wafer-Scale Engine (WSE) with 900,000 cores and 40 Pbits/s bandwidth in a single chip, eliminating traditional GPU memory bottlenecks.

---

## 🔗 Related Resources

- **API Endpoint:** `https://api.cerebras.ai/v1`
- **Developer Platform:** [https://cloud.cerebras.ai](https://cloud.cerebras.ai)
- **API Documentation:** [https://inference-docs.cerebras.ai](https://inference-docs.cerebras.ai)
- **Provider Homepage:** [Cerebras Systems](/providers/cerebras)
- **SDK Documentation:** [OpenAI Python SDK](https://github.com/openai/openai-python)
- **GitHub:** [https://github.com/Cerebras](https://github.com/Cerebras)

---

## 📝 Update Log

- **January 2024:** Cerebras Inference API publicly launched with 1 million free tokens daily
- **2024:** Added support for Llama 3 series models
- **2025:** Added Llama 4 Scout, Qwen 3-32B, and other models

---

**Service Provider:** [Cerebras Systems](/providers/cerebras)
