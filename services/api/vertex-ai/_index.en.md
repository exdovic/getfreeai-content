---
title: Google Vertex AI - API
weight: 6
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [Google Vertex AI](/en/providers/google-vertex-ai)  
**Service Type:** API Service  
**API Endpoint:** `https://[REGION]-aiplatform.googleapis.com` (replace `[REGION]`, e.g. `us-central1`)  
**Free Tier:** Trial Credits ($300, 90 days)

---

## 🎯 Service Overview

Vertex AI API provides enterprise-grade AI capabilities, supporting Gemini series models, particularly suitable for large-scale production deployments and integration with Google Cloud services.

**Key Advantages:**
- 💰 **$300 Trial Credits** - 90-day validity
- 🌟 **Gemini 1.5 Pro** - 2M super-long context
- 🏢 **Enterprise Grade** - Complete MLOps tools
- 🔐 **Security Compliance** - Google Cloud standards
- 🌐 **Global Deployment** - Multi-region availability
- 📊 **Comprehensive Monitoring** - Complete logs and metrics

---

## 🚀 Quick Start

### Prerequisites

**Required:**
- ✅ Google Cloud account created
- ✅ $300 trial credits activated
- ✅ Vertex AI API enabled
- ✅ Service account or API key created

For detailed steps, see: [Vertex AI Registration Guide](/en/providers/google-vertex-ai#registration-and-account)

### 5-Minute Quick Example

**Install SDK:**
```bash {filename="Bash"}
pip install google-cloud-aiplatform
```

**Usage Example:**
```python {filename="Python"}
import vertexai
from vertexai.generative_models import GenerativeModel

# Initialize
vertexai.init(project="YOUR_PROJECT_ID", location="us-central1")

# Create model instance
model = GenerativeModel("gemini-1.5-pro")

# Generate content
response = model.generate_content("Explain what Vertex AI is")
print(response.text)
```

---

## 🤖 Supported Models

### Gemini 1.5 Pro

**Model ID:** `gemini-1.5-pro`

| Feature | Details |
|------|------|
| **Context** | 2M tokens |
| **Multimodal** | Text, image, audio, video |
| **Price** | $1.25-2.50/M (in), $5-10/M (out) |

### Gemini 1.5 Flash

**Model ID:** `gemini-1.5-flash`

| Feature | Details |
|------|------|
| **Context** | 1M tokens |
| **Speed** | Extremely fast |
| **Price** | $0.075-0.15/M (in), $0.30-0.60/M (out) |

---

## 📖 API Usage Examples

### 1. Basic Conversation

```python {filename="Python"}
import vertexai
from vertexai.generative_models import GenerativeModel

vertexai.init(project="YOUR_PROJECT_ID", location="us-central1")

model = GenerativeModel("gemini-1.5-flash")

response = model.generate_content("Hello, introduce Gemini")
print(response.text)
```

### 2. Streaming Output

```python {filename="Python"}
model = GenerativeModel("gemini-1.5-flash")

response = model.generate_content(
    "Write an article about AI",
    stream=True
)

for chunk in response:
    print(chunk.text, end="", flush=True)
```

### 3. Multimodal Input (Images)

```python {filename="Python"}
from vertexai.generative_models import GenerativeModel, Part

model = GenerativeModel("gemini-1.5-pro")

# Load image from local
image = Part.from_uri(
    "gs://your-bucket/image.jpg",
    mime_type="image/jpeg"
)

response = model.generate_content([
    "What's in this image?",
    image
])

print(response.text)
```

### 4. Long Context Processing

```python {filename="Python"}
# Process extremely long text (e.g., entire books)
with open("long_document.txt", "r") as f:
    long_text = f.read()  # Can be millions of words

model = GenerativeModel("gemini-1.5-pro")

response = model.generate_content(
    f"Summarize the core points of the following document:\n\n{long_text}"
)

print(response.text)
```

### 5. Function Calling

```python {filename="Python"}
from vertexai.generative_models import (
    GenerativeModel,
    Tool,
    FunctionDeclaration
)

# Define function
get_weather_func = FunctionDeclaration(
    name="get_weather",
    description="Get weather for specified city",
    parameters={
        "type": "object",
        "properties": {
            "city": {
                "type": "string",
                "description": "City name"
            }
        },
        "required": ["city"]
    }
)

# Create tool
weather_tool = Tool(function_declarations=[get_weather_func])

# Use
model = GenerativeModel(
    "gemini-1.5-pro",
    tools=[weather_tool]
)

response = model.generate_content("What's the weather in Shanghai today?")
print(response)
```

---

## 🔢 Costs and Quotas

### Pricing

**Gemini 1.5 Pro:**
| Context | Input | Output |
|--------|------|------|
| ≤ 128K | $1.25/M | $5/M |
| > 128K | $2.50/M | $10/M |

**Gemini 1.5 Flash:**
| Context | Input | Output |
|--------|------|------|
| ≤ 128K | $0.075/M | $0.30/M |
| > 128K | $0.15/M | $0.60/M |

### Trial Credits Usage Example

**$300 can:**
- Gemini Pro: Process 240M input tokens
- Gemini Flash: Process 4B input tokens
- Or any combination

---

## 💡 Best Practices

### ✅ Recommended Practices

1. **Use Flash First**
   ```python
   # Flash is 16x cheaper, sufficient for most scenarios
   model = GenerativeModel("gemini-1.5-flash")
   ```

2. **Batch Processing**
   ```python
   # Batch process multiple requests
   responses = []
   for prompt in prompts:
       response = model.generate_content(prompt)
       responses.append(response.text)
   ```

3. **Cost Monitoring**
   ```python
   # Set budget alerts in GCP Console
   # Billing → Budgets & alerts
   ```

4. **Error Handling**
   ```python
   from google.api_core import exceptions
   
   try:
       response = model.generate_content(prompt)
   except exceptions.ResourceExhausted:
       print("Quota exhausted")
   except exceptions.InvalidArgument:
       print("Parameter error")
   ```

---

## 🔧 Common Issues

### 1. How to Authenticate?

**Method:**
```bash {filename="Bash"}
# Set environment variable
export GOOGLE_APPLICATION_CREDENTIALS="path/to/service-account-key.json"

# Or in code
import os
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "key.json"
```

### 2. How to Choose Region?

**Available Regions:**
- `us-central1` (recommended)
- `europe-west1`
- `asia-southeast1`

### 3. How to Monitor Usage?

**Method:**
1. GCP Console → Billing
2. View Vertex AI usage
3. Set budget alerts

---

## 📚 Related Resources

### Official Documentation
- [Vertex AI Complete Guide](/en/providers/google-vertex-ai)
- [Studio Usage Guide](/en/services/chatbot/vertex-ai)
- [API Official Docs](https://cloud.google.com/vertex-ai/docs)

### SDKs and Tools
- [Python SDK](https://cloud.google.com/python/docs/reference/aiplatform/latest)
- [Example Code](https://github.com/GoogleCloudPlatform/vertex-ai-samples)
- [Tutorials](https://cloud.google.com/vertex-ai/docs/tutorials)

---

## 🌟 Practical Case

### Case: Long Document Analysis System

```python {filename="Python"}
import vertexai
from vertexai.generative_models import GenerativeModel

vertexai.init(project="YOUR_PROJECT_ID", location="us-central1")

class DocumentAnalyzer:
    def __init__(self):
        self.model = GenerativeModel("gemini-1.5-pro")
    
    def analyze(self, document_text):
        """Analyze long document"""
        prompt = f"""
        Please analyze the following document and provide:
        1. Core theme
        2. Key points (5-10)
        3. Summary (within 200 words)
        
        Document content:
        {document_text}
        """
        
        response = self.model.generate_content(prompt)
        return response.text

# Usage
analyzer = DocumentAnalyzer()
with open("long_doc.txt") as f:
    result = analyzer.analyze(f.read())
    print(result)
```

---

**Service Provider:** [Google Vertex AI](/en/providers/google-vertex-ai)

