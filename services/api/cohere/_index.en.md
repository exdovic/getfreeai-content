---
title: Cohere - API
weight: 5
comments: true
sidebar:
  open: true
---

## 📋 Service Information

**Provider:** [Cohere](/en/providers/cohere)  
**Service Type:** API Service  
**API Endpoint:** [https://api.cohere.ai](https://api.cohere.ai)  
**Free Tier:** Trial 1,000 calls/month, Production 10,000 calls/month

---

## 🎯 Service Overview

Cohere API provides enterprise-grade AI capabilities, particularly excelling in RAG, Embedding, and Rerank—the top choice for building intelligent search and knowledge bases.

**Key Advantages:**
- 🎯 **RAG Expert** - Industry-leading Retrieval Augmented Generation
- 📊 **Powerful Embedding** - Top-tier text vectorization
- 🔝 **Best Rerank** - Improve search accuracy by 20-30%
- 🌍 **Multilingual** - 100+ language support
- 💼 **Enterprise Grade** - Production 10,000 calls/month
- 🆓 **Free Start** - Trial 1,000 calls/month, no credit card required

---

## 🚀 Quick Start

### Prerequisites

**Trial Tier (Recommended):**
- ✅ Registered Cohere account
- ❌ No credit card required

**Production Tier:**
- ✅ Registered Cohere account
- ✅ Credit card verified (no charges)

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

**Command R+ Model:**
- 128K context window
- RAG optimized
- 100+ language support

**Basic Usage:**
```python {filename="Python"}
response = co.chat(
    message="Hello, introduce Cohere",
    model="command-r-plus"
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

### 2. Embed - Text Vectorization

**Features:**
- Convert text to vectors
- Semantic search
- Text clustering and classification

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

### 3. Rerank - Search Result Reordering

**Features:**
- Reorder search results
- Improve accuracy by 20-30%
- Essential RAG tool

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

### Trial Tier (Free)

| Item | Quota | Notes |
|------|------|------|
| Monthly Calls | 1,000 calls | No credit card required |
| Rate Limit | 10 req/min | Development and testing |
| Available Models | All | Chat, Embed, Rerank |

### Production Tier (Free)

| Item | Quota | Notes |
|------|------|------|
| Monthly Calls | 10,000 calls | Credit card verification required |
| Rate Limit | 1,000 req/min | Production-grade performance |
| Available Models | All | All enterprise features |

### API Call Counting

- **Chat:** 1 request = 1 call
- **Embed:** 1,000 texts = 1 call
- **Rerank:** 1 request = 1 call

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

### 1. Difference Between Trial and Production?

**Main Differences:**
| Feature | Trial | Production |
|------|-------|------------|
| Quota | 1,000 calls/month | 10,000 calls/month |
| Rate | 10 req/min | 1,000 req/min |
| Credit Card | Not required | Verification required |
| Charges | No | No within free quota |

### 2. How to Upgrade to Production?

**Steps:**
1. Login to Dashboard
2. Select "Upgrade to Production"
3. Add credit card (verification only, no charge)
4. Automatic upgrade

### 3. Why Is Embed So Cost-effective?

**Billing Method:**
- Every 1,000 texts = 1 call
- Example: Vectorizing 5,000 documents = 5 calls
- Very suitable for large-scale text processing

### 4. How to Check Remaining Quota?

**Method:**
- Login to https://dashboard.cohere.com
- Dashboard homepage shows current month usage

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

