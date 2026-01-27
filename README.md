<div align="center">

# GetFreeAI

**免费 AI 服务使用指南**

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](contribute/_index.md)

[English](README.en.md) | 简体中文

[🌐 访问网站](https://getfreeai.net) | [📚 浏览文档](https://getfreeai.net/zh-cn) | [🤝 参与贡献](contribute/_index.md)

</div>

---

## 📖 项目简介

**GetFreeAI** 是一个开源的 AI 服务使用指南，系统化整理了各大 AI 服务提供商的免费服务信息，帮助用户：

- ✅ **快速发现** - 哪些 AI 服务提供免费额度
- ✅ **轻松上手** - 跟随详细步骤获取免费服务
- ✅ **避免踩坑** - 提前了解限制和注意事项
- ✅ **节省成本** - 充分利用免费资源开发应用

---

## 🌟 特色功能

### 📊 系统化整理

- **7+ AI 提供者** - OpenAI、Google、Groq、OpenRouter、DeepSeek、Cohere、Anthropic 等
- **15+ 服务文档** - Chatbot 服务和 API 服务分类清晰
- **双语支持** - 完整的中英文文档

### 🎯 实用导向

- **详细步骤** - 注册、获取密钥、使用示例一应俱全
- **代码示例** - Python、cURL 等多语言示例
- **配额对比** - 清晰的限制说明和对比表格
- **推荐组合** - 针对不同场景的最佳实践

### 🔄 持续更新

- **社区驱动** - 欢迎任何人贡献和完善
- **模板系统** - 标准化的文档模板
- **质量保证** - 详细的写作指南和检查清单

---

## 📚 内容概览

### 🏢 AI 提供者 (7个)

| 提供者 | 类型 | 主要特点 | 推荐指数 |
|--------|------|---------|---------|
| [OpenAI](providers/openai/) | 免费 + 试用 | ChatGPT 免费，$18 API 试用 | ⭐⭐⭐⭐⭐ |
| [Google AI Studio](providers/google-ai-studio/) | 永久免费 | 15M tokens/天，Gemini 系列 | ⭐⭐⭐⭐⭐ |
| [Groq](providers/groq/) | 永久免费 | 800+ tokens/s 极速 | ⭐⭐⭐⭐⭐ |
| [OpenRouter](providers/openrouter/) | 永久免费 | 47+ 免费模型 | ⭐⭐⭐⭐⭐ |
| [DeepSeek](providers/deepseek/) | 试用积分 | 中文顶尖，超低价格 | ⭐⭐⭐⭐⭐ |
| [Cohere](providers/cohere/) | 免费试用 | RAG 专家，1,000 次/月 | ⭐⭐⭐⭐⭐ |
| [Google Vertex AI](providers/google-vertex-ai/) | 试用积分 | $300，企业平台 | ⭐⭐⭐⭐ |
| [Anthropic](providers/anthropic/) | 免费 + 预付费 | 200K 上下文，AI 安全 | ⭐⭐⭐⭐⭐ |

### 💬 Chatbot 服务 (8个)

网页对话界面，无需编程：

- ChatGPT (OpenAI)
- Google AI Studio Chatbot
- Groq Playground
- OpenRouter Playground
- DeepSeek Chat
- Cohere Coral
- Vertex AI Studio
- Claude (Anthropic)
- 更多持续添加中...

### 🔌 API 服务 (7个)

开发者 API 接口：

- OpenAI API
- Google AI Studio API
- Groq API
- OpenRouter API
- DeepSeek API
- Cohere API
- Vertex AI API
- Anthropic API
- 更多持续添加中...

---

## 🗂️ 项目结构

```
getfreeai-content/
├── providers/              # AI 提供者文档
│   ├── google-ai-studio/   # 每个提供者一个目录
│   ├── groq/
│   ├── openrouter/
│   └── ...
├── services/               # 服务文档
│   ├── chatbot/            # Chatbot 服务
│   │   ├── google-ai-studio/
│   │   ├── groq/
│   │   └── ...
│   └── api/                # API 服务
│       ├── google-ai-studio/
│       ├── groq/
│       └── ...
├── templates/              # 文档模板和写作指南
│   ├── PROVIDER-TEMPLATE.md
│   ├── SERVICE-CHATBOT-TEMPLATE.md
│   ├── SERVICE-API-TEMPLATE.md
│   ├── WRITING-GUIDE.md
│   └── README.md
├── contribute/             # 贡献指南
├── about/                  # 关于页面
└── README.md               # 本文件
```

### 📐 文档架构

GetFreeAI 采用**模块化文档架构**：

- **Provider 文档** - 介绍提供者背景、注册流程、服务列表
- **Service 文档** - 详细说明每个服务的使用方法、限制、代码示例
- **双向关联** - Provider ↔ Service 相互链接，方便导航

---

## 🤝 参与贡献

我们欢迎各种形式的贡献！

### 贡献方式

- 📝 **完善文档** - 改进现有文档的内容和准确性
- ➕ **添加提供者** - 补充新的免费 AI 服务
- 🐛 **报告问题** - 发现错误或过时信息
- 💡 **提出建议** - 分享您的想法和改进方案
- 🌟 **Star 项目** - 支持我们的工作
- 📢 **传播分享** - 让更多人受益

### 快速开始贡献

1. **阅读贡献指南** - [contribute/_index.md](contribute/_index.md)
2. **查看文档模板** - [templates/](templates/)
3. **参考写作指南** - [templates/WRITING-GUIDE.md](templates/WRITING-GUIDE.md)
4. **Fork 项目并提交 PR**

### 添加新提供者

```bash
# 1. 创建 Provider 文档
mkdir -p providers/your-provider
cp templates/PROVIDER-TEMPLATE.md providers/your-provider/_index.md

# 2. 创建 Chatbot 服务文档（如有）
mkdir -p services/chatbot/your-service
cp templates/SERVICE-CHATBOT-TEMPLATE.md services/chatbot/your-service/_index.md

# 3. 创建 API 服务文档（如有）
mkdir -p services/api/your-service
cp templates/SERVICE-API-TEMPLATE.md services/api/your-service/_index.md

# 4. 编辑文档并提交 PR
```

详细步骤请查看 [贡献指南](contribute/_index.md)。

---

## 🎯 我们需要的帮助

### 急需添加的提供者

- [x] OpenAI（ChatGPT、GPT API）
- [x] Anthropic（Claude、Claude API）
- [ ] Mistral AI（Le Chat、Mistral API）
- [ ] Perplexity（Perplexity Chatbot）
- [ ] HuggingFace（各种免费模型）
- [ ] Together AI
- [ ] Replicate
- [ ] 更多...

### 待改进的内容

- [ ] 添加视频教程
- [ ] 提供者对比工具
- [ ] 配额使用计算器
- [ ] 更多代码示例
- [ ] 常见问题 FAQ

---

## 🛠️ 技术栈

- **静态网站生成器** - [Hugo](https://gohugo.io/)
- **文档主题** - [Hextra](https://imfing.github.io/hextra/)
- **文档格式** - Markdown
- **版本控制** - Git / GitHub

---

## 📊 项目统计

**当前状态**（2026年1月）：

- 🏢 提供者文档：**7 个**
- 💬 Chatbot 服务：**8 个**
- 🔌 API 服务：**7 个**
- 📝 总计文档：**22 个**
- 🌐 支持语言：**中文 + 英语**

---

## 📜 开源协议

本项目采用 [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 许可证。

这意味着您可以：

- ✅ **分享** - 以任何形式复制和传播
- ✅ **修改** - 重新混合、转换和基于本作品创作
- ✅ **商业使用** - 用于商业目的

但您必须：

- 📝 **署名** - 标明原作者和来源
- 🔗 **相同方式共享** - 使用相同的许可证

---

## 🌈 项目愿景

我们希望 GetFreeAI 能够：

1. **降低 AI 使用门槛** - 让每个人都能用上先进的 AI 服务
2. **促进 AI 普及** - 推动 AI 技术的广泛应用
3. **节省开发成本** - 帮助开发者和团队降低 AI 使用成本
4. **建设社区** - 创建一个友好的 AI 学习与分享社区
5. **持续进化** - 随着 AI 技术发展而不断改进

---

## 📞 联系我们

- **网站：** [GetFreeAI.net](https://getfreeai.net)
- **GitHub：** [github.com/exdovic/getfreeai-content](https://github.com/exdovic/getfreeai-content)
- **问题反馈：** [GitHub Issues](https://github.com/exdovic/getfreeai-content/issues)
- **邮箱：** [exdovic@gmail.com](mailto:exdovic@gmail.com)

---

## 💝 致谢

感谢所有为本项目做出贡献的朋友们！

特别感谢：

- 所有提供免费服务的 AI 公司
- 开源社区的支持和帮助
- 每一位使用和反馈的用户

---

## ⭐ Star History

如果这个项目对您有帮助，请给我们一个 Star ⭐！

---

<div align="center">

**让 AI 服务触手可及！** 🚀

[开始探索](https://getfreeai.net) | [参与贡献](contribute/_index.md) | [关于我们](about/_index.md)

Made with ❤️ by GetFreeAI.net Team

</div>

