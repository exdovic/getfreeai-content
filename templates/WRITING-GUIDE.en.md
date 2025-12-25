---
title: "Documentation Writing Guide"
weight: 40
comments: true
---

# GetFreeAI Documentation Writing Guide

This guide is designed to help content contributors create high-quality, consistent AI service provider and service documentation.

---

## 📚 Table of Contents

1. [Documentation Architecture](#documentation-architecture)
2. [Provider Document Specifications](#provider-document-specifications)
3. [Service Document Specifications](#service-document-specifications)
4. [Writing Specifications](#writing-specifications)
5. [Formatting Requirements](#formatting-requirements)
6. [Code Example Specifications](#code-example-specifications)
7. [Research Methods](#research-methods)
8. [Quality Checklist](#quality-checklist)

---

## 🌐 Multi-language Support

This project supports **Simplified Chinese** and **English**.

### Multi-language File Structure

Use Hugo's filename suffix method to manage translations:

- **Chinese document** (default): `content/providers/google-ai-studio/_index.md`
- **English document**: `content/providers/google-ai-studio/_index.en.md`

### Adding English Translations

When adding English translations for existing Chinese documents:

1. Copy the Chinese document
2. Rename to `_index.en.md` (or `filename.en.md`)
3. Translate all content (including `title` in front matter)
4. Keep document structure and formatting consistent

**Example:**

```markdown {filename="_index.en.md"}
---
title: Google AI Studio  # English title
type: docs
weight: 1
prev: /providers
next: /providers/groq
sidebar:
  open: true
---

## 🎯 Overview

Google AI Studio is...
```

### Translation Notes

- ✅ **Must translate**: Titles, body text, link text, image alt text
- ✅ **Keep consistent**: URL paths, front matter parameters (except `title`), code block content
- ✅ **Keep formatting**: Markdown syntax, shortcodes, document structure
- ❌ **Don't translate**: Code examples, API endpoints, technical terms (like API Key, Token)

---

## 🏗️ Documentation Architecture

### Core Principle: Modular, Bidirectionally Linked

GetFreeAI adopts a **Provider-Service Separation Architecture**:

```
Provider
    ├── Basic Information
    ├── Company Introduction
    ├── General Registration Process
    └── List of Provided Services ──┐
                         │
                         │ (Links)
                         │
                         ↓
Service          
    ├── Chatbot Service ←───┘
    │   ├── Access Address
    │   ├── Features List
    │   └── Usage Methods
    │
    └── API Service
        ├── API Endpoint
        ├── Available Models
        ├── Quota Limits
        └── Code Examples
```

### Information Layering Principle

**General Information → Provider Document**
- Company background introduction
- General registration process common to all services
- Credit card requirement explanations
- Official resource links

**Differentiated Information → Service Document**
- Service-specific access addresses
- Specific models lists
- Service-specific quota limitations
- Code examples and usage methods

### When to Split, When to Merge?

**Split when:**
- Chatbot and API have different limitations
- Chatbot and API use different models
- Chatbot and API require different registration processes

**Merge when:**
- If Provider only has one simple Chatbot (no API), you can consider writing everything in the Provider document
- But recommended: Even if merged, maintain clear structure for easy future splitting

---

## 🏢 Provider Document Specifications

### Document Location

```
content/providers/{provider-name}/_index.md
```

### Required Sections

#### 1. Basic Information

```markdown {filename="Markdown"}
**Provider Name:** Anthropic  
**Official Website:** https://www.anthropic.com  
**Headquarters Location:** San Francisco, USA  
**Founded:** 2021
```

**Requirements:**
- Provider English full name
- Chinese name (if any)
- Official website URL
- Headquarters location and founding year (enhances credibility)

---

#### 2. Provider Introduction

**Purpose:** Let users quickly understand who this company is and what they do.

**Requirements:**
- 1-2 paragraphs of concise introduction (200-300 words)
- List 3-5 core features
- Explain technical advantages or uniqueness

**Example:**

```markdown {filename="Markdown"}
Anthropic is an AI safety company founded by former OpenAI researchers, focused on developing safer, more controllable AI systems.

### Core Features

- **Safety First:** Constitutional AI technology
- **Long Context:** 200K tokens context window
- **Code Capability:** Powerful code generation and analysis
- **Enterprise-Grade:** Reliability and security assurance
```

---

#### 3. Provided Services

**Purpose:** List all available services and link to detailed documentation.

**Use Hugo Cards format:**

```markdown {filename="Markdown"}
### Chatbot Services

{{< cards >}}
  {{< card link="/services/chatbot/claude-chat" title="Claude Chat" subtitle="Web-based conversation service with long context support" >}}
{{< /cards >}}

### API Services

{{< cards >}}
  {{< card link="/services/api/anthropic-api" title="Anthropic API" subtitle="Developer API supporting Claude series models" >}}
{{< /cards >}}
```

**Requirements:**
- One card per service
- Brief subtitle explanation (1 sentence)
- Correct link to Service document

---

#### 4. Getting Started

**When to include:**
- When all services share the same registration process
- When the registration process is complex enough to warrant separate explanation

**When to omit:**
- When each service has different registration processes, explain separately in Service documents

**Includes:**
- Requirement checklist table
- Detailed registration steps (using Steps shortcode)
- Important reminders (like no credit card charges)

**Registration Steps Format (Must use Steps shortcode):**

```markdown {filename="Markdown"}
### Registration Steps

{{% steps %}}

#### Step Title 1

Step content explanation...

#### Step Title 2

Step content explanation...

#### Step Title 3

Step content explanation...

{{% /steps %}}
```

**Steps Shortcode Key Points:**
- ✅ Use `{{% steps %}}` and `{{% /steps %}}` to wrap all steps
- ✅ Step titles should be concise, directly explaining the step content (like "Register Account", not "Step 1: Register Account")
- ✅ Step content can include paragraphs, lists, bold, links, etc.
- ✅ Can use emojis and icons to enhance readability (⚠️, 💡, ✅ etc.)
- ❌ Don't add prefixes like "Step 1", "First step" in step titles (system will auto-number)

---

#### 5. General Precautions

**Includes:**
- ✅ Recommended practices (3-5 items)
- ⚠️ Important reminders (3-5 items)
- 🔧 Common questions (3-5 items)

---

#### 6. Related Links

**Required Links:**
- Official website
- Developer platform
- API documentation
- Pricing information
- Status page

**Optional Links:**
- GitHub
- Discord/Slack
- Community forums
- Blog

---

### Provider Document Length

**Recommended Length:** 2,000-3,000 words

**Too Short (< 1,500 words):** Insufficient information  
**Too Long (> 4,000 words):** Consider splitting into Service documents

---

## 🎯 Service Document Specifications

### Chatbot Service Documents

#### Document Location

```
content/services/chatbot/{service-name}/_index.md
```

**Note:** Don't repeat "chatbot" or "chat" in the directory name

#### Required Sections

**1. Service Overview**

```markdown {filename="Markdown"}
**Service Name:** Claude Chat  
**Provider:** [Anthropic](/providers/anthropic)  
**Access URL:** https://claude.ai ⬅️ Required!  
**Service Type:** Freemium  
**Registration Requirements:** Email registration required
```

**⚠️ Important: Access URL is the most critical information for Chatbot documentation!**

---

**2. Available Features**

List all features the Chatbot supports:

```markdown {filename="Markdown"}
- ✅ **Long Context Conversations** - Supports 200K tokens
- ✅ **File Upload** - Supports PDF, Word, images, etc.
- ✅ **Code Execution** - Can run Python code
- ❌ **Web Search** - Not currently supported
```

---

**3. Usage Limitations**

**Display clearly using tables:**

| Limitation | Quota | Notes |
|-----------|-------|-------|
| **Daily Conversations** | ~50 times | Free users |
| **Single Conversation Length** | No hard limit | But uses context |
| **File Upload** | ✅ Supported | Max 10MB |
| **Credit Card Required** | ❌ Not Required | Completely free |

---

**4. How to Use**

- If Provider has explained registration process, link to it
- Explain in detail the Chatbot usage steps
- Include advanced features usage methods

---

**5. Practical Tips**

- ✅ Recommended practices
- 🎯 Best practices
- ⚠️ Precautions

---

**Chatbot Document Length:** 1,000-1,500 words

---

### API Service Documents

#### Document Location

```
content/services/api/{service-name}/_index.md
```

**Note:** Don't repeat "api" in the directory name

#### Required Sections

**1. Service Overview**

```markdown {filename="Markdown"}
**Service Name:** Anthropic API  
**Provider:** [Anthropic](/providers/anthropic)  
**API Endpoint:** `https://api.anthropic.com/v1`  
**Service Type:** Paid, with trial credits  
**Registration Requirements:** Credit card verification required
```

---

**2. Available Models**

**Use detailed tables:**

| Model Name | Context Length | Output Length | Features | Use Cases |
|-----------|---------------|---------------|----------|-----------|
| **claude-3-opus** | 200K | 4K | Most powerful | Complex tasks |
| **claude-3-sonnet** | 200K | 4K | Balanced | Daily use |
| **claude-3-haiku** | 200K | 4K | Fastest | High-frequency calls |

---

**3. Quotas and Limitations**

**Detailed limitation tables:**

| Limitation | Quota | Notes |
|-----------|-------|-------|
| **Daily Requests** | 1,000 requests/day | Free tier |
| **Requests Per Minute** | 20 requests/min | All tiers |
| **Daily Tokens** | 100K tokens/day | Free tier |
| **Trial Credits** | $5 | New users |

**⚠️ Important Limitations:** List separately any limitations that need special attention

---

**4. Pricing Information**

**Distinguish between free and paid:**

```markdown {filename="Markdown"}
### Free/Trial

- **Trial Credits:** $5 for new users
- **Validity Period:** 30 days
- **Acquisition Method:** Granted upon registration

### Paid Pricing

| Model | Input Price | Output Price |
|-------|------------|--------------|
| **claude-3-opus** | $15/M tokens | $75/M tokens |
| **claude-3-sonnet** | $3/M tokens | $15/M tokens |
```

---

**5. How to Use**

- Prerequisites (registration, getting API key)
- If Provider has explained, link to it
- If it's API-specific process, explain in detail

---

**6. Code Examples**

**Must provide:**
- ✅ Python examples (basic + streaming)
- ✅ cURL examples

**Optional to provide:**
- Node.js examples
- Other popular languages

**Code requirements:**
- Can run directly (or note what needs to be replaced)
- Include error handling examples
- Add necessary comments

---

**7. Practical Suggestions**

- ✅ Recommended practices
- 🎯 Best practices (optimize tokens, error handling)
- ⚠️ Precautions

---

**8. Practical Application Cases**

Provide 2-4 complete code examples showing actual use cases.

---

**API Document Length:** 2,000-3,000 words

---

## 📝 Writing Specifications

### Language and Style

1. **Use English**
   - Main content in English
   - Provide native terms when professional terms first appear
   - Code comments can use English

2. **Clear and Direct**
   - Avoid vague expressions
   - Use specific data
   - One idea per sentence

3. **Friendly but Professional**
   - Use "you" instead of overly formal address
   - Avoid being too colloquial
   - Maintain objectivity and neutrality

4. **User-Oriented**
   - Start from user's perspective
   - Answer questions users actually care about
   - Provide actionable guidance

---

### Terminology Usage

**Unified Terminology:**
- Provider - Not "supplier"
- Service - Not "product"
- Chatbot - Not "chat robot"
- API Key - Not just "key"
- Free Quota - Not "allowance"
- Trial Credits - Not "free allowance"

**Unit Representation:**
- Dollars: $10 or 10 dollars
- RMB: ¥10 or 10 yuan
- Requests: requests/day, requests/min
- Tokens: tokens, M tokens (million), K tokens (thousand)

---

### Numbers and Data

**Specific > Vague:**

❌ "Very high free quota"  
✅ "15M tokens per day"

❌ "Very fast"  
✅ "800+ tokens/s"

❌ "Supports many models"  
✅ "Supports 47+ free models"

---

### Title Writing

**Good Titles:**
- ✅ "How to Get API Key" (clear, actionable)
- ✅ "Free Quotas and Limitations" (specific)
- ✅ "Python Code Examples" (clear)

**Poor Titles:**
- ❌ "Getting Started" (too vague)
- ❌ "More Information" (not specific)
- ❌ "Others" (meaningless)

---

## 🎨 Formatting Requirements

### Markdown Format

**Heading Levels:**

```markdown {filename="Markdown"}
## Level-2 Heading (Main Section)
### Level-3 Heading (Subsection)
#### Level-4 Heading (Sub-subsection, use sparingly)
```

**⚠️ Important: Don't use level-1 headings (`#`)!**

Hugo will automatically use the `title` from front matter to generate the page title. If you write a level-1 heading again in Markdown, it will cause duplicate titles.

**Correct Approach:**
```markdown {filename="Markdown"}
---
title: Google AI Studio
---

## 📋 Basic Information  ← Start from level-2 heading
```

**Incorrect Approach:**
```markdown {filename="Markdown"}
---
title: Google AI Studio
---

# Google AI Studio  ← Don't write level-1 heading! Will duplicate!

## 📋 Basic Information
```

**Table Format:**
- Must be aligned
- Use bold for headers (`**Title**`)
- Important columns can be bolded

**List Format:**
- Ordered list use numbers: `1.`, `2.`, `3.`
- Unordered list use `-`
- Feature list use `- ✅` or `- ❌`

**Emphasis Format:**
- Important content: **Bold**
- Terms first appearance: **Bold**
- Code or commands: `inline code`
- Don't overuse emphasis

---

### Emoji Usage

**Section Title Emojis (Fixed):**
- 📋 Basic Information/Service Overview
- 🏢 Provider Introduction
- 🎁 Provided Services/Available Features
- 🔢 Quotas and Limitations
- 🚀 Getting Started/How to Use
- 💰 Pricing Information
- 💻 Code Examples
- 🌟 Core Advantages
- 💡 Practical Suggestions
- 🎯 Application Cases/Use Cases
- 🔧 Common Questions
- 🔗 Related Links
- 📝 Changelog
- 📧 Support & Feedback

**Emojis in Content (Moderate):**
- ✅ Indicates "have", "support", "yes"
- ❌ Indicates "no", "don't support", "no"
- ⚠️ Indicates warnings and precautions
- 🏆 Indicates advantages or first place
- 💡 Indicates tips
- 🔧 Indicates technical-related

---

### Link Format

**Internal Links (to other documents):**

```markdown {filename="Markdown"}
[Provider Name](/providers/provider-name)
[Service Name](/services/chatbot/service-name)
[API Documentation](/services/api/service-name-api)
```

**External Links (official resources):**

```markdown {filename="Markdown"}
[Official Website](https://www.example.com)
[API Documentation](https://docs.example.com)
```

**⚠️ Important Notice:**
- External links will **automatically display arrow icon (↗)**, this is a built-in feature of the Hextra theme
- Please use full Markdown link format: `[Link Text](URL)`
- **Don't write plain URLs** (like `https://example.com`), otherwise won't display arrow icon
- Link text is recommended to use **full URL** (like `[https://ai.google.dev/docs](https://ai.google.dev/docs)`)
- **Don't manually add arrow symbol** (like `[Link Text ↗](URL)`), theme will automatically add it

**Anchor Links (intra-document jumps):**

```markdown {filename="Markdown"}
[Jump to Code Examples](#code-examples)
```

---

### Front Matter Configuration

**Basic Configuration:**

All Provider and Service documents should include the following configuration in Front Matter:

```markdown {filename="Markdown"}
---
title: "Document Title"
type: docs              # ⬅️ Required! Enables documentation layout and navigation features
weight: 10             # ⬅️ Controls sorting (smaller numbers appear first)
comments: true           # ⬅️ Controls whether comments are enabled
prev: /path/to/previous  # ⬅️ Optional: Previous page link
next: /path/to/next      # ⬅️ Optional: Next page link
sidebar:
  open: true           # ⬅️ Auto-expand left navigation bar
---
```

**Page Bottom Navigation (prev/next):**

`prev` and `next` parameters are used to configure "previous/next page" navigation buttons at the bottom of the page.

**Provider Document Example:**

```markdown {filename="Markdown"}
---
title: Groq
type: docs
weight: 2
comments: true
prev: /providers/google-ai-studio  # Previous provider
next: /providers/openrouter         # Next provider
sidebar:
  open: true
---
```

**Chatbot Service Document Example:**

```markdown {filename="Markdown"}
---
title: "DeepSeek Chat"
type: docs
weight: 4
comments: true
prev: /services/chatbot/openrouter   # Previous Chatbot service
next: /services/chatbot/cohere       # Next Chatbot service
sidebar:
  open: true
---
```

**API Service Document Example:**

```markdown {filename="Markdown"}
---
title: "Groq API"
type: docs
weight: 2
comments: true
prev: /services/api/google-ai-studio  # Previous API service
next: /services/api/openrouter         # Next API service
sidebar:
  open: true
---
```

**Configuration Explanation:**

- **`type: docs`**: Required! This tells Hugo to use the documentation layout template, which includes page navigation features.
- **`weight`**: Controls sorting in the list, smaller numbers appear first. Recommended to use intervals of 10 (10, 20, 30...), convenient for inserting new documents later.
- **`prev`**: Path to previous document. Will display "← Previous" button at page bottom.
- **`next`**: Path to next document. Will display "Next →" button at page bottom.
- **`sidebar.open: true`**: Makes left navigation bar expand by default, convenient for users to quickly browse document structure.

**Notes:**

- `prev` and `next` are optional, but strongly recommended to provide better reading experience.
- Paths must be absolute paths relative to website root (starting with `/`).
- First document can only configure `next`, last document can only configure `prev`.
- If unsure which document to link to, refer to document order in left navigation bar.

---

## 💻 Code Example Specifications

### Python Code

**Basic Requirements:**
- Use official SDK (if available)
- Include complete import statements
- Clear variable naming (use meaningful names)
- Add necessary comments
- Can run directly (or note what needs to be replaced)

**Standard Structure:**

```python {filename="Python"}
from openai import OpenAI

# Initialize client (please replace with your API key)
client = OpenAI(
    base_url="https://api.example.com/v1",
    api_key="YOUR_API_KEY"  # ⬅️ Replace with your key
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

**Must Include:**
1. Basic call example
2. Streaming output example (for APIs)
3. Error handling example

---

### cURL Examples

**Standard Format:**

```bash {filename="Bash"}
curl https://api.example.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "model-name",
    "messages": [
      {"role": "system", "content": "You are a helpful assistant."},
      {"role": "user", "content": "Hello, please introduce yourself."}
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**Requirements:**
- Use backslash for line breaks
- Clear indentation (2 or 4 spaces)
- Include all required headers
- Correct JSON format

---

### Node.js Examples (Optional)

If target users include JavaScript developers, provide Node.js examples:

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
      { role: 'user', content: 'Hello' }
    ],
  });

  console.log(completion.choices[0].message.content);
}

main();
```

---

## 🔍 Research Methods

### Information Source Priority

1. **Official Documentation** (highest priority, most reliable)
   - Official website
   - API documentation
   - Pricing page
   - Official blog
   - Official Changelog

2. **Actual Testing** (strongly recommended)
   - Register and use yourself
   - Test limits and quotas
   - Verify code examples
   - Record encountered issues

3. **Community Resources** (verify real user experiences)
   - GitHub Issues
   - Reddit
   - Stack Overflow
   - Discord/Slack communities
   - User comments

4. **Third-party Comparisons** (reference, but need verification)
   - Tech blogs
   - Review articles
   - YouTube videos
   - But verify timeliness!

---

### Information That Must Be Verified

#### For All Documents

1. **Official Links**
   - Official website URL
   - Chatbot access address
   - API endpoint address
   - Documentation links

2. **Registration Requirements**
   - Email/phone required
   - Credit card required
   - Identity verification required
   - Whether charges apply

3. **Timeliness**
   - Policy changes
   - Price adjustments
   - Feature updates

---

#### For Chatbot Documents

1. **Access Address** (Most important!)
2. **Available Features** (web search, file upload, code execution, etc.)
3. **Usage Limitations** (daily limits, single session length, etc.)

---

#### For API Documents

1. **Quotas and Limitations**
   - Daily/per-minute request counts
   - Token limits
   - Whether truly free

2. **Available Models**
   - Model names (precise)
   - Context length
   - Streaming output support

3. **Pricing Information**
   - Free quotas
   - Trial credits
   - Paid pricing (input/output separately)

---

### Recommended Research Steps

**Provider Document Research:**
1. Read official website and About page - 1 hour
2. Check pricing and services pages - 30 minutes
3. Actual registration testing - 1 hour
4. Write documentation - 2 hours
**Total: About 4-5 hours**

---

**Chatbot Service Document Research:**
1. Visit Chatbot and test features - 1 hour
2. Test various feature limitations - 1 hour
3. Check help documentation - 30 minutes
4. Write documentation - 1.5 hours
**Total: About 4 hours**

---

**API Service Document Research:**
1. Read API documentation - 2 hours
2. Actual registration and get API key - 1 hour
3. Run code examples and test - 2 hours
4. Check community feedback - 1 hour
5. Write documentation - 3 hours
**Total: About 9 hours**

---

## ✅ Quality Checklist

### Provider Document Check

- [ ] Basic information complete (name, website, location, year)
- [ ] Company introduction clear (1-2 paragraphs)
- [ ] Lists all provided services
- [ ] Each service correctly links to Service document
- [ ] If has general registration process, explained in detail
- [ ] All related links valid
- [ ] Format complies with specifications
- [ ] Length appropriate (2,000-3,000 words)

---

### Chatbot Service Document Check

- [ ] **Access address clearly indicated** (Most important!)
- [ ] Provider linked
- [ ] Features list complete (web search, file, code, etc.)
- [ ] Usage limitations clear (table format)
- [ ] Usage steps actionable
- [ ] Practical tips valuable
- [ ] Links back to Provider document
- [ ] Format complies with specifications
- [ ] Length appropriate (1,000-1,500 words)

---

### API Service Document Check

- [ ] API endpoint address correct
- [ ] Provider linked
- [ ] Models list accurate (names, context, features)
- [ ] Quota limitations detailed (table format)
- [ ] Pricing information current (free + paid)
- [ ] Python code examples can run
- [ ] cURL examples correct
- [ ] Includes error handling examples
- [ ] Practical application cases complete
- [ ] Links back to Provider document
- [ ] Format complies with specifications
- [ ] Length appropriate (2,000-3,000 words)

---

### General Check

#### Content Completeness
- [ ] All required sections included
- [ ] No empty sections or placeholders
- [ ] All "[To be filled]" replaced

#### Format Compliance
- [ ] Markdown format correct
- [ ] Tables aligned
- [ ] Emoji usage appropriate
- [ ] Code blocks have language tags
- [ ] Heading hierarchy reasonable

#### Accuracy
- [ ] All data verified
- [ ] Pricing information current
- [ ] Limitation descriptions accurate
- [ ] No outdated information
- [ ] All links accessible

#### Readability
- [ ] Language clear and fluent
- [ ] No typos
- [ ] Terminology usage consistent
- [ ] Logically coherent
- [ ] Suitable for target readers

#### Practicality
- [ ] Steps can be actually followed
- [ ] Code can be directly used
- [ ] Precautions valuable
- [ ] FAQ answers real questions
- [ ] Suggestions actionable

---

## 📋 Final Pre-Submission Check

```markdown {filename="Markdown"}
Provider Document:
- [ ] I used PROVIDER-TEMPLATE.md
- [ ] All services linked
- [ ] Registration process clear (or links to Service)
- [ ] All related links valid
- [ ] Format complies with specifications

Chatbot Document:
- [ ] I used SERVICE-CHATBOT-TEMPLATE.md
- [ ] **Access address clearly indicated**
- [ ] Linked back to Provider document
- [ ] Features and limitations clear
- [ ] Format complies with specifications

API Document:
- [ ] I used SERVICE-API-TEMPLATE.md
- [ ] Code examples verified to run
- [ ] Quota and pricing information accurate
- [ ] Linked back to Provider document
- [ ] Format complies with specifications

All Documents:
- [ ] I've actually tested the service
- [ ] All information verified accurate
- [ ] Document self-reviewed at least once
- [ ] Last update time filled in
```

---

## 🎓 Learning Resources

**Reference Existing Documents:**

**Provider Documents:**
- `content/providers/google-ai-studio/_index.md`
- `content/providers/groq/_index.md`
- `content/providers/openrouter/_index.md`

**Chatbot Documents:**
- `content/services/chatbot/google-ai-studio/_index.md`
- `content/services/chatbot/deepseek/_index.md`

**API Documents:**
- `content/services/api/google-ai-studio/_index.md`
- `content/services/api/groq/_index.md`

**Markdown References:**
- [Markdown Basic Syntax](https://www.markdownguide.org/basic-syntax/)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)

**Hugo References:**
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Hextra Theme Documentation](https://imfing.github.io/hextra/)

---

## 💬 Getting Help

If you have any questions:

1. Check existing Provider and Service documents as references
2. Refer to this writing guide
3. Use corresponding template files as starting points
4. Contact documentation maintenance team

---

## 📞 Contact Us

- **Website:** GetFreeAI.net
- **Issue Feedback:** GitHub Issues
- **Documentation Contribution:** Pull Request
- **Email:** [To be added]

---

**Guide Version:** v2.0 (Modular Structure)  
**Last Updated:** December 2024  
**Maintainers:** GetFreeAI.net Team

