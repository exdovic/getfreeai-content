---
title: "GitHub Models API - Free AI Model API Service"
linkTitle: "API - GitHub Models"
description: "GitHub Models API offers free AI model API access! OpenAI compatible, supports 10+ models including GPT-4o, Llama 3.1, Phi-3, DeepSeek-R1. Each model has independent free quota."
keywords:
  - GitHub Models API
  - GitHub API
  - Free AI API
  - GPT-4o API
  - Llama 3.1 API
  - Phi-3 API
  - DeepSeek-R1 API
  - OpenAI Compatible
  - Free LLM API
  - GitHub Developer API
image: /images/logo.svg
type: docs
weight: 14
comments: true
prev: /services/api/cerebras
next: /services/chatbot
sidebar:
  open: true
---

## 📋 Service Overview

**Service Name:** GitHub Models API  
**Provider:** [GitHub Models](/providers/github-models)  
**API Endpoint:** `https://models.github.ai/inference`  
**Service Type:** Free (with rate limits)  
**Requirements:** GitHub account and Personal Access Token

---

## ✅ Service Description

GitHub Models API is a developer API interface provided by GitHub, allowing developers to programmatically call various mainstream AI models. The API is fully compatible with OpenAI specifications and can be called directly using the OpenAI SDK.

### Main Features

- **🔌 OpenAI Compatible** - Fully compatible with OpenAI API specifications, easy integration
- **🆓 Completely Free** - All models offer free access with rate limits
- **🤖 Multi-Model Support** - Supports 10+ mainstream AI models
- **🔒 Secure & Reliable** - Authentication based on GitHub Personal Access Token
- **🚀 Easy to Use** - Use OpenAI SDK or any HTTP client
- **📚 Comprehensive Docs** - Detailed official documentation and examples

---

## 🎁 Available Models

### Free Model List

| Model Name | Provider | Context Length | Features | Use Cases |
|---------|--------|-----------|------|---------|
| **gpt-4o** | OpenAI | 128K | Strongest overall | Complex reasoning, creative writing |
| **gpt-4o-mini** | OpenAI | 128K | Fast & lightweight | Daily chat, high-frequency calls |
| **Llama-3.1-405B** | Meta | 128K | Ultra-large open-source | Complex tasks |
| **Llama-3.1-70B** | Meta | 128K | Balanced performance | General tasks |
| **Llama-3.1-8B** | Meta | 128K | Fast response | Lightweight apps |
| **Phi-3.5-mini** | Microsoft | 128K | Small but powerful | Efficiency-focused |
| **Phi-3-medium** | Microsoft | 128K | Balanced | Medium complexity |
| **DeepSeek-R1** | DeepSeek | 64K | Strong reasoning | Logic, Chinese tasks |
| **Mistral-Large** | Mistral | 128K | European leader | Multilingual |
| **Mistral-Nemo** | Mistral | 128K | Lightweight & fast | Real-time apps |
| **Command-R+** | Cohere | 128K | RAG expert | Knowledge retrieval |

### Model Details

#### GPT-4o (Recommended)
- **Context Window:** 128K tokens
- **Primary Use:** Complex reasoning, creative writing, professional tasks
- **Advantages:** World-leading AI capability, multimodal support
- **Rate Limit:** 10 RPM, 50 RPD

#### Llama-3.1-405B
- **Context Window:** 128K tokens
- **Primary Use:** Complex reasoning, professional applications
- **Advantages:** Most powerful open-source model
- **Rate Limit:** 10 RPM, 50 RPD

#### DeepSeek-R1
- **Context Window:** 64K tokens
- **Primary Use:** Logic reasoning, Chinese tasks
- **Advantages:** Chinese optimized, strong reasoning
- **Rate Limit:** 15 RPM, 150 RPD

---

## 🔢 Quotas and Limits

### Free Tier Limits

Different models have different rate limits. Here are typical examples:

**High-tier Models (GPT-4o, Llama-3.1-405B):**

| Limit Item | Quota | Notes |
|--------|------|------|
| **Requests Per Minute** | 10 | RPM (Requests Per Minute) |
| **Requests Per Day** | 50 | RPD (Requests Per Day) |
| **Max Input Tokens** | 8,000 | Single request input limit |
| **Max Output Tokens** | 4,000 | Single request output limit |
| **Max Concurrent Requests** | 2 | Simultaneous requests |
| **Credit Card** | ❌ | Completely free |

