---
title: DeepSeek
type: docs
weight: 4
comments: true
prev: /providers/openrouter
next: /providers/cohere
sidebar:
  open: true
---

## 🏢 提供者信息

**提供者名称：** DeepSeek（深度求索）  
**官方网站：** https://www.deepseek.com  
**Chatbot：** https://chat.deepseek.com  
**开发者平台：** https://platform.deepseek.com  
**类型：** 免费 Chatbot + 试用积分 API

---

## 📋 产品简介

DeepSeek 是中国领先的 AI 公司，提供强大的大语言模型服务。其 R1 推理模型媲美 OpenAI o1，而价格仅为其零头。

**核心特点：**
- 🧠 **强大推理能力** - R1 模型思维链可见
- 💻 **顶尖代码生成** - Coder V2 专注编程
- 💰 **超低价格** - 比 GPT-4 便宜 97%
- 🇨🇳 **中文优化** - 中文性能顶尖
- 🎁 **免费 Chatbot** - 每日 50 条消息
- 🔧 **试用积分** - 新用户赠送 ¥5

**推荐指数：** ⭐⭐⭐⭐⭐ （中文最强，价格最低！）

---

## 🔐 注册和账号

### 注册要求

**Chatbot（免费）：**

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 手机号或邮箱 |
| 手机验证 | ✅ 必需 | 中国手机号 |
| 信用卡 | ❌ 不需要 | 完全免费 |

**API 服务（试用积分）：**

| 要求项 | 是否必需 | 说明 |
|--------|---------|------|
| 注册账户 | ✅ 必需 | 手机号或邮箱 |
| 实名认证 | ✅ 必需 | 上传身份证 |
| 信用卡绑定 | ❌ 不需要 | 支持支付宝/微信 |

### 注册步骤

#### Chatbot 注册（最简单）

