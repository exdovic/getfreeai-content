---
title: "Mistral API - European Open-Source AI Developer Interface"
linkTitle: "API - Mistral"
description: "Mistral API provides multiple open-source and proprietary AI model interfaces, supporting text generation, code generation, embeddings, and more. Flexible pay-as-you-go pricing with multi-cloud deployment support (AWS, Azure, Google Cloud). OpenAI-compatible API format for easy integration."
keywords:
  - Mistral API
  - Mistral AI API
  - European AI API
  - Open Source AI API
  - Pixtral API
  - Mistral Large API
  - French AI Interface
  - Multi-Cloud Deployment API
image: /images/logo.svg
type: docs
weight: 10
comments: true
prev: /services/api/hugging-face
next: /services/api/cohere
sidebar:
  open: true
---

## 📋 Service Overview

**Service Name:** Mistral API  
**Provider:** [Mistral AI](/providers/mistral)  
**API Endpoint:** `https://api.mistral.ai/v1`  
**Service Type:** Experiment free trial + Scale pay-as-you-go  
**Registration:** Account required; Experiment plan needs phone verification only, Scale plan requires payment method

---

## ✅ Service Description

Mistral API is a developer API interface provided by Mistral AI, allowing developers to integrate Mistral's advanced AI models into their applications. The API uses an OpenAI-compatible format for easy migration from other services.

### Key Features

- **🔓 Open Source Models:** Some models are open-source for local deployment
- **💰 Flexible Pricing:** Pay-as-you-go with transparent, reasonable pricing
- **☁️ Multi-Cloud Support:** Deploy on AWS, Azure, Google Cloud
- **🔄 OpenAI Compatible:** API format compatible with OpenAI for easy migration
- **🎨 Multimodal:** Pixtral Large supports image understanding
- **🇪🇺 Data Sovereignty:** European servers, GDPR compliant

---

## 🎁 Available Models

### Free/Paid Model List

|| Model Name | Context Length | Features | Use Cases | Pricing |
||-----------|---------------|----------|-----------|---------|
|| **Mistral Large 2** | 128K | Best performance, multilingual | Complex reasoning, long text | $2-6/M tokens |
|| **Pixtral Large** | 128K | Multimodal, image understanding | Visual tasks, OCR | $2-6/M tokens |
|| **Mistral Medium** | 32K | Balanced performance/cost | Daily applications | $0.40-2/M tokens |
|| **Mistral Small** | 32K | Lightweight, efficient | Simple tasks, high frequency | $0.20-0.60/M tokens |
|| **Mixtral 8x7B** | 32K | Open-source MoE | General tasks | Free (open)/Paid (API) |
|| **Mistral 7B** | 8K | Open-source base | Learning, entry-level | Free (open-source) |

### Model Details

#### Mistral Large 2
- **Context Window:** 128K tokens
- **Primary Use:** Complex reasoning, multilingual tasks, code generation
- **Advantages:** Top performance, supports 80+ languages
- **Pricing:** Input $2/M, Output $6/M

#### Pixtral Large
- **Context Window:** 128K tokens
- **Primary Use:** Image understanding, document analysis, multimodal tasks
- **Advantages:** Europe's first multimodal model, strong visual capabilities
- **Pricing:** Input $2/M, Output $6/M

#### Mistral Medium
- **Context Window:** 32K tokens
- **Primary Use:** Daily conversations, content generation
- **Advantages:** Balance of performance and cost
- **Pricing:** Input $0.40/M, Output $2/M

---

## 🔢 Quotas and Limits

### Free Trial (Experiment Plan)

| Item | Details |
|------|---------|
| **Trial Method** | Experiment plan, free trial (phone verification only, no credit card) |
| **Rate Limits** | Limited rates, suitable for experiments and prototyping |
| **Access** | Activate Experiment plan in console Subscription after registration |
| **Upgrade Option** | Upgrade to Scale plan (pay-as-you-go) for higher quotas |

### Rate Limits

|| Limit Item | Free/Trial | Paid |
||-----------|-----------|------|
|| **Requests per Minute** | Lower | By tier |
|| **Tokens per Minute** | Limited | By tier |
|| **Concurrent Requests** | Limited | By tier |

### ⚠️ Important Limits

1. **Experiment vs Scale:** Experiment plan is free but rate-limited, Scale plan is pay-as-you-go with higher quotas
2. **Rate Limits:** Different rate limits based on account tier and plan
3. **Data Usage:** Experiment plan requests may be used for model improvement, Scale plan is opt-out by default (adjustable in console)

