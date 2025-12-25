# GetFreeAI Documentation Template Library

Welcome to the GetFreeAI.net documentation template library! This directory contains all the templates and guides needed to create new documentation.

---

## 🌐 Multi-language Notes

This project supports **Simplified Chinese** and **English**. When adding English translations for Chinese documents:

- **Chinese document**: `content/providers/google-ai-studio/_index.md`
- **English document**: `content/providers/google-ai-studio/_index.en.md`

When translating, keep the document structure and formatting consistent, only translate the content text and `title`. See the "Multi-language Support" chapter in [WRITING-GUIDE.md](./WRITING-GUIDE.md) for details.

---

## 📚 Documentation Structure

Since December 2024, GetFreeAI has adopted a **modular documentation structure**:

### 🏢 Provider Documents
- **Location:** `content/providers/{provider-name}/_index.md`
- **Purpose:** Introduce provider's basic information, registration process, general features
- **Content:** Company introduction, official website links, general registration steps, credit card requirements, etc.

### 🎯 Service Documents
- **Location:** `content/services/{service-type}/{service-name}.md`
- **Types:**
  - `chatbot/` - Web conversation services
  - `api/` - Developer API services
  - Future additions may include: `ide/`, `software/`, etc.
- **Purpose:** Detailed instructions on how to use each specific service, limitations, code examples
- **Content:** Specific models, quota limits, code examples, access addresses, etc.

### 🔗 Bidirectional Linking
- Provider documents list all their Services
- Service documents link back to their Provider
- Users can find the information they need from any entry point

---

## 📋 Available Templates

### 1. Provider Template

**File:** [PROVIDER-TEMPLATE.md](./PROVIDER-TEMPLATE.md)

**Use Case:** Adding a new AI service provider

**Includes:**
- Provider basic information
- Company background introduction
- General registration process
- List of provided services (links to Service documents)
- General precautions

**Naming Convention:** `content/providers/{provider-name}/_index.md`  
Example: `content/providers/anthropic/_index.md`

---

### 2. Chatbot Service Template

**File:** [SERVICE-CHATBOT-TEMPLATE.md](./SERVICE-CHATBOT-TEMPLATE.md)

**Use Case:** Adding a new web conversation service

**Includes:**
- Chatbot access address (required!)
- Available features (web search, file upload, etc.)
- Usage limitations
- Usage steps
- Practical tips

**Naming Convention:** `content/services/chatbot/{service-name}/_index.md`  
Example: `content/services/chatbot/claude/_index.md`

**Note:** Do not repeat "chatbot" or "chat" in the directory name

---

### 3. API Service Template

**File:** [SERVICE-API-TEMPLATE.md](./SERVICE-API-TEMPLATE.md)

**Use Case:** Adding a new API service

**Includes:**
- API endpoint address
- Available models list
- Quotas and limitations
- API key acquisition steps
- Code examples (Python, cURL, etc.)
- Pricing information

**Naming Convention:** `content/services/api/{service-name}/_index.md`  
Example: `content/services/api/anthropic/_index.md`

**Note:** Do not repeat "api" in the directory name

---

## 📖 Writing Guide

**File:** [WRITING-GUIDE.md](./WRITING-GUIDE.md)

This is a detailed writing specification document (10,000+ words), including:

- 📐 Documentation structure specifications
- ✍️ Writing style guidelines
- 🎨 Formatting requirements
- 💻 Code example specifications
- 🔍 Research method suggestions
- ✅ Quality checklist

**Required reading for all contributors!**

---

## 🚀 Quick Start: Adding a New Provider

### Step 1: Create Provider Document

```bash {filename="Bash"}
# Create directory
mkdir -p content/providers/your-provider

# Copy template
cp content/templates/PROVIDER-TEMPLATE.md content/providers/your-provider/_index.md

# Edit document
# Fill in: company introduction, website, registration process, etc.
```

### Step 2: Create Service Documents

**If there's a Chatbot:**
```bash {filename="Bash"}
cp content/templates/SERVICE-CHATBOT-TEMPLATE.md content/services/chatbot/your-service/_index.md
# Fill in: access address, features, usage methods
```

**If there's an API:**
```bash {filename="Bash"}
mkdir -p content/services/api/your-service
cp content/templates/SERVICE-API-TEMPLATE.md content/services/api/your-service/_index.md
# Fill in: API endpoint, models, code examples
```

### Step 3: Establish Bidirectional Links

**In Provider document:**
```markdown {filename="Markdown"}
## 🎁 Provided Services

- [Service Name Chatbot](/services/chatbot/your-service)
- [Service Name API](/services/api/your-service-api)
```

**In Service document:**
```markdown {filename="Markdown"}
**Provider:** [Your Provider](/providers/your-provider)
```

### Step 4: Update Navigation

Edit `hugo.yaml`, add to `menu.sidebar`:

```yaml {filename="YAML"}
- name: Your Provider
  pageRef: /providers/your-provider
  parent: providers
  weight: 17
```

---

## 📊 Existing Documents

### Providers (6)

