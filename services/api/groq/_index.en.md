---
title: Groq - API
weight: 2
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [Groq](/en/providers/groq)  
**Service Type:** API Service  
**API Endpoint:** [https://api.groq.com/openai/v1](https://api.groq.com/openai/v1)  
**Free Tier:** Free Forever (with usage limits)  
**API Compatibility:** Fully compatible with OpenAI API

---

## 🎯 Service Overview

Groq API provides the industry's fastest LLM inference service, fully compatible with OpenAI API format, allowing you to switch existing code to Groq by simply changing the `base_url`.

**Key Advantages:**
- ⚡ **Industry Fastest** - 800+ tokens/s inference speed
- 🔄 **OpenAI Compatible** - Seamless code migration
- 🎁 **High Quota** - 14,400 requests/day
- 💰 **Completely Free** - No hidden fees
- 🚀 **Low Latency** - Millisecond first-token response

---

## 🚀 Quick Start

### Prerequisites

**Required:**
- ✅ API key created

For detailed steps, see: [Groq Registration Guide](/en/providers/groq#registration-and-account)

### 5-Minute Quick Example

**Method 1: Using Groq SDK (Recommended)**

```bash {filename="Bash"}
pip install groq
```

```python {filename="Python"}
from groq import Groq

# Initialize client
client = Groq(api_key="YOUR_API_KEY")

# Send request
chat_completion = client.chat.completions.create(
    messages=[
        {
            "role": "user",
            "content": "Explain Groq's LPU technology",
        }
    ],
    model="llama-3.3-70b-versatile",
)

# Print response
print(chat_completion.choices[0].message.content)
```

**Method 2: Using OpenAI SDK (Compatibility Mode)**

```python {filename="Python"}
from openai import OpenAI

# Just modify base_url and api_key
client = OpenAI(
    base_url="https://api.groq.com/openai/v1",
    api_key="YOUR_API_KEY"
)

# Rest of the code is identical to OpenAI
response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "user", "content": "Hello"}
    ]
)

print(response.choices[0].message.content)
```

---

## 🤖 Supported Models

### Llama Series (Recommended)

| Model ID | Parameters | Context | Speed | Use Cases |
|---------|-------|--------|------|---------|
| `llama-3.3-70b-versatile` | 70B | 128K | ⚡⚡⚡ | General tasks, best balance |
| `llama-3.1-70b-versatile` | 70B | 128K | ⚡⚡⚡ | Complex tasks |
| `llama-3.1-8b-instant` | 8B | 128K | ⚡⚡⚡⚡ | Fast responses |

### Other Models

| Model ID | Parameters | Context | Features |
|---------|-------|--------|------|
| `mixtral-8x7b-32768` | 47B | 32K | Mistral Mixture of Experts |
| `gemma2-9b-it` | 9B | 8K | Google Open Source |
| `deepseek-r1-distill-llama-70b` | 70B | 32K | Reasoning Expert |

---

## 🔢 Quotas and Limits

### API Quotas

| Limit Type | Free Tier | Notes |
|---------|---------|------|
| **Daily Requests** | 14,400 requests | Shared across all models |
| **Requests/Minute** | 30 requests | Shared across all models |
| **Daily Tokens** | 20,000-1,000,000 | Varies by model |
| **Tokens/Minute** | 6,000 tokens | Input + output combined |
| **Max Context** | 128K tokens | Llama 3.x series |
| **Max Output** | 8,192 tokens | Per request |

### ⚠️ Important Limitations

1. **Quota Sharing:** All models share the same account quota
2. **Rate Limits:** Returns 429 error when exceeded
3. **Daily Reset:** UTC 00:00
4. **Concurrency Limit:** Recommended max 10 concurrent requests

---

## 📖 API Usage Examples

### 1. Basic Conversation

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "system", "content": "You are a helpful AI assistant"},
        {"role": "user", "content": "What is machine learning?"}
    ]
)

