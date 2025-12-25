---
title: Google AI Studio - API
weight: 1
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [Google AI Studio](/en/providers/google-ai-studio)  
**Service Type:** API Service  
**API Endpoint:** [https://generativelanguage.googleapis.com](https://generativelanguage.googleapis.com)  
**Free Tier:** Free Forever (with usage limits)

---

## 🎯 Service Overview

Google AI Studio API provides powerful access to Gemini models, fully compatible with OpenAI API format, allowing developers to easily integrate into their applications.

**Key Advantages:**
- 🎁 **High Free Quota** - 15M tokens/day (Flash series)
- ⚡ **Fast Response** - Flash series optimized
- 🔄 **OpenAI Compatible** - Seamless code migration
- 🎨 **Multimodal API** - Text, image, audio, video support
- 📱 **Long Context** - Up to 2M tokens
- 🔍 **Web Search** - Google Search Grounding

---

## 🚀 Quick Start

### Prerequisites

**Required:**
- ✅ API key created

For detailed steps, see: [Google AI Studio Registration Guide](/en/providers/google-ai-studio#registration-and-account)

### Get API Key

1. Visit: https://aistudio.google.com
2. Click "Get API key" in left menu
3. Select or create a Google Cloud project
4. Click "Create API key"
5. **Copy and save the key immediately**

### 5-Minute Quick Example

**Python Example:**

```python {filename="Python"}
import google.generativeai as genai

# Configure API key
genai.configure(api_key="YOUR_API_KEY")

# Create model instance
model = genai.GenerativeModel('gemini-2.5-flash')

# Send request
response = model.generate_content("Hello, please introduce yourself")
print(response.text)
```

**cURL Example:**

```bash {filename="Bash"}
curl https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=YOUR_API_KEY \
  -H 'Content-Type: application/json' \
  -d '{
    "contents": [{
      "parts":[{"text": "Hello, please introduce yourself"}]
    }]
  }'
```

---

## 🤖 Supported Models

### Gemini Flash Series (Recommended)

| Model Name | Model ID | Features | Use Cases |
|---------|---------|------|---------|
| **Gemini 3 Flash** | `gemini-3-flash` | Fastest speed | High-frequency calls, real-time responses |
| **Gemini 2.5 Flash** | `gemini-2.5-flash` | Next-gen fast model | Daily tasks, balanced performance |
| **Gemini 2.5 Flash-Lite** | `gemini-2.5-flash-lite` | Lightweight ultra-fast | Simple tasks, instant responses |

### Gemini Pro Series

| Model Name | Model ID | Features | Use Cases |
|---------|---------|------|---------|
| **Gemini Pro** | `gemini-pro` | Better understanding | Complex tasks, deep reasoning |

### Gemma Open Source Series

| Model Name | Model ID | Features | Use Cases |
|---------|---------|------|---------|
| **Gemma 3 27B** | `gemma-3-27b-instruct` | Large parameters | Complex tasks |
| **Gemma 3 12B** | `gemma-3-12b-instruct` | Medium parameters | Balanced performance |
| **Gemma 3 4B** | `gemma-3-4b-instruct` | Small and fast | Lightweight tasks |

---

## 🔢 Quotas and Limits

### API Quotas

| Model Name | Daily Requests | Requests/Minute | Tokens/Minute |
|---------|-----------|-------------|--------------|
| Gemini 3 Flash | 20 requests/day | 5 requests/min | 250,000 tokens/min |
| Gemini 2.5 Flash | 20 requests/day | 5 requests/min | 250,000 tokens/min |
| Gemini 2.5 Flash-Lite | 20 requests/day | 10 requests/min | 250,000 tokens/min |
| Gemma 3 27B | 14,400 requests/day | 30 requests/min | 15,000 tokens/min |
| Gemma 3 12B | 14,400 requests/day | 30 requests/min | 15,000 tokens/min |
| Gemma 3 4B | 14,400 requests/day | 30 requests/min | 15,000 tokens/min |

### Daily Total Quotas

| Model Series | Daily Tokens Quota |
|---------|----------------|
| Gemini Flash Series | 15M tokens |
| Gemini Pro Series | 3M tokens |
| Gemma Series | 4M tokens |

### Context Length

| Model | Input Context | Output Length |
|------|-----------|---------|
| Gemini Series | Up to 2M tokens | 8,192 tokens |
| Gemma Series | 8K-128K tokens | 8,192 tokens |

### ⚠️ Important Limitations

1. **Total Request Limit:** All Gemini models share a daily quota of 1500 requests
2. **Cross-model Rate Limit:** 60 requests/min (across all models)
3. **Quota Sharing:** All API keys share the same GCP project quota

---

## 📖 API Usage Examples

### 1. Basic Text Generation

**Python SDK:**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# Simple conversation
response = model.generate_content("Explain what machine learning is")
print(response.text)

# Request with parameters
response = model.generate_content(
    "Write a poem about autumn",
    generation_config={
        "temperature": 0.9,
        "top_p": 0.95,
        "max_output_tokens": 1024,
    }
)
print(response.text)
```

**REST API:**

```bash {filename="Bash"}
curl https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=YOUR_API_KEY \
  -H 'Content-Type: application/json' \
  -d '{
    "contents": [{
      "parts":[{"text": "Explain what machine learning is"}]
    }],
    "generationConfig": {
      "temperature": 0.7,
      "maxOutputTokens": 1024
    }
  }'
```

### 2. Multi-turn Conversation

**Python SDK:**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# Create chat session
chat = model.start_chat(history=[])

# First round
response = chat.send_message("Hello, I want to learn Python")
print(response.text)

# Second round (model remembers context)
response = chat.send_message("Where should I start?")
print(response.text)

# View chat history
print(chat.history)
```

### 3. Image Understanding

**Python SDK:**

```python {filename="Python"}
import google.generativeai as genai
from PIL import Image

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# Load image
image = Image.open('example.jpg')

# Send image and question
response = model.generate_content([
    "What's in this image? Please describe in detail.",
    image
])
print(response.text)
```

**Load image from URL:**

```python {filename="Python"}
import google.generativeai as genai
from PIL import Image
import requests
from io import BytesIO

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# Load image from URL
response = requests.get('https://example.com/image.jpg')
image = Image.open(BytesIO(response.content))

# Analyze image
response = model.generate_content(["Analyze this image", image])
print(response.text)
```

### 4. Streaming Output

**Python SDK:**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")
model = genai.GenerativeModel('gemini-2.5-flash')

# Streaming output
response = model.generate_content(
    "Write an article about artificial intelligence",
    stream=True
)

for chunk in response:
    print(chunk.text, end='')
```

### 5. Function Calling

**Python SDK:**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

# Define function
def get_weather(city: str):
    """Get weather for specified city"""
    # Should call real weather API here
    return f"Weather in {city}: Sunny, 25°C"

# Define function description
tools = [{
    "function_declarations": [{
        "name": "get_weather",
        "description": "Get weather information for specified city",
        "parameters": {
            "type": "object",
            "properties": {
                "city": {
                    "type": "string",
                    "description": "City name"
                }
            },
            "required": ["city"]
        }
    }]
}]

model = genai.GenerativeModel(
    'gemini-2.5-flash',
    tools=tools
)

# Send request
chat = model.start_chat()
response = chat.send_message("What's the weather in Shanghai today?")

# Check if function call is needed
if response.candidates[0].content.parts[0].function_call:
    function_call = response.candidates[0].content.parts[0].function_call
    
    # Call function
    if function_call.name == "get_weather":
        result = get_weather(function_call.args["city"])
        
        # Return result to model
        response = chat.send_message({
            "function_response": {
                "name": "get_weather",
                "response": {"result": result}
            }
        })
        print(response.text)
```

### 6. Google Search Grounding

**Python SDK:**

```python {filename="Python"}
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

# Enable Google Search Grounding
model = genai.GenerativeModel('gemini-2.5-flash')

response = model.generate_content(
    "What are the latest AI technology trends?",
    tools=[{"google_search_retrieval": {}}]
)

print(response.text)

# View citation sources
for candidate in response.candidates:
    if hasattr(candidate, 'grounding_metadata'):
        print("\nCitation Sources:")
        for attribution in candidate.grounding_metadata.grounding_attributions:
            print(f"- {attribution.source_id.grounding_passage.url}")
```

---

## 🛠️ SDKs and Client Libraries

### Official SDKs

**Python:**
```bash {filename="Bash"}
pip install google-generativeai
```

**Node.js:**
```bash {filename="Bash"}
npm install @google/generative-ai
```

**Go:**
```bash {filename="Bash"}
go get github.com/google/generative-ai-go
```

### OpenAI Compatibility

Google AI Studio API is compatible with OpenAI format, you can directly use OpenAI SDK:

```python {filename="Python"}
from openai import OpenAI

client = OpenAI(
    api_key="YOUR_GOOGLE_API_KEY",
    base_url="https://generativelanguage.googleapis.com/v1beta/openai/"
)

response = client.chat.completions.create(
    model="gemini-2.5-flash",
    messages=[
        {"role": "user", "content": "Hello"}
    ]
)

print(response.choices[0].message.content)
```

---

## 💡 Best Practices

### ✅ Recommended Practices

1. **Choose the Right Model**
   - High-frequency calls: Gemini 3 Flash (fastest)
   - Daily tasks: Gemini 2.5 Flash (balanced)
   - Complex tasks: Gemini Pro (stronger)
   - Open source needs: Gemma series

2. **Optimize Quota Usage**
   ```python
   # Use streaming to reduce wait time
   response = model.generate_content(prompt, stream=True)
   
   # Set reasonable max_output_tokens
   generation_config = {"max_output_tokens": 512}
   
   # Batch process requests
   prompts = ["Question 1", "Question 2", "Question 3"]
   responses = [model.generate_content(p) for p in prompts]
   ```

3. **Error Handling and Retries**
   ```python
   import time
   from google.api_core import retry
   
   @retry.Retry(predicate=retry.if_exception_type(Exception))
   def call_api_with_retry(prompt):
       return model.generate_content(prompt)
   
   try:
       response = call_api_with_retry("Hello")
   except Exception as e:
       print(f"API call failed: {e}")
   ```

4. **Monitor Quota Usage**
   ```python
   # Log API calls
   import logging
   
   logging.basicConfig(level=logging.INFO)
   logger = logging.getLogger(__name__)
   
   def track_api_call(model, prompt):
       logger.info(f"Calling model: {model}")
       response = model.generate_content(prompt)
       logger.info(f"Tokens used: {response.usage_metadata.total_token_count}")
       return response
   ```

5. **Securely Manage API Keys**
   ```python
   # Use environment variables
   import os
   api_key = os.getenv('GOOGLE_AI_API_KEY')
   
   # Or use config file
   import json
   with open('config.json') as f:
       config = json.load(f)
       api_key = config['api_key']
   ```

### ⚠️ Practices to Avoid

1. ❌ Hard-coding API keys in code
2. ❌ Frequently sending the same requests (use caching)
3. ❌ Ignoring rate limits (implement backoff retry)
4. ❌ Not handling errors and exceptions
5. ❌ Using excessively large max_output_tokens

---

## 🔧 Common Issues

### 1. 403 Error: API key not valid

**Cause:**
- API key is incorrect or expired
- API is not enabled

**Solution:**
```python {filename="Python"}
# Check API key
import google.generativeai as genai
genai.configure(api_key="YOUR_API_KEY")

# List available models to verify
for model in genai.list_models():
    print(model.name)
```

### 2. 429 Error: Resource exhausted

**Cause:**
- Exceeded rate limit
- Exceeded daily quota

**Solution:**
```python {filename="Python"}
import time
from google.api_core.exceptions import ResourceExhausted

def call_with_backoff(prompt, max_retries=3):
    for i in range(max_retries):
        try:
            return model.generate_content(prompt)
        except ResourceExhausted:
            if i < max_retries - 1:
                wait_time = 2 ** i  # Exponential backoff
                print(f"Rate limited, waiting {wait_time} seconds...")
                time.sleep(wait_time)
            else:
                raise
```

### 3. Network Timeout

**Cause:**
- Unstable network
- Request content too large

**Solution:**
```python {filename="Python"}
from google.api_core import timeout

# Set timeout
timeout_config = timeout.ExponentialTimeout(initial=30, maximum=120)
response = model.generate_content(prompt, timeout=timeout_config)
```

### 4. Access Issues in Mainland China

**Solution:**
- Use proxy or VPN
- Configure proxy:
  ```python
  import os
  os.environ['HTTP_PROXY'] = 'http://your-proxy:port'
  os.environ['HTTPS_PROXY'] = 'https://your-proxy:port'
  ```

---

## 📊 Performance Optimization

### 1. Use Caching

```python {filename="Python"}
from functools import lru_cache

@lru_cache(maxsize=100)
def cached_api_call(prompt):
    return model.generate_content(prompt).text
```

### 2. Batch Processing

```python {filename="Python"}
import asyncio
from google.generativeai import GenerativeModel

async def batch_generate(prompts):
    model = GenerativeModel('gemini-2.5-flash')
    tasks = [model.generate_content_async(p) for p in prompts]
    return await asyncio.gather(*tasks)

# Usage
prompts = ["Question 1", "Question 2", "Question 3"]
responses = asyncio.run(batch_generate(prompts))
```

### 3. Streaming Large Text

```python {filename="Python"}
def process_large_text(text, chunk_size=10000):
    chunks = [text[i:i+chunk_size] for i in range(0, len(text), chunk_size)]
    results = []
    
    for chunk in chunks:
        response = model.generate_content(f"Summarize: {chunk}")
        results.append(response.text)
    
    return " ".join(results)
```

---

## 📚 Related Resources

### Official Documentation
- [Google AI Studio Complete Guide](/en/providers/google-ai-studio)
- [Chatbot Service Guide](/en/services/chatbot/google-ai-studio)
- [API Official Docs](https://ai.google.dev/docs)
- [API Reference](https://ai.google.dev/api)

### Code Examples
- [GitHub Examples](https://github.com/google/generative-ai-docs)
- [Cookbook](https://github.com/google-gemini/cookbook)

### Learning Resources
- [Quick Start Tutorial](https://ai.google.dev/tutorials/python_quickstart)
- [Prompt Engineering](https://ai.google.dev/docs/prompt_best_practices)
- [Function Calling Guide](https://ai.google.dev/docs/function_calling)

---

**Service Provider:** [Google AI Studio](/en/providers/google-ai-studio)

