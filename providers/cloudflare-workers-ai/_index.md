---
title: "Cloudflare Workers AI - 边缘 AI 推理平台"
linkTitle: "Cloudflare Workers AI"
description: "Cloudflare Workers AI 是无服务器边缘 AI 推理平台，提供每日 10,000 个神经元免费额度，支持 50+ 开源模型。在全球 300+ 数据中心运行 AI 模型，低延迟、高可用、无需管理 GPU。"
keywords:
  - Cloudflare Workers AI
  - Workers AI
  - 边缘 AI
  - 无服务器 AI
  - 免费 AI 推理
  - Cloudflare AI
  - 边缘计算
  - AI Gateway
  - LLM 推理
  - 开源模型
image: /images/logo.svg
type: docs
weight: 16
comments: true
prev: /providers/github-models
sidebar:
  open: true
---

## 📋 基本信息

**提供者名称：** Cloudflare Workers AI  
**官方网站：** [https://www.cloudflare.com/developer-platform/workers-ai/](https://www.cloudflare.com/developer-platform/workers-ai/)  
**开发者文档：** [https://developers.cloudflare.com/workers-ai/](https://developers.cloudflare.com/workers-ai/)  
**总部位置：** 美国旧金山  
**成立时间：** 2010 年（Cloudflare），2023 年（Workers AI）

---

## 🏢 提供者介绍

Cloudflare Workers AI 是 Cloudflare 推出的无服务器 AI 推理平台，让开发者能够在 Cloudflare 的全球网络上运行机器学习模型。与传统的 AI 推理服务不同，Workers AI 将 AI 模型部署在全球 300+ 个边缘数据中心，提供低延迟、高可用的 AI 推理服务。

### 核心特点

- **🌍 全球边缘部署：** 在全球 300+ 城市的数据中心运行 AI 模型，提供最低延迟
- **🎁 免费额度慷慨：** 每日 10,000 个神经元免费额度，无需信用卡
- **🤖 丰富模型库：** 支持 50+ 开源模型，涵盖文本生成、图像处理、语音识别等
- **⚡ 无服务器架构：** 无需管理 GPU，按使用量计费，成本超低
- **🔌 开发者友好：** REST API 和 Workers 绑定，OpenAI SDK 兼容
- **🔧 与 Cloudflare 生态集成：** 与 Workers、Pages、AI Gateway、Vectorize 等服务深度集成

**推荐指数：** ⭐⭐⭐⭐⭐ （边缘 AI 先锋！低延迟、免费额度大！）

### 技术优势

- **边缘计算优势：** 在离用户最近的数据中心执行 AI 推理，显著降低延迟
- **无服务器架构：** 自动扩展，无需预留资源，真正的按需付费
- **全球网络：** 利用 Cloudflare 的全球网络基础设施，提供高可用性
- **成本优化：** $0.011/1000 神经元，比传统云服务便宜 80%+
- **开发者体验：** 与 Cloudflare Workers 无缝集成，几行代码即可部署

---

## 🎁 提供的服务

Cloudflare Workers AI 主要提供 API 开发接口服务：

### API 服务

{{< cards >}}
  {{< card link="/zh-cn/services/api/cloudflare-workers-ai" title="Cloudflare Workers AI API" subtitle="边缘 AI 推理 API，支持 50+ 模型，每日 10,000 神经元免费" >}}
{{< /cards >}}

**特点：**
- 每日 10,000 个神经元免费额度
- 支持 50+ 开源模型（LLM、图像、语音等）
- REST API 和 Workers 绑定
- OpenAI SDK 兼容
- 全球边缘部署，低延迟

{{< callout type="info" >}}
**注意：** Cloudflare Workers AI 目前主要提供 API 服务，没有独立的 Web Chatbot 界面。但开发者可以使用 API 快速构建自己的 Chatbot 应用。
{{< /callout >}}

---

## 🚀 如何开始使用

### 注册账户

Cloudflare Workers AI 使用 Cloudflare 账户体系，注册简单快捷。

#### 门槛要求

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 免费注册 Cloudflare 账户 |
| 邮箱验证 | ✅ 必需 | 需要验证邮箱 |
| 手机验证 | ❌ 不需要 | 可选 |
| 信用卡绑定 | ❌ 不需要 | 免费额度无需信用卡 |
| 实名认证 | ❌ 不需要 | 无需实名 |

#### 注册步骤

{{% steps %}}

##### 访问 Cloudflare 官网

打开 [Cloudflare 注册页面](https://dash.cloudflare.com/sign-up)，点击"Sign Up"。

##### 创建账户

1. 输入邮箱地址
2. 设置密码
3. 点击"Create Account"

##### 验证邮箱

1. 检查邮箱中的验证邮件
2. 点击验证链接完成验证

##### 访问 Workers & Pages

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com)
2. 在左侧菜单中找到"Workers & Pages"
3. 如果是首次使用，需要设置一个 subdomain（免费）

##### 获取 API Token

1. 进入"API Tokens"页面
2. 点击"Create Token"
3. 选择"Edit Cloudflare Workers"模板或自定义权限
4. 创建 Token 并保存

{{% /steps %}}

**重要提示：**
- API Token 只显示一次，请妥善保存
- 免费额度每日自动重置，无需信用卡
- 可以在 Dashboard 中查看使用情况

---

## 💡 通用注意事项

### ✅ 推荐做法

1. **利用边缘优势：**
   - Workers AI 在全球边缘部署，适合需要低延迟的应用
   - 结合 Cloudflare Workers 使用，可以构建全栈边缘应用

2. **监控使用情况：**
   - 在 Dashboard 中查看神经元使用情况
   - 设置使用提醒，避免超出免费额度

3. **使用 AI Gateway：**
   - 结合 Cloudflare AI Gateway 使用，获得缓存、日志、重试等功能
   - 进一步降低成本和提升可靠性

4. **选择合适的模型：**
   - 根据任务需求选择合适的模型
   - 较小的模型消耗更少的神经元

### ⚠️ 重要提醒

1. **免费额度限制：** 每日 10,000 个神经元，超出后按 $0.011/1000 神经元计费
2. **神经元计算：** 不同模型消耗的神经元数量不同，具体见模型文档
3. **每日重置：** 免费额度在每天 UTC 00:00 重置
4. **模型可用性：** 部分模型可能在某些地区不可用，请查看官方文档

### 🔧 常见问题

**Q: 什么是"神经元"（Neuron）？**  
A: Neuron 是 Cloudflare Workers AI 的计费单位。不同模型每次推理消耗的神经元数量不同，通常与模型大小和输入/输出长度相关。例如，一个小型 LLM 的简单请求可能消耗 5-10 个神经元。

**Q: 免费额度够用吗？**  
A: 对于中小型应用和测试来说，每日 10,000 个神经元是足够的。例如，使用小型 LLM 可以处理约 1,000-2,000 次请求。

**Q: 如何查看我的使用情况？**  
A: 登录 Cloudflare Dashboard，在 Workers & Pages 页面可以查看 AI 使用情况和消耗的神经元数量。

**Q: Workers AI 与其他 AI 服务有什么区别？**  
A: 最大的区别是边缘部署。Workers AI 在全球 300+ 个数据中心运行，提供更低的延迟。而传统 AI 服务通常集中在少数几个区域。

**Q: 可以使用自己的模型吗？**  
A: Workers AI 已支持 **LoRA（Fine-tuned adapters）** 和从 **Hugging Face 一键部署**，可以运行定制化的模型适配器。对于更高级的需求，可以提交 Cloudflare 的 Custom Requirements 表单申请私有模型支持。

---

## 🔗 相关链接

- **官方网站：** [https://www.cloudflare.com/developer-platform/workers-ai/](https://www.cloudflare.com/developer-platform/workers-ai/)
- **开发者文档：** [https://developers.cloudflare.com/workers-ai/](https://developers.cloudflare.com/workers-ai/)
- **模型目录：** [https://developers.cloudflare.com/workers-ai/models/](https://developers.cloudflare.com/workers-ai/models/)
- **定价说明：** [https://developers.cloudflare.com/workers-ai/platform/pricing/](https://developers.cloudflare.com/workers-ai/platform/pricing/)
- **API 参考：** [https://developers.cloudflare.com/api/operations/workers-ai-post-run](https://developers.cloudflare.com/api/operations/workers-ai-post-run)
- **Discord 社区：** [https://discord.cloudflare.com](https://discord.cloudflare.com)
- **博客文章：** [https://blog.cloudflare.com/workers-ai/](https://blog.cloudflare.com/workers-ai/)
- **状态页面：** [https://www.cloudflarestatus.com/](https://www.cloudflarestatus.com/)

---

## 📈 服务对比

| 特性 | 免费层级 | 付费层级 |
|------|---------|---------|
| 价格 | 免费 | $0.011/1000 神经元 |
| 每日配额 | 10,000 神经元 | 无限制 |
| 模型数量 | 50+ | 50+ |
| 边缘部署 | ✅ | ✅ |
| 全球可用 | ✅ | ✅ |
| 技术支持 | 社区支持 | 企业支持（可选） |

---

## 📝 更新日志

- **2024年1月：** 推出更多开源模型支持，包括 Llama 2、Mistral 等
- **2023年9月：** 正式发布 Workers AI，提供每日 10,000 神经元免费额度
- **2023年：** Beta 测试阶段，逐步开放给开发者

---

## 📧 支持与反馈

- **官方支持：** 通过 Cloudflare Dashboard 提交支持工单
- **社区论坛：** [https://community.cloudflare.com/](https://community.cloudflare.com/)
- **Discord：** [https://discord.cloudflare.com](https://discord.cloudflare.com)
- **问题报告：** 通过 Dashboard 或社区论坛
