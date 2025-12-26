---
title: 贡献指南
weight: 4
comments: true
---

感谢您对 GetFreeAI 项目的关注！我们欢迎各种形式的贡献，让这个项目变得更好。

---

## 🎯 贡献方式

{{< cards >}}
  {{< card title="完善文档" icon="pencil" subtitle="改进现有文档的内容和准确性" >}}
  {{< card title="添加提供者" icon="plus" subtitle="补充新的免费 AI 服务" >}}
  {{< card title="报告问题" icon="exclamation" subtitle="发现错误或过时信息" >}}
  {{< card title="提出建议" icon="light-bulb" subtitle="分享您的想法和改进方案" >}}
{{< /cards >}}

---

## 📚 文档架构说明

GetFreeAI 采用**模块化文档架构**，将提供者（Provider）和服务（Service）分离：

### 🏢 Provider（提供者）文档

**位置：** `providers/{provider-name}/_index.md`

**内容：**
- 提供者基本信息和介绍
- 公司背景和技术优势
- 通用的注册流程（如所有服务共享）
- 提供的服务列表（链接到 Service 文档）

**示例：**
- `providers/google-ai-studio/_index.md`
- `providers/groq/_index.md`

---

### 🎯 Service（服务）文档

**Chatbot 服务位置：** `services/chatbot/{service-name}/_index.md`

**注意：** 目录名不要重复 "chatbot" 或 "chat" 字样

**内容：**
- **访问地址**（必须！）
- 可用功能（联网、文件上传等）
- 使用限制
- 使用步骤和技巧

**示例：**
- `services/chatbot/google-ai-studio/_index.md`
- `services/chatbot/deepseek/_index.md`

---

**API 服务位置：** `services/api/{service-name}/_index.md`

**注意：** 目录名不要重复 "api" 字样

**内容：**
- API 端点地址
- 可用模型列表
- 配额和限制（详细表格）
- 代码示例（Python、cURL 等）
- 价格信息

**示例：**
- `services/api/google-ai-studio/_index.md`
- `services/api/groq/_index.md`

---

### 🔗 双向关联

- Provider 文档链接到其所有 Service
- Service 文档链接回其 Provider

**示例：**

```markdown {filename="Markdown"}
# 在 Provider 文档中
{{< card link="/services/chatbot/service-name" title="Service Name" >}}

# 在 Service 文档中
**所属提供者：** [Provider 名称](/providers/provider-name)
```

---

## 📝 如何添加新的提供者

### 第一步：准备工作

**1. 阅读文档规范**

📖 **必读：** [写作指南](/templates/writing-guide)

这份详细指南包含：
- 文档架构说明
- Provider 文档规范
- Service 文档规范
- 写作风格和格式要求
- 代码示例规范
- 调研方法建议

**2. 查看文档模板**