### Quota Reset

- **Usage-Based Billing:** Real-time charges, no fixed reset
- **Rate Limits:** Per-minute rolling window

---

## 💰 Pricing

### Pay-as-you-go

|| Model | Input Price | Output Price | Notes |
||-------|------------|--------------|-------|
|| **Mistral Large 2** | $2/M tokens | $6/M tokens | Best performance |
|| **Pixtral Large** | $2/M tokens | $6/M tokens | Multimodal |
|| **Mistral Medium** | $0.40/M tokens | $2/M tokens | High value |
|| **Mistral Small** | $0.20/M tokens | $0.60/M tokens | Economical |

**Note:** M = Million

### Multi-Cloud Deployment

Pricing may vary on AWS, Azure, Google Cloud platforms. Check respective platform pricing.

---

## 🚀 Getting Started

### Prerequisites

**1. Register Account**

Please [register a Mistral AI account](/providers/mistral#account-registration)

**2. Get API Key**

{{% steps %}}

##### Log into Console

Visit [Mistral AI Console](https://console.mistral.ai) and log in.

##### Choose Plan

1. Go to "Admin" → "Subscription" section
2. Choose **Experiment** (free trial) or **Scale** (paid)
3. **Experiment:** Usually requires phone verification only, no credit card
4. **Scale:** Requires adding payment method in Billing

##### Create API Key

1. Navigate to "API Keys" page
2. Click "Create API Key"
3. Name your key (e.g., "My App API Key")
4. Copy the generated API key
5. **Important:** Save key securely, shown only once

{{% /steps %}}

---

## 💻 Code Examples

### Python Examples

**Install Dependencies:**

```bash {filename="Bash"}
pip install mistralai
# Or use OpenAI SDK (compatible)
pip install openai
```

**Using Mistral Official SDK:**

```python {filename="Python"}
from mistralai.client import MistralClient
from mistralai.models.chat_completion import ChatMessage

# Initialize client
client = MistralClient(api_key="YOUR_API_KEY")

# Send request
messages = [
    ChatMessage(role="user", content="What is machine learning?")
]

response = client.chat(
    model="mistral-large-latest",
    messages=messages
)

print(response.choices[0].message.content)
```

**Using OpenAI SDK (Compatible):**

```python {filename="Python"}
from openai import OpenAI

# Initialize client (using Mistral API)
client = OpenAI(
    api_key="YOUR_MISTRAL_API_KEY",
    base_url="https://api.mistral.ai/v1"
)

# Send request
response = client.chat.completions.create(
    model="mistral-large-latest",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain the basic principles of deep learning."}
    ],
    max_tokens=1000,
    temperature=0.7
)

print(response.choices[0].message.content)
print(f"\nTokens Used: {response.usage.total_tokens}")
```

**Streaming Example:**

```python {filename="Python"}
# Streaming output (real-time display)
stream = client.chat.completions.create(
    model="mistral-large-latest",
    messages=[
        {"role": "user", "content": "Write a poem about AI"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="", flush=True)
```

---

### cURL Examples

**Basic Request:**

```bash {filename="Bash"}
curl https://api.mistral.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "mistral-large-latest",
    "messages": [
      {
        "role": "system",
        "content": "You are a helpful assistant."
      },
      {
        "role": "user",
        "content": "Hello, please introduce yourself."
      }
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**Streaming:**

```bash {filename="Bash"}
curl https://api.mistral.ai/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "mistral-large-latest",
    "messages": [{"role": "user", "content": "Hello"}],
    "stream": true
  }'
```

---

### Node.js Example

```javascript {filename="JavaScript"}
import OpenAI from 'openai';

const client = new OpenAI({
  apiKey: 'YOUR_MISTRAL_API_KEY',
  baseURL: 'https://api.mistral.ai/v1',
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'mistral-large-latest',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: 'Hello, please introduce yourself.' }
    ],
    max_tokens: 1000,
    temperature: 0.7,
  });

  console.log(completion.choices[0].message.content);
  console.log(`\nTokens Used: ${completion.usage.total_tokens}`);
}

main();
```

---

### Multimodal Example (Pixtral Large)

```python {filename="Python"}
from openai import OpenAI
import base64

