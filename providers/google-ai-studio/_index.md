---
title: Google AI Studio
type: docs
weight: 1
comments: true
prev: /providers
next: /providers/groq
sidebar:
  open: true
---

## 🏢 提供者信息

**提供者名称：** Google  
**产品名称：** Google AI Studio  
**官方网站：** https://aistudio.google.com  
**类型：** 免费服务（永久免费，有使用限制）

---

## 📋 产品简介

Google AI Studio 是 Google 官方提供的 AI 开发平台，为开发者和研究者提供便捷的 Gemini 模型访问。

**核心特点：**
- 🎁 **业界最高免费配额** - 15M tokens/天
- 🌟 **Gemini 系列模型** - 最新的 AI 模型
- 🎨 **多模态支持** - 文本、图像、音频、视频
- 📱 **2M 超长上下文** - 处理海量信息
- 🔍 **Google Search Grounding** - 联网搜索最新信息
- ⚡ **高速推理** - Flash 系列模型提供极快响应

**推荐指数：** ⭐⭐⭐⭐⭐

---

## 🔐 注册和账号

### 注册要求

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| Google 账户 | ✅ 必需 | Gmail、YouTube 等都可以 |
| 邮箱验证 | ✅ 必需 | Google 账户自带 |
| 手机验证 | ❌ 不需要 | 部分地区可能需要 |
| 信用卡 | ❌ 不需要 | 完全免费，无需支付信息 |

### 注册步骤

{{% steps %}}

#### 访问 Google AI Studio

打开浏览器，访问 [https://aistudio.google.com](https://aistudio.google.com)，点击右上角的 **"Get started"** 按钮。

#### 登录 Google 账户

使用您的 Google 账户登录（Gmail、YouTube 等账户都可以）。如果没有 Google 账户，点击 **"Create account"** 创建一个。

#### 同意服务条款

阅读并同意 Google AI Studio 的服务条款，选择您的数据使用偏好（是否允许用于训练）。

#### 创建 API 密钥（如需使用 API）

1. 在左侧菜单中点击 **"Get API key"**
2. 选择或创建一个 Google Cloud 项目（免费）
3. 点击 **"Create API key"** 生成密钥
4. ⚠️ **重要：** 立即复制并保存您的 API 密钥，妥善保管

{{% /steps %}}

---

## 🎯 提供的服务

Google AI Studio 提供两种主要服务：

### 1. [Chatbot 服务](/services/chatbot/google-ai-studio)
- **类型：** Web 对话界面
- **访问地址：** https://aistudio.google.com
- **特点：** 无需编程，直接在网页使用
- **支持：** 多模态输入（文本、图像、音频、视频）

### 2. [API 服务](/services/api/google-ai-studio-api)
- **类型：** RESTful API
- **特点：** 兼容 OpenAI API 格式
- **模型：** Gemini 3/2.5 Flash, Gemma 3 系列
- **配额：** 15M tokens/天（Flash 系列）

---

## 📊 配额概览

### 总配额

| 模型系列 | 每日 Tokens | 每日请求数 |
|---------|-------------|-----------|
| Gemini Flash 系列 | 15M tokens | 1,500 次 |
| Gemini Pro 系列 | 3M tokens | 1,500 次 |
| Gemma 系列 | 4M tokens | 14,400 次 |

⚠️ **重要：** 所有模型共享每日 1500 次请求的总配额（Gemma 除外）

---

## 💡 通用特性

### 1. 多模态支持
- **文本：** 超长文本理解和生成（最高 2M tokens）
- **图像：** 图片识别和分析
- **音频：** 音频转文字和理解
- **视频：** 视频内容分析

### 2. Google Search Grounding
- 模型可以联网搜索最新信息
- 提供信息来源引用
- 确保答案的时效性和准确性

### 3. 函数调用（Function Calling）
- 支持定义和调用外部函数
- 可以集成到您的应用中实现复杂功能
- 适合构建 AI Agent 和工具链

### 4. Prompt 管理
- 保存和管理您的 Prompt 模板
- 支持参数化 Prompt
- 方便团队协作和版本控制

---

## ⚠️ 使用注意事项

### 数据隐私
- 在非欧盟/欧洲经济区/英国/瑞士地区，您的数据可能用于 Google 模型训练
- 可以在设置中选择退出数据训练

### 地区限制
- 部分地区（如中国大陆）可能需要科学上网才能访问

### API 密钥安全
- 不要在公开代码中暴露 API 密钥
- 所有 API 密钥共享同一个项目的配额

---

## 📊 与其他服务对比

| 特性 | Google AI Studio | OpenRouter | Groq |
|------|-----------------|------------|------|
| 每日请求数 | 1,500 | 50-1,000 | 14,400 |
| 每日 Tokens | 15M (Flash) | 不限 | 20K-1M |
| 上下文长度 | 2M | 视模型而定 | 32K-128K |
| 多模态支持 | ✅ 强大 | 部分模型 | ❌ |
| 网络搜索 | ✅ | ❌ | ❌ |
| 需要信用卡 | ❌ | ❌ | ✅ (验证) |
| 中国大陆访问 | 🔧 需科学上网 | ✅ | 🔧 需科学上网 |

---

## 🔗 相关链接

- **官方文档：** [https://ai.google.dev/docs](https://ai.google.dev/docs)
- **API 参考：** [https://ai.google.dev/api](https://ai.google.dev/api)
- **定价说明：** [https://ai.google.dev/pricing](https://ai.google.dev/pricing)
- **社区论坛：** [https://discuss.ai.google.dev](https://discuss.ai.google.dev)
- **示例代码：** [GitHub - generative-ai-docs](https://github.com/google/generative-ai-docs)
- **状态页面：** [https://status.cloud.google.com](https://status.cloud.google.com)

---

## 📝 更新日志

- **2024年12月：** Gemini 2.5 Flash 发布，提供更快的推理速度
- **2024年11月：** Gemma 3 系列发布，开源模型支持
- **2024年：** 持续提高免费配额，添加多模态功能

---

## 📧 支持与反馈

- **官方支持：** 通过 Google Cloud Console 提交支持工单
- **社区讨论：** https://discuss.ai.google.dev
- **问题报告：** 通过官方文档的反馈按钮
