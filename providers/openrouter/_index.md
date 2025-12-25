---
title: OpenRouter
type: docs
weight: 3
comments: true
prev: /providers/groq
next: /providers/deepseek
sidebar:
  open: true
---

## 🏢 提供者信息

**提供者名称：** OpenRouter  
**官方网站：** https://openrouter.ai  
**控制台：** https://openrouter.ai/keys  
**类型：** 免费增值（Freemium）- 提供 47+ 免费模型

---

## 📋 产品简介

OpenRouter 是一个 AI 模型聚合平台，通过统一的 API 接口提供来自多个提供者的 47+ 个免费模型，让开发者无需注册多个服务即可访问各种 AI 模型。

**核心特点：**
- 🎯 **模型聚合** - 一个 API 访问 47+ 免费模型
- 🔄 **OpenAI 兼容** - 完全兼容 OpenAI API 格式
- 🎁 **大量免费模型** - Llama 3.3 405B, DeepSeek, Qwen 等
- 🚀 **智能路由** - 自动选择最优提供者
- 💰 **灵活定价** - 免费层 + 按需付费

**推荐指数：** ⭐⭐⭐⭐⭐ （模型最全！）

---

## 🔐 注册和账号

### 注册要求

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 支持邮箱、Google、Discord |
| 邮箱验证 | ✅ 必需 | 需要验证邮箱 |
| 手机验证 | ❌ 不需要 | 不需要手机号 |
| 信用卡绑定 | ❌ 不需要 | 完全免费，无需支付信息 |
| 充值建议 | 💡 可选 | $10 可升级到 1000 req/day |

### 注册步骤

{{% steps %}}

#### 注册账户

