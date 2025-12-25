---
title: Google Vertex AI
type: docs
weight: 6
comments: true
prev: /providers/cohere
sidebar:
  open: true
---

## 🏢 提供者信息

**提供者名称：** Google Cloud  
**产品名称：** Google Vertex AI  
**官方网站：** https://cloud.google.com/vertex-ai  
**控制台：** https://console.cloud.google.com/vertex-ai  
**类型：** 试用积分（$300，90天有效期）

---

## 📋 产品简介

Google Vertex AI 是 Google Cloud 的企业级 AI 平台，提供 Gemini 系列模型和完整的 MLOps 工具链，是大规模生产部署的首选。

**核心特点：**
- 💰 **$300 试用积分** - 90天有效期
- 🌟 **Gemini 1.5 Pro** - 2M 超长上下文
- 🎨 **多模态** - 文本、图像、音频、视频
- 🏢 **企业级平台** - 完整 MLOps 工具
- 🔐 **安全合规** - Google Cloud 级别保障
- 🌐 **全球部署** - 多区域可用

**推荐指数：** ⭐⭐⭐⭐⭐ （企业级首选！）

---

## 🔐 注册和账号

### 注册要求

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| Google 账户 | ✅ 必需 | Gmail 或 Google Workspace |
| 邮箱验证 | ✅ 必需 | Google 账户自带 |
| 手机验证 | ✅ 必需 | 需要验证手机号 |
| 信用卡绑定 | ✅ 必需 | 试用期不扣费 |
| 地址信息 | ✅ 必需 | 填写账单地址 |

### 注册步骤

{{% steps %}}

#### 创建 Google Cloud 账户

