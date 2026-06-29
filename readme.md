# Local RAG Chatbot with Ollama, LangChain & BrightData

## Overview

This project implements a **Retrieval-Augmented Generation (RAG) chatbot** using LangChain, Ollama, and ChromaDB.

The system is designed to:
- Collect data using BrightData API
- Process and convert text into embeddings
- Store embeddings in a vector database
- Retrieve relevant information based on user queries
- Generate accurate responses using a local Large Language Model (LLM)

The chatbot runs **locally without relying on external LLM APIs**, making it efficient, private, and cost-effective.

---

## Project Context

This project was developed as part of a learning exercise to understand modern AI systems such as RAG pipelines.

The implementation is inspired by online tutorials and extended with:
- Local LLM execution using Ollama
- Vector database integration using ChromaDB
- Automated data ingestion using BrightData API
- Error handling and offline execution improvements

---

## Features

- Automated data ingestion using BrightData API
- Local embeddings using `mxbai-embed-large`
- Vector search using ChromaDB
- Local LLM using Ollama (`llama3`)
- Retrieval-Augmented Generation pipeline
- Streamlit chatbot interface
- Works offline after dataset generation

---

## Tech Stack

- Python
- LangChain
- Ollama (LLM + Embeddings)
- ChromaDB
- BrightData API
- Streamlit

---

## Workflow

1. Collect data using BrightData API
2. Store raw data in dataset file
3. Split text into smaller chunks
4. Convert chunks into embeddings using Ollama
5. Store embeddings in ChromaDB
6. Convert user query into embedding
7. Retrieve most relevant chunks using similarity search
8. Generate response using local LLM


## Setup Instructions

### 1. Clone the repository
 git clone https://github.com/PS-Bhavya-B/Local-RAG-Ollama.git
 cd Local-RAG-Ollama

### 2. Create virtual environment
python -m venv venv
venv\Scripts\activate

### 3. Install dependencies
pip install -r requirements.txt

### 4. Setup environment variables
EMBEDDING_MODEL=mxbai-embed-large
CHAT_MODEL=llama3.2:3b
MODEL_PROVIDER=ollama

DATABASE_LOCATION=chroma_db
COLLECTION_NAME=rag_data
DATASET_STORAGE_FOLDER=datasets/

BRIGHTDATA_API_KEY=your_key_here
SNAPSHOT_STORAGE_FILE=snapshot.txt

### 5. Install Ollama models
ollama pull llama3.2:3b2
ollama pull mxbai-embed-large

### 6. Run data scraping 
python 1_scraping_wikipedia.pyShow more lines

### 7. Generate embeddings
python 2_chunking_embedding_ingestion.py2

### 8. Run chatbot
streamlit run 3_chatbot.py