访问 [https://openrouter.ai](https://openrouter.ai)，点击右上角 **"Sign In"** 按钮。选择注册方式：
- **Google 账户**（推荐，最快）
- **Discord 账户**
- **邮箱注册**

#### 验证邮箱

如果使用邮箱注册，检查收件箱，点击验证链接，返回 OpenRouter 完成注册。

#### 创建 API 密钥

1. 登录后，进入控制台：[https://openrouter.ai/keys](https://openrouter.ai/keys)
2. 点击 **"Create Key"** 按钮
3. 为密钥命名（如 "My Free API Key"）
4. 可选：设置每月限额（建议设为 $0 避免误用付费模型）
5. 点击 **"Create"** 创建密钥
6. ⚠️ **重要：** 立即复制并保存 API 密钥

#### （可选）充值升级配额

如果每日 50 次请求不够用：

1. 点击右上角的余额显示
2. 选择 **"Add Credits"**
3. 充值 $10（支持信用卡、PayPal、支付宝、微信支付）
4. 充值后自动升级到 1000 requests/day
5. 💡 **提示：** 充值金额不会自动扣除，仅在使用付费模型时消耗

{{% /steps %}}

---

## 🎯 提供的服务

OpenRouter 提供两种主要服务：

### 1. [Playground 服务](/services/chatbot/openrouter)
- **类型：** Web 测试界面
- **访问地址：** https://openrouter.ai/playground
- **特点：** 直接测试所有免费模型，查看使用统计
- **支持：** 所有 47+ 免费模型

### 2. [API 服务](/services/api/openrouter-api)
- **类型：** RESTful API
- **特点：** 完全兼容 OpenAI API 格式
- **模型：** 47+ 免费模型，包括 Llama, DeepSeek, Qwen 等
- **配额：** 基础 50 次/天，充值 $10 升级至 1000 次/天

---

## 📊 配额概览

### 基础免费层级（无充值）

| 限制类型 | 配额 | 说明 |
|---------|------|------|
| **每日请求数** | 50 requests/day | 所有免费模型共享 |
| **每分钟请求数** | 20 requests/min | 所有免费模型共享 |
| **可用模型** | 47+ 模型 | 标记为 `:free` 的模型 |
| **费用** | $0 | 完全免费 |

### 升级免费层级（$10 终身充值）

| 限制类型 | 配额 | 说明 |
|---------|------|------|
| **每日请求数** | 1,000 requests/day | 20倍提升 |
| **每分钟请求数** | 20 requests/min | 保持不变 |
| **可用模型** | 所有免费模型 | 无限制 |
| **费用** | $10 一次性 | 永久享受高配额 |

⚠️ **重要说明：**
- 充值金额可用于付费模型，免费模型不消耗余额
- 可设置信用额度为 $0，防止意外使用付费模型
- 免费模型永远不会扣费

---

## 🤖 免费模型列表（精选）

### 🏆 顶级大模型

| 模型名称 | 参数量 | 上下文 | 特点 |
|---------|-------|--------|------|
| **Llama 3.3 70B** | 70B | 128K | Meta 最新 |
| **Llama 3.1 405B** | 405B | 128K | 超大参数量 |
| **DeepSeek R1 0528** | - | 64K | 推理专家（最新）|
| **DeepSeek V3.1** | - | 64K | 中文优化 |

### 🚀 高性能模型

| 模型名称 | 参数量 | 上下文 | 特点 |
|---------|-------|--------|------|
| **Qwen 3 235B** | 235B | 128K | 阿里通义千问旗舰 |
| **Mistral Small 3.1** | 24B | 32K | Mistral 高效 |
| **Gemma 3 27B** | 27B | 8K | Google 开源 |

### ⚡ 轻量快速模型

| 模型名称 | 参数量 | 上下文 | 特点 |
|---------|-------|--------|------|
| **Llama 3.2 3B** | 3B | 128K | 轻量快速 |
| **Gemma 3 4B** | 4B | 8K | 小而强大 |
| **Mistral 7B** | 7B | 32K | 经典高效 |

### 🎨 多模态模型

| 模型名称 | 参数量 | 上下文 | 特点 |
|---------|-------|--------|------|
| **Qwen 2.5 VL 7B** | 7B | 32K | 支持视觉 |
| **Nemotron Nano 12B VL** | 12B | 32K | NVIDIA 多模态 |

### 💻 代码专用模型

| 模型名称 | 参数量 | 上下文 | 特点 |
|---------|-------|--------|------|
| **Devstral 2512** | - | 32K | Mistral 代码专家 |
| **Qwen 3 Coder** | - | 32K | 通义千问代码版 |

---

## 🌟 核心优势

### 1. 模型聚合

**统一接口：**
- 一个 API 密钥访问 47+ 模型
- 无需分别注册各个提供者
- 统一的计费和监控

**智能路由：**
- 自动选择最优提供者
- 负载均衡
- 故障转移

### 2. OpenAI 兼容性

**无缝迁移：**
```python {filename="Python"}
# 从 OpenAI 迁移只需修改两行
from openai import OpenAI

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",  # 修改这行
    api_key="YOUR_OPENROUTER_KEY"              # 修改这行
)

# 其余代码完全相同
```

### 3. 灵活的定价

**多层级选择：**
- 免费层：50 次/天
- 升级层：$10 终身，1000 次/天
- 付费层：按需使用，仅付费模型扣费

---

## ⚠️ 使用注意事项

### 配额管理

- 基础免费层 50 次/天适合轻度使用
- 建议开发阶段充值 $10 升级配额
- 在控制台设置信用限额防止意外扣费

### 模型选择

- 查看模型列表的 `:free` 标记
- 免费模型性能已经很强大
- 根据任务选择合适的模型大小

### API 密钥安全

- 不要在公开代码中暴露密钥
- 可以为不同项目创建不同密钥
- 定期检查使用统计

---

## 📊 与其他服务对比

| 特性 | OpenRouter | Google AI Studio | Groq |
|------|-----------|------------------|------|
| 免费模型数量 | 🏆 47+ | 6 | 6 |
| 每日请求数 | 50-1,000 | 1,500 | 14,400 |
| 模型来源 | 多个提供者 | Google | Groq |
| OpenAI 兼容 | ✅ 完全兼容 | ❌ | ✅ |
| 需要信用卡 | ❌ | ❌ | ✅ |
| 升级成本 | $10 终身 | - | - |
| 中国大陆访问 | ✅ 较好 | 🔧 需科学上网 | 🔧 需稳定网络 |

---

## 💡 选择建议

### 选择 OpenRouter 的理由

✅ **强烈推荐：**
- 需要访问多种不同的模型
- 想要 OpenAI API 兼容性
- 需要灵活切换不同模型
- 希望有大量免费选择

✅ **适合场景：**
- 开发和测试不同模型
- 构建模型对比工具
- 需要备用模型选项

❌ **不太适合：**
- 需要极高的每日请求配额（选 Groq）
- 只用单一模型（选专门提供者）
- 需要多模态功能（选 Google AI Studio）

---

## 📈 升级建议

### 何时应该充值 $10？

✅ **建议充值：**
- 每日请求超过 50 次
- 需要更高的开发测试频率
- 希望使用更多高级免费模型
- 偶尔需要使用付费模型

❌ **暂不需要：**
- 只是偶尔测试
- 每日请求少于 50 次
- 仅用于学习目的

---

## 🔗 相关链接

- **官方网站：** [https://openrouter.ai](https://openrouter.ai)
- **模型列表：** [https://openrouter.ai/models](https://openrouter.ai/models)
- **API 文档：** [https://openrouter.ai/docs](https://openrouter.ai/docs)
- **控制台：** [https://openrouter.ai/keys](https://openrouter.ai/keys)
- **使用统计：** [https://openrouter.ai/activity](https://openrouter.ai/activity)
- **定价说明：** [https://openrouter.ai/docs/limits](https://openrouter.ai/docs/limits)
- **Discord 社区：** [https://discord.gg/openrouter](https://discord.gg/openrouter)

---

## 📝 更新日志

- **2024年12月：** 新增 DeepSeek R1 系列模型
- **2024年11月：** 新增 Llama 3.3 70B 支持
- **2024年：** 持续增加免费模型数量
- **2024年：** 优化智能路由算法

---

## 📧 支持与反馈

- **官方支持：** [https://openrouter.ai/docs](https://openrouter.ai/docs)
- **Discord 社区：** [https://discord.gg/openrouter](https://discord.gg/openrouter)
- **问题报告：** 通过 Discord 或官网联系
- **功能建议：** 在 Discord 社区反馈