print(response.choices[0].message.content)
```

### 2. Streaming Output

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

stream = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "user", "content": "Write an article about AI"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

### 3. Multi-turn Conversation

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

messages = [
    {"role": "system", "content": "You are a Python programming assistant"}
]

# First round
messages.append({"role": "user", "content": "How to read a file?"})
response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=messages
)
messages.append({"role": "assistant", "content": response.choices[0].message.content})

# Second round (model remembers context)
messages.append({"role": "user", "content": "What about writing?"})
response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=messages
)
print(response.choices[0].message.content)
```

### 4. Adjust Generation Parameters

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

response = client.chat.completions.create(
    model="llama-3.3-70b-versatile",
    messages=[
        {"role": "user", "content": "Write a poem"}
    ],
    temperature=0.9,        # Increase creativity
    max_tokens=1024,        # Limit output length
    top_p=0.95,            # Nucleus sampling
    frequency_penalty=0.5,  # Reduce repetition
    presence_penalty=0.5    # Increase topic diversity
)

print(response.choices[0].message.content)
```

### 5. Using cURL

```bash {filename="Bash"}
curl "https://api.groq.com/openai/v1/chat/completions" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "llama-3.3-70b-versatile",
    "messages": [
      {
        "role": "user",
        "content": "Hello, introduce Groq"
      }
    ]
  }'
```

### 6. Node.js Example

```bash {filename="Bash"}
npm install groq-sdk
```

```javascript {filename="JavaScript"}
const Groq = require("groq-sdk");

const groq = new Groq({
  apiKey: "YOUR_API_KEY"
});

async function main() {
  const chatCompletion = await groq.chat.completions.create({
    messages: [
      { role: "user", content: "Introduce Groq's LPU technology" }
    ],
    model: "llama-3.3-70b-versatile",
  });

  console.log(chatCompletion.choices[0].message.content);
}

main();
```

---

## 💡 Best Practices

### ✅ Recommended Practices

1. **Choose the Right Model**
   ```python
   # Fast tasks
   model = "llama-3.1-8b-instant"
   
   # Balanced performance
   model = "llama-3.3-70b-versatile"
   
   # Math/code reasoning
   model = "deepseek-r1-distill-llama-70b"
   ```

2. **Implement Error Handling and Retries**
   ```python
   import time
   from groq import Groq, RateLimitError
   
   client = Groq(api_key="YOUR_API_KEY")
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="llama-3.3-70b-versatile",
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

3. **Monitor Quota Usage**
   ```python
   import logging
   
   logging.basicConfig(level=logging.INFO)
   logger = logging.getLogger(__name__)
   
   def track_usage(response):
       usage = response.usage
       logger.info(f"Tokens used: "
                   f"input={usage.prompt_tokens}, "
                   f"output={usage.completion_tokens}, "
                   f"total={usage.total_tokens}")
       return response
   ```

4. **Use Streaming to Optimize Experience**
   ```python
   def stream_chat(prompt):
       stream = client.chat.completions.create(
           model="llama-3.3-70b-versatile",
           messages=[{"role": "user", "content": prompt}],
           stream=True
       )
       
       full_response = ""
       for chunk in stream:
           if chunk.choices[0].delta.content:
               content = chunk.choices[0].delta.content
               print(content, end="", flush=True)
               full_response += content
       
       return full_response
   ```

5. **Securely Manage API Keys**
   ```python
   import os
   from dotenv import load_dotenv
   
   # Use environment variables
   load_dotenv()
   api_key = os.getenv('GROQ_API_KEY')
   
   client = Groq(api_key=api_key)
   ```

---

## 🔧 Common Issues

### 1. 429 Error: Rate Limit Exceeded

**Cause:** Exceeded rate limit

**Solution:**
```python {filename="Python"}
import time
from groq import RateLimitError

try:
    response = client.chat.completions.create(...)
except RateLimitError as e:
    print(f"Rate limited: {e}")
    print("Retry after waiting...")
    time.sleep(60)  # Wait 1 minute
    response = client.chat.completions.create(...)
```

### 2. 401 Error: Invalid API Key

**Cause:** API key is invalid or expired

**Solution:**
1. Check if API key is correct
2. Regenerate key in Console
3. Ensure no extra spaces in key

### 3. Network Timeout