我们提供三种模板：
- 📋 [Provider 模板](https://github.com/exdovic/getfreeai-content/blob/main/templates/PROVIDER-TEMPLATE.md)
- 💬 [Chatbot 服务模板](https://github.com/exdovic/getfreeai-content/blob/main/templates/SERVICE-CHATBOT-TEMPLATE.md)
- 🔌 [API 服务模板](https://github.com/exdovic/getfreeai-content/blob/main/templates/SERVICE-API-TEMPLATE.md)

**3. 参考现有文档**

查看任意完整的 Provider 及其 Services：
- Provider: `/providers/google-ai-studio/`
- Chatbot: `/services/chatbot/google-ai-studio/`
- API: `/services/api/google-ai-studio/`

---

### 第二步：调研信息

在开始编写前，请确保您已经：

#### 对于 Provider 文档

✅ **访问官方网站** - 了解公司背景和服务  
✅ **查看定价页面** - 了解免费和付费服务  
✅ **阅读官方文档** - 理解整体架构  
✅ **实际注册账户** - 验证注册流程

#### 对于 Chatbot 服务文档

✅ **访问 Chatbot 界面** - 确认访问地址  
✅ **测试所有功能** - 验证联网、文件上传、代码执行等  
✅ **测试使用限制** - 确认每日次数、长度限制  
✅ **记录特殊功能** - 记录独特或有用的功能

#### 对于 API 服务文档

✅ **阅读 API 文档** - 了解端点、参数、响应格式  
✅ **获取 API 密钥** - 实际注册并获取密钥  
✅ **运行代码示例** - 确保代码可以运行  
✅ **测试配额限制** - 验证请求限制、Token 限制  
✅ **核实价格信息** - 确认最新的定价

---

### 第三步：创建文档

#### 创建 Provider 文档

```bash {filename="Bash"}
# 1. 创建 Provider 目录
mkdir -p providers/your-provider

# 2. 复制 Provider 模板
cp templates/PROVIDER-TEMPLATE.md \
   providers/your-provider/_index.md

# 3. 编辑文档
# 填写：基本信息、公司介绍、注册流程、服务列表
```

#### 创建 Chatbot 服务文档（如有）

```bash {filename="Bash"}
# 创建目录并复制 Chatbot 模板
mkdir -p services/chatbot/your-service
cp templates/SERVICE-CHATBOT-TEMPLATE.md \
   services/chatbot/your-service/_index.md

# 编辑文档
# 填写：访问地址、功能、限制、使用方法
```

#### 创建 API 服务文档（如有）

```bash {filename="Bash"}
# 创建目录并复制 API 模板
mkdir -p services/api/your-service
cp templates/SERVICE-API-TEMPLATE.md \
   services/api/your-service/_index.md

# 编辑文档
# 填写：API 端点、模型、配额、代码示例
```

---

### 第四步：建立双向链接

**在 Provider 文档中添加服务卡片：**

```markdown {filename="Markdown"}
## 🎁 提供的服务

### Chatbot 服务

{{< cards >}}
  {{< card link="/services/chatbot/your-service" title="Your Service" subtitle="简短描述" >}}
{{< /cards >}}

### API 服务

{{< cards >}}
  {{< card link="/services/api/your-service-api" title="Your Service API" subtitle="简短描述" >}}
{{< /cards >}}
```

**在 Service 文档中链接回 Provider：**

```markdown {filename="Markdown"}
**所属提供者：** [Your Provider](/providers/your-provider)
```

---

### 第五步：更新导航

编辑 `hugo.yaml`，在 `menu.sidebar` 中添加：

```yaml {filename="YAML"}
- name: Your Provider
  pageRef: /providers/your-provider
  parent: providers
  weight: 17  # 使用下一个可用的编号
```

---

### 第六步：质量检查

使用我们的检查清单：

#### Provider 文档检查

- [ ] 基本信息完整（名称、官网、位置、时间）
- [ ] 公司介绍清晰（1-2 段）
- [ ] 列出所有提供的服务
- [ ] 每个服务都正确链接到 Service 文档
- [ ] 相关链接都有效
- [ ] 格式符合规范

#### Chatbot 服务文档检查

- [ ] **访问地址已明确标注**（最重要！）
- [ ] 所属 Provider 已链接
- [ ] 功能列表完整
- [ ] 使用限制清楚（表格形式）
- [ ] 使用步骤可操作
- [ ] 格式符合规范

#### API 服务文档检查

- [ ] API 端点地址正确
- [ ] 所属 Provider 已链接
- [ ] 模型列表准确
- [ ] 配额限制详细（表格形式）
- [ ] Python 代码示例可运行
- [ ] cURL 示例正确
- [ ] 价格信息最新
- [ ] 格式符合规范

---

## 📋 提交流程

### 1. Fork 项目

```bash {filename="Bash"}
# Fork 项目到您的 GitHub 账号
# 然后克隆到本地
git clone https://github.com/exdovic/getfreeai-content.git
cd getfreeai-content
```

### 2. 创建分支

```bash {filename="Bash"}
# 创建新分支
git checkout -b add-provider-name

# 或修复问题
git checkout -b fix-issue-description
```

### 3. 添加文档

```bash {filename="Bash"}
# 添加 Provider 文档
git add providers/your-provider/_index.md

# 添加 Chatbot 服务文档（如有）
git add services/chatbot/your-service/

# 添加 API 服务文档（如有）
git add services/api/your-service/

# 更新导航配置（如需要）
git add hugo.yaml
```

### 4. 提交更改

```bash {filename="Bash"}
# 提交
git commit -m "docs: 添加 Provider Name 及其服务文档"

# 推送到您的仓库
git push origin add-provider-name
```

### 5. 创建 Pull Request

1. 访问您 fork 的仓库
2. 点击 "New Pull Request"
3. 填写 PR 描述：

**PR 标题示例：**
```
docs: 添加 Anthropic (Claude) 提供者和服务文档
```

**PR 描述模板：**
```markdown {filename="Markdown"}
## 添加内容

- [ ] Provider 文档：Anthropic
- [ ] Chatbot 服务：Claude Chat
- [ ] API 服务：Anthropic API

## 已完成检查

- [ ] 所有信息已核实
- [ ] 代码示例已测试
- [ ] 访问地址已确认
- [ ] 格式符合规范
- [ ] 已建立双向链接
- [ ] 已更新导航菜单

## 其他说明

[如有其他需要说明的内容]
```

---

## 🎨 命名规范

### Provider 目录命名

- 全小写
- 使用连字符 `-` 分隔
- 使用官方英文名称

```
✅ google-ai-studio
✅ anthropic
✅ mistral-ai
❌ GoogleAIStudio
❌ google_ai_studio
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

## 💡 内容建议

### 写作风格

- **清晰直接** - 避免模糊表述，使用具体数据
- **用户视角** - 从用户需求出发，解决实际问题
- **友好专业** - 保持礼貌和专业，用"您"而不是"你"
- **实用为主** - 提供可操作的指导，而非理论

### 示例质量

- **代码可运行** - 示例必须可以直接运行
- **包含注释** - 添加必要的注释说明
- **标注替换部分** - 明确标注需要替换的内容（如 API 密钥）
- **多语言支持** - 至少提供 Python 和 cURL 示例

### 注意事项

- **标注限制** - 清楚说明所有限制和警告
- **说明问题** - 提及可能遇到的问题
- **提供方案** - 给出解决方案或替代建议
- **避免错误** - 帮助用户避免常见错误

---

## 🔍 文档审查要点

### 内容完整性

- [ ] 所有必需章节都已包含
- [ ] Chatbot URL 已明确标注（如有）
- [ ] 限制和配额信息完整
- [ ] 注册步骤详细可操作
- [ ] 代码示例完整且可运行
- [ ] 所有链接都有效
- [ ] 已建立 Provider ↔ Service 双向链接

### 格式规范

- [ ] Markdown 格式正确
- [ ] 表格对齐整齐
- [ ] Emoji 使用恰当
- [ ] 代码块有语言标注（如 `` ```python {filename="Python"}` ``）
- [ ] **外部链接使用 Markdown 格式**（如 `[URL](URL)`），不要直接写纯 URL。Markdown 格式的外部链接会自动显示箭头图标（↗）
- [ ] 标题层级合理（Provider 用 #，章节用 ##）
- [ ] **Front Matter 配置正确**：
  - [ ] 包含 `type: docs`（必需！启用文档布局和导航功能）
  - [ ] 配置 `weight` 字段（控制排序）
  - [ ] 配置 `prev` 和 `next`（启用页面底部的前后导航按钮）
  - [ ] 包含 `sidebar.open: true`（自动展开左侧导航栏）

### 准确性验证

- [ ] 所有数据都已核实
- [ ] 价格信息是最新的
- [ ] 限制说明准确
- [ ] 没有过时信息
- [ ] 链接都能访问
- [ ] 代码示例已测试

---

## 🐛 报告问题

发现错误或过时信息？请帮助我们改进！

### 通过 Issue 报告

1. 访问项目的 Issues 页面
2. 点击 "New Issue"
3. 选择适当的模板：
   - 📝 文档错误
   - ❌ 过时信息
   - 💡 改进建议
   - 🆕 新增提供者请求

### 问题描述要点

**好的 Issue 标题：**
```
✅ [Google AI Studio] API 配额信息已过时
✅ [DeepSeek] Chatbot 访问地址失效
✅ [Groq] Python 代码示例无法运行
❌ 有个问题（太模糊）
```

**Issue 描述应包含：**
- **清晰的标题** - 简要描述问题
- **详细的描述** - 具体说明问题所在
- **截图或链接** - 如果适用
- **建议的修复** - 如果您知道如何修复
- **受影响的文档** - 明确指出哪个文档

---

## 🌟 最佳贡献者

我们会在这里展示对项目有突出贡献的朋友！

**贡献类型：**
- 🏆 **添加新 Provider** - 完整的 Provider + Services 文档
- 📝 **完善现有文档** - 重大改进和更新
- 🐛 **修复问题** - 修复错误和过时信息
- 💡 **提出建议** - 有价值的改进建议

---

## 📧 联系我们

如果您有任何问题或建议：

- **GitHub Issues** - 提出问题或建议
- **Pull Request** - 直接提交改进
- **Email** - [待添加]
- **Discord** - [待添加]

---

## 📜 行为准则

参与本项目即表示您同意遵守我们的行为准则：

- **尊重他人** - 友好、包容、尊重每一位贡献者
- **建设性讨论** - 理性、客观、有益的交流
- **专业态度** - 负责、认真、专业的工作方式
- **开源精神** - 分享、协作、共同进步

**我们不容忍：**
- 骚扰、歧视、攻击性言论
- 垃圾信息、广告、恶意内容
- 抄袭、盗用他人成果
- 违反开源协议的行为

---

## 🎓 学习资源

### 参考现有文档

查看这些优秀示例：

**完整的 Provider 示例：**
- [Google AI Studio](/providers/google-ai-studio) - 高免费配额
- [Groq](/providers/groq) - 技术优势说明
- [OpenRouter](/providers/openrouter) - 多模型聚合
- [DeepSeek](/providers/deepseek) - 中文优化服务

**Chatbot 服务示例：**
- [Google AI Studio Chatbot](/services/chatbot/google-ai-studio/)
- [DeepSeek Chat](/services/chatbot/deepseek/)
- [Cohere Coral](/services/chatbot/cohere/)

**API 服务示例：**
- [Google AI Studio API](/services/api/google-ai-studio/)
- [Groq API](/services/api/groq/)
- [OpenRouter API](/services/api/openrouter/)

### 文档和工具

- **[写作指南](/templates/writing-guide)** - 详细的写作规范
- **[模板库](/templates)** - Provider 和 Service 模板
- [Markdown 语法](https://www.markdownguide.org/) - Markdown 基础
- [Hugo 文档](https://gohugo.io/documentation/) - 静态站点生成器
- [Hextra 主题](https://imfing.github.io/hextra/) - 文档主题

---

## 📊 贡献统计

**当前状态：**
- 🏢 提供者文档：6 个
- 💬 Chatbot 服务：7 个
- 🔌 API 服务：6 个
- 📝 总计文档：19 个

**我们需要您帮助添加：**
- OpenAI（ChatGPT、GPT API）
- Anthropic（Claude、Claude API）
- Mistral AI（Le Chat、Mistral API）
- Perplexity（Perplexity Chatbot）
- HuggingFace（各种免费模型）
- ...更多提供者

---

<div align="center">

**感谢您的贡献！** 🙏

让我们一起让 AI 服务触手可及！

[开始贡献](https://github.com/exdovic/getfreeai-content) · [查看模板](/templates) · [阅读指南](/templates/writing-guide)

</div>

