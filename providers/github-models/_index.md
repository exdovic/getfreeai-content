---
title: "GitHub Models - GitHub 官方免费 AI 模型平台"
linkTitle: "GitHub Models"
description: "GitHub Models 提供多种主流 AI 模型的免费使用！支持 GPT-4o、Llama 3.1、Phi-3、DeepSeek-R1 等模型，提供免费 Playground 和 API 服务，兼容 OpenAI 规范。"
keywords:
  - GitHub Models
  - GitHub AI
  - 免费AI模型
  - GPT-4o免费
  - Llama 3.1
  - Phi-3
  - DeepSeek-R1
  - 免费AI API
  - OpenAI兼容
  - GitHub Playground
image: /images/providers/github-models-og.png
type: docs
weight: 14
comments: true
prev: /providers/vercel-ai-gateway
next: /services
sidebar:
  open: true
---

## 🏢 提供者信息

**提供者名称：** GitHub Models  
**官方网站：** [https://github.com](https://github.com)  
**Marketplace：** [https://github.com/marketplace/models](https://github.com/marketplace/models)  
**所属公司：** GitHub（Microsoft）  
**类型：** 免费 Playground + 免费 API（有速率限制）

---

## 📋 产品简介

GitHub Models 是 GitHub 推出的 AI 模型平台，允许开发者直接在 GitHub 生态系统中免费试验和使用多种主流 AI 大语言模型。该平台无需复杂的云资源配置或模型下载，即可快速体验 GPT-4o、Llama、Phi、DeepSeek 等前沿模型。

**核心特点：**
- 🎯 **开箱即用** - 无需配置，登录 GitHub 即可使用
- 🆓 **完全免费** - Playground 和 API 均提供免费访问
- 🤖 **多模型支持** - 集成 OpenAI、Meta、Microsoft 等主流模型
- 🔌 **OpenAI 兼容** - API 兼容 OpenAI 规范，易于集成
- 🔒 **安全可靠** - 基于 GitHub 账户体系，安全有保障
- 🚀 **开发者友好** - 深度集成 GitHub 生态，方便原型开发

> **信息更新：** 本页面最后更新于 2026 年 1 月。GitHub Models 目前处于公开测试阶段，功能和限制可能随时调整，请以 [GitHub Models 官方页面](https://github.com/marketplace/models) 为准。

**推荐指数：** ⭐⭐⭐⭐⭐ （GitHub 生态首选 AI 平台！）

---

## 🔐 注册和账号

### 注册要求

**所有服务通用：**

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| GitHub 账户 | ✅ 必需 | 需要有效的 GitHub 账户 |
| 邮箱验证 | ✅ 必需 | GitHub 账户需已验证邮箱 |
| API 密钥（PAT） | ⚠️ API使用需要 | Playground 不需要，API 需要 |
| 信用卡 | ❌ 不需要 | 完全免费，无需绑卡 |
| 实名认证 | ❌ 不需要 | 无需实名 |

### 注册步骤

{{% steps %}}

##### 注册/登录 GitHub 账户

1. 访问 [https://github.com](https://github.com)
2. 如果已有 GitHub 账户，直接登录
3. 如果没有账户：
   - 点击"Sign up"注册
   - 输入邮箱、密码和用户名
   - 验证邮箱地址

##### 访问 GitHub Models

1. 登录后，访问 [https://github.com/marketplace/models](https://github.com/marketplace/models)
2. 浏览可用的 AI 模型列表
3. 选择感兴趣的模型查看详情

##### 使用 Playground（可选）

1. 在模型详情页点击"Try in Playground"
2. 直接在 Chat 界面与模型对话
3. 无需任何额外设置或 API 密钥

##### 创建 API 令牌（仅 API 使用需要）

1. 访问 GitHub Settings > Developer settings > Personal access tokens
2. 点击"Generate new token" > "Generate new token (classic)"
3. 设置 Token 名称和过期时间
4. **重要：** 选择 `models` 作用域（scope）
5. 点击"Generate token"
6. **立即复制并保存** Token（只显示一次）

{{% /steps %}}

---

## 🎯 提供的服务

GitHub Models 提供两种主要免费服务：

### 1. [Playground 服务](/services/chatbot/github-models)
- **类型：** Web 对话界面
- **访问地址：** [https://github.com/marketplace/models](https://github.com/marketplace/models)（选择模型后进入 Playground）
- **特点：** 完全免费，无需 API 密钥，即时使用
- **功能：** 文本对话、提示词测试、模型对比

### 2. [API 服务](/services/api/github-models)
- **类型：** RESTful API
- **特点：** OpenAI 兼容，需要 GitHub PAT
- **模型：** GPT-4o, GPT-4o mini, Llama 3.1, Phi-3, DeepSeek-R1 等
- **免费额度：** 每个模型有不同的速率限制

---

## 📊 配额概览

### Playground 免费配额

| 限制类型 | 配额 | 说明 |
|---------|------|------|
| 使用次数 | 因模型而异 | 每个模型有独立的速率限制 |
| 访问方式 | 网页界面 | 无需 API 密钥 |
| 模型切换 | 自由切换 | 可随时切换不同模型 |
| 上下文长度 | 因模型而异 | 取决于所选模型的上下文窗口 |

**注：** Playground 使用完全免费，但受到速率限制约束。

### API 免费配额

不同模型有不同的速率限制。以下是典型限制示例：

**High 级别模型（如 GPT-4o）：**

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每分钟请求数** | 10 次 | RPM (Requests Per Minute) |
| **每天请求数** | 50 次 | RPD (Requests Per Day) |
| **每次最大输入 Token** | 8,000 | 单次请求输入上限 |
| **每次最大输出 Token** | 4,000 | 单次请求输出上限 |
| **最大并发请求** | 2 个 | 同时进行的请求数 |

**Low 级别模型（如 Phi-3, Llama 3.1 8B）：**

| 限制项 | 配额 | 说明 |
|--------|------|------|
| **每分钟请求数** | 15 次 | RPM |
| **每天请求数** | 150 次 | RPD |
| **每次最大输入 Token** | 8,000 | 单次请求输入上限 |
| **每次最大输出 Token** | 4,000 | 单次请求输出上限 |
| **最大并发请求** | 5 个 | 同时进行的请求数 |

**注：** 
- 具体限制因模型而异，请在模型详情页查看最新信息
- 速率限制会根据使用情况动态调整

---

## 🤖 支持的模型

### OpenAI 模型

| 模型名称 | 参数规模 | 特点 | 适用场景 |
|---------|--------|------|---------|
| **GPT-4o** | 未公开 | 最强综合能力 | 复杂任务、推理 |
| **GPT-4o-mini** | 未公开 | 快速轻量 | 日常对话、高频调用 |

### Meta Llama 模型

| 模型名称 | 参数规模 | 特点 | 适用场景 |
|---------|--------|------|---------|
| **Llama-3.1-405B** | 4050亿 | 超大规模，最强开源 | 复杂推理、专业应用 |
| **Llama-3.1-70B** | 700亿 | 平衡性能和效率 | 通用任务 |
| **Llama-3.1-8B** | 80亿 | 快速响应 | 轻量应用、高频调用 |

### Microsoft Phi 模型

| 模型名称 | 参数规模 | 特点 | 适用场景 |
|---------|--------|------|---------|
| **Phi-3.5-mini** | 38亿 | 小而精，高效 | 移动端、边缘设备 |
| **Phi-3-medium** | 140亿 | 平衡性能 | 中等复杂度任务 |

### DeepSeek 模型

| 模型名称 | 参数规模 | 特点 | 适用场景 |
|---------|--------|------|---------|
| **DeepSeek-R1** | 未公开 | 推理能力强，中文优化 | 复杂推理、中文任务 |

### Mistral 模型

| 模型名称 | 参数规模 | 特点 | 适用场景 |
|---------|--------|------|---------|
| **Mistral-Large** | 未公开 | 欧洲领先模型 | 多语言任务 |
| **Mistral-Nemo** | 120亿 | 轻量快速 | 实时应用 |

### Cohere 模型

| 模型名称 | 参数规模 | 特点 | 适用场景 |
|---------|--------|------|---------|
| **Command-R+** | 未公开 | RAG 优化 | 知识检索、文档分析 |

---

## 🌟 核心优势

### 1. GitHub 生态深度集成

**无缝集成：**
- 使用 GitHub 账户直接登录
- 与 GitHub Codespaces 集成
- 可在代码仓库中直接使用
- 支持 GitHub Actions 自动化

**开发者友好：**
- 熟悉的 GitHub 界面
- 完善的文档和示例
- 活跃的开发者社区
- 便捷的协作分享

### 2. 多模型免费访问

**丰富选择：**
- 支持多家主流 AI 提供商
- 涵盖从小型到超大型模型
- 可自由切换对比不同模型
- 持续添加新模型

**应用场景：**
- 模型性能对比测试
- 原型快速验证
- 学习研究不同模型特点
- 选择最适合的模型

### 3. OpenAI 兼容 API

**标准接口：**
- 兼容 OpenAI API 规范
- 可使用 OpenAI SDK
- 易于从其他平台迁移
- 降低学习成本

**代码示例：**
```python
from openai import OpenAI

# 只需修改 base_url 和 api_key
client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key="YOUR_GITHUB_PAT"
)

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "user", "content": "Hello!"}
    ]
)
```

### 4. 安全可靠

**安全保障：**
- 基于 GitHub 账户体系
- 支持 Token 权限管理
- 可随时撤销访问权限
- 数据传输加密

---

## ⚠️ 使用注意事项

### 访问要求

- **GitHub 账户：** 必须拥有有效的 GitHub 账户
- **邮箱验证：** GitHub 账户需要已验证邮箱
- **网络访问：** 部分地区可能需要特殊网络环境访问 GitHub
- **API 使用：** 需要创建具有 `models` 作用域的 Personal Access Token

### 速率限制

**Playground：**
- 每个模型有独立的使用限制
- 达到限制后需要等待配额重置
- 可切换到其他模型继续使用

**API：**
- 不同模型有不同的速率限制
- 超出限制会返回 429 错误
- 建议实现重试机制和错误处理
- 合理分配请求，避免浪费配额

### 使用场景限制

**适合场景：**
- ✅ 个人项目和原型开发
- ✅ 学习研究和模型测试
- ✅ 小规模应用开发
- ✅ 模型性能对比

**不适合场景：**
- ❌ 高频商业应用
- ❌ 生产环境大规模部署
- ❌ 需要稳定 SLA 保障的场景
- ❌ 超出速率限制的使用需求

### Token 安全

**重要提醒：**
- ⚠️ Personal Access Token 只显示一次，请立即保存
- ⚠️ 不要将 Token 提交到公开代码仓库
- ⚠️ 使用环境变量存储 Token
- ⚠️ 定期轮换 Token 增强安全性
- ⚠️ 只授予必需的权限范围（`models` scope）

---

## 📊 与其他服务对比

| 特性 | GitHub Models | Google AI Studio | Groq |
|------|---------------|------------------|------|
| 免费 Playground | ✅ 有速率限制 | ✅ 完全免费 | ✅ 约14,400次/天 |
| 模型数量 | 🏆 10+ 模型 | 5+ 模型 | 5+ 模型 |
| OpenAI 兼容 | ✅ 完全兼容 | ❌ 需适配 | ✅ 完全兼容 |
| GitHub 集成 | 🏆 深度集成 | ❌ 无 | ❌ 无 |
| 中国访问 | ⚠️ 部分需科学上网 | ❌ 需科学上网 | ⚠️ 部分需科学上网 |
| 适用场景 | GitHub 开发者 | 个人开发者 | 实时应用 |

---

## 💡 选择建议

### 选择 GitHub Models 的理由

✅ **强烈推荐：**
- GitHub 生态开发者
- 需要对比多种 AI 模型
- 希望快速原型验证
- 追求零配置开箱即用
- 希望使用 OpenAI 兼容 API

✅ **适合场景：**
- 个人项目和学习研究
- 代码生成和开发辅助
- 模型性能测试对比
- GitHub Actions 集成
- 小规模应用开发

❌ **不太适合：**
- 需要极高免费配额
- 生产环境大规模部署
- 对速率限制敏感的应用
- 不使用 GitHub 生态的开发者

---

## 🎯 使用场景

### 学习研究

- 对比不同 AI 模型的性能
- 学习大语言模型的使用
- 测试不同提示词效果
- 研究模型能力边界

### 代码开发

- GitHub Copilot 的补充
- 代码生成和优化建议
- 代码审查和 Bug 修复
- 文档自动生成

### 原型开发

- 快速验证 AI 应用想法
- 对比选择最佳模型
- 低成本试错
- MVP 开发

### GitHub 集成

- GitHub Actions 自动化
- Issues 和 PR 自动处理
- 代码仓库智能分析
- README 和文档生成

---

## 🔗 相关链接

- **GitHub Models Marketplace：** [https://github.com/marketplace/models](https://github.com/marketplace/models)
- **官方文档：** [https://docs.github.com/zh/github-models](https://docs.github.com/zh/github-models)
- **快速入门：** [https://docs.github.com/zh/github-models/quickstart](https://docs.github.com/zh/github-models/quickstart)
- **原型开发指南：** [https://docs.github.com/zh/github-models/use-github-models/prototyping-with-ai-models](https://docs.github.com/zh/github-models/use-github-models/prototyping-with-ai-models)
- **GitHub 官方博客：** [https://github.blog](https://github.blog)
- **GitHub 开发者文档：** [https://docs.github.com](https://docs.github.com)

---

## 📝 更新日志

- **2024年9月：** GitHub Models 进入公开测试阶段
- **2024年10月：** 新增 DeepSeek-R1 等模型支持
- **2024年11月：** 优化速率限制和 API 响应速度
- **2025年：** 持续添加新模型，优化用户体验

---

## 📧 支持与反馈

- **官方文档：** [https://docs.github.com/zh/github-models](https://docs.github.com/zh/github-models)
- **GitHub Support：** [https://support.github.com](https://support.github.com)
- **社区论坛：** [https://github.community](https://github.community)
- **反馈问题：** 通过 GitHub Support 提交工单