client = OpenAI(
    api_key="YOUR_MISTRAL_API_KEY",
    base_url="https://api.mistral.ai/v1"
)

# Read image and convert to base64
def encode_image(image_path):
    with open(image_path, "rb") as image_file:
        return base64.b64encode(image_file.read()).decode('utf-8')

image_base64 = encode_image("path/to/your/image.jpg")

# Send multimodal request
response = client.chat.completions.create(
    model="pixtral-large-latest",
    messages=[
        {
            "role": "user",
            "content": [
                {"type": "text", "text": "What's in this image?"},
                {
                    "type": "image_url",
                    "image_url": {
                        "url": f"data:image/jpeg;base64,{image_base64}"
                    }
                }
            ]
        }
    ]
)

print(response.choices[0].message.content)
```

---

## 🌟 Core Advantages

### Technical Advantages

1. **Open Source Transparency:**
   - Multiple open-source models (Mistral 7B, Mixtral 8x7B)
   - Downloadable for local deployment
   - Active community

2. **Multi-Cloud Flexibility:**
   - AWS Sagemaker
   - Microsoft Azure AI
   - Google Cloud Vertex AI
   - Self-hosted servers

3. **European Data Sovereignty:**
   - Data stored in Europe
   - GDPR compliant
   - Strong privacy protection

### Comparison with Other APIs

|| Feature | Mistral API | OpenAI API | Google AI Studio | DeepSeek API |
||---------|------------|-----------|-----------------|-------------|
|| Free Quota | Trial credits | Trial credits | High free quota | ¥5 trial |
|| Open Source | ✅ Partial | ❌ | ❌ | ✅ |
|| Multi-Cloud | ✅ | ❌ | ✅ | ❌ |
|| EU Servers | ✅ | ❌ | ❌ | ❌ |
|| OpenAI Compatible | ✅ | ✅ | Partial | ✅ |
|| Multimodal | ✅ Pixtral | ✅ GPT-4V | ✅ Gemini | ❌ |

---

## 💡 Best Practices

### ✅ Recommendations

1. **Choose Right Model:**
   ```python
   # Complex tasks → Mistral Large
   model = "mistral-large-latest"
   
   # Image tasks → Pixtral Large
   model = "pixtral-large-latest"
   
   # Economical → Mistral Small
   model = "mistral-small-latest"
   ```

2. **Error Handling and Retry:**
   ```python
   import time
   from openai import OpenAI, APIError
   
   def call_with_retry(messages, max_retries=3):
       for i in range(max_retries):
           try:
               return client.chat.completions.create(
                   model="mistral-large-latest",
                   messages=messages
               )
           except APIError as e:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"API error, waiting {wait_time}s...")
                   time.sleep(wait_time)
               else:
                   raise
   ```

3. **Secure API Key Management:**
   ```python
   import os
   from dotenv import load_dotenv
   
   load_dotenv()
   api_key = os.getenv('MISTRAL_API_KEY')
   
   client = OpenAI(
       api_key=api_key,
       base_url="https://api.mistral.ai/v1"
   )
   ```

4. **Monitor Usage:**
   - Regularly check [Console](https://console.mistral.ai) usage stats
   - Set budget alerts
   - Log API calls and costs

### 🎯 Optimization

**Optimize Token Usage:**
- Use concise prompts
- Avoid repetitive system messages
- Set reasonable max_tokens

**Choose Temperature:**
```python
# Creative tasks (poetry, stories)
temperature = 0.9

# Balanced (daily chat)
temperature = 0.7

# Precise tasks (code, translation)
temperature = 0.3
```

**Batch Processing:**
```python
# Batch process multiple requests
requests = ["Question 1", "Question 2", "Question 3"]
responses = []

for question in requests:
    response = client.chat.completions.create(
        model="mistral-large-latest",
        messages=[{"role": "user", "content": question}]
    )
    responses.append(response.choices[0].message.content)
```

### ⚠️ Important Notes

1. **Cost Control:** API is pay-as-you-go, monitor costs
2. **Rate Limits:** Don't exceed rate limits
3. **Data Privacy:** Don't send sensitive information to API
4. **Model Selection:** Choose appropriate model to optimize costs

---

## 🎯 Real-World Use Cases

### Case 1: Smart Customer Service

```python {filename="Python"}
def customer_service_bot(user_message, conversation_history):
    """Smart customer service assistant"""
    messages = [
        {"role": "system", "content": "You are a professional customer service assistant, friendly and efficient."}
    ]
    
    # Add conversation history
    messages.extend(conversation_history)
    
    # Add user message
    messages.append({"role": "user", "content": user_message})
    
    response = client.chat.completions.create(
        model="mistral-medium-latest",  # Use Medium for cost balance
        messages=messages,
        temperature=0.7
    )
    
    return response.choices[0].message.content

