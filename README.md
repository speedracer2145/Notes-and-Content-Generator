# 📄 PDF Query System with LangChain, ChromaDB, and Local LLM

This project is a **PDF Query System** that lets you interact with uploaded PDFs by asking questions and receiving context-driven answers. It uses:

- **LangChain** for retrieval-augmented generation (RAG)  
- **ChromaDB** for vector storage and retrieval  
- **Sentence Transformers** for local embeddings  
- **Ollama** for running a local LLM (privacy-first, offline)  
- **Streamlit** for a clean, interactive frontend  

---

## 🚀 Features

- Query PDFs in natural language  
- Retrieval-Augmented Generation with **LangChain**  
- Store and retrieve embeddings with **ChromaDB**  
- Generate embeddings using **Sentence Transformers** (`all-MiniLM-L6-v2`)  
- Run a local **LLM via Ollama** (no external API keys needed)  
- Streamlit-based interactive web interface  

---

## 📂 Project Structure

app.py # Main Streamlit application
requirements.txt # Required Python packages
README.md # Project documentation
/content/chroma_db/ # Persistent ChromaDB storage
sample_pdfs/ # Example PDFs for testing

---

## ⚙️ Installation & Setup

### 1. Prerequisites
- Python **3.8+**  
- [Streamlit](https://streamlit.io/)  
- [Ollama](https://ollama.ai/) installed and running locally  
- Required Python packages (`requirements.txt`)  

### 2. Create and Activate Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
3. Install Dependencies
pip install -r requirements.txt
4. Run Ollama Server
Check if Ollama is running on the default port:
lsof -i :11434
If not running, start Ollama.
⚠️ Make sure there are no port conflicts.
▶️ Running the Application
Add your PDF files to the pdf_paths list in app.py.
Launch the Streamlit app:
streamlit run app.py
Open the UI in your browser: http://localhost:8501
🧑‍💻 Usage
Start the application and upload your PDFs
Enter your question in natural language
The system will:
Retrieve relevant chunks from ChromaDB
Generate a context-aware response with the local LLM
Sources of retrieved information are displayed for reference
✨ Code Highlights
Custom LLM Integration:
The CustomOllamaLLM class in app.py directly interfaces with Ollama’s local server → no API keys needed.
LangChain + ChromaDB:
Efficient document chunking, embedding, retrieval, and querying.
Local Embeddings:
Uses Sentence Transformers (all-MiniLM-L6-v2) to generate embeddings locally for privacy and offline use.
⚠️ Known Issues
Port Conflicts:
Ensure only one Ollama instance runs on port 11434.
Server Unavailability:
If Ollama server is unreachable, verify it’s installed and running.
🔮 Future Improvements
Add real-time PDF upload directly via Streamlit
Experiment with advanced LLMs for richer responses
Explore alternative retrieval methods in LangChain for improved accuracy
📦 Requirements
Python 3.8+
fitz (PyMuPDF) → PDF handling
langchain → Document processing
streamlit → Web interface
chromadb → Vector storage and retrieval
sentence-transformers → Embeddings
ollama → Local LLM server
