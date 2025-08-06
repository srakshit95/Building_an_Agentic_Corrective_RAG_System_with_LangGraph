# 🤖 Agentic Corrective RAG System with LangGraph

This project demonstrates how to build an **Agentic Corrective Retrieval-Augmented Generation (RAG)** pipeline using [LangGraph](https://docs.langgraph.dev/). Inspired by the [Corrective RAG (CRAG) research paper](https://arxiv.org/pdf/2401.15884), this system introduces **self-corrective behavior** by detecting retrieval failures and invoking web search or fallback mechanisms.

---

## 🚀 What’s Inside

### 🧠 What is Corrective RAG?
Traditional RAG systems rely heavily on vector search. If the vector DB doesn’t return good results, the LLM often hallucinates. This notebook extends RAG by:
- **Monitoring the quality of retrieved documents**
- **Detecting knowledge gaps**
- **Triggering web search** or other agents when context is insufficient

### 🕸️ What is Agentic RAG?
By modeling RAG steps as **agent-driven graph nodes**, each stage (retrieval, reasoning, verification, fallback) becomes autonomous and orchestrated through **LangGraph**, enabling:
- Custom logic at each node
- Memory and stateful decision-making
- Corrective flows with optional tool use

---

## 🔧 Key Components

- ✅ **RAG pipeline (LangChain + LangGraph)**
- 🔎 **Context Quality Checker Agent**
- 🌐 **Web Search Agent** (fallback mechanism)
- 📚 **Document Retriever** (vector store + embeddings)
- 🧠 **LLM Answer Generator**
- 🔁 **LangGraph Flow:** Define stepwise logic with fail-safe branches

---

## 🧪 Use Case

User asks a question →  
📥 Retrieve documents →  
📉 Low relevance? →  
🔁 Trigger Web Search →  
✅ Combine retrieved + web context →  
🧠 Generate LLM response

---

## 📦 Setup Instructions

1. **Install dependencies**

```bash
pip install langchain langgraph openai faiss-cpu
