# 🧠 RAG PDF Retrieval Engine

An end-to-end Retrieval-Augmented Generation (RAG) pipeline built on top of multi-page PDF documents that include text, images, and tables. The system extracts, chunks, embeds, stores, and retrieves information from large PDF corpora — and generates high-quality answers using Google Gemini.

---

## 🚀 Features

- 📄 Multi-page PDF ingestion with OCR support
- ✂️ Semantic chunking with context preservation
- 🧠 Embedding generation using HuggingFace models
- 🗃️ Vector store integration with Zilliz (Milvus)
- 🧩 Multiple indexing strategies: FLAT, HNSW, IVF
- 🔍 High-performance retrieval + optional MMR re-ranking
- 🤖 LLM answer generation using **Google Gemini (gemini-pro)**
- 📄 Output formatting in `.docx` using `python-docx`
- 📊 Benchmarking: retrieval time + precision@K

---

## 🛠️ Tech Stack

| Component         | Tool / Library                          |
|------------------|------------------------------------------|
| PDF Extraction    | `PyMuPDF`, `pdfplumber`, `pytesseract`   |
| Chunking          | `LangChain` `RecursiveCharacterTextSplitter` |
| Embedding Model   | `HuggingFace` (`all-MiniLM-L6-v2`, etc.) |
| Vector DB         | `Milvus` (Zilliz Cloud) via `langchain-milvus` |
| Index Types       | `flat`, `hnsw`, `ivf_flat`               |
| Retriever Logic   | `LangChain` retrievers + `MMR`           |
| LLM Integration   | `Google Gemini Pro` via `google-generativeai` and `langchain-google-genai` |
| Docx Output       | `python-docx`                            |

---

## 📦 Setup

### ✅ 1. Clone the repository

```bash
    git clone https://github.com/rohit83r/rag-pdf-retrieval-engine.git
cd rag-pdf-retrieval-engine


