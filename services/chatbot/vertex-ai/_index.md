---
title: Google Vertex AI - Studio
weight: 6
comments: true
sidebar:
  open: true
---


## 📋 服务信息

**提供者：** [Google Vertex AI](/providers/google-vertex-ai)  
**服务类型：** Web 界面（Vertex AI Studio）  
**访问地址：** [https://console.cloud.google.com/vertex-ai/generative](https://console.cloud.google.com/vertex-ai/generative)  
**免费类型：** 试用积分（$300，90天）

---

## 🎯 服务简介

Vertex AI Studio 是 Google Cloud 提供的可视化 AI 测试平台，让您无需编程即可测试 Gemini 模型的强大能力。

**核心优势：**
- 🎨 **可视化界面** - 无需编程
- 🌟 **Gemini 1.5 Pro** - 2M 超长上下文
- 🖼️ **多模态** - 文本、图像、音频、视频
- 🎛️ **参数调节** - 自定义生成参数
- 💾 **Prompt 管理** - 保存和复用
- 🏢 **企业功能** - 完整工具链

---

## 🚀 如何使用

### 前提条件

- ✅ 已创建 Google Cloud 账户
- ✅ 已激活 $300 试用积分
- ✅ 已启用 Vertex AI API

详细注册步骤请参考：[Vertex AI 注册指南](/providers/google-vertex-ai#注册和账号)

### 使用步骤

#### 步骤 1：访问 Vertex AI Studio

1. 登录 https://console.cloud.google.com
2. 搜索 "Vertex AI"
3. 选择 "Vertex AI Studio"
4. 或直接访问：https://console.cloud.google.com/vertex-ai/generative

#### 步骤 2：选择模型

在 Studio 界面选择模型：

| 模型 | 上下文 | 适用场景 |
|------|--------|---------|
| **Gemini 1.5 Pro** | 2M tokens | 复杂任务、长文档 |
| **Gemini 1.5 Flash** | 1M tokens | 快速响应、高频 |

#### 步骤 3：开始测试

1. 输入 Prompt
2. 上传文件（可选）
3. 调整参数（可选）
4. 点击"Generate"
5. 查看结果

---

## 🎨 功能特性

### 1. 多模态测试

**支持输入：**
- 📝 文本
- 🖼️ 图像（JPG、PNG、WEBP）
- 🎵 音频（MP3、WAV）
- 🎬 视频（MP4、MOV）

**应用场景：**
- 图像识别和描述
- 视频内容分析
- 音频转文字
- 多模态问答

### 2. 超长上下文

**Gemini 1.5 Pro：**
- 2M tokens 上下文
- 相当于 1,400 页书
- 分析完整电影脚本
- 处理大量文档

### 3. Prompt 设计

**功能：**
- Prompt 编辑器
- 参数调节
- 示例库
- 最佳实践

### 4. 参数调整

| 参数 | 范围 | 说明 |
|------|------|------|
| **Temperature** | 0-2 | 控制创造性 |
| **Top P** | 0-1 | 核采样 |
| **Top K** | 1-40 | 候选词数量 |
| **Max Output Tokens** | 1-8192 | 输出长度 |

### 5. 批量测试

**功能：**
- 批量 Prompt 测试
- 结果对比
- 性能评估

---

## 🔢 使用成本

### 基于试用积分

使用 Vertex AI Studio 会消耗 $300 试用积分：

**Gemini 1.5 Pro：**
- 输入：$1.25/M tokens (≤128K)
- 输出：$5/M tokens
- $300 ≈ 240M input tokens

**Gemini 1.5 Flash：**
- 输入：$0.075/M tokens (≤128K)
- 输出：$0.30/M tokens
- $300 ≈ 4B input tokens

---

## 💡 使用技巧

### ✅ 最佳实践

1. **优先使用 Flash**
   - 成本更低（便宜 16 倍）
   - 速度更快
   - 适合大部分场景

2. **充分利用长上下文**
   - 上传完整文档
   - 分析长对话历史
   - 处理大量数据

3. **管理试用积分**
   - 监控使用量
   - 设置预算警报
   - 避免意外消耗

4. **Prompt 优化**
   - 使用 Prompt 库
   - A/B 测试
   - 保存最佳版本

### ⚠️ 注意事项

1. **成本控制**
   - 注意 $300 限额
   - 90 天有效期
   - 监控消耗速度

2. **网络要求**
   - 需要稳定网络
   - 中国大陆需科学上网
   - 上传大文件需时间

3. **数据隐私**
   - 谨慎上传敏感数据
   - 理解数据使用政策
   - 使用 GCP 安全功能

---

## 🔧 常见问题

### 1. 如何查看剩余积分？

**方法：**
1. GCP Console 顶部
2. 点击"Billing"
3. 查看试用积分余额

### 2. 90 天后会怎样？

**说明：**
- 试用结束后不自动扣费
- 需要手动升级到付费
- 可以选择不升级

### 3. Pro 和 Flash 如何选择？

**建议：**
- 测试用 Flash（更便宜）
- 复杂任务用 Pro
- 长文档用 Pro（2M 上下文）

---

## 📚 相关资源

### 文档和教程
- [Vertex AI 完整介绍](/providers/google-vertex-ai)
- [API 服务使用指南](/services/api/vertex-ai-api)
- [官方文档](https://cloud.google.com/vertex-ai/docs)

---

**服务提供者：** [Google Vertex AI](/providers/google-vertex-ai)
