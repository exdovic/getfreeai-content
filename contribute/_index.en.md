---
title: Contribution Guide
weight: 4
comments: true
---

Thank you for your interest in the GetFreeAI project! We welcome all forms of contribution to make this project better.

---

## 🎯 Ways to Contribute

{{< cards >}}
  {{< card title="Improve Documentation" icon="pencil" subtitle="Enhance content and accuracy of existing docs" >}}
  {{< card title="Add Providers" icon="plus" subtitle="Add new free AI services" >}}
  {{< card title="Report Issues" icon="exclamation" subtitle="Discover errors or outdated information" >}}
  {{< card title="Make Suggestions" icon="light-bulb" subtitle="Share your ideas and improvement plans" >}}
{{< /cards >}}

---

## 📚 Documentation Architecture

GetFreeAI uses a **modular documentation architecture**, separating providers and services:

### 🏢 Provider Documents

**Location:** `content/providers/{provider-name}/_index.md`

**Content:**
- Basic information and introduction of the provider
- Company background and technical advantages
- General registration process (if shared across all services)
- List of services provided (links to Service documents)

**Examples:**
- `content/providers/google-ai-studio/_index.md`
- `content/providers/groq/_index.md`

---

### 🎯 Service Documents

**Chatbot Service Location:** `content/services/chatbot/{service-name}/_index.md`

**Note:** Directory names should not repeat "chatbot" or "chat"

**Content:**
- **Access URL** (required!)
- Available features (internet access, file upload, etc.)
- Usage limitations
- Usage steps and tips

**Examples:**
- `content/services/chatbot/google-ai-studio/_index.md`
- `content/services/chatbot/deepseek/_index.md`

---

**API Service Location:** `content/services/api/{service-name}/_index.md`

**Note:** Directory names should not repeat "api"

**Content:**
- API endpoint address
- List of available models
- Quotas and limitations (detailed table)
- Code examples (Python, cURL, etc.)
- Pricing information

**Examples:**
- `content/services/api/google-ai-studio/_index.md`
- `content/services/api/groq/_index.md`

---

### 🔗 Bidirectional Linking

- Provider documents link to all their Services
- Service documents link back to their Provider

**Examples:**

```markdown {filename="Markdown"}
# In Provider document
{{< card link="/services/chatbot/service-name" title="Service Name" >}}

# In Service document
**Provider:** [Provider Name](/providers/provider-name)
```

---

## 📝 How to Add a New Provider

### Step 1: Preparation

**1. Read Documentation Standards**

📖 **Required Reading:** [Writing Guide](/en/templates/writing-guide)

This detailed guide includes:
- Documentation architecture explanation
- Provider document standards
- Service document standards
- Writing style and format requirements
- Code example standards
- Research method suggestions

**2. Check Document Templates**

