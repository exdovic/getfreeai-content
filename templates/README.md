# GetFreeAI 文档模板库

欢迎来到 GetFreeAI.net 的文档模板库！本目录包含创建新文档所需的所有模板和指南。

---

## 🌐 多语言说明

本项目支持**简体中文**和**英语**两种语言。为中文文档添加英文翻译时：

- **中文文档**：`content/providers/google-ai-studio/_index.md`
- **英文文档**：`content/providers/google-ai-studio/_index.en.md`

翻译时保持文档结构和格式一致，只翻译内容文本和 `title`。详见 [WRITING-GUIDE.md](./WRITING-GUIDE.md) 的"多语言支持"章节。

---

## 📚 文档结构说明

从 2024 年 12 月起，GetFreeAI 采用**模块化文档结构**：

### 🏢 Provider（提供者）文档
- **位置：** `content/providers/{provider-name}/_index.md`
- **用途：** 介绍提供者的基本信息、注册流程、通用特性
- **内容：** 公司介绍、官网链接、通用注册步骤、信用卡要求等

### 🎯 Service（服务）文档
- **位置：** `content/services/{service-type}/{service-name}.md`
- **类型：**
  - `chatbot/` - 网页对话服务
  - `api/` - 开发者 API 服务
  - 未来可能增加：`ide/`、`software/` 等
- **用途：** 详细说明每个具体服务的使用方法、限制、代码示例
- **内容：** 具体模型、配额限制、代码示例、访问地址等

### 🔗 双向关联
- Provider 文档列出其所有 Services
- Service 文档链接回其 Provider
- 用户可以从任意入口找到所需信息

---

## 📋 可用模板

### 1. Provider 模板

**文件：** [PROVIDER-TEMPLATE.md](./PROVIDER-TEMPLATE.md)

**使用场景：** 添加新的 AI 服务提供者

**包含内容：**
- 提供者基本信息
- 公司背景介绍
- 通用注册流程
- 提供的服务列表（链接到 Service 文档）
- 通用的注意事项

**命名规范：** `content/providers/{provider-name}/_index.md`  
例如：`content/providers/anthropic/_index.md`

---

### 2. Chatbot 服务模板

**文件：** [SERVICE-CHATBOT-TEMPLATE.md](./SERVICE-CHATBOT-TEMPLATE.md)

**使用场景：** 添加新的网页对话服务

**包含内容：**
- Chatbot 访问地址（必须！）
- 可用功能（联网搜索、文件上传等）
- 使用限制
- 使用步骤
- 实用技巧

**命名规范：** `content/services/chatbot/{service-name}/_index.md`  
例如：`content/services/chatbot/claude/_index.md`

**注意：** 不要在目录名中重复 "chatbot" 或 "chat" 字样

---

### 3. API 服务模板

**文件：** [SERVICE-API-TEMPLATE.md](./SERVICE-API-TEMPLATE.md)

**使用场景：** 添加新的 API 服务

**包含内容：**
- API 端点地址
- 可用模型列表
- 配额和限制
- API 密钥获取步骤
- 代码示例（Python、cURL 等）
- 价格信息

**命名规范：** `content/services/api/{service-name}/_index.md`  
例如：`content/services/api/anthropic/_index.md`

**注意：** 不要在目录名中重复 "api" 字样

---

## 📖 写作指南

**文件：** [WRITING-GUIDE.md](./WRITING-GUIDE.md)

这是一份详细的写作规范文档（10,000+ 字），包含：

- 📐 文档结构规范
- ✍️ 写作风格指南
- 🎨 格式要求
- 💻 代码示例规范
- 🔍 调研方法建议
- ✅ 质量检查清单

**所有贡献者必读！**

---

## 🚀 快速开始：添加新 Provider

### Step 1: 创建 Provider 文档

```bash {filename="Bash"}
# 创建目录
mkdir -p content/providers/your-provider

# 复制模板
cp content/templates/PROVIDER-TEMPLATE.md content/providers/your-provider/_index.md

# 编辑文档
# 填写：公司介绍、官网、注册流程等
```

### Step 2: 创建 Service 文档

**如果有 Chatbot：**
```bash {filename="Bash"}
cp content/templates/SERVICE-CHATBOT-TEMPLATE.md content/services/chatbot/your-service/_index.md
# 填写：访问地址、功能、使用方法
```

**如果有 API：**
```bash {filename="Bash"}
mkdir -p content/services/api/your-service
cp content/templates/SERVICE-API-TEMPLATE.md content/services/api/your-service/_index.md
# 填写：API 端点、模型、代码示例
```

### Step 3: 建立双向链接

**在 Provider 文档中：**
```markdown {filename="Markdown"}
## 🎁 提供的服务

- [Service Name Chatbot](/services/chatbot/your-service)
- [Service Name API](/services/api/your-service-api)
```

**在 Service 文档中：**
```markdown {filename="Markdown"}
**所属提供者：** [Your Provider](/providers/your-provider)
```

### Step 4: 更新导航

编辑 `hugo.yaml`，在 `menu.sidebar` 中添加：

```yaml {filename="YAML"}
- name: Your Provider
  pageRef: /providers/your-provider
  parent: providers
  weight: 17
```

---

## 📊 现有文档

### 提供者（6 个）

