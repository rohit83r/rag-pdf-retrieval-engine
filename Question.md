## 🔍 **Assignment 2: End-to-End RAG Pipeline on Multi-Page PDF Data**

### 🎯 **Objective:**

Build a complete Retrieval-Augmented Generation (RAG) pipeline that ingests multiple PDF documents (containing text, tables, and images), performs semantic chunking, stores data in a vector database with multiple indexing strategies, and enables high-performance retrieval and answer generation using LLMs. The final output should be rendered in a `.docx` file.

---

### 📘 **Task Description:**

1. **PDF Data Extraction**

   * Collect and ingest multiple PDF files totaling **at least 200 pages**.
   * Ensure the PDFs include **text, tables, and images**.
   * Extract all readable data (text from paragraphs, images, and tables).
   * Use appropriate tools to handle OCR for image-based PDFs.

2. **Semantic Chunking**

   * If required, chunk the extracted data using **semantic chunking techniques**.
   * Preserve context during chunking (avoid naive splitting).
   * Use tools like Langchain’s `RecursiveCharacterTextSplitter` or similar.

3. **Embeddings Generation**

   * Convert the text chunks into embeddings using any embedding model:

     * OpenAI (`text-embedding-ada-002`)
     * HuggingFace (`all-MiniLM-L6-v2`, etc.)

4. **Vector Database Integration**

   * Choose **one** of the following vector databases:

     * MongoDB Atlas (Vector Search)
     * AstraDB (Vector + Cassandra)
     * OpenSearch (with vector plugin)
     * Milvus (optimized for ANN search)
   * Store your embedded data in the selected vector store.

5. **Indexing Techniques**

   * Create **three separate vector indexes** for the stored data using:

     * Flat Index (brute-force)
     * HNSW (Hierarchical Navigable Small World)
     * IVF (Inverted File Index)
   * If your vector DB doesn’t support all three, use FAISS locally for comparison.

6. **Retriever Pipeline**

   * Build a retriever pipeline that:

     * Accepts a query input.
     * Fetches the most relevant chunks using each index type.
     * Measures **retrieval time** and logs it.

7. **Performance Metrics**

   * For each index type (Flat, HNSW, IVF), compute:

     * **Retrieval time**
     * **Accuracy score** (e.g., precision, recall\@K, or custom similarity score)

8. **Re-ranking (Optional but Recommended)**

   * Re-rank the retrieved chunks using one of the following:

     * **BM25** (based on lexical relevance)
     * **MMR** (Maximal Marginal Relevance — balances relevance and diversity)

9. **LLM Integration**

   * Write a **prompt template** to query an LLM.
   * Feed the retrieved and re-ranked context into an LLM (e.g., GPT-4, Mistral, etc.).
   * Generate a coherent answer based on the context.

10. **Final Output Rendering**

* Render the LLM-generated response in a structured `.docx` file.
* Use `python-docx` to format output (headings, paragraphs, etc.).

---

### 📦 **Deliverables**

* Python scripts or Jupyter notebook covering the entire pipeline.
* A sample `.docx` file containing generated answers.
* Retrieval benchmark summary:

  * Time comparisons
  * Accuracy metrics
* Screenshots or logs validating the working pipeline.
* (Optional) A short report or `README.md` explaining setup, architecture, and observations.

---