# Usage example
history = []
user_msg = "I'd like to know about your return policy"
reply = customer_service_bot(user_msg, history)
print(reply)
```

### Case 2: Document Analysis

```python {filename="Python"}
def analyze_document(image_path):
    """Analyze document image and extract information"""
    import base64
    
    with open(image_path, "rb") as f:
        image_data = base64.b64encode(f.read()).decode()
    
    response = client.chat.completions.create(
        model="pixtral-large-latest",
        messages=[
            {
                "role": "user",
                "content": [
                    {"type": "text", "text": "Please analyze this document and extract key information."},
                    {
                        "type": "image_url",
                        "image_url": {"url": f"data:image/jpeg;base64,{image_data}"}
                    }
                ]
            }
        ]
    )
    
    return response.choices[0].message.content

# Usage example
result = analyze_document("invoice.jpg")
print(result)
```

### Case 3: Code Review

```python {filename="Python"}
def code_review(code):
    """Code review and optimization suggestions"""
    response = client.chat.completions.create(
        model="mistral-large-latest",  # Large model better for code
        messages=[
            {
                "role": "system",
                "content": "You are a senior code reviewer providing constructive feedback."
            },
            {
                "role": "user",
                "content": f"Please review the following code and provide optimization suggestions:\n\n```python\n{code}\n```"
            }
        ],
        temperature=0.3  # Low temperature for precision
    )
    
    return response.choices[0].message.content

# Usage example
code = """
def calculate(a, b):
    return a + b
"""
review = code_review(code)
print(review)
```

---

## 🔧 Common Questions

**Q: Does Mistral API have free quota?**  
A: Yes. Mistral offers an **Experiment free trial plan** that requires only phone verification (no credit card). The Experiment plan is suitable for experiments and prototyping with rate limits. For higher quotas, upgrade to the Scale pay-as-you-go plan. See [official pricing page](https://mistral.ai/pricing).

**Q: How to migrate from OpenAI API to Mistral API?**  
A: Just modify `base_url` and `api_key`, no other code changes needed:
```python
# Original OpenAI
client = OpenAI(api_key="sk-...")

# Change to Mistral
client = OpenAI(
    api_key="YOUR_MISTRAL_KEY",
    base_url="https://api.mistral.ai/v1"
)
```

**Q: How to use open-source models?**  
A: Mistral's open-source models can be:
1. Used via API (paid)
2. Downloaded from Hugging Face for local deployment (free)
3. Deployed on cloud platforms (cloud platform fees apply)

**Q: Does Mistral API support function calling?**  
A: Yes, Mistral API supports function calling, similar to OpenAI. See [official docs](https://docs.mistral.ai).

**Q: How to use Mistral on multi-cloud platforms?**  
A: Mistral supports multi-cloud deployment:
- **AWS:** Via Sagemaker
- **Azure:** Via Azure AI Foundry
- **Google Cloud:** Via Vertex AI
See respective platform documentation.

---

## 🔗 Related Resources

- **API Endpoint:** `https://api.mistral.ai/v1`
- **Developer Console:** [https://console.mistral.ai](https://console.mistral.ai)
- **API Documentation:** [https://docs.mistral.ai](https://docs.mistral.ai)
- **Provider Page:** [Mistral AI Complete Guide](/providers/mistral)
- **Chatbot Service:** [Le Chat Usage Guide](/services/chatbot/mistral)
- **SDK Repository:** [https://github.com/mistralai/client-python](https://github.com/mistralai/client-python)
- **Pricing:** [https://mistral.ai/pricing](https://mistral.ai/pricing)

---

## 📝 Update Log

- **January 2025:** Updated pricing and rate limits
- **November 2024:** Released Pixtral Large multimodal API
- **July 2024:** Released Mistral Large 2
- **May 2024:** Added function calling support
- **March 2024:** Launched Mistral Medium
- **December 2023:** Released Mixtral 8x7B API
- **September 2023:** Mistral API officially launched

---

**Service Provider:** [Mistral AI](/providers/mistral)
