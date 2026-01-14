---
title: "Vercel AI Gateway - 统一 AI 模型访问网关"
linkTitle: "Vercel AI Gateway"
description: "Vercel AI Gateway 提供统一接口访问数百种 AI 模型！每月 $5 免费额度，支持 OpenAI、Anthropic、Google 等多家提供商，自动故障转移，透明定价无加价。提供 API 服务，支持 BYOK，详细教程。"
keywords:
  - Vercel AI Gateway
  - AI Gateway
  - 统一AI接口
  - 多模型访问
  - 免费AI Gateway
  - Vercel AI
  - OpenAI代理
  - AI聚合器
  - BYOK
  - 免费AI额度
image: /images/logo.svg
type: docs
weight: 12
comments: true
prev: /providers/nvidia-nim
next: /services
sidebar:
  open: true
---

## 📋 基本信息

**提供者名称：** Vercel  
**产品名称：** Vercel AI Gateway  
**官方网站：** [https://vercel.com/ai-gateway](https://vercel.com/ai-gateway)  
**类型：** 免费试用（每月 $5 免费额度）

---

## 🏢 提供者介绍

Vercel AI Gateway 是由 Vercel 提供的统一 AI 模型访问网关，通过单一接口让开发者便捷访问来自多个 AI 提供商的数百种模型。

### 核心特点

- **🌐 统一接口** - 一个端点访问所有模型，无需管理多个 API 密钥
- **🔄 自动故障转移** - 提供商故障时自动切换，确保高可用性
- **💰 透明定价** - 按上游提供商列表价格，无额外加价
- **🔑 支持 BYOK** - 可使用自己的 API 密钥，完全无加价
- **⚡ 高并发支持** - Vercel 不设速率限制，性能由上游提供商决定
- **📊 统一计费** - 所有费用通过单一来源结算

**推荐指数：** ⭐⭐⭐⭐

### 技术优势

Vercel AI Gateway 的主要优势在于：

- **简化集成** - 统一的接口大幅降低多模型集成的复杂度
- **灵活切换** - 轻松在不同提供商和模型之间切换
- **高可用性** - 自动故障转移保障服务连续性
- **成本透明** - 无隐藏费用，所有价格基于上游提供商

---

## 🎁 提供的服务

Vercel AI Gateway 为开发者提供以下服务：

### API 服务

{{< cards >}}
  {{< card link="/zh-cn/services/api/vercel-ai-gateway" title="Vercel AI Gateway API" subtitle="统一接口访问数百种 AI 模型，每月 $5 免费额度" >}}
{{< /cards >}}

**特点：**
- 统一 API 端点
- 支持多家提供商（OpenAI、Anthropic、Google、Meta、xAI 等）
- 自动故障转移
- 透明定价，无加价

**注意：** Vercel AI Gateway 本身不提供独立的 Chatbot 界面，但开发者可以使用其 API 服务构建自己的聊天机器人应用。Vercel 提供了开源的 [AI Chatbot 模板](https://github.com/vercel-labs/ai-chatbot-gateway)供参考。

---

## 🚀 如何开始使用

### 注册要求

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| Vercel 账户 | ✅ 必需 | 需要 Vercel 账户 |
| 邮箱验证 | ✅ 必需 | 注册时需要邮箱 |
| 手机验证 | ❌ 不需要 | 通常不需要 |
| 信用卡 | ❌ 不需要 | 免费额度不需要，付费时需要 |

### 注册步骤

{{% steps %}}

#### 访问 Vercel 并注册

打开浏览器，访问 [https://vercel.com](https://vercel.com)，点击右上角的 **"Sign Up"** 按钮。

#### 选择注册方式

您可以使用以下方式注册：
- GitHub 账户（推荐）
- GitLab 账户
- Bitbucket 账户
- 邮箱注册

#### 创建团队（可选）

Vercel 会提示您创建团队，每个团队账户每月可获得 $5 的 AI Gateway 免费额度。

#### 访问 AI Gateway

1. 登录 Vercel 后，访问 [AI Gateway 页面](https://vercel.com/ai-gateway)
2. 点击 **"Get Started"** 开始使用
3. 系统会自动为您的团队账户分配每月 $5 的免费额度

{{% /steps %}}

---

## 💡 通用注意事项

### ✅ 推荐做法

1. **合理使用免费额度：**
   - 每月 $5 免费额度适用于所有可用模型
   - 可用于测试不同提供商的模型
   - 适合小规模应用和原型开发

2. **使用 BYOK 降低成本：**
   - 如果您已有其他提供商的 API 密钥，可以使用 BYOK
   - Vercel 不会对 Token 价格进行任何加价（0%）
   - 仅需支付上游提供商的费用

3. **利用故障转移功能：**
   - 配置多个提供商作为备份
   - 提高应用的可用性和稳定性

### ⚠️ 重要提醒

1. **免费额度说明：** 首次使用 AI Gateway 后，每 30 天获得 $5 免费额度。一旦购买 Credits（充值），将转为付费状态，不再享受每月免费额度。
2. **上游限制：** Vercel 本身不设速率限制，但上游提供商可能有自己的限制。
3. **BYOK 使用：** 使用自带密钥（BYOK）时，Vercel 承诺零加价，但建议在生产环境前充分测试。
4. **地区访问：** 部分地区可能需要科学上网才能访问 Vercel 服务。

### 🔧 常见问题

**Q: Vercel AI Gateway 与直接使用各提供商 API 有什么区别？**  
A: AI Gateway 提供统一接口、自动故障转移和统一计费，简化了多模型集成。如果只使用单一提供商，直接使用其 API 可能更简单。

**Q: 免费额度用完后会怎样？**  
A: 免费额度用完后，可以选择购买 AI Gateway Credits 继续使用，或者使用 BYOK 模式（需要自己的 API 密钥）。

**Q: BYOK 模式下 Vercel 收费吗？**  
A: 使用 BYOK 时，Vercel 对 Token 价格零加价（0%），您只需支付上游提供商的费用。

**Q: 支持哪些 AI 提供商？**  
A: 支持 OpenAI、Anthropic、Google、Meta、xAI 等主流提供商，具体列表请查看官方文档。

**Q: 可以用于生产环境吗？**  
A: 可以，Vercel AI Gateway 提供企业级可靠性和自动故障转移，适合生产环境使用。

---

## 🔗 相关链接

- **官方网站：** [https://vercel.com/ai-gateway](https://vercel.com/ai-gateway)
- **官方文档：** [https://vercel.com/docs/ai-gateway](https://vercel.com/docs/ai-gateway)
- **定价说明：** [https://vercel.com/docs/ai-gateway/pricing](https://vercel.com/docs/ai-gateway/pricing)
- **AI SDK 文档：** [https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway](https://ai-sdk.dev/providers/ai-sdk-providers/ai-gateway)
- **开源 Chatbot 模板：** [https://github.com/vercel-labs/ai-chatbot-gateway](https://github.com/vercel-labs/ai-chatbot-gateway)
- **官方博客：** [https://vercel.com/blog/ai-gateway](https://vercel.com/blog/ai-gateway)

---

## 📈 服务对比

| 特性 | 免费层级 | BYOK 模式 | 付费层级 |
|------|---------|----------|---------|
| 价格 | $5/月 免费额度 | 仅上游费用（0% 加价） | 按使用付费 |
| 模型访问 | 所有模型 | 所有模型 | 所有模型 |
| 故障转移 | ✅ | ✅ | ✅ |
| 统一计费 | ✅ | ❌ | ✅ |
| 速率限制 | 上游提供商决定 | 上游提供商决定 | 上游提供商决定 |

---

## 📝 更新日志

- **2024年12月：** Vercel AI Gateway 正式发布
- **2024年：** 持续添加更多 AI 提供商支持
- **2026年1月：** 继续提供每月 $5 免费额度

---

## 📧 支持与反馈

- **官方支持：** 通过 Vercel Dashboard 提交支持请求
- **社区讨论：** [https://github.com/vercel/next.js/discussions](https://github.com/vercel/next.js/discussions)
- **问题报告：** [https://github.com/vercel-labs/ai-chatbot-gateway/issues](https://github.com/vercel-labs/ai-chatbot-gateway/issues)