**Low-tier Models (Phi-3, Llama-3.1-8B, DeepSeek-R1):**

| Limit Item | Quota | Notes |
|--------|------|------|
| **Requests Per Minute** | 15 | RPM |
| **Requests Per Day** | 150 | RPD |
| **Max Input Tokens** | 8,000 | Single request input limit |
| **Max Output Tokens** | 4,000 | Single request output limit |
| **Max Concurrent Requests** | 5 | Simultaneous requests |
| **Credit Card** | ❌ | Completely free |

### ⚠️ Important Limits

1. **Rate Limits:** Exceeding limits returns 429 error, recommend implementing exponential backoff retry.
2. **Daily Reset:** Daily quota resets at UTC 0:00.
3. **Concurrent Limit:** Requests exceeding max concurrency will be rejected.
4. **Token Limits:** Both input and output tokens have per-request limits.
5. **Quota Examples:** Above quotas are reference examples, actual limits may vary by model and account, check [model details page](https://github.com/marketplace/models) for real-time info.

### Quota Reset Time

- **Daily Quota:** Resets at UTC 0:00
- **Per-Minute Quota:** Rolling window, continuous reset
- **Concurrent Limit:** Real-time calculation, released immediately after request completes

---

## 💰 Pricing

### Free Quota

- **Free Usage:** All models completely free
- **No Credit Card:** No card required
- **Rate Limits:** Each model has independent rate limits
- **How to Get:** Register GitHub account and create PAT

### Paid Options

Currently GitHub Models API is completely free with no paid options. For higher quotas, consider:
- Using multiple models to distribute load
- Optimizing request frequency
- Or using official APIs from model providers

---

## 🚀 How to Use

### Prerequisites

**1. Register GitHub Account**

If you don't have a GitHub account, please [register first](/providers/github-models#registration-and-account).

**2. Create Personal Access Token**

{{% steps %}}

##### Visit GitHub Settings

1. Login to GitHub
2. Click avatar in top right > Settings
3. Select Developer settings in left menu

##### Create Token

1. Click Personal access tokens > Tokens (classic)
2. Click "Generate new token" > "Generate new token (classic)"
3. Set token name (e.g., GitHub Models API)
4. Set expiration (recommend choosing appropriate period)

##### Select Permission Scope

1. **Important:** Check `models` scope
2. This is required permission for GitHub Models API
3. No need to check other permissions

##### Generate and Save Token

1. Click "Generate token" at bottom of page
2. **Copy and save immediately** (shown only once!)
3. Save token to secure location (recommend using password manager)

{{% /steps %}}

---

## 💻 Code Examples

### Python Example

**Install Dependencies:**

```bash {filename="Bash"}
pip install openai
```

**Basic Usage:**

```python {filename="Python"}
from openai import OpenAI

# Initialize client
client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key="YOUR_GITHUB_PAT"  # Replace with your GitHub Personal Access Token
)

# Send request
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Hello, please introduce GitHub Models."}
    ],
    max_tokens=1000,
    temperature=0.7
)

# Print response
print(response.choices[0].message.content)

# View token usage
print(f"\nTotal Tokens: {response.usage.total_tokens}")
print(f"Input Tokens: {response.usage.prompt_tokens}")
print(f"Output Tokens: {response.usage.completion_tokens}")
```

**Streaming Example:**

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key="YOUR_GITHUB_PAT"
)

# Streaming output (suitable for real-time display)
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "user", "content": "Write a poem about programming"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)

print()  # New line
```

---

### cURL Example

**Basic Request:**

```bash {filename="Bash"}
curl -X POST "https://models.github.ai/inference/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_GITHUB_PAT" \
  -d '{
    "model": "gpt-4o",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "Hello, please introduce GitHub Models."
      }
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**Streaming:**

```bash {filename="Bash"}
curl -X POST "https://models.github.ai/inference/chat/completions" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_GITHUB_PAT" \
  -d '{
    "model": "gpt-4o",
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
  baseURL: 'https://models.github.ai/inference',
  apiKey: process.env.GITHUB_PAT,  // Use environment variable
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'gpt-4o',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: 'Hello, please introduce GitHub Models.' }
    ],
    max_tokens: 1000,
    temperature: 0.7,
  });

  console.log(completion.choices[0].message.content);
  console.log(`\nTotal Tokens: ${completion.usage.total_tokens}`);
}

main();
```

---

## 🌟 Core Advantages

