---
title: OpenRouter - Playground
weight: 3
comments: true
sidebar:
  open: true
---


## 📋 Service Information

**Provider:** [OpenRouter](/en/providers/openrouter)  
**Service Type:** Chatbot (Web Playground)  
**Access URL:** [https://openrouter.ai/playground](https://openrouter.ai/playground)  
**Free Tier:** Free Forever (with usage limits)

---

## 🎯 Service Overview

OpenRouter Playground is a powerful web testing interface that allows you to test and compare 47+ free AI models directly in your browser without writing any code.

**Key Advantages:**
- 🎯 **47+ Free Models** - Test all models in one interface
- 🔄 **Model Comparison** - Test multiple models simultaneously
- 📊 **Usage Statistics** - View quotas and costs in real-time
- 🎛️ **Parameter Adjustment** - Customize generation parameters
- 💾 **History Management** - Save and manage conversations

---

## 🚀 How to Use

### Prerequisites

- ✅ Registered OpenRouter account
- ✅ Created API key (Playground automatically uses it)

For detailed registration steps, see: [OpenRouter Registration Guide](/en/providers/openrouter#registration-and-account)

### Usage Steps

#### Step 1: Access Playground

1. Visit: https://openrouter.ai/playground
2. Login with your account (automatically recognized)

#### Step 2: Select Model

Select free models (marked as **FREE**) in the model dropdown:

**Recommended Models:**

| Model | Use Cases | Features |
|------|---------|------|
| **Llama 3.3 70B** | General tasks | Meta's latest, strong performance |
| **Llama 3.1 405B** | Complex tasks | Huge parameters, top capabilities |
| **DeepSeek R1** | Reasoning tasks | Math, code expert |
| **Qwen 3 235B** | Chinese tasks | Alibaba Qwen flagship |
| **Mistral 7B** | Quick response | Lightweight efficient |

#### Step 3: Enter Prompt

1. Enter your question or prompt in the input box
2. Can use System Message to set role
3. Click send or press Enter

#### Step 4: Adjust Parameters (Optional)

Adjust generation parameters in the right panel:

| Parameter | Range | Description | Recommended Value |
|------|------|------|--------|
| **Temperature** | 0-2 | Controls creativity | 0.7 |
| **Max Tokens** | 1-unlimited | Limits output length | 1024 |
| **Top P** | 0-1 | Nucleus sampling probability | 0.9 |
| **Top K** | 0-unlimited | Number of candidate words | 40 |
| **Frequency Penalty** | -2 to 2 | Reduce repetition | 0 |
| **Presence Penalty** | -2 to 2 | Increase topic diversity | 0 |

---

## 🎨 Feature Highlights

### 1. Multi-Model Selection

**Free Model Categories:**

- **🏆 Top-tier Models:** Llama 3.3/3.1 405B, DeepSeek R1
- **🚀 High-Performance Models:** Qwen 3 235B, Mistral Small, Gemma 3 27B
- **⚡ Lightweight Models:** Llama 3.2 3B, Gemma 3 4B, Mistral 7B
- **🎨 Multimodal Models:** Qwen 2.5 VL, Nemotron Nano VL
- **💻 Code Models:** Devstral, Qwen 3 Coder

**How to View:**
- Click model dropdown menu
- Look for models marked "FREE"
- Hover to view model details

### 2. System Message

**Features:**
- Define AI's role and behavior
- Set output format and rules
- Provide background knowledge

**Example:**
```
You are a professional Python programming assistant.
Please provide:
1. Clear code examples
2. Detailed comments
3. Best practice suggestions
```

### 3. Conversation History Management

**Features:**
- 📝 **Save Conversations** - Save important conversations
- 🔄 **Multi-turn Conversations** - Automatically maintain context
- 📂 **History** - View past conversations
- 🗑️ **Clear History** - Start new conversations

### 4. Usage Statistics

**Real-time Display:**
- 💰 **Cost Statistics** - View cost per request (free models show $0)
- 📊 **Token Count** - Number of input/output tokens
- 📈 **Quota Usage** - Remaining requests for the day
- ⏱️ **Response Time** - Request duration

### 5. Model Comparison Mode

**Features:**
- Run multiple models simultaneously
- Compare output quality
- Compare response speed
- Select the most suitable model

**Use Cases:**
- Choose best model
- A/B testing
- Evaluate model performance

### 6. Export and Share

**Features:**
- 📤 **Export Conversations** - Save as text or JSON
- 🔗 **Generate Links** - Share conversations
- 📋 **Copy Code** - Quickly get API code

---

## 🔢 Usage Limits

### Playground Quotas

Playground shares API quotas:

| Quota Type | Basic Tier | Upgraded Tier ($10) |
|---------|--------|-------------|
| Daily Requests | 50 times | 1,000 times |
| Requests per Minute | 20 times | 20 times |
| Free Models | 47+ | 47+ |

### Actual Usage Experience

For Playground users:
- ✅ Basic tier suitable for light testing
- ✅ Upgraded tier suitable for frequent development
- ✅ All free models available

---

## 💡 Usage Tips

### ✅ Best Practices

1. **Choose the Right Model**
   ```
   Quick testing → Mistral 7B, Llama 3.2 3B
   General tasks → Llama 3.3 70B
   Complex tasks → Llama 3.1 405B
   Chinese optimization → Qwen 3 235B, DeepSeek V3
   Code tasks → Devstral, Qwen 3 Coder
   Math reasoning → DeepSeek R1
   ```

2. **Optimize System Prompt**
   - Clear role and task
   - Provide specific requirements
   - Give output examples

3. **Leverage Comparison Feature**
   - Test same prompt on different models
   - Find the model that best suits your task
   - Record best configurations

4. **Monitor Quotas**
   - Check remaining quota in top right
   - Allocate test attempts reasonably
   - Consider upgrading to 1000 times/day

5. **Manage Conversation History**
   - Save important test results
   - Regularly clean unnecessary history
   - Export valuable conversations

### ⚠️ Precautions

1. **Quota Management**
   - Playground shares quotas with API
   - Be aware of 50 times/day limit (basic tier)
   - Frequent testing recommends upgrading

2. **Model Selection**
   - Ensure selecting models marked FREE
   - Paid models consume balance
   - Can set credit limit in settings

3. **Parameter Settings**
   - High temperature causes unstable output
   - Max tokens affects quota consumption
   - Different models need different parameters

4. **Network Requirements**
   - Needs stable network connection
   - Mainland China access relatively smooth
   - Avoid delays caused by network proxies

---

## 🔧 Common Issues

### 1. Can't Find Free Models?

**Solutions:**
1. Filter "FREE" in model list
2. Visit https://openrouter.ai/models
3. Confirm model names include `:free` suffix

### 2. Exceeded Quota Limit?

**Solutions:**
- Wait for next day quota reset (UTC time)
- Recharge $10 to upgrade to 1000 times/day
- Optimize testing strategy, reduce repeated requests

### 3. How to Save Test Results?

**Methods:**
1. Click save icon in top right of conversation
2. Use export function to save as file
3. Copy text and save manually

### 4. Response Quality Not Ideal?

**Optimization Methods:**
- Try different models
- Adjust System Prompt
- Modify Temperature and other parameters
- Provide more context

---

## 📚 Related Resources

### Documentation and Tutorials
- [OpenRouter Complete Guide](/en/providers/openrouter)
- [API Service Guide](/en/services/api/openrouter)
- [Official Documentation](https://openrouter.ai/docs)

### Model Information
- [Free Models List](https://openrouter.ai/models?free=true)
- [Model Performance Comparison](https://openrouter.ai/models)
- [Model Update Log](https://openrouter.ai/docs/models)

---

## 🌟 Advanced Usage

### Creating High-Quality Prompts

**Structured Example:**
```
System Message:
You are a professional technical documentation writer skilled at explaining complex concepts clearly.

User Message:
Topic: OpenRouter's Model Aggregation Feature
Requirements:
1. About 500 words
2. Include core advantages
3. Provide examples
4. Target developers
```

### Comparison Testing Workflow

1. **Prepare Same Prompt**
2. **Select 3-5 Candidate Models**
3. **Test One by One and Record Results**
4. **Compare Quality, Speed, Cost**
5. **Choose Optimal Model for Production**

### From Playground to API

1. Validate prompts and models in Playground
2. Fine-tune parameters for best results
3. Click "View Code" to export API code
4. Implement same configuration in application

---

**Service Provider:** [OpenRouter](/en/providers/openrouter)

