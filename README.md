# 🧠 GenAI RAG QA Bot

> An AI-powered Question Answering system — upload any PDF and chat with it using **Retrieval-Augmented Generation (RAG)**.

[![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)](https://python.org)
[![LangChain](https://img.shields.io/badge/LangChain-0.2.17-green?style=flat-square)](https://langchain.com)
[![Mistral AI](https://img.shields.io/badge/LLM-Mistral_AI-orange?style=flat-square)](https://mistral.ai)
[![ChromaDB](https://img.shields.io/badge/VectorDB-ChromaDB-purple?style=flat-square)](https://trychroma.com)
[![Gradio](https://img.shields.io/badge/UI-Gradio-yellow?style=flat-square)](https://gradio.app)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UDlGI99L5I_08xsCI2PiCp1IgbbneehR?usp=sharing)

---

## 📖 Overview

**GenAI RAG QA Bot** lets you upload PDF documents and ask natural language questions about the content. It uses **semantic search** to find relevant context and **Mistral LLM** to generate accurate, context-aware answers — no hallucinations, just grounded responses.

---

## 🚀 Live Demo
 
> **No setup needed — run it directly in your browser!**
 
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UDlGI99L5I_08xsCI2PiCp1IgbbneehR?usp=sharing)
 
👉 **[Click here to open in Google Colab](https://colab.research.google.com/drive/1UDlGI99L5I_08xsCI2PiCp1IgbbneehR?usp=sharing)**
 
1. Open the Colab link above
2. Run all cells (`Runtime → Run All`)
3. Upload a PDF and start asking questions!
---

## ✨ Features

| Feature | Description |
|---|---|
| 📄 PDF Upload | Upload any PDF document directly via the UI |
| 🔍 Semantic Search | Finds the most relevant chunks using vector embeddings |
| 🤖 AI-Powered Answers | Mistral LLM generates grounded, context-aware responses |
| ⚡ Fast Retrieval | ChromaDB enables millisecond-level similarity search |
| 🧩 Modular Pipeline | Clean LangChain pipeline — easy to extend |
| 🎯 RAG Architecture | Retrieval-Augmented Generation prevents hallucinations |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **LLM** | [Mistral AI](https://mistral.ai) |
| **Framework** | [LangChain](https://langchain.com) |
| **Vector Database** | [ChromaDB](https://trychroma.com) |
| **Embeddings** | Sentence Transformers (`all-MiniLM-L6-v2`) |
| **UI** | [Gradio](https://gradio.app) |
| **Language** | Python 3.10+ |

---

## 🏗️ Architecture

```
PDF Document
    │
    ▼
┌─────────────────┐
│  PDF Loader     │  ← PyPDF
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Text Splitter  │  ← Recursive Character Text Splitter
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Embeddings    │  ← Sentence Transformers (MiniLM)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  ChromaDB       │  ← Vector Store & Retriever
└────────┬────────┘
         │
    User Query
         │
         ▼
┌─────────────────┐
│  Mistral LLM    │  ← Answer Generation
└────────┬────────┘
         │
         ▼
    ✅ Final Answer
```

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/genai-rag-qa-bot.git
cd genai-rag-qa-bot
```

### 2. Install Dependencies

```bash
pip install -q \
  langchain==0.2.17 \
  langchain-community==0.2.17 \
  langchain-core==0.2.43 \
  langchain-text-splitters==0.2.4 \
  langchain-mistralai \
  chromadb \
  pypdf \
  sentence-transformers \
  gradio
```

> 💡 Or install from requirements file: `pip install -r requirements.txt`

---

## 🔑 Configuration

Set your **Mistral API Key** before running:

```python
import os
os.environ["MISTRAL_API_KEY"] = "your_api_key_here"
```

> Get your free API key at [console.mistral.ai](https://console.mistral.ai)

---

## ▶️ Run the Application

```bash
intelligent-document-qa-bot.ipynb
```

Then open your browser at `http://localhost:7860`

**Or try it instantly on Google Colab →**  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UDlGI99L5I_08xsCI2PiCp1IgbbneehR?usp=sharing)

---

## 🖥️ UI Workflow

```
Step 1 → Upload your PDF document
Step 2 → Type your question in the input box
Step 3 → Get an AI-generated answer grounded in document content
```

---
<img width="1512" height="828" alt="Output_Image" src="https://github.com/user-attachments/assets/bb39a8f9-7dc7-44ea-b97c-a8c0c64b4c20" />


## 🧪 Example Questions to Try

```
📌 "What is this document about?"
📌 "Summarize the key points"
📌 "List the main findings or conclusions"
📌 "Explain [specific concept] mentioned in the document"
📌 "What does the author recommend?"
```

---

## 💡 Key Concepts

- **Retrieval-Augmented Generation (RAG)** — combines retrieval + generation for accurate answers
- **Vector Embeddings** — converts text into numerical representations for semantic similarity
- **Document Chunking** — splits large PDFs into manageable pieces for efficient retrieval
- **Semantic Search** — finds contextually similar content, not just keyword matches
- **Prompt Engineering** — structures context + query for optimal LLM output

---

## 📈 Roadmap

- [ ] Multi-PDF support with document selection
- [ ] Persistent vector storage across sessions
- [ ] Conversation memory (multi-turn chat)
- [ ] Streaming responses (token-by-token)
- [ ] FastAPI backend with REST endpoints
- [ ] Docker deployment support
- [ ] HuggingFace Spaces deployment

---

## 📂 Project Structure (You Can Make Like this)

```
genai-rag-qa-bot/
│
├── app.py                  # Main Gradio application
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
│
├── src/
│   ├── loader.py           # PDF loading & text splitting
│   ├── embeddings.py       # Embedding model setup
│   ├── vectorstore.py      # ChromaDB vector store
│   └── chain.py            # LangChain RAG pipeline
│
└── sample_docs/
    └── sample.pdf          # Sample PDF for testing
```

---

## 👨‍💻 Author

**Babloo Kumar**  
QA Automation Engineer | GenAI Developer

[![Portfolio](https://img.shields.io/badge/Portfolio-bablookumar.netlify.app-blue?style=flat-square&logo=netlify)](https://bablookumar.netlify.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com)

---

## ⭐ Support

If this project helped you, please consider giving it a ⭐ — it motivates me to build more!

---

## 🏷️ Tags

`rag` `langchain` `genai` `llm` `chatbot` `mistral` `chromadb` `ai` `document-qa` `python` `nlp` `vector-search` `pdf-qa` `prompt-engineering`