1. 访问 [https://chat.deepseek.com](https://chat.deepseek.com)
2. 点击"注册"
3. 使用手机号或邮箱注册
4. 验证并设置密码
5. 立即开始使用

#### API 注册（需实名）

1. 访问 [https://platform.deepseek.com](https://platform.deepseek.com)
2. 注册账户
3. **完成实名认证**（上传身份证）
4. 等待审核（1-24小时）
5. 创建 API 密钥
6. 自动获得 ¥5 试用积分（7天有效）

---

## 🎯 提供的服务

DeepSeek 提供两种主要服务：

### 1. [Chatbot 服务](/services/chatbot/deepseek-chat)
- **类型：** Web 对话界面
- **访问地址：** https://chat.deepseek.com
- **特点：** 完全免费，每日 50 条消息
- **功能：** 联网搜索、代码执行、文件上传、思维链展示

### 2. [API 服务](/services/api/deepseek-api)
- **类型：** RESTful API
- **特点：** OpenAI 兼容，超低价格
- **模型：** deepseek-chat, deepseek-reasoner, deepseek-coder
- **试用：** 新用户赠送 ¥5（约 500M tokens）

---

## 📊 配额概览

### Chatbot 免费配额

| 限制类型 | 配额 | 说明 |
|---------|------|------|
| 每日消息数 | 50 messages | 所有模型共享 |
| 单次对话长度 | 无限制 | 支持超长上下文 |
| 高级功能 | 全部支持 | 联网、代码执行、文件上传 |

### API 试用积分

| 项目 | 详情 |
|------|------|
| **试用积分** | ¥5 人民币 |
| **可使用 tokens** | 约 500M tokens（chat 模型）|
| **有效期** | 注册后 7 天 |
| **充值后价格** | ¥1/M tokens（输入）<br>¥2/M tokens（输出）|

---

## 🤖 支持的模型

### DeepSeek V3 - 旗舰对话模型

| 特性 | 详情 |
|------|------|
| **参数量** | 671B |
| **上下文** | 64K tokens |
| **特点** | 中英文双语顶尖，知识丰富 |
| **适用** | 通用对话、知识问答 |

### DeepSeek R1 - 推理专家

| 特性 | 详情 |
|------|------|
| **类型** | 推理模型 |
| **特点** | 思维链可见，类似 OpenAI o1 |
| **擅长** | 数学、逻辑、科学问题 |
| **适用** | 复杂推理、算法设计 |

### DeepSeek Coder V2 - 代码专家

| 特性 | 详情 |
|------|------|
| **参数量** | 236B |
| **特点** | 专为代码优化 |
| **支持** | Python、Java、C++、JS 等 |
| **适用** | 代码生成、bug 修复、测试 |

---

## 🌟 核心优势

### 1. 强大的推理能力

**DeepSeek R1：**
- 思维链可见：可以看到模型的思考过程
- 数学专家：在数学、逻辑问题上表现优异
- 代码推理：复杂算法设计和优化

**推理示例：**
```
用户：一个水池有两个进水管和一个出水管，
     A管单独注满需要6小时，B管单独注满需要8小时，
     排水管单独排空需要12小时。
     如果同时打开三个管子，多久能注满？

DeepSeek R1 思维过程：
1. 设水池容量为24（6、8、12的最小公倍数）
2. A管速度：24÷6 = 4/小时
3. B管速度：24÷8 = 3/小时
4. 排水管速度：24÷12 = 2/小时
5. 三管同时：(4+3-2) = 5/小时
6. 注满时间：24÷5 = 4.8小时

答案：4.8小时，即4小时48分钟。
```

### 2. 超低价格优势

**价格对比：**

| 模型 | 输入价格 | 输出价格 | 相对便宜 |
|------|---------|---------|---------|
| **DeepSeek Chat** | ¥1/M tokens | ¥2/M tokens | 基准 |
| GPT-4 Turbo | ¥70/M tokens | ¥210/M tokens | **70-105倍** |
| Claude 3.5 | ¥21/M tokens | ¥105/M tokens | **21-53倍** |
| Gemini 1.5 Pro | ¥8.75/M tokens | ¥35/M tokens | **8.75-17.5倍** |

**DeepSeek 比 GPT-4 便宜 97%！** 🎉

### 3. 中文性能优化

- 中文和英文性能都极强
- 理解中文语境和文化
- 支持人民币结算
- 服务器在国内，速度快

### 4. 高级功能丰富

**Chatbot 功能：**
- ✅ 联网搜索（实时信息）
- ✅ 代码执行（Python、JS 等）
- ✅ 文件上传（PDF、Word、图片）
- ✅ 图片理解（多模态）
- ✅ 思维链展示（R1 模型）

---

## ⚠️ 使用注意事项

### 实名认证

- API 服务需要实名认证（上传身份证）
- Chatbot 不需要实名
- 审核通常 1-24 小时

### 试用积分

- 新用户赠送 ¥5
- 7 天内有效
- 用完后可充值，价格极低

### 内容审核

- 遵守中国法律法规
- 敏感内容会被拒绝
- 专注合法合规使用

### 配额管理

- Chatbot 每日 50 条消息
- 北京时间 00:00 重置
- API 按用量计费

---

## 📊 与其他服务对比

| 特性 | DeepSeek | Google AI Studio | Groq |
|------|---------|------------------|------|
| 免费 Chatbot | ✅ 50条/天 | ❌ | ❌ |
| 中文性能 | 🏆 顶尖 | 良好 | 一般 |
| 推理能力 | 🏆 R1 可见思维链 | 无 | 无 |
| API 价格 | 🏆 ¥1-2/M | 免费（有限） | 免费（有限） |
| 代码能力 | 🏆 Coder V2 专业 | 良好 | 良好 |
| 实名要求 | ✅ API需要 | ❌ | ❌ |
| 中国访问 | ✅ 极快 | 🔧 需科学上网 | 🔧 需稳定网络 |

---

## 💡 选择建议

### 选择 DeepSeek 的理由

✅ **强烈推荐：**
- 需要强大的中文能力
- 数学、推理、代码任务
- 希望看到模型思维过程
- 预算有限但需要高性能
- 中国大陆用户（速度快）

✅ **适合场景：**
- 学术研究和论文分析
- 代码开发和审查
- 数学问题求解
- 教育和学习辅助

❌ **不太适合：**
- 不能提供身份证（API）
- 需要其他语言优化
- 需要极高的免费配额

---

## 📈 模型性能

### 通用能力对比

| 模型 | 参数量 | 性能 | 价格 | 性价比 |
|------|--------|------|------|--------|
| DeepSeek V3 | 671B | 🏆 顶尖 | ¥1-2 | 🏆 极高 |
| GPT-4 Turbo | 未知 | 优秀 | ¥70-210 | 低 |
| Claude 3.5 | 未知 | 优秀 | ¥21-105 | 中 |

### 代码能力对比

| 模型 | HumanEval 得分 | 价格 |
|------|---------------|------|
| DeepSeek Coder V2 | 🏆 90%+ | ¥1-2 |
| GPT-4 | 85%+ | ¥70-210 |
| Claude 3.5 | 88%+ | ¥21-105 |

### 推理能力对比

| 模型 | 推理能力 | 思维链可见 | 价格 |
|------|---------|-----------|------|
| DeepSeek R1 | 🏆 顶尖 | ✅ | ¥5.5-19 |
| OpenAI o1 | 顶尖 | ❌ | ¥110-440 |
| Claude 3.5 | 优秀 | ❌ | ¥21-105 |

---

## 🔗 相关链接

- **官方网站：** [https://www.deepseek.com](https://www.deepseek.com)
- **Chatbot：** [https://chat.deepseek.com](https://chat.deepseek.com)
- **开发者平台：** [https://platform.deepseek.com](https://platform.deepseek.com)
- **API 文档：** [https://platform.deepseek.com/api-docs](https://platform.deepseek.com/api-docs)
- **定价说明：** [https://platform.deepseek.com/pricing](https://platform.deepseek.com/pricing)
- **GitHub：** [https://github.com/deepseek-ai](https://github.com/deepseek-ai)
- **论文：** [arXiv - DeepSeek](https://arxiv.org)（搜索 "DeepSeek"）
- **帮助中心：** [https://platform.deepseek.com/docs](https://platform.deepseek.com/docs)

---

## 📝 更新日志

- **2024年12月：** 发布 DeepSeek R1 推理模型
- **2024年11月：** 发布 DeepSeek V3（671B 参数）
- **2024年9月：** 发布 DeepSeek Coder V2
- **2024年：** 持续降低 API 价格，提升模型性能

---

## 📧 支持与反馈

- **官方邮箱：** support@deepseek.com
- **工单系统：** 通过平台提交工单
- **社区交流：** 微信公众号"DeepSeek"
- **商务合作：** business@deepseek.com
