"# PDF_RAG_with_Lanchain" 

# PDF Retrieval-Augmented Generation (RAG) with LangChain & Google Gemini

## 📌 Overview
This project demonstrates how to build a **Retrieval-Augmented Generation (RAG) system** using:
- **LangChain** for document processing and orchestration,
- **Google Gemini (Generative AI)** for embeddings and answering questions,
- **ChromaDB** as the vector database for efficient semantic search,
- **PDF documents** as the knowledge source.

The pipeline extracts text from a PDF, splits it into chunks, embeds the chunks, stores them in ChromaDB, and enables natural language question answering using Gemini.

---

## ⚙️ Tools & Libraries Used
- **LangChain Core & LangGraph** – RAG pipeline building blocks
- **LangChain Community** – PDF loader utilities
- **Google Generative AI** – Embeddings & LLM (`gemini-1.5-flash`)
- **PyPDF** – PDF document loading
- **ChromaDB** – Vector database for storing embeddings
- **Python (Colab/Jupyter)** – Development environment

---

## 🚀 How It Works
1. **Unzip and Load PDF**  
   - Extracts PDF files from a `.zip` archive.  
   - Loads PDF content using `PyPDFLoader`.  

2. **Text Splitting**  
   - Splits the document into chunks (`1000` characters with `200` overlap).  

3. **Embedding Generation**  
   - Uses `GoogleGenerativeAIEmbeddings` to generate vector embeddings for each chunk.  

4. **Vector Database Creation**  
   - Stores embeddings in **ChromaDB** for semantic search and retrieval.  

5. **RAG Pipeline Setup**  
   - Defines a prompt template with context injection.  
   - Creates a document chain with **Gemini LLM**.  
   - Connects retriever with LLM to form the retrieval chain.  

6. **Question Answering**  
   - User can ask natural language questions.  
   - The system retrieves relevant chunks and generates context-aware answers.  

---


## ▶️ How to Run
1. Install dependencies:
   ```bash
   pip install langchain-core langgraph>0.2.27
   pip install -U langchain-community
   pip install "langchain[google-genai]" google-ai-generativelanguage==0.6.15
   pip install pypdf chromadb
