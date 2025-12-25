---
title: Cohere
type: docs
weight: 5
comments: true
prev: /providers/deepseek
next: /providers/google-vertex-ai
sidebar:
  open: true
---

## 🏢 提供者信息

**提供者名称：** Cohere  
**官方网站：** https://cohere.com  
**Chatbot：** https://coral.cohere.com  
**开发者控制台：** https://dashboard.cohere.com  
**类型：** 试用积分（1,000-10,000 API calls/月）

---

## 📋 产品简介

Cohere 是一家专注于企业级 AI 的公司，提供强大的 RAG（检索增强生成）能力和多语言支持，特别擅长 Embedding 和 Rerank。

**核心特点：**
- 🎯 **RAG 专家** - 业界领先的检索增强生成
- 🌍 **多语言支持** - 100+ 语言
- 📊 **强大 Embedding** - 顶尖文本向量化
- 🔝 **最佳 Rerank** - 提升搜索准确度
- 🎁 **免费 Chatbot** - Coral 完全免费无限制
- 💼 **企业级** - Production 层级 10,000 calls/月

**推荐指数：** ⭐⭐⭐⭐⭐ （RAG 和企业应用首选！）

---

## 🔐 注册和账号

### 注册要求

**Chatbot（Coral）：**

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 邮箱或 Google 账户 |
| 邮箱验证 | ✅ 必需 | 需要验证 |
| 信用卡 | ❌ 不需要 | 完全免费 |

**API（Trial 层级）：**

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 邮箱或 Google 账户 |
| 邮箱验证 | ✅ 必需 | 需要验证 |
| 信用卡 | ❌ 不需要 | 1,000 calls/月 |

**API（Production 层级）：**

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 邮箱或 Google 账户 |
| 邮箱验证 | ✅ 必需 | 需要验证 |
| 信用卡验证 | ✅ 必需 | 不扣费，仅验证身份 |

### 注册步骤

{{% steps %}}

#### 基础注册