访问 [https://console.cloud.google.com](https://console.cloud.google.com)，使用 Google 账户登录，首次使用会提示激活免费试用。

#### 激活 $300 免费试用

点击"激活"或"开始免费试用"，选择账户类型（个人/企业），填写信息：
- 国家/地区
- 账单地址
- 联系信息

#### 验证身份（绑定信用卡）

输入信用卡信息，Google 可能扣除 $1 验证（立即退回），完成验证。

⚠️ **重要：**
- 试用期间（90天）不会自动扣费
- 用完 $300 或 90 天后需手动升级

#### 启用 Vertex AI API

搜索 **"Vertex AI"**，点击"启用 API"，等待启用完成。

#### 创建项目

点击顶部项目选择器，新建项目，输入项目名称。

{{% /steps %}}

---

## 🎯 提供的服务

Google Vertex AI 提供两种主要服务：

### 1. [Vertex AI Studio 服务](/services/chatbot/vertex-ai-studio)
- **类型：** Web 界面（AI Studio）
- **访问地址：** https://console.cloud.google.com/vertex-ai/generative
- **特点：** 可视化测试，无需编程
- **功能：** 模型测试、Prompt 设计、多模态

### 2. [API 服务](/services/api/vertex-ai-api)
- **类型：** RESTful API 和 SDK
- **特点：** 企业级性能，完整功能
- **模型：** Gemini 1.5 Pro/Flash, PaLM 2 等
- **试用：** $300 积分，90 天有效

---

## 📊 配额概览

### 试用积分

| 项目 | 详情 |
|------|------|
| **积分金额** | $300 USD |
| **有效期** | 90 天 |
| **适用范围** | 所有 Google Cloud 服务 |
| **到期后** | 不会自动扣费，需手动升级 |

### Gemini 模型定价

**Gemini 1.5 Pro：**
| 上下文 | 输入 | 输出 |
|--------|------|------|
| ≤ 128K | $1.25/M | $5/M |
| > 128K | $2.50/M | $10/M |

**Gemini 1.5 Flash：**
| 上下文 | 输入 | 输出 |
|--------|------|------|
| ≤ 128K | $0.075/M | $0.30/M |
| > 128K | $0.15/M | $0.60/M |

**$300 能用多久：**
- Gemini Pro: ~240M input tokens
- Gemini Flash: ~4B input tokens

---

## 🤖 支持的模型

### Gemini 1.5 Pro

| 特性 | 详情 |
|------|------|
| **上下文** | 2M tokens（业界最长）|
| **多模态** | 文本、图像、音频、视频 |
| **特点** | 企业级性能 |
| **适用** | 复杂任务、长文档 |

### Gemini 1.5 Flash

| 特性 | 详情 |
|------|------|
| **上下文** | 1M tokens |
| **速度** | 极快 |
| **成本** | 更低 |
| **适用** | 高频场景 |

### 其他模型

- **PaLM 2** - 旧版大模型
- **Imagen** - 图像生成
- **Chirp** - 语音识别

---

## 🌟 核心优势

### 1. 超长上下文

**Gemini 1.5 Pro：**
- 2M tokens 上下文
- 处理完整书籍
- 分析大量文档
- 长时间对话

### 2. 企业级平台

**完整功能：**
- Vertex AI Studio（Web UI）
- Model Garden（模型市场）
- AutoML（自动机器学习）
- Model Deployment（部署）
- Monitoring & Logging（监控）
- SLA 保障

### 3. Google Cloud 集成

**无缝集成：**
- Cloud Storage
- BigQuery
- Compute Engine
- 其他 GCP 服务

### 4. 安全合规

- Google Cloud 安全标准
- 数据加密
- 访问控制
- 合规认证

---

## ⚠️ 使用注意事项

### 信用卡要求

- 必须绑定信用卡
- 试用期不扣费
- $1 验证会退回
- 到期后不自动计费

### 配额管理

- 监控积分使用
- 90 天有效期
- 设置预算警报
- 避免意外扣费

### 地区可用性

- 部分地区可能不支持
- 检查服务可用区域
- 中国大陆需科学上网

---

## 📊 与其他服务对比

| 特性 | Vertex AI | Google AI Studio | DeepSeek |
|------|-----------|------------------|----------|
| 上下文长度 | 🏆 2M tokens | 2M | 64K |
| 免费形式 | $300积分(90天) | 永久免费 | ¥5(7天) |
| 企业功能 | 🏆 完整 | 基础 | 基础 |
| 门槛 | 高（需信用卡）| 低 | 中（需实名）|
| GCP 集成 | 🏆 完整 | 无 | 无 |
| 适用场景 | 企业生产 | 个人开发 | 个人/中小企业 |

---

## 💡 选择建议

### 选择 Vertex AI 的理由

✅ **强烈推荐：**
- 企业级生产部署
- 需要 MLOps 工具
- 大规模应用
- GCP 用户
- 需要 SLA 保障

✅ **适合场景：**
- 企业 AI 应用
- 大数据分析
- 模型训练和部署
- 合规要求高

❌ **不太适合：**
- 个人学习（选 AI Studio）
- 简单测试（选 AI Studio）
- 不能提供信用卡
- 预算极度有限

---

## 🔗 相关链接

- **官方网站：** [https://cloud.google.com/vertex-ai](https://cloud.google.com/vertex-ai)
- **控制台：** [https://console.cloud.google.com/vertex-ai](https://console.cloud.google.com/vertex-ai)
- **API 文档：** [https://cloud.google.com/vertex-ai/docs](https://cloud.google.com/vertex-ai/docs)
- **定价说明：** [https://cloud.google.com/vertex-ai/pricing](https://cloud.google.com/vertex-ai/pricing)
- **教程：** [https://cloud.google.com/vertex-ai/docs/tutorials](https://cloud.google.com/vertex-ai/docs/tutorials)
- **示例代码：** [GitHub - vertex-ai-samples](https://github.com/GoogleCloudPlatform/vertex-ai-samples)

---

## 📝 更新日志

- **2024年11月：** Gemini 1.5 Pro 2M 上下文正式发布
- **2024年9月：** Gemini 1.5 Flash 优化性能
- **2024年：** 持续增强企业功能

---

## 📧 支持与反馈

- **官方支持：** Google Cloud Support
- **文档：** [https://cloud.google.com/vertex-ai/docs](https://cloud.google.com/vertex-ai/docs)
- **社区：** [https://cloud.google.com/community](https://cloud.google.com/community)
- **工单系统：** 通过 GCP Console 提交
