---
title: Cohere - API
weight: 5
comments: true
sidebar:
  open: true
---

## 📋 服务信息

**提供者：** [Cohere](/providers/cohere)  
**服务类型：** API 服务  
**API 端点：** [https://api.cohere.ai](https://api.cohere.ai)  
**免费类型：** Trial 1,000 calls/月，Production 10,000 calls/月

---

## 🎯 服务简介

Cohere API 提供企业级 AI 能力，特别擅长 RAG、Embedding 和 Rerank，是构建智能搜索和知识库的首选。

**核心优势：**
- 🎯 **RAG 专家** - 业界领先的检索增强生成
- 📊 **强大 Embedding** - 顶尖文本向量化
- 🔝 **最佳 Rerank** - 提升搜索准确度 20-30%
- 🌍 **多语言** - 100+ 语言支持
- 💼 **企业级** - Production 10,000 calls/月
- 🆓 **免费开始** - Trial 1,000 calls/月，无需信用卡

---

## 🚀 快速开始

### 前提条件

**Trial 层级（推荐）：**
- ✅ 已注册 Cohere 账户
- ❌ 无需信用卡

**Production 层级：**
- ✅ 已注册 Cohere 账户
- ✅ 已验证信用卡（不扣费）

详细步骤请参考：[Cohere 注册指南](/providers/cohere#注册和账号)

### 5 分钟快速示例

**安装 SDK：**
```bash {filename="Bash"}
pip install cohere
```

**基础对话：**
```python {filename="Python"}
import cohere

# 初始化客户端
co = cohere.Client('YOUR_API_KEY')

# 使用 Command R+ 对话
response = co.chat(
    message="什么是 RAG？请用简单的语言解释。",
    model="command-r-plus"
)

print(response.text)
```

---

## 🤖 核心模型和功能

### 1. Chat - 对话生成

**Command R+ 模型：**
- 128K 上下文窗口
- RAG 优化
- 100+ 语言支持

**基础使用：**
```python {filename="Python"}
response = co.chat(
    message="你好，介绍一下 Cohere",
    model="command-r-plus"
)
print(response.text)
```

**带 RAG 的对话：**
```python {filename="Python"}
# 基于文档的对话
response = co.chat(
    message="总结一下这些文档的要点",
    documents=[
        {
            "title": "AI 发展", 
            "text": "人工智能近年来发展迅速..."
        },
        {
            "title": "RAG 技术", 
            "text": "检索增强生成是一种..."
        }
    ],
    model="command-r-plus"
)

print(response.text)

# 查看引用的文档
for citation in response.citations:
    print(f"引用: {citation['text']}")
```

### 2. Embed - 文本向量化

**功能：**
- 将文本转换为向量
- 语义搜索
- 文本聚类和分类

**使用示例：**
```python {filename="Python"}
texts = [
    "机器学习是人工智能的一个分支",
    "深度学习使用神经网络",
    "RAG 结合了检索和生成"
]

response = co.embed(
    texts=texts,
    model="embed-multilingual-v3.0",
    input_type="search_document"
)

print(f"向量维度: {len(response.embeddings[0])}")
print(f"第一个文本的向量: {response.embeddings[0][:5]}...")
```

**语义搜索示例：**
```python {filename="Python"}
import numpy as np

# 1. 准备文档
documents = [
    "Python是一种编程语言",
    "机器学习使用算法从数据中学习",
    "今天天气很好",
    "深度学习是机器学习的子领域"
]

# 2. 生成文档向量
doc_embeddings = co.embed(
    texts=documents,
    model="embed-multilingual-v3.0",
    input_type="search_document"
).embeddings

# 3. 生成查询向量
query = "什么是机器学习？"
query_embedding = co.embed(
    texts=[query],
    model="embed-multilingual-v3.0",
    input_type="search_query"
).embeddings[0]

# 4. 计算相似度
scores = [
    np.dot(query_embedding, doc_emb)
    for doc_emb in doc_embeddings
]

# 5. 排序并显示结果
for idx in np.argsort(scores)[::-1]:
    print(f"{documents[idx]}: {scores[idx]:.4f}")
```

### 3. Rerank - 搜索结果重排序

**功能：**
- 对搜索结果重新排序
- 提升准确度 20-30%
- RAG 必备工具

**使用示例：**
```python {filename="Python"}
query = "什么是机器学习？"
documents = [
    "机器学习是AI的一个重要分支",
    "今天天气不错",
    "深度学习是机器学习的子领域",
    "我喜欢吃披萨"
]

response = co.rerank(
    query=query,
    documents=documents,
    model="rerank-multilingual-v3.0",
    top_n=2
)

# 显示重排序后的结果
for result in response.results:
    print(f"相关度 {result.relevance_score:.4f}: {documents[result.index]}")
```

---

## 🔢 配额和定价

### Trial 层级（免费）

| 项目 | 配额 | 说明 |
|------|------|------|
| 月度调用 | 1,000 calls | 无需信用卡 |
| 速率限制 | 10 req/min | 开发测试 |
| 可用模型 | 全部 | Chat, Embed, Rerank |

### Production 层级（免费）

| 项目 | 配额 | 说明 |
|------|------|------|
| 月度调用 | 10,000 calls | 需验证信用卡 |
| 速率限制 | 1,000 req/min | 生产级性能 |
| 可用模型 | 全部 | 所有企业功能 |

### API 调用计数

- **Chat：** 每次请求 = 1 call
- **Embed：** 每 1,000 texts = 1 call
- **Rerank：** 每次请求 = 1 call

---

## 💡 最佳实践

### ✅ 推荐做法

1. **构建 RAG 系统**
   ```python
   # 完整 RAG 流程
   # 1. Embed - 向量化文档
   # 2. 语义搜索 - 找到相关文档
   # 3. Rerank - 重排序结果
   # 4. Chat - 基于文档生成回答
   
   # 步骤 1: 向量化
   doc_embeddings = co.embed(
       texts=documents,
       model="embed-multilingual-v3.0",
       input_type="search_document"
   ).embeddings
   
   # 步骤 2: 搜索（使用向量数据库如 Pinecone）
   relevant_docs = search_vector_db(query, doc_embeddings)
   
   # 步骤 3: 重排序
   reranked = co.rerank(
       query=query,
       documents=relevant_docs,
       model="rerank-multilingual-v3.0",
       top_n=5
   )
   
   # 步骤 4: 生成回答
   response = co.chat(
       message=query,
       documents=[{"text": doc} for doc in reranked.results],
       model="command-r-plus"
   )
   ```

2. **优化 API 调用**
   ```python
   # Embed 很划算：1,000 texts = 1 call
   # 批量处理文本
   large_batch = ["text1", "text2", ..., "text1000"]
   embeddings = co.embed(
       texts=large_batch,
       model="embed-multilingual-v3.0"
   )  # 只消耗 1 call
   ```

3. **错误处理**
   ```python
   import time
   
   def call_with_retry(func, max_retries=3):
       for i in range(max_retries):
           try:
               return func()
           except Exception as e:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"错误，等待 {wait_time} 秒...")
                   time.sleep(wait_time)
               else:
                   raise
   ```

---

## 🔧 常见问题

### 1. Trial 和 Production 的区别？

**主要区别：**
| 特性 | Trial | Production |
|------|-------|------------|
| 配额 | 1,000 calls/月 | 10,000 calls/月 |
| 速率 | 10 req/min | 1,000 req/min |
| 信用卡 | 不需要 | 需要验证 |
| 扣费 | 不会 | 免费配额内不会 |

### 2. 如何升级到 Production？

**步骤：**
1. 登录 Dashboard
2. 选择 "Upgrade to Production"
3. 添加信用卡（仅验证，不扣费）
4. 自动升级

### 3. Embed 为什么这么划算？

**计费方式：**
- 每 1,000 texts = 1 call
- 例如：向量化 5,000 个文档 = 5 calls
- 非常适合大规模文本处理

### 4. 如何查看剩余配额？

**方法：**
- 登录 https://dashboard.cohere.com
- Dashboard 首页显示当月使用情况

---

## 📚 相关资源

### 官方文档
- [Cohere 完整介绍](/providers/cohere)
- [Coral Chatbot 使用指南](/services/chatbot/cohere-coral)
- [API 官方文档](https://docs.cohere.com)

### 工具和资源
- [Python SDK](https://github.com/cohere-ai/cohere-python)
- [示例代码](https://github.com/cohere-ai/notebooks)
- [Discord 社区](https://discord.gg/co-mmunity)

---

## 🌟 实战案例

### 案例 1：智能文档问答系统

```python {filename="Python"}
import cohere

co = cohere.Client('YOUR_API_KEY')

class DocumentQA:
    def __init__(self, documents):
        self.documents = documents
        # 向量化文档
        self.embeddings = co.embed(
            texts=documents,
            model="embed-multilingual-v3.0",
            input_type="search_document"
        ).embeddings
    
    def ask(self, question):
        # 1. 搜索相关文档
        query_emb = co.embed(
            texts=[question],
            model="embed-multilingual-v3.0",
            input_type="search_query"
        ).embeddings[0]
        
        # 2. 计算相似度并取 top 5
        scores = [np.dot(query_emb, doc_emb) for doc_emb in self.embeddings]
        top_indices = np.argsort(scores)[-5:][::-1]
        relevant_docs = [self.documents[i] for i in top_indices]
        
        # 3. Rerank 精排
        reranked = co.rerank(
            query=question,
            documents=relevant_docs,
            model="rerank-multilingual-v3.0",
            top_n=3
        )
        
        # 4. 生成回答
        response = co.chat(
            message=question,
            documents=[{"text": relevant_docs[r.index]} for r in reranked.results],
            model="command-r-plus"
        )
        
        return response.text

# 使用
docs = ["文档1内容...", "文档2内容...", "文档3内容..."]
qa_system = DocumentQA(docs)
answer = qa_system.ask("这些文档的主要内容是什么？")
print(answer)
```

### 案例 2：语义搜索引擎

```python {filename="Python"}
class SemanticSearch:
    def __init__(self, documents):
        self.documents = documents
        self.embeddings = co.embed(
            texts=documents,
            model="embed-multilingual-v3.0",
            input_type="search_document"
        ).embeddings
    
    def search(self, query, top_k=5):
        # 1. 向量搜索
        query_emb = co.embed(
            texts=[query],
            model="embed-multilingual-v3.0",
            input_type="search_query"
        ).embeddings[0]
        
        scores = [np.dot(query_emb, doc_emb) for doc_emb in self.embeddings]
        top_indices = np.argsort(scores)[-top_k*2:][::-1]
        candidates = [self.documents[i] for i in top_indices]
        
        # 2. Rerank 精排
        reranked = co.rerank(
            query=query,
            documents=candidates,
            model="rerank-multilingual-v3.0",
            top_n=top_k
        )
        
        # 3. 返回结果
        results = []
        for result in reranked.results:
            results.append({
                "document": candidates[result.index],
                "score": result.relevance_score
            })
        
        return results

# 使用
search_engine = SemanticSearch(documents)
results = search_engine.search("机器学习相关内容", top_k=3)
for r in results:
    print(f"{r['score']:.4f}: {r['document'][:100]}...")
```

---

**服务提供者：** [Cohere](/providers/cohere)
