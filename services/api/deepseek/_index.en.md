---
title: DeepSeek - API
weight: 4
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [DeepSeek](/en/providers/deepseek)  
**Service Type:** API Service  
**API Endpoint:** [https://api.deepseek.com](https://api.deepseek.com)  
**Free Tier:** Trial Credits (¥5, 7-day validity)  
**API Compatibility:** Fully compatible with OpenAI API

---

## 🎯 Service Overview

DeepSeek API provides powerful AI capabilities, fully compatible with OpenAI API format, priced 97% cheaper than GPT-4, making it ideal for developers on a budget who need high performance.

**Key Advantages:**
- 💰 **Ultra-low Price** - 97% cheaper than GPT-4
- 🔄 **OpenAI Compatible** - Seamless code migration
- 🧠 **Strong Reasoning** - R1 model with visible chain-of-thought
- 💻 **Code Expert** - Coder V2 specialized in programming
- 🇨🇳 **Chinese Optimized** - Top-tier Chinese performance
- 🎁 **Trial Credits** - New users receive ¥5

---

## 🚀 Quick Start

### Prerequisites

**Required:**
- ✅ Registered developer account
- ✅ Completed real-name verification (ID card upload)
- ✅ API key created

For detailed steps, see: [DeepSeek Registration Guide](/en/providers/deepseek#registration-and-account)

### 5-Minute Quick Example

**Using OpenAI SDK (Recommended)**

```python {filename="Python"}
from openai import OpenAI

# Configure DeepSeek
client = OpenAI(
    api_key="YOUR_DEEPSEEK_API_KEY",
    base_url="https://api.deepseek.com"
)

# Use DeepSeek Chat
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "system", "content": "You are a helpful assistant"},
        {"role": "user", "content": "Explain what deep learning is"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 Supported Models

### Model List

| Model ID | Type | Features | Price |
|----------|------|------|------|
| `deepseek-chat` | General conversation | V3 flagship | ¥1(in)/¥2(out) |
| `deepseek-reasoner` | Reasoning model | R1 visible chain-of-thought | ¥5.5(in)/¥19(out) |
| `deepseek-coder` | Code model | Coder V2 professional | ¥1(in)/¥2(out) |

**Price unit:** RMB per million tokens

---

## 🔢 Trial Credits and Pricing

### Trial Credits

| Item | Details |
|------|------|
| **Amount** | ¥5 RMB |
| **Usage** | ~500M tokens (chat model) |
| **Validity** | 7 days after registration |
| **How to Get** | Automatically after registration and verification |

### Pricing After Recharge

**deepseek-chat & deepseek-coder:**
- Input: ¥1 / million tokens
- Output: ¥2 / million tokens

**deepseek-reasoner:**
- Input: ¥5.5 / million tokens
- Output: ¥19 / million tokens

### Price Comparison

| Model | Input | Output | Relative Savings |
|------|------|------|---------|
| **DeepSeek** | ¥1 | ¥2 | Baseline |
| GPT-4 Turbo | ¥70 | ¥210 | **70-105x** |
| Claude 3.5 | ¥21 | ¥105 | **21-53x** |
| Gemini 1.5 | ¥8.75 | ¥35 | **8.75-17.5x** |

---

## 📖 API Usage Examples

### 1. Basic Conversation

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_DEEPSEEK_API_KEY",
    base_url="https://api.deepseek.com"
)

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "system", "content": "You are a helpful AI assistant"},
        {"role": "user", "content": "What is machine learning?"}
    ]
)

print(response.choices[0].message.content)
```

### 2. Streaming Output

```python {filename="Python"}
stream = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "user", "content": "Write an article about AI"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

### 3. Using Reasoning Model (R1)

```python {filename="Python"}
# Use DeepSeek R1 reasoning model
response = client.chat.completions.create(
    model="deepseek-reasoner",
    messages=[
        {
            "role": "user",
            "content": "There are 100 balls. Each time, take half and put back 1. Repeat this process. How many balls remain?"
        }
    ]
)

# View reasoning process
print("=== Thinking Process ===")
print(response.choices[0].message.reasoning_content)

# View final answer
print("\n=== Final Answer ===")
print(response.choices[0].message.content)
```

### 4. Code Generation (Coder)

```python {filename="Python"}
response = client.chat.completions.create(
    model="deepseek-coder",
    messages=[
        {
            "role": "system",
            "content": "You are a professional programming assistant"
        },
        {
            "role": "user",
            "content": "Implement quicksort algorithm in Python"
        }
    ]
)

print(response.choices[0].message.content)
```

### 5. cURL Example

```bash {filename="Bash"}
curl https://api.deepseek.com/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_DEEPSEEK_API_KEY" \
  -d '{
    "model": "deepseek-chat",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant"
      },
      {
        "role": "user",
        "content": "Hello, introduce yourself"
      }
    ]
  }'
