<div align="center">

# GetFreeAI

**Free AI Services Guide**

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](contribute/_index.en.md)

English | [简体中文](README.md)

[🌐 Visit Website](https://getfreeai.net) | [📚 Browse Docs](https://getfreeai.net/en) | [🤝 Contribute](contribute/_index.en.md)

</div>

---

## 📖 About

**GetFreeAI** is an open-source guide for free AI services, systematically organizing information about free services from major AI providers to help users:

- ✅ **Quick Discovery** - Which AI services offer free quotas
- ✅ **Easy Start** - Follow detailed steps to access free services
- ✅ **Avoid Pitfalls** - Learn about limitations and precautions upfront
- ✅ **Save Costs** - Make full use of free resources for development

---

## 🌟 Features

### 📊 Systematic Organization

- **7+ AI Providers** - OpenAI, Google, Groq, OpenRouter, DeepSeek, Cohere, Anthropic, etc.
- **15+ Service Docs** - Clear categorization of Chatbot and API services
- **Bilingual Support** - Complete Chinese and English documentation

### 🎯 Practical Focus

- **Detailed Steps** - Registration, API key acquisition, usage examples
- **Code Examples** - Multi-language examples including Python, cURL
- **Quota Comparison** - Clear limitation descriptions and comparison tables
- **Recommended Combinations** - Best practices for different scenarios

### 🔄 Continuous Updates

- **Community-Driven** - Contributions welcome from everyone
- **Template System** - Standardized documentation templates
- **Quality Assurance** - Detailed writing guides and checklists

---

## 📚 Content Overview

### 🏢 AI Providers (7)

| Provider | Type | Key Features | Rating |
|----------|------|-------------|---------|
| [OpenAI](providers/openai/) | Free + Trial | ChatGPT free, $18 API trial | ⭐⭐⭐⭐⭐ |
| [Google AI Studio](providers/google-ai-studio/) | Permanent Free | 15M tokens/day, Gemini series | ⭐⭐⭐⭐⭐ |
| [Groq](providers/groq/) | Permanent Free | 800+ tokens/s speed | ⭐⭐⭐⭐⭐ |
| [OpenRouter](providers/openrouter/) | Permanent Free | 47+ free models | ⭐⭐⭐⭐⭐ |
| [DeepSeek](providers/deepseek/) | Trial Credits | Top Chinese, ultra-low price | ⭐⭐⭐⭐⭐ |
| [Cohere](providers/cohere/) | Free Trial | RAG expert, 1,000 calls/month | ⭐⭐⭐⭐⭐ |
| [Google Vertex AI](providers/google-vertex-ai/) | Trial Credits | $300, enterprise platform | ⭐⭐⭐⭐ |
| [Anthropic](providers/anthropic/) | Free + Prepaid | 200K context, AI safety | ⭐⭐⭐⭐⭐ |

### 💬 Chatbot Services (8)

Web conversational interfaces, no coding required:

- ChatGPT (OpenAI)
- Google AI Studio Chatbot
- Groq Playground
- OpenRouter Playground
- DeepSeek Chat
- Cohere Coral
- Vertex AI Studio
- Claude (Anthropic)
- More coming soon...

### 🔌 API Services (7)

Developer API interfaces:

- OpenAI API
- Google AI Studio API
- Groq API
- OpenRouter API
- DeepSeek API
- Cohere API
- Vertex AI API
- Anthropic API
- More coming soon...

---

## 🗂️ Project Structure

```
getfreeai-content/
├── providers/              # AI provider documents
│   ├── google-ai-studio/   # One directory per provider
│   ├── groq/
│   ├── openrouter/
│   └── ...
├── services/               # Service documents
│   ├── chatbot/            # Chatbot services
│   │   ├── google-ai-studio/
│   │   ├── groq/
│   │   └── ...
│   └── api/                # API services
│       ├── google-ai-studio/
│       ├── groq/
│       └── ...
├── templates/              # Document templates and writing guides
│   ├── PROVIDER-TEMPLATE.md
│   ├── SERVICE-CHATBOT-TEMPLATE.md
│   ├── SERVICE-API-TEMPLATE.md
│   ├── WRITING-GUIDE.md
│   └── README.md
├── contribute/             # Contribution guide
├── about/                  # About page
└── README.md               # This file
```

### 📐 Documentation Architecture

GetFreeAI uses a **modular documentation architecture**:

- **Provider Docs** - Introduce provider background, registration process, service list
- **Service Docs** - Detail usage methods, limitations, code examples for each service
- **Bidirectional Linking** - Provider ↔ Service mutual linking for easy navigation

---

## 🤝 Contributing

We welcome all forms of contribution!

### Ways to Contribute

- 📝 **Improve Documentation** - Enhance content and accuracy of existing docs
- ➕ **Add Providers** - Add new free AI services
- 🐛 **Report Issues** - Discover errors or outdated information
- 💡 **Make Suggestions** - Share your ideas and improvement plans
- 🌟 **Star the Project** - Support our work
- 📢 **Spread the Word** - Let more people benefit

### Quick Start Contributing

1. **Read Contribution Guide** - [contribute/_index.en.md](contribute/_index.en.md)
2. **Check Document Templates** - [templates/](templates/)
3. **Reference Writing Guide** - [templates/WRITING-GUIDE.en.md](templates/WRITING-GUIDE.en.md)
4. **Fork the project and submit a PR**

### Adding a New Provider

```bash
# 1. Create Provider document
mkdir -p providers/your-provider
cp templates/PROVIDER-TEMPLATE.en.md providers/your-provider/_index.en.md

# 2. Create Chatbot service document (if applicable)
mkdir -p services/chatbot/your-service
cp templates/SERVICE-CHATBOT-TEMPLATE.en.md services/chatbot/your-service/_index.en.md

# 3. Create API service document (if applicable)
mkdir -p services/api/your-service
cp templates/SERVICE-API-TEMPLATE.en.md services/api/your-service/_index.en.md

# 4. Edit documents and submit PR
```

See [Contribution Guide](contribute/_index.en.md) for detailed steps.

---

## 🎯 Help Needed

### Providers Urgently Needed

- [x] OpenAI (ChatGPT, GPT API)
- [x] Anthropic (Claude, Claude API)
- [ ] Mistral AI (Le Chat, Mistral API)
- [ ] Perplexity (Perplexity Chatbot)
- [ ] HuggingFace (Various free models)
- [ ] Together AI
- [ ] Replicate
- [ ] More...

### Content to Improve

- [ ] Add video tutorials
- [ ] Provider comparison tool
- [ ] Quota usage calculator
- [ ] More code examples
- [ ] FAQ section

---

## 🛠️ Tech Stack

- **Static Site Generator** - [Hugo](https://gohugo.io/)
- **Documentation Theme** - [Hextra](https://imfing.github.io/hextra/)
- **Document Format** - Markdown
- **Version Control** - Git / GitHub
- **Deployment** - [To be configured]

---

## 📊 Project Statistics

**Current Status** (January 2026):

- 🏢 Provider Docs: **7**
- 💬 Chatbot Services: **8**
- 🔌 API Services: **7**
- 📝 Total Documents: **22**
- 🌐 Languages Supported: **Chinese + English**

---

## 📜 License

This project uses the [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) license.

This means you can:

- ✅ **Share** - Copy and distribute in any format
- ✅ **Adapt** - Remix, transform, and build upon this work
- ✅ **Commercial Use** - Use for commercial purposes

But you must:

- 📝 **Attribution** - Give appropriate credit and indicate the source
- 🔗 **ShareAlike** - Use the same license

---

## 🌈 Vision

We hope GetFreeAI can:

1. **Lower AI Barriers** - Enable everyone to use advanced AI services
2. **Promote AI Adoption** - Facilitate widespread application of AI technology
3. **Reduce Development Costs** - Help developers and teams lower AI usage costs
4. **Build Community** - Create a friendly AI learning and sharing community
5. **Continuous Evolution** - Keep improving with AI technology development

---

## 📞 Contact Us

- **Website:** [GetFreeAI.net](https://getfreeai.net)
- **GitHub:** [github.com/exdovic/getfreeai-content](https://github.com/exdovic/getfreeai-content)
- **Issue Tracker:** [GitHub Issues](https://github.com/exdovic/getfreeai-content/issues)
- **Email:** [exdovic@gmail.com](mailto:exdovic@gmail.com)

---

## 💝 Acknowledgments

Thanks to all friends who have contributed to this project!

Special thanks to:

- All AI companies providing free services
- Open source community support and help
- Every user who uses and provides feedback

---

## ⭐ Star History

If this project helps you, please give us a Star ⭐!

---

<div align="center">

**Making AI Services Accessible!** 🚀

[Start Exploring](https://getfreeai.net) | [Contribute](contribute/_index.en.md) | [About Us](about/_index.en.md)

Made with ❤️ by GetFreeAI.net Team

</div>

