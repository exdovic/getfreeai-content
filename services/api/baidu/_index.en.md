---
title: "Baidu Qianfan API - Permanently Free Chinese AI API Service"
linkTitle: "API - Baidu"
description: "Baidu Qianfan platform offers permanently free API service! ERNIE-3.5-8K and ERNIE-Speed-8K permanently free unlimited, performance exceeds GPT-3.5, supports OpenAI SDK, optimized for Chinese, fast domestic access."
keywords:
  - Baidu Qianfan API
  - ERNIE API
  - Wenxin API
  - Free Chinese API
  - Chinese AI API
  - Permanently Free API
  - OpenAI Compatible
  - Baidu Cloud AI
image: /images/logo.svg
type: docs
weight: 8
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [Baidu](/providers/baidu)  
**Service Type:** API Service  
**API Endpoint:** `https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop/chat/`  
**Free Type:** Permanently Free (some models) + New User Gift  
**API Compatibility:** Supports OpenAI SDK

---

## 🎯 Service Overview

Baidu Qianfan LLM Platform provides powerful AI API services, featuring **permanently free** high-performance models, fully compatible with OpenAI SDK, offering zero-cost AI capabilities for developers.

**Core Advantages:**
- 🎁 **Permanently Free Models** - ERNIE-3.5-8K, ERNIE-Speed-8K permanently free
- 💰 **Excellent Value** - Free models outperform GPT-3.5 Turbo
- 🔄 **OpenAI Compatible** - Supports OpenAI SDK, one-line migration
- 🇨🇳 **Chinese Optimized** - Optimized for Chinese, top performance
- 🚀 **Fast Domestic Access** - Servers in China, quick response
- 🎁 **New User Gift** - ERNIE-4.0-8K 1M tokens/month (first month)
- 🔒 **Compliant for Business** - Domestic compliance, safe for commercial use

---

## 🚀 Quick Start

### Prerequisites

**Required:**
- ✅ Registered Baidu Cloud account
- ✅ Completed real-name verification
- ✅ Created application and obtained API Key

For detailed steps, see: [Baidu Registration Guide](/providers/baidu#registration-and-account)

### 5-Minute Quick Example

**Using OpenAI SDK (Recommended)**

```python {filename="Python"}
from openai import OpenAI

# Configure Baidu Qianfan (using OpenAI SDK)
client = OpenAI(
    api_key="YOUR_BAIDU_API_KEY",
    base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
)

# Call permanently free ERNIE-3.5-8K
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=[
        {"role": "system", "content": "You are a helpful assistant"},
        {"role": "user", "content": "Introduce quantum computing"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 Supported Models

### Permanently Free Models

| Model ID | Context | Features | QPS | Price |
|----------|---------|----------|-----|-------|
| `ernie-3.5-8k` | 8K | 🏆 Exceeds GPT-3.5 | 50 | **Permanently Free** |
| `ernie-speed-8k` | 8K | ⚡ Ultra-fast | 50 | **Permanently Free** |

### New User Gift

| Model ID | Context | Features | QPS | Free Quota |
|----------|---------|----------|-----|-----------|
| `ernie-4.0-8k` | 8K | 🆕 Latest flagship | 5 | 1M tokens/month (first month) |

### Paid Models

| Model ID | Context | Features | Price (input/output) |
|----------|---------|----------|---------------------|
| `ernie-4.0-turbo-8k` | 8K | High-performance flagship | ¥12/M / ¥12/M |
| `ernie-4.0-turbo-128k` | 128K | Ultra-long context | ¥20/M / ¥20/M |
| `ernie-lite-8k` | 8K | Lightweight & fast | ¥0/M / ¥0/M (trial) |

⚠️ **Important Notes:**
- ERNIE-3.5-8K and ERNIE-Speed-8K are **permanently free with unlimited tokens**
- QPS Limit: Maximum requests per second (can be increased with paid plans)
- New users receive 1M tokens of ERNIE-4.0-8K in first month
- For detailed pricing, see [Official Pricing](https://cloud.baidu.com/doc/qianfan/s/Blfmc9dlf)

---

## 🔢 Quotas and Limits

### Permanently Free Model Limits

| Limit | ERNIE-3.5-8K | ERNIE-Speed-8K |
|-------|--------------|----------------|
| **Token Limit** | Unlimited | Unlimited |
| **QPS** | 50 | 50 |
| **Concurrent** | 50 | 50 |
| **Context** | 8K tokens | 8K tokens |
| **Duration** | Permanent | Permanent |

### New User Gift Limits

| Limit | ERNIE-4.0-8K |
|-------|--------------|
| **Free Quota** | 1M tokens/month |
| **Duration** | First month after registration |
| **QPS** | 5 |

### Quota Query

- Real-time quota check: [Console Quota Page](https://console.bce.baidu.com/qianfan/ais/console/quota)
- Usage statistics: Console → Qianfan Platform → Usage Statistics

---

## 💻 Code Examples

### 1. Basic Conversation (OpenAI SDK)

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_BAIDU_API_KEY",
    base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
)

# Use permanently free ERNIE-3.5
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=[
        {"role": "user", "content": "What is artificial intelligence?"}
    ]
)

print(response.choices[0].message.content)
```

### 2. Streaming Output

```python {filename="Python"}
# Streaming output (for real-time display)
stream = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=[
        {"role": "user", "content": "Write an article about AI"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

### 3. Multi-turn Conversation

```python {filename="Python"}
messages = [
    {"role": "system", "content": "You are a Python programming assistant"}
]

# First round
messages.append({"role": "user", "content": "How to read CSV files?"})
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=messages
)
messages.append({
    "role": "assistant", 
    "content": response.choices[0].message.content
})

