---
title: "Cohere API - Enterprise RAG-Focused API Service"
linkTitle: "API - Cohere"
description: "Cohere provides RAG-focused API service, supporting Command R+ chat, Embed v3 vectorization, Rerank 3.5 reranking. 1,000 free requests monthly, enterprise-grade accuracy, optimized for RAG applications."
keywords:
  - Cohere API
  - RAG API
  - free enterprise AI API
  - Command R+ API
  - Embed API
  - Rerank API
  - vectorization API
  - enterprise AI interface
image: /images/logo.svg
weight: 5
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [Cohere](/en/providers/cohere)  
**Service Type:** API Service  
**API Endpoint:** [https://api.cohere.ai](https://api.cohere.ai)  
**Free Quota:** Trial 1,000 calls/month (resets monthly, no credit card required)

---

## 🎯 Service Overview

Cohere API provides enterprise-grade AI capabilities, particularly excelling in RAG, Embedding, and Rerank—the top choice for building intelligent search and knowledge bases. Provided by Canadian AI company Cohere (founded in 2019), serving global leading enterprises.

**Key Advantages:**
- 🎯 **RAG Expert** - Industry-leading Retrieval-Augmented Generation
- 📊 **Powerful Embedding** - Top-tier text and image vectorization
- 🔝 **Best Rerank** - Improve search accuracy by 20-30%
- 🌍 **Multilingual** - Supports 100+ languages with excellent Chinese performance
- 🆓 **Free to Start** - Trial 1,000 calls/month, no credit card required
- 🔄 **Monthly Reset** - Free quota resets monthly, continuously available
- 🆕 **Latest Models** - Command A (111B parameters, 256K context)

---

## 🚀 Quick Start

### Prerequisites

**Using Free API:**
- ✅ Registered Cohere account
- ❌ No credit card required
- ✅ Automatically receive Trial API Key (1,000 calls/month)

For detailed steps, see: [Cohere Registration Guide](/en/providers/cohere#registration-and-account)

### 5-Minute Quick Example

**Install SDK:**
```bash {filename="Bash"}
pip install cohere
```

**Basic Conversation:**
```python {filename="Python"}
import cohere

# Initialize client
co = cohere.Client('YOUR_API_KEY')

# Use Command R+ for chat
response = co.chat(
    message="What is RAG? Please explain in simple terms.",
    model="command-r-plus"
)

print(response.text)
```

---

## 🤖 Core Models and Features

### 1. Chat - Conversation Generation

**Command A Model (Latest) 🆕:**
- 111B parameters (111 billion)
- 256K context window
- 150% improved inference efficiency
- Enterprise-grade performance

**Command R+ Model:**
- 128K context window
- Deeply optimized for RAG
- 100+ language support

**Basic Usage:**
```python {filename="Python"}
# Using the latest Command A model
response = co.chat(
    message="Hello, introduce Cohere",
    model="command-a"  # or use "command-r-plus"
)
print(response.text)
```

**Chat with RAG:**
```python {filename="Python"}
# Document-based conversation
response = co.chat(
    message="Summarize the key points of these documents",
    documents=[
        {
            "title": "AI Development", 
            "text": "Artificial intelligence has developed rapidly in recent years..."
        },
        {
            "title": "RAG Technology", 
            "text": "Retrieval Augmented Generation is a..."
        }
    ],
    model="command-r-plus"
)

print(response.text)

# View cited documents
for citation in response.citations:
    print(f"Citation: {citation['text']}")
```

### 2. Embed - Text and Image Vectorization

**Features:**
- Convert text to high-quality vectors
- Support image vectorization 🆕
- Semantic search optimization
- Text clustering and classification
- Multilingual support (100+)

**Usage Example:**
```python {filename="Python"}
texts = [
    "Machine learning is a branch of artificial intelligence",
    "Deep learning uses neural networks",
    "RAG combines retrieval and generation"
]

response = co.embed(
    texts=texts,
    model="embed-multilingual-v3.0",
    input_type="search_document"
)

print(f"Vector dimension: {len(response.embeddings[0])}")
print(f"First text vector: {response.embeddings[0][:5]}...")
```

**Semantic Search Example:**
```python {filename="Python"}
import numpy as np

# 1. Prepare documents
documents = [
    "Python is a programming language",
    "Machine learning uses algorithms to learn from data",
    "The weather is nice today",
    "Deep learning is a subfield of machine learning"
]

# 2. Generate document vectors
doc_embeddings = co.embed(
    texts=documents,
    model="embed-multilingual-v3.0",
    input_type="search_document"
).embeddings

# 3. Generate query vector
query = "What is machine learning?"
query_embedding = co.embed(
    texts=[query],
    model="embed-multilingual-v3.0",
    input_type="search_query"
).embeddings[0]

# 4. Calculate similarity
scores = [
    np.dot(query_embedding, doc_emb)
    for doc_emb in doc_embeddings
]

# 5. Sort and display results
for idx in np.argsort(scores)[::-1]:
    print(f"{documents[idx]}: {scores[idx]:.4f}")
```

### 3. Rerank - Search Result Reordering (v3.5)

**Features:**
- Intelligently reorder search results
- Improve accuracy by 20-30%
- Essential tool for RAG applications
- Industry-best performance
- Supports 100+ languages

**Usage Example:**
```python {filename="Python"}
query = "What is machine learning?"
documents = [
    "Machine learning is an important branch of AI",
    "The weather is nice today",
    "Deep learning is a subfield of machine learning",
    "I like pizza"
]

response = co.rerank(
    query=query,
    documents=documents,
    model="rerank-multilingual-v3.0",
    top_n=2
)

# Display reranked results
for result in response.results:
    print(f"Relevance {result.relevance_score:.4f}: {documents[result.index]}")
```

---

## 🔢 Quotas and Pricing

### Trial Free Tier

| Item | Quota | Notes |
|------|------|------|
| Monthly Calls | 1,000 calls | No credit card required |
| Chat Rate | 20 req/min | Command series |
| Embed Rate | 2,000 inputs/min | Batch processing |
| Rerank Rate | 10 req/min | Reranking |
| Available Models | All | Command A, R+, Embed, Rerank |
| Credit Card Required | ❌ No | No payment info needed |

### Production Paid Tier

| Item | Notes |
|------|------|
| Billing Method | Pay-as-you-go |
| Rate Limit | 500-1,000 req/min |
| Credit Card Required | ✅ Yes |

### API Call Counting (Trial Tier)

- **Chat:** Each API request = 1 call
- **Embed:** Each API request = 1 call (supports batch processing)
- **Rerank:** Each API request = 1 call
- **Quota Reset:** Automatically resets monthly, continuously available
- **Tip:** Embed supports processing multiple texts in one request for efficiency

---

## 💡 Best Practices

### ✅ Recommended Practices

1. **Build RAG System**
   ```python
   # Complete RAG workflow
   # 1. Embed - vectorize documents
   # 2. Semantic search - find relevant documents
   # 3. Rerank - reorder results
   # 4. Chat - generate answer based on documents
   
   # Step 1: Vectorization
   doc_embeddings = co.embed(
       texts=documents,
       model="embed-multilingual-v3.0",
       input_type="search_document"
   ).embeddings
   
   # Step 2: Search (using vector DB like Pinecone)
   relevant_docs = search_vector_db(query, doc_embeddings)
   
   # Step 3: Rerank
   reranked = co.rerank(
       query=query,
       documents=relevant_docs,
       model="rerank-multilingual-v3.0",
       top_n=5
   )
   
   # Step 4: Generate answer
   response = co.chat(
       message=query,
       documents=[{"text": doc} for doc in reranked.results],
       model="command-r-plus"
   )
   ```

2. **Optimize API Calls**
   ```python
   # Embed is cost-effective: 1,000 texts = 1 call
   # Batch process texts
   large_batch = ["text1", "text2", ..., "text1000"]
   embeddings = co.embed(
       texts=large_batch,
       model="embed-multilingual-v3.0"
   )  # Only consumes 1 call
   ```

3. **Error Handling**
   ```python
   import time
   
   def call_with_retry(func, max_retries=3):
       for i in range(max_retries):
           try:
               return func()
           except Exception as e:
               if i < max_retries - 1:
                   wait_time = 2 ** i
                   print(f"Error, waiting {wait_time} seconds...")
                   time.sleep(wait_time)
               else:
                   raise
   ```

---

## 🔧 Common Issues

### 1. Is the Trial Free Tier Sufficient?

**Use Cases:**
- ✅ Personal development and learning
- ✅ Small-scale applications (e.g., smart search for personal blog)
- ✅ Prototype development and testing
- ⚠️ For higher quotas, consider paid Production tier

### 2. Does the Free Quota Expire?

**No Expiration:**
- Trial API Key can be used long-term
- Monthly quota automatically resets
- No need to worry about credits running out

### 3. Why Is Embed So Cost-effective?

**Billing Method:**
- 1,000 texts = 1 call
- Example: Vectorizing 5,000 documents = 5 calls
- Very suitable for large-scale text processing

### 4. How to Check Remaining Quota?

**Method:**
- Login to https://dashboard.cohere.com
- Dashboard homepage displays current month's usage

### 5. What If I Need Higher Quota?

**Upgrade to Production:**
1. Select "Go to Production" in Dashboard
2. Add credit card information
3. Pay-as-you-go based on usage
4. Get higher rate limits

---

## 📚 Related Resources

### Official Documentation
- [Cohere Complete Guide](/en/providers/cohere)
- [Coral Chatbot Usage Guide](/en/services/chatbot/cohere)
- [API Official Docs](https://docs.cohere.com)

### Tools and Resources
- [Python SDK](https://github.com/cohere-ai/cohere-python)
- [Example Code](https://github.com/cohere-ai/notebooks)
- [Discord Community](https://discord.gg/co-mmunity)

---

## 🌟 Practical Cases

### Case 1: Intelligent Document Q&A System

```python {filename="Python"}
import cohere

co = cohere.Client('YOUR_API_KEY')

class DocumentQA:
    def __init__(self, documents):
        self.documents = documents
        # Vectorize documents
        self.embeddings = co.embed(
            texts=documents,
            model="embed-multilingual-v3.0",
            input_type="search_document"
        ).embeddings
    
    def ask(self, question):
        # 1. Search relevant documents
        query_emb = co.embed(
            texts=[question],
            model="embed-multilingual-v3.0",
            input_type="search_query"
        ).embeddings[0]
        
        # 2. Calculate similarity and get top 5
        scores = [np.dot(query_emb, doc_emb) for doc_emb in self.embeddings]
        top_indices = np.argsort(scores)[-5:][::-1]
        relevant_docs = [self.documents[i] for i in top_indices]
        
        # 3. Rerank for precision
        reranked = co.rerank(
            query=question,
            documents=relevant_docs,
            model="rerank-multilingual-v3.0",
            top_n=3
        )
        
        # 4. Generate answer
        response = co.chat(
            message=question,
            documents=[{"text": relevant_docs[r.index]} for r in reranked.results],
            model="command-r-plus"
        )
        
        return response.text

# Usage
docs = ["Document 1 content...", "Document 2 content...", "Document 3 content..."]
qa_system = DocumentQA(docs)
answer = qa_system.ask("What is the main content of these documents?")
print(answer)
```

### Case 2: Semantic Search Engine

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
        # 1. Vector search
        query_emb = co.embed(
            texts=[query],
            model="embed-multilingual-v3.0",
            input_type="search_query"
        ).embeddings[0]
        
        scores = [np.dot(query_emb, doc_emb) for doc_emb in self.embeddings]
        top_indices = np.argsort(scores)[-top_k*2:][::-1]
        candidates = [self.documents[i] for i in top_indices]
        
        # 2. Rerank for precision
        reranked = co.rerank(
            query=query,
            documents=candidates,
            model="rerank-multilingual-v3.0",
            top_n=top_k
        )
        
        # 3. Return results
        results = []
        for result in reranked.results:
            results.append({
                "document": candidates[result.index],
                "score": result.relevance_score
            })
        
        return results

# Usage
search_engine = SemanticSearch(documents)
results = search_engine.search("Machine learning related content", top_k=3)
for r in results:
    print(f"{r['score']:.4f}: {r['document'][:100]}...")
```

---

**Service Provider:** [Cohere](/en/providers/cohere)

