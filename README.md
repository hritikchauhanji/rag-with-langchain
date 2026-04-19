# 📚 RAG with LangChain + Ollama + Qdrant

A simple **Retrieval-Augmented Generation (RAG)** project that allows you to ask questions from a PDF using:

- Local embeddings (Ollama)
- Vector database (Qdrant)
- Local LLM (Gemma)

---

## 🚀 Features

- 📄 Load and process PDF documents  
- ✂️ Smart text chunking  
- 🧠 Generate embeddings using Ollama  
- 🗄️ Store vectors in Qdrant  
- 🔍 Semantic search  
- 🤖 Answer questions using local LLM (Gemma)  
- 🔒 Fully local (no API cost)

---

## 🏗️ Tech Stack

- LangChain  
- Ollama  
- Qdrant  
- Python  
- dotenv  

---

## 📂 Project Structure

```
rag-with-langchain/
│── qdrant_storage/      # Vector DB storage (DO NOT COMMIT)
│── venv/                # Virtual environment
│── .gitignore
│── chat.py              # Query + response
│── index.py             # Indexing script
│── nodejs.pdf           # Source document
│── docker-compose.yml   # Qdrant setup
│── requirements.txt
│── README.md
```

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the repository

```
git clone <your-repo-url>
cd rag-with-langchain
```

---

### 2️⃣ Create virtual environment

```
python3 -m venv venv
source venv/bin/activate
```

---

### 3️⃣ Install dependencies

```
pip install -r requirements.txt
```

---

### 4️⃣ Start Qdrant (Docker)

```
docker-compose up -d
```

👉 Runs Qdrant at:
```
http://localhost:6333
```

---

### 5️⃣ Install Ollama models

```
ollama pull gemma:2b
ollama pull mxbai-embed-large
```

---

## 📥 Indexing the PDF

Run:

```
python3 index.py
```

### What happens:
- Loads PDF (`nodejs.pdf`)
- Splits into chunks
- Converts into embeddings
- Stores in Qdrant

---

## 💬 Ask Questions

Run:

```
python3 chat.py
```

Then ask:

```
Ask something: What is Node.js?
```

---

## 🧠 How It Works

```
PDF → Chunking → Embeddings → Qdrant → Retrieval → Gemma → Answer
```

---

## 🔄 Workflow

1. Load PDF using `PyPDFLoader`  
2. Split text into chunks  
3. Generate embeddings via Ollama  
4. Store in Qdrant  
5. Retrieve relevant chunks  
6. Send context + query to Gemma  
7. Generate final answer  

---

## ⚠️ Important Notes

### ❌ Do NOT commit:

```
qdrant_storage/
venv/
.env
```

Add to `.gitignore`:

```
qdrant_storage/
venv/
.env
```

---

## 💡 Example Output

```
Ask something: What is Node.js?

🤖: Node.js is a runtime environment that allows you to run JavaScript on the server side...
(Page: 2)
```

---

## 📌 Future Improvements

- 🌐 Web UI (React / FastAPI)
- 📊 Better ranking (reranking models)
- 🧠 Memory-based chat
- 🔁 Streaming responses
- 📚 Multi-document support

---

## 🧑‍💻 Author

Hritik Chauhan

---

## ⭐ Summary

- Local RAG system  
- No API cost  
- Uses Ollama + Qdrant  
- Fast and production-ready base  