访问 [https://dashboard.cohere.com](https://dashboard.cohere.com)，点击 **"Sign Up"** 注册，使用邮箱或 Google 账户注册，验证邮箱地址，自动获得 Trial 层级（1,000 calls/月）。

#### 升级到 Production

1. 登录 Dashboard
2. 选择 **"Upgrade to Production"**
3. 添加信用卡信息（不会扣费）
4. 验证通过后升级到 10,000 calls/月

{{% /steps %}}

---

## 🎯 提供的服务

Cohere 提供两种主要服务：

### 1. [Coral Chatbot 服务](/services/chatbot/cohere-coral)
- **类型：** Web 对话界面
- **访问地址：** https://coral.cohere.com
- **特点：** 完全免费，无使用限制
- **功能：** RAG、文档上传、引用来源、多语言

### 2. [API 服务](/services/api/cohere-api)
- **类型：** RESTful API
- **特点：** 企业级性能，RAG 优化
- **模型：** Command R+, Embed v3, Rerank v3.5
- **配额：** Trial 1,000 calls/月，Production 10,000 calls/月

---

## 📊 配额概览

### Trial 层级（无需信用卡）

| 限制类型 | 配额 | 说明 |
|---------|------|------|
| **月度 API 调用** | 1,000 calls | 所有 API 共享 |
| **速率限制** | 10 requests/min | 避免滥用 |
| **可用模型** | 全部 | Command R+, Embed, Rerank |
| **需要信用卡** | ❌ 否 | 完全免费 |

### Production 层级（需验证信用卡）

| 限制类型 | 配额 | 说明 |
|---------|------|------|
| **月度 API 调用** | 10,000 calls | 10倍提升 |
| **速率限制** | 1,000 requests/min | 生产级性能 |
| **可用模型** | 全部 | 所有企业级功能 |
| **需要信用卡** | ✅ 是 | 验证身份，不扣费 |

### API 调用计数规则

- **Chat（对话）：** 每次请求 = 1 call
- **Embed（向量化）：** 每 1,000 texts = 1 call
- **Rerank（重排序）：** 每次请求 = 1 call
- **配额重置：** 每月 1 号

---

## 🤖 核心模型

### Command R+ - 对话模型

| 特性 | 详情 |
|------|------|
| **上下文** | 128K tokens |
| **特点** | RAG 优化，多语言支持 |
| **语言** | 100+ 语言 |
| **适用** | 对话、问答、RAG |

### Embed v3 - Embedding 模型

| 特性 | 详情 |
|------|------|
| **类型** | 文本向量化 |
| **维度** | 256/512/1024 可选 |
| **语言** | 100+ 语言 |
| **适用** | 语义搜索、聚类、分类 |

### Rerank v3.5 - 重排序模型

| 特性 | 详情 |
|------|------|
| **类型** | 搜索结果重排序 |
| **特点** | 业界最佳性能 |
| **语言** | 100+ 语言 |
| **适用** | RAG、搜索优化 |

---

## 🌟 核心优势

### 1. RAG 专家

**检索增强生成：**
- 自动引用来源
- 文档上下文理解
- 多文档融合
- 降低幻觉

### 2. 强大的 Embedding

**文本向量化：**
- 多语言支持（100+）
- 多种维度选择
- 语义搜索优化
- 高性能检索

### 3. 业界最佳 Rerank

**搜索结果重排序：**
- 提升准确度 20-30%
- 多语言支持
- RAG 必备工具
- 快速响应

### 4. 多语言支持

**100+ 语言：**
- 中文性能优秀
- 跨语言理解
- 统一 API
- 无需切换模型

---

## ⚠️ 使用注意事项

### 配额管理

- Trial 层级 1,000 calls/月适合开发测试
- Production 层级 10,000 calls/月适合生产
- 每月 1 号配额重置

### 信用卡验证

- Production 层级需要信用卡
- 仅用于验证身份
- 免费配额内不会扣费
- 超出配额才会付费

### API 调用优化

- Embed 每 1,000 texts = 1 call（很划算）
- Chat 和 Rerank 每次 = 1 call
- 合理使用批量处理

---

## 📊 与其他服务对比

| 特性 | Cohere | Google AI Studio | OpenRouter |
|------|--------|------------------|------------|
| RAG 能力 | 🏆 业界领先 | 良好 | 一般 |
| Embedding | 🏆 顶尖 | 良好 | 不提供 |
| Rerank | 🏆 独有优势 | 不提供 | 不提供 |
| 多语言 | 🏆 100+ 语言 | 良好 | 视模型而定 |
| 免费配额 | 1,000-10,000/月 | 1,500/天 | 50-1,000/天 |
| 需要信用卡 | Production需要 | ❌ | ❌ |
| 企业功能 | 🏆 完善 | 一般 | 一般 |

---

## 💡 选择建议

### 选择 Cohere 的理由

✅ **强烈推荐：**
- 需要 RAG 能力
- 构建语义搜索系统
- 需要 Embedding 和 Rerank
- 多语言应用
- 企业级应用

✅ **适合场景：**
- 知识库问答
- 智能搜索
- 文档分析
- 多语言内容处理

❌ **不太适合：**
- 仅需简单对话（选其他）
- 需要极高免费配额（选 Groq）
- 不需要 RAG 功能

---

## 🔗 相关链接

- **官方网站：** [https://cohere.com](https://cohere.com)
- **Coral Chatbot：** [https://coral.cohere.com](https://coral.cohere.com)
- **开发者控制台：** [https://dashboard.cohere.com](https://dashboard.cohere.com)
- **API 文档：** [https://docs.cohere.com](https://docs.cohere.com)
- **定价说明：** [https://cohere.com/pricing](https://cohere.com/pricing)
- **GitHub：** [https://github.com/cohere-ai](https://github.com/cohere-ai)
- **Discord 社区：** [https://discord.gg/co-mmunity](https://discord.gg/co-mmunity)

---

## 📝 更新日志

- **2024年11月：** 推出 Rerank v3.5，性能提升 30%
- **2024年9月：** 发布 Command R+，128K 上下文
- **2024年：** 持续优化 RAG 性能和多语言支持

---

## 📧 支持与反馈

- **官方文档：** [https://docs.cohere.com](https://docs.cohere.com)
- **Discord 社区：** [https://discord.gg/co-mmunity](https://discord.gg/co-mmunity)
- **问题报告：** 通过 Dashboard 提交
- **企业合作：** sales@cohere.com