### Technical Advantages

1. **OpenAI Compatibility:**
   - Fully compatible with OpenAI API specs
   - Can use OpenAI SDK directly
   - Easy migration from other platforms
   - Lower learning curve

2. **Multi-Model Access:**
   - One API accesses models from multiple providers
   - Easy to compare and select best model
   - Different models have different strengths
   - Flexible switching for different needs

3. **GitHub Ecosystem Integration:**
   - Deep integration with GitHub
   - Can be used in GitHub Actions
   - Convenient for development workflow
   - Unified authentication

### Comparison with Other APIs

| Feature | GitHub Models | Google AI Studio | Groq |
|------|---------------|------------------|------|
| Free Quota | Varies by model | Completely free | ~14,400/day |
| Model Count | 🏆 10+ models | 5+ models | 5+ models |
| OpenAI Compatible | ✅ Fully compatible | ❌ Needs adaptation | ✅ Fully compatible |
| Context Length | Up to 128K | Up to 2M | Up to 128K |
| GitHub Integration | 🏆 Deep integration | ❌ None | ❌ None |
| Credit Card | ❌ | ❌ | ⚠️ Some require |

---

## 💡 Practical Recommendations

### ✅ Recommended Practices

1. **Secure Token Management:**
   ```python
   import os
   from dotenv import load_dotenv
   
   # Use environment variables
   load_dotenv()
   api_key = os.getenv('GITHUB_PAT')
   
   # Don't hardcode tokens
   # ❌ api_key = "github_pat_xxxx"  # Don't do this!
   ```

2. **Choose the Right Model:**
   - Complex tasks: GPT-4o or Llama-3.1-405B
   - Daily tasks: GPT-4o-mini or Llama-3.1-8B
   - Chinese tasks: DeepSeek-R1
   - Knowledge retrieval: Cohere Command-R+

3. **Implement Error Handling:**
   ```python
   from openai import OpenAI, RateLimitError, APIError
   import time
   
   client = OpenAI(
       base_url="https://models.github.ai/inference",
       api_key=os.getenv('GITHUB_PAT')
   )
   
   def call_api_with_retry(messages, model="gpt-4o", max_retries=3):
       """API call with retry mechanism"""
       for attempt in range(max_retries):
           try:
               response = client.chat.completions.create(
                   model=model,
                   messages=messages
               )
               return response
           except RateLimitError:
               if attempt < max_retries - 1:
                   wait_time = 2 ** attempt  # Exponential backoff
                   print(f"Rate limit reached, waiting {wait_time}s...")
                   time.sleep(wait_time)
               else:
                   print("Max retries reached")
                   raise
           except APIError as e:
               print(f"API error: {e}")
               if attempt == max_retries - 1:
                   raise
       return None
   ```

### 🎯 Best Practices

**Maximize Free Quota:**
- Choose appropriate model based on task complexity
- Use caching to avoid duplicate requests
- Batch similar tasks
- Optimize prompts to reduce token usage

**Optimize Token Usage:**
```python
# ✅ Concise prompts
messages = [
    {"role": "user", "content": "Summarize key points: [text]"}
]

# ❌ Avoid redundancy
messages = [
    {"role": "system", "content": "You are an excellent assistant..."},
    {"role": "user", "content": "Please help me summarize..."}
]
```

**Monitor Usage:**
```python
def log_usage(response):
    """Log token usage"""
    usage = response.usage
    print(f"Input: {usage.prompt_tokens} tokens")
    print(f"Output: {usage.completion_tokens} tokens")
    print(f"Total: {usage.total_tokens} tokens")
    
    # Can save to file or database
    with open('usage_log.txt', 'a') as f:
        f.write(f"{usage.total_tokens}\n")
```

### ⚠️ Notes

1. **Rate Limits:** Different models have different limits, choose and allocate carefully.
2. **Token Security:** Don't commit PAT to public repos, use environment variables.
3. **Error Handling:** Implement comprehensive error handling and retry mechanisms.
4. **Cost Control:** Although free, use reasonably to avoid wasting quota.
5. **Data Privacy:** Do not include sensitive information (passwords, keys, personal data, etc.) in API requests.

---

## 🎯 Real-World Use Cases

### Case 1: Smart Code Review

**Scenario:** Use AI to automatically review code and provide improvement suggestions.