| Provider | Chatbot | API | Features |
|----------|---------|-----|----------|
| [Google AI Studio](/providers/google-ai-studio) | ✅ | ✅ | Highest free quota |
| [Google Vertex AI](/providers/google-vertex-ai) | ✅ | ✅ | Enterprise platform |
| [Groq](/providers/groq) | ✅ | ✅ | Fastest speed |
| [OpenRouter](/providers/openrouter) | ✅ | ✅ | 47+ free models |
| [DeepSeek](/providers/deepseek) | ✅ | ✅ | Chinese optimization |
| [Cohere](/providers/cohere) | ✅ | ✅ | RAG expert |

### Chatbot Services (7)

- Google AI Studio
- Vertex AI Studio
- Groq Playground
- OpenRouter Playground
- DeepSeek Chat
- Cohere Coral
- *(More to be added)*

### API Services (6)

- Google AI Studio API
- Vertex AI API
- Groq API
- OpenRouter API
- DeepSeek API
- Cohere API
- *(More to be added)*

---

## 🎯 Documentation Standards

### ✅ Provider Documents Must Include

- Provider name, website, logo (optional)
- Company background introduction (1-2 paragraphs)
- Registration process (if common to all services)
- List of provided services (links to Service documents)
- General precautions (such as credit card requirements)
- Related links

### ✅ Service Documents Must Include

**Chatbot Services:**
- Access address URL (required!)
- Available features list
- Usage limitations
- Usage steps
- Practical tips

**API Services:**
- API endpoint address
- Available models list
- Quotas and limitations (detailed table)
- API key acquisition steps
- Code examples (Python + cURL)
- Pricing information

---

## 💡 Writing Suggestions

### 1. Information Layering Principle

**General Information → Provider Document**
- Company introduction
- General registration process
- Credit card requirements
- Official resource links

**Differentiated Information → Service Document**
- Specific models list
- Service-specific limitations
- Code examples
- Service access addresses

### 2. Avoid Repetition

If multiple services share the same registration process, write it once in the Provider document only, and Service documents can link to it.

### 3. Keep It Concise

- Provider document: 2,000-3,000 words
- Chatbot service: 1,000-1,500 words
- API service: 2,000-3,000 words

### 4. Link Format

**External Links (Official Resources):**
- ✅ **Recommended:** `[https://example.com](https://example.com)`
- ❌ **Not Recommended:** Directly writing `https://example.com` (plain URL)
- **Reason:** Markdown link format will automatically display an arrow icon (↗), enhancing user experience
- **Effect:** [https://ai.google.dev/docs](https://ai.google.dev/docs) ↗

**Internal Links:**
- `[Provider Name](/providers/provider-name)`
- `[Service Name](/services/chatbot/service-name)`

**API Endpoints:**
- If it contains placeholders (like `[REGION]`), use code format: `` `https://[REGION]-api.example.com` ``
- If it's a fixed URL, you can use link format: `[https://api.example.com](https://api.example.com)`

### 5. User Perspective

**Provider Document Answers:**
- Who is this?
- What do they provide?
- How to get started?

**Service Document Answers:**
- What can this service do?
- What are the limitations?
- How to use it? (Code)

---

## 🔍 Naming Conventions

### Provider Directory Naming

- All lowercase
- Use hyphens as separators
- Use official English names

```
✅ google-ai-studio
✅ anthropic
✅ mistral-ai
❌ GoogleAIStudio
❌ google_ai_studio
❌ Google-AI-Studio
```

### Service Directory Naming

**Chatbot Service Directories:**
```
✅ claude/         (concise)
✅ gemini/         (concise)
✅ deepseek/       (concise)
❌ claude-chat/    (don't repeat "chat")
❌ claude-chatbot/ (don't repeat "chatbot")
```

**API Service Directories:**
```
✅ anthropic/      (concise)
✅ openai/         (concise)
✅ cohere/         (concise)
❌ anthropic-api/  (don't repeat "api")
❌ openai-api/     (don't repeat "api")
```

**Explanation:**
- Each service is a directory containing an `_index.md` file
- Directory names should not contain redundant information like "chat", "chatbot", "api"
- Directory names use lowercase letters and hyphens

---

## ✅ Quality Checklist

### Pre-Submission Check

#### Provider Documents
- [ ] Includes provider basic information
- [ ] Registration process is clear
- [ ] Lists all services and links to Service documents
- [ ] Format complies with specifications
- [ ] All links are valid

#### Chatbot Service Documents
- [ ] **Access address URL is clearly indicated**
- [ ] Features list is complete
- [ ] Limitations are clearly stated
- [ ] Usage steps are actionable
- [ ] Links back to Provider document

#### API Service Documents
- [ ] API endpoint address is correct
- [ ] Models list is accurate
- [ ] Quota limitations are detailed
- [ ] Code examples can run (Python + cURL)
- [ ] Pricing information is current
- [ ] Links back to Provider document

---

## 📞 Getting Help

### Reference Existing Documents

Check any existing Provider and its Services documentation as examples:
- `content/providers/google-ai-studio/`
- `content/services/chatbot/google-ai-studio/_index.md`
- `content/services/api/google-ai-studio/_index.md`

### Read the Writing Guide

[WRITING-GUIDE.md](./WRITING-GUIDE.md) contains detailed writing specifications and research methods.

### Contact Us

- **Website:** GetFreeAI.net
- **Issue Feedback:** GitHub Issues
- **Documentation Contribution:** Pull Request

---

## 📜 License

The content of this documentation library is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

---

**Template Version:** v2.0 (Modular Structure)  
**Last Updated:** December 2024  
**Maintainers:** GetFreeAI.net Team