**Solution:**
```python {filename="Python"}
from groq import Groq

client = Groq(
    api_key="YOUR_API_KEY",
    timeout=60.0  # Set 60 second timeout
)
```

### 4. How to Check Remaining Quota?

**Method:**
1. Login to https://console.groq.com
2. Visit "Usage" page
3. View current quota usage

---

## 📊 Performance Optimization

### 1. Batch Processing

```python {filename="Python"}
import asyncio
from groq import AsyncGroq

async def batch_process(questions):
    client = AsyncGroq(api_key="YOUR_API_KEY")
    
    tasks = []
    for q in questions:
        task = client.chat.completions.create(
            model="llama-3.1-8b-instant",
            messages=[{"role": "user", "content": q}]
        )
        tasks.append(task)
    
    return await asyncio.gather(*tasks)

# Usage
questions = ["Question 1", "Question 2", "Question 3"]
responses = asyncio.run(batch_process(questions))
```

### 2. Cache Results

```python {filename="Python"}
from functools import lru_cache
import hashlib
import json

cache = {}

def get_cache_key(messages):
    return hashlib.md5(
        json.dumps(messages, sort_keys=True).encode()
    ).hexdigest()

def cached_completion(messages):
    key = get_cache_key(messages)
    
    if key in cache:
        print("Using cached result")
        return cache[key]
    
    response = client.chat.completions.create(
        model="llama-3.3-70b-versatile",
        messages=messages
    )
    
    cache[key] = response
    return response
```

### 3. Choose Appropriate Model

```python {filename="Python"}
def select_model(task_complexity):
    if task_complexity == "simple":
        return "llama-3.1-8b-instant"  # Fastest
    elif task_complexity == "medium":
        return "llama-3.3-70b-versatile"  # Balanced
    elif task_complexity == "complex":
        return "deepseek-r1-distill-llama-70b"  # Reasoning
```

---

## 📚 Related Resources

### Official Documentation
- [Groq Complete Guide](/en/providers/groq)
- [Playground Usage Guide](/en/services/chatbot/groq)
- [API Official Docs](https://console.groq.com/docs)

### SDKs and Tools
- [Python SDK](https://github.com/groq/groq-python)
- [Node.js SDK](https://github.com/groq/groq-typescript)
- [API Reference](https://console.groq.com/docs/api-reference)

### Example Code
- [Example Repository](https://github.com/groq/groq-api-cookbook)
- [Community Examples](https://discord.gg/groq)

---

## 🌟 Practical Cases

### Case 1: Real-time Chatbot

```python {filename="Python"}
import streamlit as st
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

st.title("Groq Ultra-fast Chatbot")

if "messages" not in st.session_state:
    st.session_state.messages = []

# Display message history
for message in st.session_state.messages:
    with st.chat_message(message["role"]):
        st.write(message["content"])

# User input
if prompt := st.chat_input("Enter your question..."):
    # Add user message
    st.session_state.messages.append({"role": "user", "content": prompt})
    with st.chat_message("user"):
        st.write(prompt)
    
    # Generate response
    with st.chat_message("assistant"):
        stream = client.chat.completions.create(
            model="llama-3.3-70b-versatile",
            messages=st.session_state.messages,
            stream=True
        )
        
        response = st.write_stream(
            (chunk.choices[0].delta.content for chunk in stream 
             if chunk.choices[0].delta.content)
        )
    
    # Add assistant message
    st.session_state.messages.append({"role": "assistant", "content": response})
```

### Case 2: Code Assistant

```python {filename="Python"}
from groq import Groq

client = Groq(api_key="YOUR_API_KEY")

def code_assistant(language, task):
    response = client.chat.completions.create(
        model="llama-3.3-70b-versatile",
        messages=[
            {
                "role": "system",
                "content": f"You are a professional {language} programming assistant. "
                           f"Provide clear code examples and explanations."
            },
            {
                "role": "user",
                "content": task
            }
        ],
        temperature=0.2  # Lower temperature for more deterministic code
    )
    
    return response.choices[0].message.content

# Usage
result = code_assistant("Python", "Implement a binary search algorithm")
print(result)
```

---

**Service Provider:** [Groq](/en/providers/groq)

