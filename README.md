# Retrieval Augmented Generation (RAG) Model – From Scratch

This project demonstrates how to build a **Retrieval Augmented Generation (RAG)** system from scratch using **Hugging Face models**, **Sentence Transformers**, and **ChromaDB**.  
The notebook was implemented and tested in **Google Colab with T4 GPU**.

---

## Project Overview

Large Language Models (LLMs) often fail to answer questions accurately when the required information is not present in their training data.  
To solve this problem, **RAG combines information retrieval with text generation**.

In this project:
- Documents are converted into embeddings
- Stored in a vector database (ChromaDB)
- Relevant documents are retrieved for a given query
- A language model generates an answer using the retrieved context

---

## Technologies Used

- **Python**
- **Google Colab (T4 GPU)**
- **Hugging Face Transformers**
- **Sentence-Transformers**
- **ChromaDB (Vector Database)**
- **PyTorch**
- **Pandas**

---

## Model Architecture

### 1. Data Source
- The dataset is loaded from **Hugging Face**
- Text data is preprocessed and stored as documents

### 2. Embedding Model
- Sentence embeddings are created using **Sentence-Transformers**
- These embeddings represent the semantic meaning of documents

### 3. Vector Database
- **ChromaDB** is used to store document embeddings
- Enables fast similarity search for relevant documents

### 4. Retriever
- Retrieves top relevant documents based on cosine similarity
- Acts as the knowledge source for the LLM

### 5. Language Model (LLM)
- Loaded using **AutoModelForCausalLM** and **AutoTokenizer**
- Text generation handled through the Hugging Face `pipeline`

### 6. RAG Pipeline
- A custom `RAG` class is implemented
- Combines retriever output and LLM response
- Uses a system prompt and user prompt to control answers

---