# Second round
messages.append({"role": "user", "content": "How to handle missing values?"})
response = client.chat.completions.create(
    model="ernie-3.5-8k",
    messages=messages
)
print(response.choices[0].message.content)
```

### 4. Using Official SDK

```python {filename="Python"}
# Install official SDK
# pip install qianfan

import qianfan

# Initialize with API Key and Secret Key
chat_comp = qianfan.ChatCompletion(
    api_key="YOUR_API_KEY",
    secret_key="YOUR_SECRET_KEY"
)

# Call ERNIE-3.5-8K
resp = chat_comp.do(
    model="ERNIE-3.5-8K",
    messages=[{
        "role": "user",
        "content": "Hello, please introduce yourself"
    }]
)

print(resp["result"])
```

### 5. cURL Example

```bash {filename="Bash"}
# Get access_token
curl -X POST \
  'https://aip.baidubce.com/oauth/2.0/token?grant_type=client_credentials&client_id=YOUR_API_KEY&client_secret=YOUR_SECRET_KEY'

# Call API (using obtained access_token)
curl -X POST \
  'https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop/chat/ernie-3.5-8k?access_token=YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{
    "messages": [
      {
        "role": "user",
        "content": "Hello, please introduce yourself"
      }
    ]
  }'
```

---

## 💡 Best Practices

### ✅ Recommended Approaches

1. **Choose the Right Model**
   ```python
   # General tasks, cost priority → ERNIE-3.5-8K (permanently free)
   model = "ernie-3.5-8k"
   
   # Speed priority → ERNIE-Speed-8K (permanently free)
   model = "ernie-speed-8k"
   
   # Quality priority → ERNIE-4.0-8K (free for new users)
   model = "ernie-4.0-8k"
   ```

2. **Error Handling and Retry**
   ```python
   import time
   from openai import OpenAI, APIError
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="ernie-3.5-8k",
                   messages=messages
               )
           except APIError as e:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"API error, waiting {wait_time} seconds...")
                   time.sleep(wait_time)
               else:
                   raise
   ```

3. **Secure Key Management**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('BAIDU_API_KEY')
   secret_key = os.getenv('BAIDU_SECRET_KEY')
   
   client = OpenAI(
       api_key=api_key,
       base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
   )
   ```

