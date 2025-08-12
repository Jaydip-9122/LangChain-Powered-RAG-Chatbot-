# Aerodynamics PDF Chatbot (LangChain + Groq + FAISS)

## Overview
This project implements an interactive chatbot capable of answering questions about aerodynamics or any uploaded PDF. It uses LangChain for document processing, HuggingFace embeddings for semantic search, FAISS for vector storage, and the Groq LLM API for natural language answers. The app runs in Streamlit with ngrok tunneling for public access.

## Features
- Upload a PDF and automatically split it into searchable text chunks.
- Generate semantic embeddings using HuggingFace's `all-MiniLM-L6-v2`.
- Store and query documents with FAISS vector database.
- Retrieve relevant text sections and generate answers with Groq LLM.
- Streamlit interface for an interactive Q&A experience.
- Runs locally with a public link via ngrok.

## Requirements
- Python 3.x
- LangChain & LangChain Community
- HuggingFace Sentence Transformers
- FAISS CPU
- tqdm
- pyngrok
- Streamlit
- Groq API Key

Install dependencies:
pip install sentence-transformers langchain-community faiss-cpu tqdm pyngrok streamlit

## Usage
1. Set your Groq API key and ngrok auth token in the script.
2. Run the Python script or notebook.
3. Upload your desired PDF when prompted.
4. Wait for the FAISS database to be generated.
5. Streamlit launches and provides an ngrok link for public access.
6. Enter questions in the text area; the chatbot will search the document and answer based on relevant context.

## How It Works
1. **PDF Processing** – PDF is loaded using PyPDFLoader and split into chunks with `RecursiveCharacterTextSplitter`.
2. **Embedding Generation** – Each chunk is converted to a semantic vector using HuggingFace embeddings.
3. **Vector Storage** – Embeddings are stored in a FAISS index for fast similarity search.
4. **Query Handling** – User queries are embedded, matched against stored chunks, and the most relevant are passed to the LLM.
5. **Answer Generation** – The Groq LLM (`deepseek-r1-distill-llama-70b`) generates an answer using retrieved context.
6. **User Interface** – A simple Streamlit app provides the chat interface.

## Applications
- Aerodynamics lecture and notes Q&A.
- Engineering PDF research assistant.
- General-purpose document-based chatbot.

## License
This project is open-source and available under the MIT License.