We provide three templates:
- 📋 [Provider Template](https://github.com/your-repo/blob/main/content/templates/PROVIDER-TEMPLATE.md)
- 💬 [Chatbot Service Template](https://github.com/your-repo/blob/main/content/templates/SERVICE-CHATBOT-TEMPLATE.md)
- 🔌 [API Service Template](https://github.com/your-repo/blob/main/content/templates/SERVICE-API-TEMPLATE.md)

**3. Reference Existing Documents**

Check any complete Provider and its Services:
- Provider: `/providers/google-ai-studio/`
- Chatbot: `/services/chatbot/google-ai-studio/`
- API: `/services/api/google-ai-studio/`

---

### Step 2: Research Information

Before starting to write, please ensure you have:

#### For Provider Documents

✅ **Visit Official Website** - Learn about company background and services  
✅ **Check Pricing Page** - Understand free and paid services  
✅ **Read Official Documentation** - Understand overall architecture  
✅ **Actually Register Account** - Verify registration process

#### For Chatbot Service Documents

✅ **Visit Chatbot Interface** - Confirm access URL  
✅ **Test All Features** - Verify internet access, file upload, code execution, etc.  
✅ **Test Usage Limits** - Confirm daily limits, length restrictions  
✅ **Record Special Features** - Note unique or useful features

#### For API Service Documents

✅ **Read API Documentation** - Understand endpoints, parameters, response formats  
✅ **Obtain API Key** - Actually register and obtain key  
✅ **Run Code Examples** - Ensure code can run  
✅ **Test Quota Limits** - Verify request limits, token limits  
✅ **Verify Pricing Info** - Confirm latest pricing

---

### Step 3: Create Documents

#### Create Provider Document

```bash {filename="Bash"}
# 1. Create Provider directory
mkdir -p content/providers/your-provider

# 2. Copy Provider template
cp content/templates/PROVIDER-TEMPLATE.md \
   content/providers/your-provider/_index.md

# 3. Edit document
# Fill in: basic info, company intro, registration process, service list
```

#### Create Chatbot Service Document (if applicable)

```bash {filename="Bash"}
# Create directory and copy Chatbot template
mkdir -p content/services/chatbot/your-service
cp content/templates/SERVICE-CHATBOT-TEMPLATE.md \
   content/services/chatbot/your-service/_index.md

# Edit document
# Fill in: access URL, features, limitations, usage methods
```

#### Create API Service Document (if applicable)

```bash {filename="Bash"}
# Create directory and copy API template
mkdir -p content/services/api/your-service
cp content/templates/SERVICE-API-TEMPLATE.md \
   content/services/api/your-service/_index.md

# Edit document
# Fill in: API endpoint, models, quotas, code examples
```

---

### Step 4: Establish Bidirectional Links

**Add service cards in Provider document:**

```markdown {filename="Markdown"}
## 🎁 Services Provided

### Chatbot Services

{{< cards >}}
  {{< card link="/services/chatbot/your-service" title="Your Service" subtitle="Brief description" >}}
{{< /cards >}}

### API Services

{{< cards >}}
  {{< card link="/services/api/your-service-api" title="Your Service API" subtitle="Brief description" >}}
{{< /cards >}}
```

**Link back to Provider in Service document:**

```markdown {filename="Markdown"}
**Provider:** [Your Provider](/providers/your-provider)
```

---

### Step 5: Update Navigation

Edit `hugo.yaml`, add to `menu.sidebar`:

```yaml {filename="YAML"}
- name: Your Provider
  pageRef: /providers/your-provider
  parent: providers
  weight: 17  # Use next available number
```

---

### Step 6: Quality Check

Use our checklist:

#### Provider Document Check

- [ ] Complete basic information (name, website, location, time)
- [ ] Clear company introduction (1-2 paragraphs)
- [ ] List all services provided
- [ ] Each service correctly links to Service document
- [ ] All related links are valid
- [ ] Format complies with standards

#### Chatbot Service Document Check

- [ ] **Access URL clearly marked** (most important!)
- [ ] Provider linked
- [ ] Complete feature list
- [ ] Clear usage limitations (table format)
- [ ] Actionable usage steps
- [ ] Format complies with standards

#### API Service Document Check

- [ ] Correct API endpoint address
- [ ] Provider linked
- [ ] Accurate model list
- [ ] Detailed quota limits (table format)
- [ ] Runnable Python code example
- [ ] Correct cURL example
- [ ] Latest pricing information
- [ ] Format complies with standards

---

## 📋 Submission Process

### 1. Fork the Project

```bash {filename="Bash"}
# Fork the project to your GitHub account
# Then clone locally
git clone https://github.com/your-username/getfreeai.git
cd getfreeai
```

### 2. Create Branch

```bash {filename="Bash"}
# Create new branch
git checkout -b add-provider-name

# Or fix issue
git checkout -b fix-issue-description
```

### 3. Add Documents

```bash {filename="Bash"}
# Add Provider document
git add content/providers/your-provider/_index.md

# Add Chatbot service document (if applicable)
git add content/services/chatbot/your-service/

# Add API service document (if applicable)
git add content/services/api/your-service/

# Update navigation config (if needed)
git add hugo.yaml
```

### 4. Commit Changes

```bash {filename="Bash"}
# Commit
git commit -m "docs: add Provider Name and its service documents"

# Push to your repository
git push origin add-provider-name
```

### 5. Create Pull Request

1. Visit your forked repository
2. Click "New Pull Request"
3. Fill in PR description:

**PR Title Example:**
```
docs: add Anthropic (Claude) provider and service documents
```

**PR Description Template:**
```markdown {filename="Markdown"}
## Added Content

- [ ] Provider document: Anthropic
- [ ] Chatbot service: Claude Chat
- [ ] API service: Anthropic API

## Completed Checks

- [ ] All information verified
- [ ] Code examples tested
- [ ] Access URLs confirmed
- [ ] Format complies with standards
- [ ] Bidirectional links established
- [ ] Navigation menu updated

## Additional Notes

[Any other notes if needed]
```

---

## 🎨 Naming Conventions

### Provider Directory Naming

- All lowercase
- Use hyphens `-` as separators
- Use official English names

```
✅ google-ai-studio
✅ anthropic
✅ mistral-ai
❌ GoogleAIStudio
❌ google_ai_studio
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

**Notes:**
- Each service is a directory containing an `_index.md` file
- Directory names should not include repetitive information like "chat", "chatbot", "api"
- Directory names use lowercase letters and hyphens

---

## 💡 Content Suggestions

### Writing Style

- **Clear and Direct** - Avoid vague statements, use specific data
- **User Perspective** - Start from user needs, solve practical problems
- **Friendly and Professional** - Maintain courtesy and professionalism
- **Practical First** - Provide actionable guidance, not theory

### Example Quality

- **Runnable Code** - Examples must be directly runnable
- **Include Comments** - Add necessary explanatory comments
- **Mark Replacements** - Clearly mark content that needs replacement (like API keys)
- **Multi-language Support** - Provide at least Python and cURL examples

### Precautions

- **Mark Limitations** - Clearly state all limitations and warnings
- **Explain Issues** - Mention possible problems
- **Provide Solutions** - Give solutions or alternative suggestions
- **Avoid Errors** - Help users avoid common mistakes

---

## 🔍 Document Review Points

### Content Completeness

- [ ] All required sections included
- [ ] Chatbot URL clearly marked (if applicable)
- [ ] Complete limitation and quota information
- [ ] Detailed actionable registration steps
- [ ] Complete and runnable code examples
- [ ] All links are valid
- [ ] Provider ↔ Service bidirectional links established

### Format Standards

- [ ] Correct Markdown format
- [ ] Tables neatly aligned
- [ ] Appropriate emoji usage
- [ ] Code blocks have language tags (e.g., `` ```python {filename="Python"}` ``)
- [ ] **External links use Markdown format** (e.g., `[URL](URL)`), not plain URLs. Markdown formatted external links automatically display arrow icons (↗)
- [ ] Reasonable heading hierarchy (Provider uses #, sections use ##)
- [ ] **Correct Front Matter configuration**:
  - [ ] Include `type: docs` (required! Enables document layout and navigation)
  - [ ] Configure `weight` field (controls sorting)
  - [ ] Configure `prev` and `next` (enables previous/next navigation buttons at page bottom)
  - [ ] Include `sidebar.open: true` (automatically expands left sidebar)

### Accuracy Verification

- [ ] All data verified
- [ ] Pricing information is latest
- [ ] Limitation descriptions accurate
- [ ] No outdated information
- [ ] Links are accessible
- [ ] Code examples tested

---

## 🐛 Report Issues

Found errors or outdated information? Please help us improve!

### Report via Issue

1. Visit the project's Issues page
2. Click "New Issue"
3. Choose appropriate template:
   - 📝 Documentation error
   - ❌ Outdated information
   - 💡 Improvement suggestion
   - 🆕 New provider request

### Issue Description Points

**Good Issue Title:**
```
✅ [Google AI Studio] API quota information outdated
✅ [DeepSeek] Chatbot access URL invalid
✅ [Groq] Python code example cannot run
❌ There's a problem (too vague)
```

**Issue description should include:**
- **Clear title** - Briefly describe the problem
- **Detailed description** - Specifically explain the issue
- **Screenshots or links** - If applicable
- **Suggested fix** - If you know how to fix it
- **Affected documentation** - Clearly indicate which document

---

## 🌟 Top Contributors

We'll showcase friends who have made outstanding contributions to the project here!

**Contribution Types:**
- 🏆 **Add New Provider** - Complete Provider + Services documentation
- 📝 **Improve Existing Docs** - Major improvements and updates
- 🐛 **Fix Issues** - Fix errors and outdated information
- 💡 **Make Suggestions** - Valuable improvement suggestions

---

## 📧 Contact Us

If you have any questions or suggestions:

- **GitHub Issues** - Raise questions or suggestions
- **Pull Request** - Submit improvements directly
- **Email** - [To be added]
- **Discord** - [To be added]

---

## 📜 Code of Conduct

By participating in this project, you agree to abide by our code of conduct:

- **Respect Others** - Friendly, inclusive, respect every contributor
- **Constructive Discussion** - Rational, objective, beneficial communication
- **Professional Attitude** - Responsible, serious, professional work style
- **Open Source Spirit** - Share, collaborate, progress together

**We do not tolerate:**
- Harassment, discrimination, offensive speech
- Spam, advertising, malicious content
- Plagiarism, theft of others' work
- Violation of open source licenses

---

## 🎓 Learning Resources

### Reference Existing Documents

Check out these excellent examples:

**Complete Provider Examples:**
- [Google AI Studio](/en/providers/google-ai-studio) - High free quota
- [Groq](/en/providers/groq) - Technical advantage explanation
- [OpenRouter](/en/providers/openrouter) - Multi-model aggregation
- [DeepSeek](/en/providers/deepseek) - Chinese-optimized service

**Chatbot Service Examples:**
- [Google AI Studio Chatbot](/en/services/chatbot/google-ai-studio/)
- [DeepSeek Chat](/en/services/chatbot/deepseek/)
- [Cohere Coral](/en/services/chatbot/cohere/)

**API Service Examples:**
- [Google AI Studio API](/en/services/api/google-ai-studio/)
- [Groq API](/en/services/api/groq/)
- [OpenRouter API](/en/services/api/openrouter/)

### Documentation and Tools

- **[Writing Guide](/en/templates/writing-guide)** - Detailed writing standards
- **[Template Library](/en/templates)** - Provider and Service templates
- [Markdown Syntax](https://www.markdownguide.org/) - Markdown basics
- [Hugo Documentation](https://gohugo.io/documentation/) - Static site generator
- [Hextra Theme](https://imfing.github.io/hextra/) - Documentation theme

---

## 📊 Contribution Statistics

**Current Status:**
- 🏢 Provider documents: 6
- 💬 Chatbot services: 7
- 🔌 API services: 6
- 📝 Total documents: 19

**We need your help to add:**
- OpenAI (ChatGPT, GPT API)
- Anthropic (Claude, Claude API)
- Mistral AI (Le Chat, Mistral API)
- Perplexity (Perplexity Chatbot)
- HuggingFace (Various free models)
- ...More providers

---

<div align="center">

**Thank you for your contribution!** 🙏

Let's make AI services accessible together!

[Start Contributing](https://github.com/your-repo) · [View Templates](/en/templates) · [Read Guide](/en/templates/writing-guide)

</div>