4. **Monitor Usage**
   - Regularly visit [Console](https://console.bce.baidu.com/qianfan/ais/console/quota)
   - Check remaining quota and usage statistics
   - Set quota alerts

### 🎯 Optimization Tips

**Leverage Permanently Free Models:**
- ERNIE-3.5-8K already exceeds GPT-3.5 Turbo
- Suitable for most use cases
- Zero-cost development and operations

**Optimize QPS Usage:**
- Allocate concurrent requests reasonably
- Excess QPS will queue
- Consider paid upgrade for higher QPS

**Result Caching:**
```python
import hashlib
import json

cache = {}

def cached_completion(model, messages):
    key = hashlib.md5(
        json.dumps({"model": model, "messages": messages}).encode()
    ).hexdigest()
    
    if key in cache:
        return cache[key]
    
    response = client.chat.completions.create(
        model=model,
        messages=messages
    )
    
    cache[key] = response
    return response
```

### ⚠️ Notes

1. **Real-name Verification Required:** Must complete verification for API use
2. **QPS Limits:** Free models have QPS of 50, excess will queue
3. **Content Moderation:** Complies with Chinese laws, sensitive content rejected
4. **Token Calculation:** Chinese calculated by characters, ~1.5-2 chars = 1 token

---

## 🔧 FAQ

### 1. How to get API Key?

**Steps:**
1. Login to [Baidu Cloud Qianfan Platform](https://qianfan.cloud.baidu.com)
2. Complete real-name verification
3. Create application
4. Get API Key and Secret Key

### 2. Are permanently free models really unlimited?

**Answer:** Yes! ERNIE-3.5-8K and ERNIE-Speed-8K are permanently free with unlimited tokens, only QPS (50 requests/second) limit.

### 3. How to use OpenAI SDK?

**Answer:** Baidu Qianfan supports OpenAI SDK, just modify `base_url`:
```python
client = OpenAI(
    api_key="YOUR_BAIDU_API_KEY",
    base_url="https://aip.baidubce.com/rpc/2.0/ai_custom/v1/wenxinworkshop"
)
```

### 4. How does ERNIE-3.5 compare to GPT-3.5?

**Answer:** According to official data and testing:
- Chinese: ERNIE-3.5 > GPT-3.5 Turbo
- English: ERNIE-3.5 ≈ GPT-3.5 Turbo
- Price: ERNIE-3.5 permanently free, GPT-3.5 paid

### 5. How to get new user gift?

**Answer:** 
- Register Baidu Cloud account
- Complete real-name verification
- Automatically receive 1M tokens of ERNIE-4.0-8K in first month
- Valid for first month after registration

### 6. What payment methods are supported?

**Answer:** 
- Alipay
- WeChat Pay
- Bank transfer
- Bank card

---

## 📊 Performance Comparison

### Comparison with Other APIs

| API | Free Type | Quota | Chinese | OpenAI Compatible |
|-----|-----------|-------|---------|-------------------|
| **Baidu Qianfan** | 🏆 Permanently Free | Unlimited | 🏆 Top | ✅ |
| Google AI Studio | Permanently Free | Free | Good | ❌ |
| DeepSeek | Trial Credits | ¥5 (7 days) | 🏆 Top | ✅ |
| Groq | Free Service | ~14,400 req/day | Good | ✅ |

### Price Advantage

| Scenario | Baidu Qianfan | GPT-3.5 Turbo | Savings |
|----------|--------------|---------------|---------|
| 1M tokens | **Free** | ~$1.5 | 100% |
| 10M tokens | **Free** | ~$15 | 100% |
| 100M tokens | **Free** | ~$150 | 100% |

---

## 🌟 Practical Cases

### Case 1: AI Customer Service

```python {filename="Python"}
def ai_customer_service(user_question):
    """AI customer service assistant"""
    response = client.chat.completions.create(
        model="ernie-3.5-8k",  # Use permanently free model
        messages=[
            {
                "role": "system",
                "content": "You are a professional customer service assistant"
            },
            {
                "role": "user",
                "content": user_question
            }
        ]
    )
    return response.choices[0].message.content

# Usage
answer = ai_customer_service("What are the features of your product?")
print(answer)
```

### Case 2: Document Summarization

```python {filename="Python"}
def summarize_document(document_text):
    """Generate document summary"""
    response = client.chat.completions.create(
        model="ernie-3.5-8k",
        messages=[
            {
                "role": "system",
                "content": "You are a document analysis expert"
            },
            {
                "role": "user",
                "content": f"Please summarize the core content:\n\n{document_text}"
            }
        ]
    )
    return response.choices[0].message.content
```

### Case 3: Content Moderation

```python {filename="Python"}
def content_moderation(user_content):
    """Content moderation"""
    response = client.chat.completions.create(
        model="ernie-speed-8k",  # Use ultra-fast model
        messages=[
            {
                "role": "system",
                "content": "You are a content moderation expert"
            },
            {
                "role": "user",
                "content": f"Judge if this content is compliant:\n{user_content}"
            }
        ]
    )
    return response.choices[0].message.content
```

---

## 📚 Related Resources

### Official Documentation
- [Complete Baidu Introduction](/providers/baidu)
- [Chatbot Usage Guide](/services/chatbot/baidu)
- [API Official Documentation](https://cloud.baidu.com/doc/qianfan/index.html)

### Tools and Resources
- [Qianfan Console](https://console.bce.baidu.com/qianfan/overview)
- [Quota Query](https://console.bce.baidu.com/qianfan/ais/console/quota)
- [Pricing](https://cloud.baidu.com/doc/qianfan/s/Blfmc9dlf)
- [Real-name Verification](https://console.bce.baidu.com/idc/#/personal/verify)
- [Official SDK (Python)](https://github.com/baidubce/bce-qianfan-sdk)

---

## 📝 Update Log

- **2025:** ERNIE-3.5-8K and ERNIE-Speed-8K permanently free
- **March 2025:** Released ERNIE 4.5 and ERNIE X1 new models
- **Continuous Updates:** Ongoing optimization of API performance and stability

---

**Service Provider:** [Baidu](/providers/baidu)
