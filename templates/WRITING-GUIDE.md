---
title: "文档写作指南"
weight: 40
comments: true
---

# GetFreeAI 文档写作指南

本指南旨在帮助内容贡献者创建高质量、一致性强的 AI 服务提供者和服务文档。

---

## 📚 目录

1. [文档架构](#文档架构)
2. [Provider 文档规范](#provider-文档规范)
3. [Service 文档规范](#service-文档规范)
4. [写作规范](#写作规范)
5. [格式要求](#格式要求)
6. [代码示例规范](#代码示例规范)
7. [调研方法](#调研方法)
8. [质量检查清单](#质量检查清单)

---

## 🌐 多语言支持

本项目支持**简体中文**和**英语**两种语言。

### 多语言文件结构

使用 Hugo 的文件名后缀方式管理翻译：

- **中文文档**（默认）：`content/providers/google-ai-studio/_index.md`
- **英文文档**：`content/providers/google-ai-studio/_index.en.md`

### 添加英文翻译

为现有中文文档添加英文翻译时：

1. 复制中文文档
2. 重命名为 `_index.en.md`（或 `filename.en.md`）
3. 翻译所有内容（包括 front matter 中的 `title`）
4. 保持文档结构和格式一致

**示例：**

```markdown {filename="_index.en.md"}
---
title: Google AI Studio  # 英文标题
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

### 翻译注意事项

- ✅ **必须翻译**：标题、正文、链接文本、图片 alt 文本
- ✅ **保持一致**：URL 路径、front matter 参数（除 `title`）、代码块内容
- ✅ **保持格式**：Markdown 语法、shortcode、文档结构
- ❌ **不要翻译**：代码示例、API 端点、技术术语（如 API Key, Token）

---

## 🏗️ 文档架构

### 核心原则：模块化、双向关联

GetFreeAI 采用 **Provider-Service 分离架构**：

```
提供者（Provider）
    ├── 基本信息
    ├── 公司介绍
    ├── 通用注册流程
    └── 提供的服务列表 ──┐
                         │
                         │ (链接)
                         │
                         ↓
服务（Service）          
    ├── Chatbot 服务 ←───┘
    │   ├── 访问地址
    │   ├── 功能列表
    │   └── 使用方法
    │
    └── API 服务
        ├── API 端点
        ├── 可用模型
        ├── 配额限制
        └── 代码示例
```

### 信息分层原则

**通用信息 → Provider 文档**
- 公司背景介绍
- 所有服务通用的注册流程
- 信用卡要求说明
- 官方资源链接

**差异信息 → Service 文档**
- 服务特定的访问地址
- 具体模型列表
- 服务特定的配额限制
- 代码示例和使用方法

### 何时拆分，何时合并？

**拆分的情况：**
- Chatbot 和 API 有不同的限制
- Chatbot 和 API 使用不同的模型
- Chatbot 和 API 需要不同的注册流程

**合并的情况：**
- 如果 Provider 只有一个简单的 Chatbot（没有 API），可以考虑全部写在 Provider 文档中
- 但建议：即使合并，也保持结构清晰，方便未来拆分

---

## 🏢 Provider 文档规范

### 文档位置

```
content/providers/{provider-name}/_index.md
```

### 必需章节

#### 1. 基本信息

```markdown {filename="Markdown"}
**提供者名称：** Anthropic  
**官方网站：** https://www.anthropic.com  
**总部位置：** 美国旧金山  
**成立时间：** 2021 年
```

**要求：**
- 提供者英文全称
- 中文名称（如有）
- 官方网站 URL
- 总部位置和成立时间（增强可信度）

---

#### 2. 提供者介绍

**目的：** 让用户快速了解这家公司是谁、做什么的。

**要求：**
- 1-2 段简洁介绍（200-300 字）
- 列出 3-5 个核心特点
- 说明技术优势或独特性

**示例：**

```markdown {filename="Markdown"}
Anthropic 是由前 OpenAI 研究人员创立的 AI 安全公司，专注于开发更安全、更可控的 AI 系统。

### 核心特点

- **安全优先：** Constitutional AI 技术
- **长上下文：** 200K tokens 上下文窗口
- **代码能力：** 强大的代码生成和分析
- **企业级：** 可靠性和安全性保障
```

---

#### 3. 提供的服务

**目的：** 列出所有可用服务，并链接到详细文档。

**使用 Hugo Cards 格式：**

```markdown {filename="Markdown"}
### Chatbot 服务

{{< cards >}}
  {{< card link="/services/chatbot/claude-chat" title="Claude Chat" subtitle="网页端对话服务，支持长上下文" >}}
{{< /cards >}}

### API 服务

{{< cards >}}
  {{< card link="/services/api/anthropic-api" title="Anthropic API" subtitle="开发者 API，支持 Claude 系列模型" >}}
{{< /cards >}}
```

**要求：**
- 每个服务一张卡片
- 简短的副标题说明（1 句话）
- 正确的链接到 Service 文档

---

#### 4. 如何开始使用

**何时包含：**
- 当所有服务共享相同的注册流程时
- 当注册流程较复杂，值得单独说明时

**何时省略：**
- 当各个服务的注册流程不同时，在 Service 文档中分别说明

**包含内容：**
- 门槛要求表格
- 详细的注册步骤（使用 Steps 短代码）
- 重要提醒（如信用卡不扣费）

**注册步骤格式（必须使用 Steps 短代码）：**

```markdown {filename="Markdown"}
### 注册步骤

{{% steps %}}

#### 步骤标题 1

步骤内容说明...

#### 步骤标题 2

步骤内容说明...

#### 步骤标题 3

步骤内容说明...

{{% /steps %}}
```

**Steps 短代码使用要点：**
- ✅ 使用 `{{% steps %}}` 和 `{{% /steps %}}` 包裹所有步骤
- ✅ 步骤标题要简洁，直接说明步骤内容（如"注册账户"，而不是"步骤 1：注册账户"）
- ✅ 步骤内容可以包含段落、列表、加粗、链接等
- ✅ 可以使用 emoji 和图标增强可读性（⚠️、💡、✅等）
- ❌ 不要在步骤标题中加"步骤 1"、"第一步"等前缀（系统会自动编号）

---

#### 5. 通用注意事项

**包含：**
- ✅ 推荐做法（3-5 条）
- ⚠️ 重要提醒（3-5 条）
- 🔧 常见问题（3-5 个）

---

#### 6. 相关链接

**必需链接：**
- 官方网站
- 开发者平台
- API 文档
- 定价说明
- 状态页面

**可选链接：**
- GitHub
- Discord/Slack
- 社区论坛
- 博客

---

### Provider 文档篇幅

**推荐长度：** 2,000-3,000 字

**太短（< 1,500 字）：** 信息不足  
**太长（> 4,000 字）：** 应考虑拆分到 Service 文档

---

## 🎯 Service 文档规范

### Chatbot 服务文档

#### 文档位置

```
content/services/chatbot/{service-name}/_index.md
```

**注意：** 不要在目录名中重复 "chatbot" 或 "chat" 字样

#### 必需章节

**1. 服务概览**

```markdown {filename="Markdown"}
**服务名称：** Claude Chat  
**所属提供者：** [Anthropic](/providers/anthropic)  
**访问地址：** https://claude.ai ⬅️ 必填！  
**服务类型：** 免费增值  
**注册要求：** 需要邮箱注册
```

**⚠️ 重要：访问地址是 Chatbot 文档最关键的信息！**

---

**2. 可用功能**

列出 Chatbot 支持的所有功能：

```markdown {filename="Markdown"}
- ✅ **长上下文对话** - 支持 200K tokens
- ✅ **文件上传** - 支持 PDF、Word、图片等
- ✅ **代码执行** - 可运行 Python 代码
- ❌ **联网搜索** - 暂不支持
```

---

**3. 使用限制**

**使用表格清晰展示：**

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每日对话次数** | 约 50 次 | 免费用户 |
| **单次对话长度** | 无硬性限制 | 但会占用上下文 |
| **文件上传** | ✅ 支持 | 最大 10MB |
| **需要信用卡** | ❌ 不需要 | 完全免费 |

---

**4. 如何使用**

- 如果 Provider 已说明注册流程，链接过去
- 详细说明 Chatbot 的使用步骤
- 包含高级功能的使用方法

---

**5. 实用技巧**

- ✅ 推荐做法
- 🎯 最佳实践
- ⚠️ 注意事项

---

**Chatbot 文档篇幅：** 1,000-1,500 字

---

### API 服务文档

#### 文档位置

```
content/services/api/{service-name}/_index.md
```

**注意：** 不要在目录名中重复 "api" 字样

#### 必需章节

**1. 服务概览**

```markdown {filename="Markdown"}
**服务名称：** Anthropic API  
**所属提供者：** [Anthropic](/providers/anthropic)  
**API 端点：** `https://api.anthropic.com/v1`  
**服务类型：** 付费，提供试用积分  
**注册要求：** 需要信用卡验证
```

---

**2. 可用模型**

**使用详细表格：**

| 模型名称 | 上下文长度 | 输出长度 | 特点 | 适用场景 |
|---------|-----------|---------|------|---------|
| **claude-3-opus** | 200K | 4K | 最强大 | 复杂任务 |
| **claude-3-sonnet** | 200K | 4K | 平衡 | 日常使用 |
| **claude-3-haiku** | 200K | 4K | 最快 | 高频调用 |

---

**3. 配额和限制**

**详细的限制表格：**

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每日请求数** | 1,000 requests/day | 免费层级 |
| **每分钟请求数** | 20 requests/min | 所有层级 |
| **每日 Token 数** | 100K tokens/day | 免费层级 |
| **试用积分** | $5 | 新用户赠送 |

**⚠️ 重要限制：** 单独列出需要特别注意的限制

---

**4. 价格说明**

**区分免费和付费：**

```markdown {filename="Markdown"}
### 免费/试用

- **试用积分：** 新用户赠送 $5
- **有效期：** 30 天
- **获取方式：** 注册即送

### 付费定价

| 模型 | 输入价格 | 输出价格 |
|------|---------|---------|
| **claude-3-opus** | $15/M tokens | $75/M tokens |
| **claude-3-sonnet** | $3/M tokens | $15/M tokens |
```

---

**5. 如何使用**

- 前提条件（注册、获取 API 密钥）
- 如果 Provider 已说明，链接过去
- 如果是 API 特有流程，详细说明

---

**6. 代码示例**

**必须提供：**
- ✅ Python 示例（基本 + 流式）
- ✅ cURL 示例

**可选提供：**
- Node.js 示例
- 其他流行语言

**代码要求：**
- 可以直接运行（或注明需替换的部分）
- 包含错误处理示例
- 添加必要的注释

---

**7. 实用建议**

- ✅ 推荐做法
- 🎯 最佳实践（优化 Token、错误处理）
- ⚠️ 注意事项

---

**8. 实际应用案例**

提供 2-4 个完整的代码示例，展示实际使用场景。

---

**API 文档篇幅：** 2,000-3,000 字

---

## 📝 写作规范

### 语言和风格

1. **使用中文**
   - 主要内容用中文
   - 专业术语首次出现时提供英文
   - 代码注释可用中英文

2. **清晰直接**
   - 避免模糊表述
   - 使用具体数据
   - 一句话一个意思

3. **友好但专业**
   - 用"您"而不是"你"
   - 避免过于口语化
   - 保持客观中立

4. **面向用户**
   - 从用户角度出发
   - 解答用户真正关心的问题
   - 提供可操作的指导

---

### 术语使用

**统一术语：**
- Provider（提供者）- 不用"供应商"
- Service（服务）- 不用"产品"
- Chatbot - 不用"聊天机器人"
- API 密钥 - 不用"密钥"、"key"
- 免费配额 - 不用"额度"
- 试用积分 - 不用"免费额度"

**单位表示：**
- 美元：$10 或 10 美元
- 人民币：¥10 或 10 元
- 请求：requests/day, requests/min
- Token：tokens, M tokens（百万）, K tokens（千）

---

### 数字和数据

**具体 > 模糊：**

❌ "很高的免费配额"  
✅ "每天 15M tokens"

❌ "速度很快"  
✅ "800+ tokens/s"

❌ "支持多种模型"  
✅ "支持 47+ 免费模型"

---

### 标题编写

**好的标题：**
- ✅ "如何获取 API 密钥"（清晰、可操作）
- ✅ "免费配额和限制"（具体）
- ✅ "Python 代码示例"（明确）

**差的标题：**
- ❌ "开始"（太模糊）
- ❌ "更多信息"（不具体）
- ❌ "其他"（无意义）

---

## 🎨 格式要求

### Markdown 格式

**标题层级：**

```markdown {filename="Markdown"}
## 二级标题（主要章节）
### 三级标题（子章节）
#### 四级标题（子子章节，少用）
```

**⚠️ 重要：不要使用一级标题（`#`）！**

Hugo 会自动使用 front matter 中的 `title` 生成页面标题。如果您在 Markdown 中再写一次一级标题，会导致标题重复显示。

**正确做法：**
```markdown {filename="Markdown"}
---
title: Google AI Studio
---

## 📋 基本信息  ← 从二级标题开始
```

**错误做法：**
```markdown {filename="Markdown"}
---
title: Google AI Studio
---

# Google AI Studio  ← 不要写一级标题！会重复！

## 📋 基本信息
```

**表格格式：**
- 必须对齐
- 表头使用粗体（`**标题**`）
- 重要列可以加粗

**列表格式：**
- 有序列表用数字：`1.`, `2.`, `3.`
- 无序列表用 `-`
- 功能列表用 `- ✅` 或 `- ❌`

**强调格式：**
- 重要内容：**粗体**
- 术语首次出现：**粗体**
- 代码或命令：`行内代码`
- 不要过度使用强调

---

### Emoji 使用

**章节标题 Emoji（固定）：**
- 📋 基本信息/服务概览
- 🏢 提供者介绍
- 🎁 提供的服务/可用功能
- 🔢 配额和限制
- 🚀 如何开始/如何使用
- 💰 价格说明
- 💻 代码示例
- 🌟 核心优势
- 💡 实用建议
- 🎯 应用案例/使用场景
- 🔧 常见问题
- 🔗 相关链接
- 📝 更新日志
- 📧 支持与反馈

**内容中的 Emoji（适度）：**
- ✅ 表示"有"、"支持"、"是"
- ❌ 表示"没有"、"不支持"、"否"
- ⚠️ 表示警告和注意事项
- 🏆 表示优势或第一名
- 💡 表示提示
- 🔧 表示技术相关

---

### 链接格式

**内部链接（链接到其他文档）：**

```markdown {filename="Markdown"}
[Provider 名称](/providers/provider-name)
[Service 名称](/services/chatbot/service-name)
[API 文档](/services/api/service-name-api)
```

**外部链接（官方资源）：**

```markdown {filename="Markdown"}
[官方网站](https://www.example.com)
[API 文档](https://docs.example.com)
```

**⚠️ 重要提示：**
- 外部链接会**自动显示箭头图标（↗）**，这是 Hextra 主题的内置功能
- 请使用完整的 Markdown 链接格式：`[链接文本](URL)`
- **不要直接写纯 URL**（如 `https://example.com`），否则不会显示箭头图标
- 链接文本建议使用**完整 URL**（如 `[https://ai.google.dev/docs](https://ai.google.dev/docs)`）
- **不要手动添加箭头符号**（如 `[链接文本 ↗](URL)`），主题会自动添加

**锚点链接（文档内跳转）：**

```markdown {filename="Markdown"}
[跳转到代码示例](#代码示例)
```

---

### Front Matter 配置

**基本配置：**

所有 Provider 和 Service 文档都应该在 Front Matter 中包含以下配置：

```markdown {filename="Markdown"}
---
title: "文档标题"
type: docs              # ⬅️ 必需！启用文档布局和导航功能
weight: 10             # ⬅️ 控制排序（数字越小越靠前）
comments: true           # ⬅️ 控制控制是否开启评论
prev: /path/to/previous  # ⬅️ 可选：上一页链接
next: /path/to/next      # ⬅️ 可选：下一页链接
sidebar:
  open: true           # ⬅️ 自动展开左侧导航栏
---
```

**页面底部导航（prev/next）：**

`prev` 和 `next` 参数用于配置页面底部的"上一页/下一页"导航按钮。

**Provider 文档示例：**

```markdown {filename="Markdown"}
---
title: Groq
type: docs
weight: 2
comments: true
prev: /providers/google-ai-studio  # 上一个提供者
next: /providers/openrouter         # 下一个提供者
sidebar:
  open: true
---
```

**Chatbot 服务文档示例：**

```markdown {filename="Markdown"}
---
title: "DeepSeek Chat"
type: docs
weight: 4
comments: true
prev: /services/chatbot/openrouter   # 上一个 Chatbot 服务
next: /services/chatbot/cohere       # 下一个 Chatbot 服务
sidebar:
  open: true
---
```

**API 服务文档示例：**

```markdown {filename="Markdown"}
---
title: "Groq API"
type: docs
weight: 2
comments: true
prev: /services/api/google-ai-studio  # 上一个 API 服务
next: /services/api/openrouter         # 下一个 API 服务
sidebar:
  open: true
---
```

**配置说明：**

- **`type: docs`**：必需！这告诉 Hugo 使用文档布局模板，该模板包含页面导航功能。
- **`weight`**：控制文档在列表中的排序，数字越小越靠前。建议以 10 为间隔（10, 20, 30...），便于后续插入新文档。
- **`prev`**：指向上一篇文档的路径。会在页面底部显示"← 上一页"按钮。
- **`next`**：指向下一篇文档的路径。会在页面底部显示"下一页 →"按钮。
- **`sidebar.open: true`**：让左侧导航栏默认展开，方便用户快速浏览文档结构。

**注意事项：**

- `prev` 和 `next` 是可选的，但强烈建议配置，以提供更好的阅读体验。
- 路径必须是相对于网站根目录的绝对路径（以 `/` 开头）。
- 第一篇文档可以只配置 `next`，最后一篇文档可以只配置 `prev`。
- 如果不确定应该链接到哪篇文档，可以参考左侧导航栏中的文档顺序。

---

## 💻 代码示例规范

### Python 代码

**基本要求：**
- 使用官方 SDK（如有）
- 包含完整的导入语句
- 变量命名清晰（使用有意义的名称）
- 添加必要的注释
- 可以直接运行（或注明需要替换的部分）

**标准结构：**

```python {filename="Python"}
from openai import OpenAI

# 初始化客户端（请替换为您的 API 密钥）
client = OpenAI(
    base_url="https://api.example.com/v1",
    api_key="YOUR_API_KEY"  # ⬅️ 替换为您的密钥
)

# 发送请求
response = client.chat.completions.create(
    model="model-name",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "你好，请介绍一下自己。"}
    ],
    max_tokens=1000,
    temperature=0.7
)

# 打印响应
print(response.choices[0].message.content)

# 查看 Token 使用情况
print(f"\n使用 Tokens: {response.usage.total_tokens}")
```

**必须包含：**
1. 基本调用示例
2. 流式输出示例（对于 API）
3. 错误处理示例

---

### cURL 示例

**标准格式：**

```bash {filename="Bash"}
curl https://api.example.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "model-name",
    "messages": [
      {"role": "system", "content": "You are a helpful assistant."},
      {"role": "user", "content": "你好，请介绍一下自己。"}
    ],
    "max_tokens": 1000,
    "temperature": 0.7
  }'
```

**要求：**
- 使用反斜杠换行
- 清晰的缩进（2 或 4 空格）
- 包含所有必需的 headers
- JSON 格式正确

---

### Node.js 示例（可选）

如果目标用户包含 JavaScript 开发者，提供 Node.js 示例：

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
      { role: 'user', content: '你好' }
    ],
  });

  console.log(completion.choices[0].message.content);
}

main();
```

---

## 🔍 调研方法

### 信息来源优先级

1. **官方文档**（最优先，最可靠）
   - 官网
   - API 文档
   - 定价页面
   - 官方博客
   - 官方 Changelog

2. **实际测试**（强烈推荐）
   - 亲自注册和使用
   - 测试限制和配额
   - 验证代码示例
   - 记录遇到的问题

3. **社区资源**（验证真实用户体验）
   - GitHub Issues
   - Reddit
   - Stack Overflow
   - Discord/Slack 社区
   - 用户评论

4. **第三方对比**（参考，但需验证）
   - 技术博客
   - 评测文章
   - YouTube 视频
   - 但要验证时效性！

---

### 必须核实的信息

#### 对于所有文档

1. **官方链接**
   - 官网 URL
   - Chatbot 访问地址
   - API 端点地址
   - 文档链接

2. **注册要求**
   - 是否需要邮箱/手机
   - 是否需要信用卡
   - 是否需要实名认证
   - 是否会扣费

3. **时效性**
   - 政策是否有变化
   - 价格是否有调整
   - 功能是否已更新

---

#### 对于 Chatbot 文档

1. **访问地址**（最重要！）
2. **可用功能**（联网、文件上传、代码执行等）
3. **使用限制**（每日次数、单次长度等）

---

#### 对于 API 文档

1. **配额和限制**
   - 每日/每分钟请求数
   - Token 限制
   - 是否真的免费

2. **可用模型**
   - 模型名称（精确）
   - 上下文长度
   - 是否支持流式输出

3. **价格信息**
   - 免费配额
   - 试用积分
   - 付费价格（输入/输出分别）

---

### 调研步骤建议

**Provider 文档调研：**
1. 阅读官网和 About 页面 - 1 小时
2. 查看定价和服务页面 - 30 分钟
3. 实际注册测试 - 1 小时
4. 撰写文档 - 2 小时
**总计：约 4-5 小时**

---

**Chatbot 服务文档调研：**
1. 访问 Chatbot 并测试功能 - 1 小时
2. 测试各种功能限制 - 1 小时
3. 查看帮助文档 - 30 分钟
4. 撰写文档 - 1.5 小时
**总计：约 4 小时**

---

**API 服务文档调研：**
1. 阅读 API 文档 - 2 小时
2. 实际注册并获取 API 密钥 - 1 小时
3. 运行代码示例并测试 - 2 小时
4. 查看社区反馈 - 1 小时
5. 撰写文档 - 3 小时
**总计：约 9 小时**

---

## ✅ 质量检查清单

### Provider 文档检查

- [ ] 基本信息完整（名称、官网、位置、时间）
- [ ] 公司介绍清晰（1-2 段）
- [ ] 列出所有提供的服务
- [ ] 每个服务都正确链接到 Service 文档
- [ ] 如果有通用注册流程，已详细说明
- [ ] 相关链接都有效
- [ ] 格式符合规范
- [ ] 篇幅适中（2,000-3,000 字）

---

### Chatbot 服务文档检查

- [ ] **访问地址已明确标注**（最重要！）
- [ ] 所属 Provider 已链接
- [ ] 功能列表完整（联网、文件、代码等）
- [ ] 使用限制清楚（表格形式）
- [ ] 使用步骤可操作
- [ ] 实用技巧有价值
- [ ] 链接回 Provider 文档
- [ ] 格式符合规范
- [ ] 篇幅适中（1,000-1,500 字）

---

### API 服务文档检查

- [ ] API 端点地址正确
- [ ] 所属 Provider 已链接
- [ ] 模型列表准确（名称、上下文、特点）
- [ ] 配额限制详细（表格形式）
- [ ] 价格信息最新（免费 + 付费）
- [ ] Python 代码示例可运行
- [ ] cURL 示例正确
- [ ] 包含错误处理示例
- [ ] 实际应用案例完整
- [ ] 链接回 Provider 文档
- [ ] 格式符合规范
- [ ] 篇幅适中（2,000-3,000 字）

---

### 通用检查

#### 内容完整性
- [ ] 所有必需章节都已包含
- [ ] 没有空白章节或占位符
- [ ] 所有"[待填写]"都已替换

#### 格式规范
- [ ] Markdown 格式正确
- [ ] 表格对齐
- [ ] Emoji 使用恰当
- [ ] 代码块有语言标注
- [ ] 标题层级合理

#### 准确性
- [ ] 所有数据都已核实
- [ ] 价格信息是最新的
- [ ] 限制说明准确
- [ ] 没有过时信息
- [ ] 所有链接都能访问

#### 可读性
- [ ] 语言清晰流畅
- [ ] 无错别字
- [ ] 术语使用统一
- [ ] 逻辑连贯
- [ ] 适合目标读者

#### 实用性
- [ ] 步骤可以实际操作
- [ ] 代码可以直接使用
- [ ] 注意事项有价值
- [ ] FAQ 解答实际问题
- [ ] 建议具有可操作性

---

## 📋 提交前最终检查

```markdown {filename="Markdown"}
Provider 文档：
- [ ] 我已使用 PROVIDER-TEMPLATE.md
- [ ] 所有服务都已链接
- [ ] 注册流程清晰（或链接到 Service）
- [ ] 相关链接都有效
- [ ] 格式符合规范

Chatbot 文档：
- [ ] 我已使用 SERVICE-CHATBOT-TEMPLATE.md
- [ ] **访问地址已明确标注**
- [ ] 已链接回 Provider 文档
- [ ] 功能和限制清楚
- [ ] 格式符合规范

API 文档：
- [ ] 我已使用 SERVICE-API-TEMPLATE.md
- [ ] 代码示例已验证可运行
- [ ] 配额和价格信息准确
- [ ] 已链接回 Provider 文档
- [ ] 格式符合规范

所有文档：
- [ ] 我已实际测试过服务
- [ ] 所有信息都已核实准确
- [ ] 文档已自我审阅至少一遍
- [ ] 最后更新时间已填写
```

---

## 🎓 学习资源

**参考现有文档：**

**Provider 文档：**
- `content/providers/google-ai-studio/_index.md`
- `content/providers/groq/_index.md`
- `content/providers/openrouter/_index.md`

**Chatbot 文档：**
- `content/services/chatbot/google-ai-studio/_index.md`
- `content/services/chatbot/deepseek/_index.md`

**API 文档：**
- `content/services/api/google-ai-studio/_index.md`
- `content/services/api/groq/_index.md`

**Markdown 参考：**
- [Markdown 基本语法](https://www.markdownguide.org/basic-syntax/)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)

**Hugo 参考：**
- [Hugo 文档](https://gohugo.io/documentation/)
- [Hextra 主题文档](https://imfing.github.io/hextra/)

---

## 💬 获取帮助

如有任何问题：

1. 查阅现有的 Provider 和 Service 文档作为参考
2. 参考本写作指南
3. 使用对应的模板文件作为起点
4. 联系文档维护团队

---

## 📞 联系我们

- **网站：** GetFreeAI.net
- **问题反馈：** GitHub Issues
- **文档贡献：** Pull Request
- **邮箱：** [待添加]

---

**指南版本：** v2.0（模块化结构）  
**最后更新：** 2024年12月  
**维护者：** GetFreeAI.net 团队