```

### 6. Multi-turn Conversation

```python {filename="Python"}
messages = [
    {"role": "system", "content": "You are a Python programming assistant"}
]

# First round
messages.append({"role": "user", "content": "How to read a file?"})
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=messages
)
messages.append({"role": "assistant", "content": response.choices[0].message.content})

# Second round
messages.append({"role": "user", "content": "What about writing?"})
response = client.chat.completions.create(
    model="deepseek-chat",
    messages=messages
)
print(response.choices[0].message.content)
```

---

## 💡 Best Practices

### ✅ Recommended Practices

1. **Choose the Right Model**
   ```python
   # General tasks - cheapest
   model = "deepseek-chat"
   
   # Code tasks - programming expert
   model = "deepseek-coder"
   
   # Complex reasoning - math, logic
   model = "deepseek-reasoner"
   ```

2. **Error Handling and Retries**
   ```python
   import time
   from openai import OpenAI, APIError
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="deepseek-chat",
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

3. **Monitor Usage**
   ```python
   # Visit https://platform.deepseek.com
   # Billing Center → View detailed usage statistics
   ```

4. **Securely Manage API Keys**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('DEEPSEEK_API_KEY')
   
   client = OpenAI(
       api_key=api_key,
       base_url="https://api.deepseek.com"
   )
   ```

---

## 🔧 Common Issues

### 1. How to Complete Real-name Verification?

**Steps:**
1. Login to https://platform.deepseek.com
2. Avatar → Account Settings → Real-name Verification
3. Upload ID card (front and back)
4. Wait for review (1-24 hours)

### 2. What When Trial Credits Run Out?

**Solution:**
- Can recharge to continue using
- Extremely low price (¥1-2/M tokens)
- Supports Alipay, WeChat Pay

### 3. What Payment Methods Are Supported?

**Supported:**
- Alipay
- WeChat Pay
- Corporate transfer

### 4. How to Check Balance?

**Method:**
- Login to console
- Billing Center → Balance Inquiry

---

## 📊 Performance Optimization

### 1. Choose Appropriate Model

```python {filename="Python"}
def select_model(task_type):
    if task_type == "code":
        return "deepseek-coder"
    elif task_type == "reasoning":
        return "deepseek-reasoner"
    else:
        return "deepseek-chat"  # Cheapest
```

### 2. Result Caching

```python {filename="Python"}
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

---

## 📚 Related Resources

### Official Documentation
- [DeepSeek Complete Guide](/en/providers/deepseek)
- [Chatbot Usage Guide](/en/services/chatbot/deepseek)
- [API Official Docs](https://platform.deepseek.com/api-docs)

### Tools and Resources
- [Pricing Information](https://platform.deepseek.com/pricing)
- [Developer Console](https://platform.deepseek.com)
- [Help Center](https://platform.deepseek.com/docs)

---

## 🌟 Practical Cases

### Case 1: Academic Paper Assistant

```python {filename="Python"}
def analyze_paper(paper_text):
    """Analyze academic paper"""
    response = client.chat.completions.create(
        model="deepseek-chat",
        messages=[
            {
                "role": "system",
                "content": "You are an academic paper analysis expert"
            },
            {
                "role": "user",
                "content": f"Please analyze the core contributions and innovations of the following paper:\n\n{paper_text}"
            }
        ]
    )
    return response.choices[0].message.content
```

### Case 2: Code Review Assistant

```python {filename="Python"}
def code_review(code):
    """Code review and optimization suggestions"""
    response = client.chat.completions.create(
        model="deepseek-coder",
        messages=[
            {
                "role": "system",
                "content": "You are a code review expert"
            },
            {
                "role": "user",
                "content": f"Please review the following code:\n\n```python\n{code}\n```"
            }
        ]
    )
    return response.choices[0].message.content
```

### Case 3: Math Problem Solver

```python {filename="Python"}
def solve_math_problem(problem):
    """Use R1 model to solve math problems"""
    response = client.chat.completions.create(
        model="deepseek-reasoner",
        messages=[
            {
                "role": "user",
                "content": f"Please solve the following math problem: {problem}"
            }
        ]
    )
    
    print("=== Thinking Process ===")
    print(response.choices[0].message.reasoning_content)
    print("\n=== Final Answer ===")
    print(response.choices[0].message.content)
```

---

**Service Provider:** [DeepSeek](/en/providers/deepseek)

