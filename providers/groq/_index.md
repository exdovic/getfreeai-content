---
title: "Groq - 超高速免费 AI 使用指南"
description: "Groq 提供业界最快推理速度 800+ tokens/秒！每日 14,400 次免费请求，支持 Llama 3.3、Mixtral、Gemma 2 等模型。提供 Chatbot 和 API 服务，极速响应、OpenAI 兼容，详细教程。"
keywords:
  - Groq
  - Groq API
  - 极速AI推理
  - 800 tokens每秒
  - Llama 3.3
  - 免费AI API
  - 高速LLM
  - OpenAI兼容
  - 14400次请求
  - 免费推理API
image: /images/providers/groq-og.png
type: docs
weight: 2
comments: true
prev: /providers/google-ai-studio
next: /providers/openrouter
sidebar:
  open: true
---

## 🏢 提供者信息

**提供者名称：** Groq  
**官方网站：** https://groq.com  
**开发者控制台：** https://console.groq.com  
**类型：** 免费服务（永久免费，有使用限制）

---

## 📋 产品简介

Groq 是一家提供超高速 AI 推理服务的公司，基于其自研的 **LPU（Language Processing Unit）芯片**技术，提供业界最快的 AI 推理速度。

**核心特点：**
- ⚡ **业界最快推理速度** - 800+ tokens/s
- 🔧 **LPU 芯片驱动** - 专为语言模型优化的硬件
- 🎁 **超高免费配额** - 14,400 请求/天
- 🔄 **OpenAI API 兼容** - 无缝切换现有代码
- 🚀 **实时响应** - 极低延迟的对话体验

**推荐指数：** ⭐⭐⭐⭐⭐ （速度王者！）

---

## 🔐 注册和账号

### 注册要求

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 邮箱或 Google/GitHub 账户 |
| 邮箱验证 | ✅ 必需 | 需要验证邮箱 |
| 手机验证 | ❌ 不需要 | 通常不需要 |
| 信用卡绑定 | ✅ 必需 | 用于身份验证，不会扣费 |

### 注册步骤

{{% steps %}}

#### 注册账户