| Provider | Chatbot | API | 特点 |
|----------|---------|-----|------|
| [Google AI Studio](/providers/google-ai-studio) | ✅ | ✅ | 最高免费配额 |
| [Google Vertex AI](/providers/google-vertex-ai) | ✅ | ✅ | 企业级平台 |
| [Groq](/providers/groq) | ✅ | ✅ | 最快速度 |
| [OpenRouter](/providers/openrouter) | ✅ | ✅ | 47+ 免费模型 |
| [DeepSeek](/providers/deepseek) | ✅ | ✅ | 中文优化 |
| [Cohere](/providers/cohere) | ✅ | ✅ | RAG 专家 |

### Chatbot 服务（7 个）

- Google AI Studio
- Vertex AI Studio
- Groq Playground
- OpenRouter Playground
- DeepSeek Chat
- Cohere Coral
- *(待添加更多)*

### API 服务（6 个）

- Google AI Studio API
- Vertex AI API
- Groq API
- OpenRouter API
- DeepSeek API
- Cohere API
- *(待添加更多)*

---

## 🎯 文档标准

### ✅ Provider 文档必须包含

- 提供者名称、官网、Logo（可选）
- 公司背景介绍（1-2 段）
- 注册流程（如果所有服务通用）
- 提供的服务列表（链接到 Service 文档）
- 通用的注意事项（如信用卡要求）
- 相关链接

### ✅ Service 文档必须包含

**Chatbot 服务：**
- 访问地址 URL（必须！）
- 可用功能列表
- 使用限制
- 使用步骤
- 实用技巧

**API 服务：**
- API 端点地址
- 可用模型列表
- 配额和限制（详细表格）
- API 密钥获取步骤
- 代码示例（Python + cURL）
- 价格信息

---

## 💡 写作建议

### 1. 信息分层原则

**通用信息 → Provider 文档**
- 公司介绍
- 通用注册流程
- 信用卡要求
- 官方资源链接

**差异信息 → Service 文档**
- 具体模型列表
- 服务特定的限制
- 代码示例
- 服务访问地址

### 2. 避免重复

如果多个服务共享相同的注册流程，只在 Provider 文档中写一次，Service 文档链接过去即可。

### 3. 保持简洁

- Provider 文档：2,000-3,000 字
- Chatbot 服务：1,000-1,500 字
- API 服务：2,000-3,000 字

### 4. 链接格式

**外部链接（官方资源）：**
- ✅ **推荐：** `[https://example.com](https://example.com)`
- ❌ **不推荐：** 直接写 `https://example.com`（纯 URL）
- **原因：** Markdown 链接格式会自动显示箭头图标（↗），提升用户体验
- **效果：** [https://ai.google.dev/docs](https://ai.google.dev/docs) ↗

**内部链接：**
- `[Provider 名称](/providers/provider-name)`
- `[Service 名称](/services/chatbot/service-name)`

**API 端点：**
- 如果包含占位符（如 `[REGION]`），使用代码格式：`` `https://[REGION]-api.example.com` ``
- 如果是固定 URL，可以使用链接格式：`[https://api.example.com](https://api.example.com)`

### 5. 用户视角

**Provider 文档回答：**
- 这是谁？
- 他们提供什么？
- 如何开始？

**Service 文档回答：**
- 这个服务能做什么？
- 有什么限制？
- 如何使用？（代码）

---

## 🔍 命名规范

### Provider 目录命名

- 全小写
- 使用连字符分隔
- 使用官方英文名称

```
✅ google-ai-studio
✅ anthropic
✅ mistral-ai
❌ GoogleAIStudio
❌ google_ai_studio
❌ Google-AI-Studio
```

### Service 目录命名

**Chatbot 服务目录：**
```
✅ claude/         (简洁)
✅ gemini/         (简洁)
✅ deepseek/       (简洁)
❌ claude-chat/    (不要重复 "chat")
❌ claude-chatbot/ (不要重复 "chatbot")
```

**API 服务目录：**
```
✅ anthropic/      (简洁)
✅ openai/         (简洁)
✅ cohere/         (简洁)
❌ anthropic-api/  (不要重复 "api")
❌ openai-api/     (不要重复 "api")
```

**说明：**
- 每个服务是一个目录，包含 `_index.md` 文件
- 目录名不要包含 "chat"、"chatbot"、"api" 等重复信息
- 目录名使用小写字母和连字符

---

## ✅ 质量检查清单

### 提交前检查

#### Provider 文档
- [ ] 包含提供者基本信息
- [ ] 注册流程清晰
- [ ] 列出所有服务并链接到 Service 文档
- [ ] 格式符合规范
- [ ] 所有链接有效

#### Chatbot 服务文档
- [ ] **访问地址 URL 已明确标注**
- [ ] 功能列表完整
- [ ] 限制说明清楚
- [ ] 使用步骤可操作
- [ ] 链接回 Provider 文档

#### API 服务文档
- [ ] API 端点地址正确
- [ ] 模型列表准确
- [ ] 配额限制详细
- [ ] 代码示例可运行（Python + cURL）
- [ ] 价格信息最新
- [ ] 链接回 Provider 文档

---

## 📞 获取帮助

### 参考现有文档

查看任意现有 Provider 和其 Services 的文档作为范例：
- `content/providers/google-ai-studio/`
- `content/services/chatbot/google-ai-studio/_index.md`
- `content/services/api/google-ai-studio/_index.md`

### 阅读写作指南

[WRITING-GUIDE.md](./WRITING-GUIDE.md) 包含详细的写作规范和调研方法。

### 联系我们

- **网站：** GetFreeAI.net
- **问题反馈：** GitHub Issues
- **文档贡献：** Pull Request

---

## 📜 许可证

本文档库内容采用 [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 许可证。

---

**模板版本：** v2.0（模块化结构）  
**最后更新：** 2024年12月  
**维护者：** GetFreeAI.net 团队1

