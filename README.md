# 🤖 Interactive RAG Chatbot from Scratch

An end-to-end **Retrieval-Augmented Generation (RAG)** pipeline built from scratch using Python. This project allows users to upload PDF documents and have context-aware conversations with the data using **Gemini 2.5 Flash**.

## 🚀 Project Overview
Most LLMs have a "knowledge cutoff." This project implements a RAG workflow to provide the model with private, up-to-date data (from PDFs) without the need for fine-tuning. 

### Key Features:
* **Smart Document Ingestion:** Uses `PyPDFLoader` for precise text extraction.
* **Contextual Chunking:** Implements `RecursiveCharacterTextSplitter` with a 500-character size and 100-character overlap to maintain semantic integrity.
* **Vector Search:** Powered by **FAISS** (Facebook AI Similarity Search) for lightning-fast retrieval of relevant text segments.
* **Local Embeddings:** Utilizes `sentence-transformers` (`all-MiniLM-L6-v2`) to generate high-quality numerical representations of text.
* **Gemini Integration:** Leverages the latest `google-genai` SDK (2026 standard) for generating accurate, grounded responses.

## 🛠️ Tech Stack
* **Language:** Python 3.12+
* **LLM:** Google Gemini 1.5 Flash
* **Orchestration:** LangChain (Text Splitters & Document Loaders)
* **Vector DB:** FAISS (FlatL2 Index)
* **Embeddings:** HuggingFace Sentence-Transformers
* **Visualization:** Matplotlib & NumPy (for embedding heatmap analysis)

## 📸 Embedding Visualization
The project includes a custom visualization tool that normalizes high-dimensional vectors and displays them as heatmaps, allowing us to "see" the mathematical fingerprint of the document chunks.

## 📋 Installation & Setup
1. **Clone the repo:**
   ```bash
   git clone [https://github.com/aasthamewar/RAG-Chatbot.git](https://github.com/aasthamewar/RAG-Chatbot.git)
   ```
2. **Install dependencies**
   ```bash
   pip install -q -U google-genai langchain_text_splitters faiss-cpu sentence-transformers matplotlib pypdf
   ```
3.**Environment Variables**
  ```bash
Store your Gemini API Key in your environment or Google Colab Secrets as GOOGLE_API_KEY.
```

## 💡 How it Works
* Load: The PDF is scanned and converted to digital text.
* Split: Text is broken into overlapping chunks.
* Embed: Chunks are converted into vectors (numbers).
* Index: Vectors are stored in a FAISS index.
* Retrieve: When you ask a question, the system finds the "closest" chunks.
* Augment: Gemini receives the question + the specific chunks to provide an answer.