访问 [https://console.groq.com](https://console.groq.com)，点击 **"Sign Up"** 注册按钮。选择注册方式：
- 使用 Google 账户（推荐，快捷）
- 使用 GitHub 账户
- 使用邮箱注册

#### 验证邮箱

如果使用邮箱注册，检查您的邮箱，点击验证链接完成邮箱验证，返回 Groq Console。

#### 验证身份（绑定信用卡）

登录后，系统会提示进行身份验证：
1. 点击 **"Verify Account"** 按钮
2. 输入信用卡信息（支持 Visa、MasterCard、AmEx 等）
3. ⚠️ **重要说明：** 这仅用于验证身份，不会产生任何费用
4. 验证成功后即可使用免费服务

#### 获取 API 密钥

1. 在左侧菜单中选择 **"API Keys"**
2. 点击 **"Create API Key"** 按钮
3. 为您的 API 密钥命名（如 "My First Key"）
4. 点击 **"Submit"** 创建
5. ⚠️ **重要：** 立即复制并保存 API 密钥，之后将无法再次查看

{{% /steps %}}

---

## 🎯 提供的服务

Groq 提供两种主要服务：

### 1. [Playground 服务](/services/chatbot/groq)
- **类型：** Web 对话界面
- **访问地址：** https://console.groq.com/playground
- **特点：** 实时查看推理速度，直观的参数调整
- **支持：** 所有 Groq 模型

### 2. [API 服务](/services/api/groq-api)
- **类型：** RESTful API
- **特点：** 完全兼容 OpenAI API 格式
- **模型：** Llama 3.3/3.1, Mixtral, Gemma 2, DeepSeek R1 等
- **配额：** 14,400 请求/天

---

## 📊 配额概览

### 免费层级配额

| 限制类型 | 配额 | 说明 |
|---------|------|------|
| **每日请求数** | 14,400 requests/day | 所有模型共享 |
| **每分钟请求数** | 30 requests/min | 所有模型共享 |
| **每日 Tokens** | 20,000 tokens/day | 输入输出总和 |
| **每分钟 Tokens** | 6,000 tokens/min | 输入输出总和 |

⚠️ **重要说明：**
- 配额共享：所有模型共享同一个账户的配额
- 每日重置：配额在 UTC 时间每天凌晨重置
- Token 计算：输入和输出的 tokens 都计入配额

---

## 🤖 支持的模型

### Llama 系列（Meta）

| 模型名称 | 参数量 | 上下文长度 | 适用场景 |
|---------|-------|-----------|---------|
| **Llama 3.3 70B** | 70B | 128K | Meta 最新模型，强大性能 |
| **Llama 3.1 70B** | 70B | 128K | 复杂任务 |
| **Llama 3.1 8B** | 8B | 128K | 轻量高效 |

### 其他开源模型

| 模型名称 | 参数量 | 上下文长度 | 特点 |
|---------|-------|-----------|------|
| **Mixtral 8x7B** | 47B | 32K | Mistral 混合专家模型 |
| **Gemma 2 9B** | 9B | 8K | Google 开源模型 |
| **DeepSeek R1 Distill Llama 70B** | 70B | 32K | 推理专家模型 |

---

## 🌟 核心技术优势

### LPU 芯片技术

**Language Processing Unit（语言处理单元）：**
- Groq 自研的专用芯片
- 专为语言模型的顺序计算优化
- 极低延迟：相比 GPU，延迟降低 10 倍以上
- 高吞吐量：可达 800+ tokens/s 的生成速度

### 速度对比

| 提供者 | 典型速度 | Groq 优势 |
|--------|---------|----------|
| Groq | 800+ tokens/s | 基准 |
| OpenAI GPT-4 | 20-40 tokens/s | **20x 更快** |
| Anthropic Claude | 30-50 tokens/s | **16x 更快** |
| 其他云服务 | 50-100 tokens/s | **8x 更快** |

### 实时性应用场景

- **聊天机器人：** 几乎无延迟的对话体验
- **代码助手：** 实时代码补全和生成
- **内容创作：** 快速生成长文本
- **数据分析：** 实时数据解读

---

## ⚠️ 使用注意事项

### 信用卡验证

- 虽然服务免费，但需要绑定信用卡验证身份
- 这是为了防止滥用，不会产生任何费用
- 免费配额用完后不会自动扣费

### 配额管理

- 注意每日和每分钟的限制，避免超额
- 在 Console 的 Usage 页面查看配额使用情况
- 合理分配不同应用的配额

### API 密钥安全

- 不要在公开代码库中暴露 API 密钥
- 使用环境变量或配置文件管理密钥
- 定期轮换 API 密钥

### 网络要求

- Groq 支持全球大部分地区
- 中国大陆可能需要稳定的网络环境

---

## 📊 与其他服务对比

| 特性 | Groq | Google AI Studio | OpenRouter |
|------|------|------------------|------------|
| 推理速度 | 🏆 800+ tokens/s | 50-100 tokens/s | 视提供者而定 |
| 每日请求数 | 14,400 | 1,500 | 50-1,000 |
| 每日 Tokens | 20K-1M | 15M (Flash) | 不限 |
| 需要信用卡 | ✅ 验证 | ❌ | ❌ |
| OpenAI 兼容 | ✅ 完全兼容 | ❌ 不兼容 | ✅ 兼容 |
| 多模态支持 | ❌ | ✅ | 部分模型 |
| 中国大陆访问 | 🔧 需稳定网络 | 🔧 需科学上网 | ✅ 较好 |

---

## 💡 选择建议

### 选择 Groq 的理由

✅ **强烈推荐：**
- 需要极快的响应速度
- 构建实时对话应用
- 高频次调用（14,400 次/天）
- 需要 OpenAI API 兼容性

❌ **不太适合：**
- 需要多模态支持（图像、音频）
- 需要超大上下文（>128K）
- 无法提供信用卡验证

---

## 📈 付费计划（可选）

如果免费配额不够用，Groq 提供灵活的付费选项：

| 计划 | 价格 | 特点 |
|------|------|------|
| Free | $0 | 14,400 req/day |
| Pay-as-you-go | 按使用付费 | 更高配额，按 tokens 计费 |
| Enterprise | 定制 | 专属支持、SLA 保障 |

**定价示例：**
- Llama 3.3 70B: ~$0.59/M tokens
- Llama 3.1 8B: ~$0.05/M tokens

---

## 🔗 相关链接

- **官方网站：** [https://groq.com](https://groq.com)
- **开发者控制台：** [https://console.groq.com](https://console.groq.com)
- **API 文档：** [https://console.groq.com/docs](https://console.groq.com/docs)
- **Python SDK：** [GitHub - groq-python](https://github.com/groq/groq-python)
- **Node.js SDK：** [GitHub - groq-typescript](https://github.com/groq/groq-typescript)
- **社区讨论：** [Discord - Groq](https://discord.gg/groq)
- **状态页面：** [https://status.groq.com](https://status.groq.com)
- **博客：** [https://groq.com/blog](https://groq.com/blog)

---

## 📝 更新日志

- **2024年12月：** 支持 DeepSeek R1 Distill 系列推理模型
- **2024年11月：** 发布 Llama 3.3 70B 支持
- **2024年10月：** 提高免费层级配额至 14,400 requests/day
- **2024年：** 持续优化 LPU 性能，提升推理速度

---

## 📧 支持与反馈

- **官方支持：** support@groq.com
- **Discord 社区：** [https://discord.gg/groq](https://discord.gg/groq)
- **问题报告：** [https://console.groq.com/support](https://console.groq.com/support)
- **功能建议：** 通过 Discord 或邮件联系
