# 🧠 Iterative Multi-Agent System with LangGraph + Gemini

## 📌 Overview
This project implements an **iterative multi-agent system** using **LangChain, LangGraph, FAISS, SerpAPI, and Google Gemini**.  
The agent is designed to **answer queries reliably and reduce hallucinations** by combining:

- 📚 **RAG (Retrieval-Augmented Generation)** → Internal PDFs stored in FAISS.
- 🌍 **Web Search** → Real-time info via SerpAPI.
- 🤖 **LLM Reasoning** → Fallback with Google Gemini.

---

## ⚡ Core Features

- ✅ **Multi-Source Intelligence** – Combines documents, web, and LLM.
- ✅ **Strict Priority Logic** – Query flow: `RAG → Web → LLM fallback`.
- ✅ **Validation Layer** – Ensures accuracy by rejecting unverifiable answers.
- ✅ **Iterative Execution** – Loops until answer passes validation.
- ✅ **Extensible API** – Backend ready for ReactJS front-end integration.

---

## 🔄 Agent Workflow

```text
User Query
   │
   ▼
[Input Node] → Receives query
   │
   ▼
[Analyzer Node] → Classifies type
   │
   ▼
[Researcher Node]
   ├─ Step 1 → RAG (PDFs via FAISS)
   ├─ Step 2 → Web Search (SerpAPI)
   └─ Step 3 → Gemini LLM Fallback
   │
   ▼
[Validator Node] → Cross-checks answer
   │
   ▼
[Responder Node] → Returns validated response
```

---

## 💡 Example Use-Cases

- Answering questions from internal research PDFs.
- Real-time updates (e.g., "Who is the Prime Minister of the UK?").
- Cross-checking company docs with public info.
- Acting as a reliable knowledge assistant.

---

## 🛠️ Tech Stack

- **LangChain + LangGraph** – Agent orchestration
- **FAISS + PyPDFLoader** – RAG with PDFs
- **HuggingFace Embeddings** – Semantic search
- **Google Gemini API** – LLM reasoning
- **SerpAPI** – Real-time web grounding
- **FastAPI** – Backend API for integration
- **ReactJS (planned)** – Front-end interface

---

## 🚀 Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/PadalaRuchitha/Langchain-Multi-Iterative-agent-.git
   cd Langchain-Multi-Iterative-agent-
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
   - Make sure you have Python 3.8+ installed.

3. **Set up environment variables:**  
   Create a `.env` file with the following (example):
   ```
   SERPAPI_API_KEY=your_serpapi_key
   GEMINI_API_KEY=your_gemini_key
   ```

---

## 🧑‍💻 Usage

- **Start the backend:**
  ```bash
  uvicorn app.main:app --reload
  ```
- Use the API endpoints as described in the FastAPI documentation (e.g., `/query`).

- **(Planned)**: Connect with the ReactJS frontend for interactive querying.

---

## 📂 Directory Structure

```
.
├── app/                  # FastAPI backend code
├── agents/               # Agent logic and workflows
├── data/                 # PDF and document storage
├── embeddings/           # Embedding models and utilities
├── tests/                # Test cases
├── requirements.txt
└── README.md
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to open an [issue](https://github.com/PadalaRuchitha/Langchain-Multi-Iterative-agent-/issues) or submit a pull request.

---

## 📄 License

[MIT License](LICENSE)

---

## 🙏 Acknowledgements

- [LangChain](https://github.com/langchain-ai/langchain)
- [LangGraph](https://github.com/langchain-ai/langgraph)
- [FAISS](https://github.com/facebookresearch/faiss)
- [SerpAPI](https://serpapi.com/)
- [Google Gemini](https://ai.google/discover/gemini/)
- [FastAPI](https://fastapi.tiangolo.com/)
- [HuggingFace](https://huggingface.co/)
