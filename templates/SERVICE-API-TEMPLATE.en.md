---
title: "[Service Name] API"
type: docs
weight: 20
comments: true
prev: /services/api/previous-service  # Optional: Previous page link
next: /services/api/next-service      # Optional: Next page link
sidebar:
  open: true
---

{{< callout type="info" >}}
**Note:** No need to write a level-1 heading (`# Title`) in the document, Hugo will automatically use the `title` from front matter to generate the page title.
{{< /callout >}}

## 📋 Service Overview

{{< callout type="info" >}}
**Tip:** 
- **Access URL (web link)**: Use Markdown link format `[URL](URL)`, it will automatically display an arrow icon (↗)
- **API Endpoint**: If it contains placeholders or requires dynamic replacement, use code format `` `https://api.example.com/v1` ``; if it's a fixed URL, you can use link format
{{< /callout >}}

**Service Name:** [API Service Name]  
**Provider:** [Provider Name](/providers/provider-name)  
**API Endpoint:** `https://api.example.com/v1` (if has placeholders) or [https://api.example.com/v1](https://api.example.com/v1) (if fixed URL)  
**Service Type:** [Completely Free/Limited Free/Trial Credits]  
**Registration Requirements:** [Whether registration/credit card/identity verification required]

---

## ✅ Service Description

[Service Name] API is [service form description, such as: developer API interface, RESTful API service, etc.] provided by [Provider Name].

### Main Features

- **[Feature 1]:** [Detailed explanation]
- **[Feature 2]:** [Detailed explanation]
- **[Feature 3]:** [Detailed explanation]
- **[Feature 4]:** [Detailed explanation]

---

## 🎁 Available Models

### Free/Trial Models List

| Model Name | Context Length | Output Length | Features | Use Cases |
|-----------|---------------|---------------|----------|-----------|
| **[model-1]** | [Length] | [Length] | [Features] | [Cases] |
| **[model-2]** | [Length] | [Length] | [Features] | [Cases] |
| **[model-3]** | [Length] | [Length] | [Features] | [Cases] |

### Model Detailed Description

#### [Model 1]
- **Context Window:** [Specific value]
- **Main Purpose:** [Explanation]
- **Advantages:** [Explanation]

#### [Model 2]
- **Context Window:** [Specific value]
- **Main Purpose:** [Explanation]
- **Advantages:** [Explanation]

---

## 🔢 Quotas and Limitations

### Free Tier Limitations

| Limitation | Quota | Notes |
|-----------|-------|-------|
| **Daily Requests** | [Number] requests/day | [Notes] |
| **Requests Per Minute** | [Number] requests/min | [Notes] |
| **Daily Tokens** | [Number] tokens/day | [Notes] |
| **Tokens Per Minute** | [Number] tokens/min | [Notes] |
| **Max Context Length** | [Number] tokens | [Notes] |
| **Max Output Length** | [Number] tokens | [Notes] |
| **Concurrent Requests** | [Number] | [Notes] |
| **Trial Credits** | [Amount] | [Validity period] |
| **Credit Card Required** | ✅/❌ | [Notes] |

### ⚠️ Important Limitations

1. **[Limitation 1]:** [Detailed explanation]
2. **[Limitation 2]:** [Detailed explanation]
3. **[Limitation 3]:** [Detailed explanation]

### Quota Reset Time

- **Daily Quota:** [Reset time, e.g., UTC 0:00]
- **Per-minute Quota:** [Reset rules]
- **Trial Credits:** [Validity period and expiration rules]

---

## 💰 Pricing Information

### Free/Trial

- **Free Quota:** [Explanation]
- **Trial Credits:** [Amount and validity period]
- **Acquisition Method:** [Explanation]

### Paid Pricing (if applicable)

| Model | Input Price | Output Price | Notes |
|-------|------------|--------------|-------|
| **[model-1]** | $[Price]/M tokens | $[Price]/M tokens | [Notes] |
| **[model-2]** | $[Price]/M tokens | $[Price]/M tokens | [Notes] |

---

## 🚀 How to Use

### Prerequisites

**1. Register Account**

If registration process is explained in Provider document, link to it:
- Please [register an account](/providers/provider-name#account-registration) first

If it's API-specific registration process, explain in detail.

**2. Get API Key**

Detailed steps (if same for all users):

**Step 1: Login to Developer Platform**
1. Visit [Developer Platform](https://platform.example.com)
2. Login with your account

**Step 2: Create API Key**
1. [Detailed operation]
2. [Detailed operation]
3. **Important:** Copy and securely save your API key

**Step 3: [Optional step, like topping up or binding credit card]**
1. [Detailed operation]
2. [Detailed operation]

---

## 💻 Code Examples

### Python Example

**Install Dependencies:**

```bash {filename="Bash"}
pip install openai  # or other SDK
```

**Basic Usage:**

```python {filename="Python"}
from openai import OpenAI

# Initialize client (please replace with your API key)
client = OpenAI(
    base_url="https://api.example.com/v1",
    api_key="YOUR_API_KEY"
)

# Send request
response = client.chat.completions.create(
    model="model-name",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Hello, please introduce yourself."}
    ],
    max_tokens=1000,
    temperature=0.7
)

# Print response
print(response.choices[0].message.content)

# View Token usage
print(f"\nTokens used: {response.usage.total_tokens}")
```

**Streaming Output Example:**

```python {filename="Python"}
# Streaming output (suitable for real-time display)
stream = client.chat.completions.create(
    model="model-name",
    messages=[
        {"role": "user", "content": "Write a poem about AI"}
    ],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

---

### cURL Example

**Basic Request:**

```bash {filename="Bash"}
curl https://api.example.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "model-name",
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

**Streaming Output:**

```bash {filename="Bash"}
curl https://api.example.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "model-name",
    "messages": [{"role": "user", "content": "Hello"}],
    "stream": true
  }'
```

---

### Node.js Example (Optional)

```javascript {filename="JavaScript"}
import OpenAI from 'openai';

const client = new OpenAI({
  baseURL: 'https://api.example.com/v1',
  apiKey: 'YOUR_API_KEY',
});

async function main() {
  const completion = await client.chat.completions.create({
    model: 'model-name',
    messages: [
      { role: 'system', content: 'You are a helpful assistant.' },
      { role: 'user', content: 'Hello, please introduce yourself.' }
    ],
    max_tokens: 1000,
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

1. **[Advantage 1]:**
   - [Detailed explanation]
   - [Data support]

2. **[Advantage 2]:**
   - [Detailed explanation]
   - [Data support]

3. **[Advantage 3]:**
   - [Detailed explanation]
   - [Data support]

### Comparison with Other APIs

| Feature | [This Service] | [Competitor 1] | [Competitor 2] |
|---------|---------------|----------------|----------------|
| Free Quota | [Data] | [Data] | [Data] |
| Request Speed | [Data] | [Data] | [Data] |
| Number of Models | [Number] | [Number] | [Number] |
| Context Length | [Length] | [Length] | [Length] |
| Price | [Price] | [Price] | [Price] |
| Credit Card Required | ✅/❌ | ✅/❌ | ✅/❌ |

---

## 💡 Practical Suggestions

### ✅ Recommended Practices

1. **[Suggestion 1]:**
   - [Detailed explanation]
   - [Code example]

2. **[Suggestion 2]:**
   - [Detailed explanation]
   - [Code example]

3. **[Suggestion 3]:**
   - [Detailed explanation]

### 🎯 Best Practices

**Make Full Use of Free Quota:**
- [Suggestion 1]
- [Suggestion 2]
- [Suggestion 3]

**Optimize Token Usage:**
- [Suggestion 1]
- [Suggestion 2]
- [Suggestion 3]

**Error Handling:**

```python {filename="Python"}
import time
from openai import OpenAI, RateLimitError, APIError

client = OpenAI(
    base_url="https://api.example.com/v1",
    api_key="YOUR_API_KEY"
)

def call_api_with_retry(messages, max_retries=3):
    """API call with retry mechanism"""
    for attempt in range(max_retries):
        try:
            response = client.chat.completions.create(
                model="model-name",
                messages=messages
            )
            return response
        except RateLimitError:
            print(f"Rate limit reached, waiting and retrying... ({attempt + 1}/{max_retries})")
            time.sleep(2 ** attempt)  # Exponential backoff
        except APIError as e:
            print(f"API error: {e}")
            if attempt == max_retries - 1:
                raise
    
    return None
```

### ⚠️ Precautions

1. **[Precaution 1]:** [Explanation]
2. **[Precaution 2]:** [Explanation]
3. **[Precaution 3]:** [Explanation]

---

## 🎯 Practical Application Cases

### Case 1: [Application Scenario Name]

**Scenario Description:** [Description]

```python {filename="Python"}
# Complete code example
def example_case_1():
    """[Function description]"""
    client = OpenAI(
        base_url="https://api.example.com/v1",
        api_key="YOUR_API_KEY"
    )
    
    # Implementation code
    response = client.chat.completions.create(
        model="model-name",
        messages=[
            {"role": "user", "content": "Example question"}
        ]
    )
    
    return response.choices[0].message.content

# Usage example
result = example_case_1()
print(result)
```

### Case 2: [Application Scenario Name]

**Scenario Description:** [Description]

```python {filename="Python"}
# Code example
```

---

## 🔧 Common Questions

**Q: [Question 1]**  
A: [Answer]

**Q: [Question 2]**  
A: [Answer]

**Q: [Question 3]**  
A: [Answer]

**Q: [Question 4]**  
A: [Answer]

**Q: [Question 5]**  
A: [Answer]

---

## 🔗 Related Resources

- **API Endpoint:** `https://api.example.com/v1`
- **Developer Platform:** [https://platform.example.com](https://platform.example.com)
- **API Documentation:** [https://docs.example.com](https://docs.example.com)
- **Provider Homepage:** [Link to Provider document](/providers/provider-name)
- **Corresponding Chatbot Service:** [Link to Chatbot document](/services/chatbot/service-name) (if available)
- **SDK Repository:** [GitHub link]
- **Example Code:** [GitHub link]
- **API Status:** [Status page link]

---

## 📝 Changelog

- **[Year-Month]:** [API updates, new models, quota changes]
- **[Year-Month]:** [API updates, new models, quota changes]
- **[Year-Month]:** [API updates, new models, quota changes]

---

**Service Provider:** [[Provider Name]](/providers/[provider-slug])

