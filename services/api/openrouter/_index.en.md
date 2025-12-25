---
title: OpenRouter - API
weight: 3
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [OpenRouter](/en/providers/openrouter)  
**Service Type:** API Service  
**API Endpoint:** [https://openrouter.ai/api/v1](https://openrouter.ai/api/v1)  
**Free Tier:** Free Forever (with usage limits)  
**API Compatibility:** Fully compatible with OpenAI API

---

## 🎯 Service Overview

OpenRouter API provides access to 47+ free AI models through a unified interface, fully compatible with OpenAI API format, allowing you to easily switch and test different models.

**Key Advantages:**
- 🎯 **One-stop Access** - Access 47+ models with one API key
- 🔄 **OpenAI Compatible** - Seamless code migration
- 🎁 **Many Free Models** - Including top models like Llama 3.1 405B
- 🚀 **Smart Routing** - Automatically selects optimal provider
- 💰 **Flexible Pricing** - Free models never charge

---

## 🚀 Quick Start

### Prerequisites

**Required:**
- ✅ API key created

For detailed steps, see: [OpenRouter Registration Guide](/en/providers/openrouter#registration-and-account)

### 5-Minute Quick Example

**Using OpenAI SDK (Recommended)**

```python {filename="Python"}
from openai import OpenAI

# Configure OpenRouter
client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY",
)

# Call free model
response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=[
        {"role": "user", "content": "Introduce OpenRouter"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 Free Models List

### How to Identify Free Models

Free models have `:free` suffix in their model ID:
- ✅ `meta-llama/llama-3.3-70b-instruct:free`
- ❌ `meta-llama/llama-3.3-70b-instruct` (paid)

### Top Free Models

| Model ID | Parameters | Context | Features |
|----------|-------|--------|------|
| `meta-llama/llama-3.3-70b-instruct:free` | 70B | 128K | Meta's latest |
| `meta-llama/llama-3.1-405b-instruct:free` | 405B | 128K | Huge parameters |
| `deepseek/deepseek-r1-0528:free` | - | 64K | Reasoning expert |
| `qwen/qwen-3-235b-a22b:free` | 235B | 128K | Alibaba flagship |
| `mistralai/mistral-small-3.1-24b:free` | 24B | 32K | Mistral efficient |

### Lightweight Fast Models

| Model ID | Parameters | Context | Features |
|----------|-------|--------|------|
| `meta-llama/llama-3.2-3b-instruct:free` | 3B | 128K | Lightweight fast |
| `google/gemma-3-4b-instruct:free` | 4B | 8K | Small but powerful |
| `mistralai/mistral-7b-instruct:free` | 7B | 32K | Classic efficient |

### Code-specific Models

| Model ID | Features |
|----------|------|
| `mistralai/devstral-2512:free` | Mistral code expert |
| `qwen/qwen-3-coder:free` | Qwen code version |

---

## 🔢 Quotas and Limits

### API Quotas

| Limit Type | Basic Tier | Upgraded Tier ($10) |
|---------|--------|-------------|
| **Daily Requests** | 50 requests | 1,000 requests |
| **Requests/Minute** | 20 requests | 20 requests |
| **Free Models** | 47+ | 47+ |
| **Cost** | $0 | $10 one-time |

### ⚠️ Important Limitations

1. **Model Identification:** Must use model IDs with `:free` suffix
2. **Quota Sharing:** All free models share quota
3. **Rate Limits:** Returns 429 error when exceeded
4. **Balance Protection:** Can set credit limit to $0 to avoid using paid models

---

## 📖 API Usage Examples

### 1. Basic Conversation

**Python (OpenAI SDK):**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=[
        {"role": "system", "content": "You are a helpful AI assistant"},
        {"role": "user", "content": "What is machine learning?"}
    ]
)

print(response.choices[0].message.content)
```

### 2. Streaming Output

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

stream = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=[
        {"role": "user", "content": "Write an article about AI"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

### 3. Using requests Library

```python {filename="Python"}
import requests

url = "https://openrouter.ai/api/v1/chat/completions"
headers = {
    "Authorization": "Bearer YOUR_OPENROUTER_API_KEY",
    "Content-Type": "application/json"
}
data = {
    "model": "meta-llama/llama-3.3-70b-instruct:free",
    "messages": [
        {"role": "user", "content": "Hello"}
    ]
}

response = requests.post(url, headers=headers, json=data)
print(response.json()["choices"][0]["message"]["content"])
```

### 4. cURL Example

```bash {filename="Bash"}
curl https://openrouter.ai/api/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_OPENROUTER_API_KEY" \
  -d '{
    "model": "meta-llama/llama-3.3-70b-instruct:free",
    "messages": [
      {
        "role": "user",
        "content": "Introduce OpenRouter"
      }
    ]
  }'
```

### 5. Node.js Example

```javascript {filename="JavaScript"}
const fetch = require('node-fetch');

async function chat() {
    const response = await fetch('https://openrouter.ai/api/v1/chat/completions', {
        method: 'POST',
        headers: {
            'Authorization': 'Bearer YOUR_OPENROUTER_API_KEY',
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({
            model: 'meta-llama/llama-3.3-70b-instruct:free',
            messages: [
                { role: 'user', content: 'Hello' }
            ]
        })
    });
    
    const data = await response.json();
    console.log(data.choices[0].message.content);
}

chat();
```

### 6. Multi-turn Conversation

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

messages = [
    {"role": "system", "content": "You are a Python programming assistant"}
]

# First round
messages.append({"role": "user", "content": "How to read a file?"})
response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=messages
)
messages.append({"role": "assistant", "content": response.choices[0].message.content})

# Second round
messages.append({"role": "user", "content": "What about writing?"})
response = client.chat.completions.create(
    model="meta-llama/llama-3.3-70b-instruct:free",
    messages=messages
)
print(response.choices[0].message.content)
```

---

## 💡 Best Practices

### ✅ Recommended Practices

1. **Choose the Right Model**
   ```python
   # Fast tasks
   model = "meta-llama/llama-3.2-3b-instruct:free"
   
   # General tasks
   model = "meta-llama/llama-3.3-70b-instruct:free"
   
   # Complex tasks
   model = "meta-llama/llama-3.1-405b-instruct:free"
   
   # Chinese tasks
   model = "qwen/qwen-3-235b-a22b:free"
   
   # Code tasks
   model = "mistralai/devstral-2512:free"
   ```

2. **Set Balance Limit**
   ```python
   # In OpenRouter console
   # Settings → Credits → Monthly Limit → $0
   # This prevents accidental use of paid models
   ```

3. **Implement Error Handling and Retries**
   ```python
   import time
   from openai import OpenAI, RateLimitError
   
   client = OpenAI(
       base_url="https://openrouter.ai/api/v1",
       api_key="YOUR_OPENROUTER_API_KEY"
   )
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="meta-llama/llama-3.3-70b-instruct:free",
                   messages=messages
               )
           except RateLimitError:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"Rate limited, waiting {wait_time} seconds...")
                   time.sleep(wait_time)
               else:
                   raise
   ```

4. **Monitor Usage**
   ```python
   # Visit https://openrouter.ai/activity
   # View detailed usage statistics and costs
   ```

5. **Securely Manage API Keys**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('OPENROUTER_API_KEY')
   
   client = OpenAI(
       base_url="https://openrouter.ai/api/v1",
       api_key=api_key
   )
   ```

---

## 🔧 Common Issues

### 1. How to View All Free Models?

**Method:**
- Visit: https://openrouter.ai/models?free=true
- Or use API:
  ```python
  response = requests.get(
      "https://openrouter.ai/api/v1/models",
      headers={"Authorization": f"Bearer {api_key}"}
  )
  free_models = [m for m in response.json()["data"] if ":free" in m["id"]]
  ```

### 2. 429 Error: Rate Limit Exceeded

**Cause:** Exceeded daily or per-minute limit

**Solution:**
- Wait for quota reset (daily UTC 00:00)
- Upgrade to 1000 requests/day (recharge $10)
- Implement request caching and retry logic

### 3. Why Am I Being Charged?

**Cause:** Used model without `:free` suffix

**Prevention:**
```python {filename="Python"}
def ensure_free_model(model_id):
    if not model_id.endswith(":free"):
        raise ValueError(f"Model {model_id} is not a free model!")
    return model_id

# Usage
model = ensure_free_model("meta-llama/llama-3.3-70b-instruct:free")
```

### 4. How to Switch Between Models?

**Method:**
```python {filename="Python"}
# Just modify the model parameter
models_to_try = [
    "meta-llama/llama-3.3-70b-instruct:free",
    "meta-llama/llama-3.1-405b-instruct:free",
    "qwen/qwen-3-235b-a22b:free"
]

for model in models_to_try:
    response = client.chat.completions.create(
        model=model,
        messages=[{"role": "user", "content": "Test"}]
    )
    print(f"{model}: {response.choices[0].message.content[:50]}")
```

---

## 📊 Performance Optimization

### 1. Model Selection Strategy

```python {filename="Python"}
def select_model(task_type, complexity):
    if task_type == "code":
        return "mistralai/devstral-2512:free"
    elif task_type == "chinese":
        return "qwen/qwen-3-235b-a22b:free"
    elif complexity == "high":
        return "meta-llama/llama-3.1-405b-instruct:free"
    else:
        return "meta-llama/llama-3.3-70b-instruct:free"
```

### 2. Result Caching

```python {filename="Python"}
from functools import lru_cache
import hashlib
import json

cache = {}

def get_cache_key(model, messages):
    content = json.dumps({"model": model, "messages": messages}, sort_keys=True)
    return hashlib.md5(content.encode()).hexdigest()

def cached_completion(model, messages):
    key = get_cache_key(model, messages)
    
    if key in cache:
        print("Using cached result")
        return cache[key]
    
    response = client.chat.completions.create(
        model=model,
        messages=messages
    )
    
    cache[key] = response
    return response
```

### 3. Batch Processing

```python {filename="Python"}
import asyncio
from openai import AsyncOpenAI

async def batch_process(questions):
    client = AsyncOpenAI(
        base_url="https://openrouter.ai/api/v1",
        api_key="YOUR_OPENROUTER_API_KEY"
    )
    
    tasks = []
    for q in questions:
        task = client.chat.completions.create(
            model="meta-llama/llama-3.3-70b-instruct:free",
            messages=[{"role": "user", "content": q}]
        )
        tasks.append(task)
    
    return await asyncio.gather(*tasks)

# Usage
questions = ["Question 1", "Question 2", "Question 3"]
responses = asyncio.run(batch_process(questions))
```

---

## 📚 Related Resources

### Official Documentation
- [OpenRouter Complete Guide](/en/providers/openrouter)
- [Playground Usage Guide](/en/services/chatbot/openrouter)
- [API Official Docs](https://openrouter.ai/docs)

### Tools and Resources
- [Free Models List](https://openrouter.ai/models?free=true)
- [API Reference](https://openrouter.ai/docs/api-reference)
- [Usage Statistics](https://openrouter.ai/activity)
- [Pricing Information](https://openrouter.ai/docs/limits)

---

## 🌟 Practical Cases

### Case 1: Multi-model Comparison Tool

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key="YOUR_OPENROUTER_API_KEY"
)

def compare_models(prompt, models):
    results = {}
    for model in models:
        response = client.chat.completions.create(
            model=model,
            messages=[{"role": "user", "content": prompt}]
        )
        results[model] = response.choices[0].message.content
    return results

# Usage
models = [
    "meta-llama/llama-3.3-70b-instruct:free",
    "qwen/qwen-3-235b-a22b:free",
    "mistralai/mistral-small-3.1-24b:free"
]

results = compare_models("Explain quantum computing", models)
for model, answer in results.items():
    print(f"\n{model}:\n{answer[:200]}...")
```

### Case 2: Smart Model Router

```python {filename="Python"}
def smart_router(task, content):
    if "code" in task or "programming" in task:
        model = "mistralai/devstral-2512:free"
    elif "chinese" in task or len(content) > len(content.encode('utf-8')) * 0.7:
        model = "qwen/qwen-3-235b-a22b:free"
    elif len(content) > 5000:
        model = "meta-llama/llama-3.1-405b-instruct:free"
    else:
        model = "meta-llama/llama-3.3-70b-instruct:free"
    
    return model

# Usage
task = "Write a Python function"
model = smart_router(task, task)
print(f"Selected model: {model}")
```

---

**Service Provider:** [OpenRouter](/en/providers/openrouter)

