# 🩺 Medical Q&A Chatbot using Local RAG (LLaMA/Mistral)

This project is a fully offline Medical Question-Answering Chatbot built using **local Retrieval-Augmented Generation (RAG)** techniques. It answers queries by consulting content from a medical textbook PDF (`Gale Encyclopedia of Medicine - Vol 1`) using a local **Mistral-7B LLaMA model** and **FAISS** vector store — with **zero external API calls**.

---

## ✅ Features

- 🔍 **Retrieval-Augmented Generation (RAG)** Pipeline
- 📄 Ingests and processes a PDF medical book
- 🔐 Runs fully offline with **no OpenAI / cloud APIs**
- 🧠 Uses `sentence-transformers/all-MiniLM-L6-v2` for embeddings
- 📚 Stores embeddings in a **FAISS** index
- 🦙 Generates answers using **Mistral-7B Instruct** (`mistral-7b-instruct.Q4_K_M.gguf`)
- 💬 Streamlit-based Chat Interface for Q&A

---

## 🚀 Architecture & Workflow

```
PDF ➜ Text ➜ Chunking ➜ Embeddings ➜ FAISS Index
                    ↓
             User Question
                    ↓
             Retrieve top chunks
                    ↓
             LLaMA/Mistral model
                    ↓
               Final Answer
```

---

## 🧠 Tech Stack

| Component          | Tool / Model                                |
|-------------------|----------------------------------------------|
| Embedding Model    | SentenceTransformers MiniLM-L6-v2            |
| Vector Store       | FAISS (Local)                                |
| LLM Generator      | Mistral 7B Instruct (GGUF)                   |
| UI                 | Streamlit                                    |
| Framework          | LangChain + llama-cpp-python                 |

---

## 🖥 Streamlit UI Preview

```
+-----------------------------------------------+
| 🩺 Medical Chatbot (PDF-based)                 |
|-----------------------------------------------|
| Ask any medical question based on the book    |
|                                               |
|   [ "What is asthma?" ]               [Ask]   |
|                                               |
| You: What is dementia?                        |
| Bot: Dementia is a group of symptoms ...      |
+-----------------------------------------------+
```

---

## 📂 Folder Structure

```
medical-chatbot/
│
├── app.py                          # Streamlit application
├── medical_faiss_index/            # Saved FAISS vector index
├── mistral-7b-instruct.Q4_K_M.gguf # Local LLaMA/Mistral model
├── requirements.txt
├── README.md
```

---

## ✅ Setup Instructions (Local)

1. Clone this repo and place your files inside:
   - `medical_faiss_index/` folder (generated via notebook)
   - `mistral-7b-instruct.Q4_K_M.gguf` model

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Streamlit chatbot:
   ```bash
   streamlit run app.py
   ```

---

## 📄 Disclaimer

> This chatbot is for educational and demonstration purposes only and is **not meant for real medical use** or diagnosis.

---

## ⭐ Future Enhancements

- Add multi-PDF support  
- Add user-uploaded medical history context  
- Integrate additional medical textbooks or guidelines  

---

## 🙌 Acknowledgements

- Mistral 7B GGUF model by TheBloke (HuggingFace)
- FAISS + LangChain for vector search
- Sentence-Transformers SBERT team