```python {filename="Python"}
from openai import OpenAI
import os

client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key=os.getenv('GITHUB_PAT')
)

def review_code(code):
    """AI code review"""
    response = client.chat.completions.create(
        model="gpt-4o",
        messages=[
            {"role": "system", "content": "You are a professional code review expert."},
            {"role": "user", "content": f"Review this code:\n\n{code}"}
        ]
    )
    return response.choices[0].message.content

# Usage example
code = """
def calc(a, b):
    return a + b
"""

review = review_code(code)
print(review)
```

### Case 2: Auto Documentation

**Scenario:** Automatically generate docstrings for functions.

```python {filename="Python"}
def generate_docstring(function_code):
    """Generate docstring for function"""
    response = client.chat.completions.create(
        model="gpt-4o",
        messages=[
            {"role": "system", "content": "Generate Python docstrings in Google style."},
            {"role": "user", "content": f"Generate docstring:\n\n{function_code}"}
        ]
    )
    return response.choices[0].message.content

# Usage example
function_code = """
def process_data(data, threshold=0.5):
    filtered = [x for x in data if x > threshold]
    return sum(filtered) / len(filtered) if filtered else 0
"""

docstring = generate_docstring(function_code)
print(docstring)
```

### Case 3: Model Comparison

**Scenario:** Compare output quality of different models.

```python {filename="Python"}
def compare_models(prompt, models=["gpt-4o", "llama-3.1-70b", "deepseek-r1"]):
    """Compare outputs from multiple models"""
    results = {}
    
    for model in models:
        try:
            response = client.chat.completions.create(
                model=model,
                messages=[{"role": "user", "content": prompt}]
            )
            results[model] = {
                "response": response.choices[0].message.content,
                "tokens": response.usage.total_tokens
            }
        except Exception as e:
            results[model] = {"error": str(e)}
    
    return results

# Usage example
prompt = "Explain recursion with a Python example."
comparison = compare_models(prompt)

for model, result in comparison.items():
    print(f"\n{'='*50}")
    print(f"Model: {model}")
    print(f"{'='*50}")
    if "error" in result:
        print(f"Error: {result['error']}")
    else:
        print(result['response'])
        print(f"\nTokens used: {result['tokens']}")
```

---

## 🔧 FAQ

**Q: How do I get a GitHub Personal Access Token?**  
A: Visit GitHub Settings > Developer settings > Personal access tokens, create new token and check `models` permission. See [registration steps](/providers/github-models#registration-steps).

**Q: What's the API endpoint?**  
A: Base URL is `https://models.github.ai/inference`, Chat Completions endpoint is `https://models.github.ai/inference/chat/completions`.

**Q: Which models are available?**  
A: Supports 10+ models including GPT-4o, Llama 3.1, Phi-3, DeepSeek-R1, Mistral, Cohere. See [Available Models](#available-models) section.

**Q: What are the rate limits?**  
A: Different models have different limits. E.g., GPT-4o: 10 RPM, 50 RPD; DeepSeek-R1: 15 RPM, 150 RPD. See [Quotas and Limits](#quotas-and-limits).

**Q: How to handle rate limit errors (429)?**  
A: Implement exponential backoff retry, or switch to another model. See [error handling example](#practical-recommendations).

**Q: Fully compatible with OpenAI API?**  
A: Yes, fully compatible with OpenAI Chat Completions API specs, can use OpenAI SDK directly.

**Q: Do I need to pay?**  
A: Currently completely free with rate limits. No credit card required.

**Q: How to protect API Token?**  
A: Use environment variables, don't commit to repos, rotate tokens regularly.

---

## 🔗 Related Resources

- **API Endpoint:** `https://models.github.ai/inference`
- **Official Documentation:** [https://docs.github.com/en/github-models](https://docs.github.com/en/github-models)
- **Quickstart Guide:** [https://docs.github.com/en/github-models/quickstart](https://docs.github.com/en/github-models/quickstart)
- **Provider Homepage:** [GitHub Models](/providers/github-models)
- **Corresponding Chatbot Service:** [GitHub Models Playground](/services/chatbot/github-models)
- **GitHub Marketplace:** [https://github.com/marketplace/models](https://github.com/marketplace/models)

---

## 📝 Update Log

- **September 2024:** GitHub Models API public testing launched
- **October 2024:** Added DeepSeek-R1 and other model support
- **November 2024:** Optimized API response speed and stability
- **2025:** Continuously adding new models, optimizing developer experience

---

**Service Provider:** [GitHub Models](/providers/github-models)

