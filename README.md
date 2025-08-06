# LLM-Powered RAG System with Multiple Vector Store Options

A comprehensive Retrieval-Augmented Generation (RAG) system built with LangChain, featuring multiple vector store backends including AstraDB, FAISS, and various LLM providers like Groq and OpenAI.

## 🚀 Features

- **Multiple Vector Store Options**: Support for AstraDB (Cassandra), FAISS
- **Multiple LLM Providers**: Integration with Groq (Mixtral, Llama3) and OpenAI
- **Document Processing**: Web scraping and PDF document ingestion
- **Interactive UI**: Streamlit-based chat interface
- **Real-time Retrieval**: Fast similarity search with document context
- **Flexible Embeddings**: Support for OpenAI and Ollama embeddings

## 📋 Prerequisites

- Python 3.8+
- Valid API keys for:
  - Groq API
  - OpenAI API (optional)
  - AstraDB credentials (for Cassandra option)

## 🛠️ Installation

1. **Clone the repository**
```bash
git clone <your-repository-url>
cd <repository-name>
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Set up environment variables**
Create a `.env` file in the root directory:
```env
GROQ_API_KEY=your_groq_api_key_here
OPENAI_API_KEY=your_openai_api_key_here
ASTRA_DB_APPLICATION_TOKEN=your_astra_token_here
ASTRA_DB_ID=your_astra_db_id_here
```

## 📦 Required Dependencies

Create a `requirements.txt` file with the following packages:

```txt
streamlit
langchain
langchain-groq
langchain-community
langchain-openai
cassio
faiss-cpu
pypdf
beautifulsoup4
python-dotenv
ollama
openai
```

## 🏗️ Project Structure

```
├── app1.py                 # Streamlit app with FAISS + web scraping
├── app2.py                 # Streamlit app with FAISS + PDF processing
├── paste.txt               # Jupyter notebook with AstraDB implementation
├── us_census/              # Directory for PDF documents
├── .env                    # Environment variables (create this)
├── requirements.txt        # Python dependencies
└── README.md              # This file
```

## 🚦 Usage

### Option 1: Web-based RAG with FAISS

Run the first Streamlit app for web document processing:

```bash
streamlit run app1.py
```

This app:
- Loads documents from LangSmith documentation
- Uses Ollama embeddings
- Stores vectors in FAISS
- Powered by Groq's Mixtral model

### Option 2: PDF-based RAG with FAISS

Run the second Streamlit app for PDF document processing:

```bash
streamlit run app2.py
```

This app:
- Processes PDF files from the `us_census` directory
- Uses OpenAI embeddings
- Stores vectors in FAISS
- Powered by Groq's Llama3 model

### Option 3: AstraDB Vector Store

The Jupyter notebook (`paste.txt`) demonstrates:
- Integration with AstraDB (Cassandra)
- Web scraping from Lilian Weng's blog
- OpenAI embeddings
- Advanced retrieval chains

## 🔧 Configuration

### AstraDB Setup

1. Create an AstraDB account
2. Create a new database
3. Generate an application token
4. Update the credentials in your `.env` file

### Document Preparation

For PDF processing:
1. Create a `us_census` directory
2. Add your PDF files to this directory
3. Run the embedding process through the Streamlit interface

## 🎯 Key Components

### Vector Stores
- **FAISS**: Fast similarity search for local development
- **AstraDB**: Cloud-native vector database for production

### LLM Models
- **Groq Mixtral-8x7B**: Fast inference for complex reasoning
- **Groq Llama3-8B**: Efficient model for general tasks

### Embeddings
- **OpenAI Embeddings**: High-quality semantic representations
- **Ollama Embeddings**: Local embedding generation

## 💡 How It Works

1. **Document Ingestion**: Load documents from web or PDF sources
2. **Text Splitting**: Break documents into manageable chunks
3. **Embedding Generation**: Convert text chunks to vector representations
4. **Vector Storage**: Store embeddings in chosen vector database
5. **Query Processing**: Convert user questions to embeddings
6. **Similarity Search**: Find relevant document chunks
7. **Answer Generation**: Use LLM to generate contextual responses

## 🎮 Example Usage

1. **Start the application**:
   ```bash
   streamlit run app1.py
   ```

2. **Wait for vector embedding** (first-time setup)

3. **Ask questions** like:
   - "What is Chain of Thought prompting?"
   - "Explain LLM-powered autonomous agents"
   - "How does task decomposition work?"

4. **View results** with source document context

## 🔍 Features in Detail

### Real-time Response
- Measure and display response times
- Efficient retrieval with approximate nearest neighbors

### Document Context
- Show relevant source chunks for each answer
- Expandable sections for detailed document exploration

### Flexible Prompting
- Customizable prompt templates
- Context-aware answer generation

## 🙏 Acknowledgments

- LangChain team for the excellent framework
- Groq for fast LLM inference
- AstraDB for vector database capabilities
- Streamlit for the user interface framework