# Retrieval-Augmented Generation (RAG) System

A production-ready RAG system for multi-format document Q&A using FastAPI, Streamlit, FAISS, open-source embeddings, and Groq LLM (ChatGroq).

## Features
- **Multi-format document support:** PDF, DOCX, TXT, CSV, Excel, images (with OCR)
- **Text extraction:** Uses `unstructured` and OCR (`pytesseract`)
- **Embeddings:** Open-source model via `sentence-transformers`
- **Vector DB:** Local FAISS for fast retrieval
- **LLM:** Groq API (ChatGroq, e.g., Llama3)
- **Frontend:** Streamlit chat interface for upload and Q&A
- **Backend:** FastAPI
- **Memory:** Langchain chat memory
- **Secure secrets:** Uses `.env` for API keys

## Project Structure
```
rag_system/
├── backend/
│   ├── main.py
│   ├── rag_engine.py
│   ├── file_utils.py
│   ├── config.py
│   ├── requirements.txt
│   └── .env              # (Not tracked by git, holds secrets)
├── frontend/
│   ├── app.py
│   └── requirements.txt
└── README.md
```

## Setup

### 1. Clone the repository
```
git clone <your-repo-url>
cd <repo-folder>
```

### 2. Backend Setup
```
cd backend
python -m venv venv
venv\Scripts\activate  # On Windows
pip install -r requirements.txt
```
- Create a `.env` file in `backend/`:
  ```
  GROQ_API_KEY=your_groq_api_key_here
  ```
- Make sure Tesseract OCR is installed and on your PATH (for OCR support).

### 3. Frontend Setup
```
cd ../frontend
pip install -r requirements.txt
```

### 4. Run the System
- **Start backend:**
  ```
  cd backend
  venv\Scripts\activate
  uvicorn main:app --reload
  ```
- **Start frontend:**
  ```
  cd ../frontend
  streamlit run app.py
  ```

## Usage
- Upload one or more documents via the Streamlit sidebar.
- Ask questions in the chat interface.
- The system retrieves relevant chunks and uses Groq LLM to answer.

## Security
- **Never commit your `.env` file or any secrets to git!**
- This project uses `.gitignore` to protect secrets and virtual environments.

## License
MIT

---
**Author:** Zain Ul Abaiden
