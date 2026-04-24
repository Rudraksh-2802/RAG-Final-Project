# 🤖 RAG-Based Customer Support Assistant

**LangGraph · ChromaDB · HITL · FastAPI**

---

## 📌 Overview

This project implements a **Retrieval-Augmented Generation (RAG)** based customer support assistant.

It answers user queries using a **PDF knowledge base**, retrieves relevant context using embeddings, and generates accurate responses using an LLM.
If the system is uncertain or detects sensitive queries, it automatically escalates to a **Human-in-the-Loop (HITL)** system.

---

## 🚀 Features

* 📄 PDF Knowledge Base Ingestion
* 🔍 Semantic Search using Embeddings
* 🧠 Context-Aware Answer Generation (RAG)
* 🔀 Graph-based Workflow using LangGraph
* 🎯 Intent-based Conditional Routing
* 🧑‍💼 Human-in-the-Loop (HITL) Escalation
* ⚡ FastAPI Backend with Interactive UI

---

## 🏗️ System Architecture

```text
User Query
   ↓
Input Node (Validation + Intent)
   ↓
Retrieval (ChromaDB)
   ↓
Generation (LLM)
   ↓
Routing Decision
   ↓
[Answer] OR [Escalation]
```

---

## ⚙️ Tech Stack

* **Python 3.11**
* **FastAPI**
* **LangGraph**
* **ChromaDB**
* **Sentence Transformers (HuggingFace)**
* **OpenAI / GROQ (LLM)**

---

## 📂 Project Structure

```
backend/
 ├── document_processor.py
 ├── embedder.py
 ├── vector_store.py
 ├── query_processor.py
 ├── graph_engine.py
 ├── hitl_handler.py

main.py
requirements.txt
.env
```

---

## 🛠️ Setup & Run

### 1️⃣ Create Virtual Environment

```
py -3.11 -m venv venv
venv\Scripts\activate
```

### 2️⃣ Install Dependencies

```
pip install -r requirements.txt
```

### 3️⃣ Add Environment Variables

Create `.env` file:

```
GROQ_API_KEY=your_api_key_here
```

---

### 4️⃣ Run the Application

```
uvicorn main:app --reload
```

---

### 5️⃣ Open in Browser

```
http://localhost:8000
```

---

## 📊 How It Works

1. Upload a PDF knowledge base
2. System splits into chunks
3. Converts text → embeddings
4. Stores in ChromaDB
5. User asks a query
6. Relevant chunks retrieved
7. LLM generates answer
8. System decides:

   * Answer directly
   * OR escalate to human

---

## 🧪 Example Queries

* What is the return policy?
* How long does shipping take?
* I want a refund, this is fraud!
* Explain quantum computing

---

## ⚠️ Escalation Logic

The system escalates when:

* Low retrieval confidence
* Sensitive keywords (refund, fraud, legal)
* Complex queries
* Insufficient context

---

## 📈 Future Improvements

* Multi-document support
* Chat memory
* Web UI (React)
* Hybrid retrieval (BM25 + embeddings)
* Deployment (AWS / Docker)

---

## 👨‍💻 Author

**Rudraksh Joshi**

---

## 🏁 Conclusion

This project demonstrates a **complete RAG pipeline with decision-making capability**, combining retrieval, generation, and workflow orchestration with real-world support scenarios.

---
