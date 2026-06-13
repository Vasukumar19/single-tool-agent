# 🤖 Memory-Aware Multi-Tool AI Assistant

A personalized AI assistant built with LangChain, Groq LLMs, FAISS, and HuggingFace embeddings.

The system combines Retrieval-Augmented Generation (RAG), long-term memory, semantic search, web search, and intent-based routing to provide context-aware and personalized responses.

---

## 🏗️ Architecture

```text
User Query
     ↓
Intent Router
     ↓
 ┌───────────────────────────────────┐
 │   simple        → Direct Response │
 │   memory        → Memory Update   │
 │   tool          → Tool Agent      │
 │   personal_tool → Personalized AI │
 └───────────────────────────────────┘
                 ↓
            ReAct Agent
                 ↓
 ┌─────────────┬─────────────┬─────────────┐
 │ Web Search  │ Calculator  │ RAG Search  │
 └─────────────┴─────────────┴─────────────┘
                 ↓
             Response
```

---

## ✨ Features

### Intent-Based Routing

Classifies user requests into:

* `simple`
* `memory`
* `tool`
* `personal_tool`

and dynamically routes execution through the appropriate workflow.

### Profile Memory

Stores persistent user information such as:

* Goals
* Interests
* Preferences
* Education
* Profession

Stored in JSON format for fast retrieval.

### Semantic Memory

Stores long-term memories such as:

* Projects completed
* Courses completed
* Skills learned
* Achievements

Uses FAISS vector search for semantic retrieval.

### Retrieval-Augmented Generation (RAG)

Supports querying custom PDF and text documents.

Features:

* Automatic document loading
* Chunking using RecursiveCharacterTextSplitter
* FAISS vector indexing
* Semantic retrieval

### Tool-Using Agent

The assistant can autonomously decide when to use:

* Web Search
* Calculator
* Document Retrieval

using LangChain's ReAct Agent architecture.

### Persistent Conversation History

Maintains conversation history across sessions for improved context awareness.

---

## 🛠️ Tech Stack

| Component          | Technology         |
| ------------------ | ------------------ |
| LLM                | Groq Llama 3.3 70B |
| Framework          | LangChain          |
| Vector Database    | FAISS              |
| Embeddings         | HuggingFace MiniLM |
| Document Retrieval | RAG                |
| Search Engine      | DuckDuckGo         |
| Memory Storage     | JSON + FAISS       |
| Language           | Python             |

---

## 📂 Project Structure

```text
project/
│
├── documents/
│   ├── *.pdf
│   └── *.txt
│
├── memory/
│   ├── memory.json
│   ├── chat_history.json
│   └── semantic_memory/
│
├── faiss_index/
│
├── agent.py
├── requirements.txt
├── .env
└── README.md
```

---

## 🚀 Key Concepts Demonstrated

* Agentic AI
* ReAct Reasoning
* Tool Calling
* Intent Classification
* Retrieval-Augmented Generation (RAG)
* Long-Term Memory Systems
* Semantic Search
* Vector Databases
* Personalized AI Assistants
* Context-Aware Reasoning

---

## 🎯 Example Queries

```text
What is the latest AI news?

Summarize the company handbook.

What projects have I completed?

What technologies do I like?

Calculate sqrt(144) * 25

What do you remember about me?
```

---

## 📈 Future Improvements

* LangGraph Workflow Orchestration
* Reflection & Self-Correction Loops
* Episodic Memory
* Hybrid Retrieval (BM25 + Vector Search)
* Streaming Responses
* Source Citation Generation

---

## Author

Vasu Kumar

Built as part of an AI Engineering learning journey focused on Agentic AI, RAG systems, memory architectures, and LLM-powered applications.
