
# TD Bank Generative AI Executive Advisor

This project is a Columbia University Data Science Capstone developed in collaboration with TD Bank. It introduces a Generative AI-powered chatbot that helps executives quickly retrieve strategic, evidence-based insights from financial documents using advanced Retrieval-Augmented Generation (RAG) techniques.

## 🔍 Project Overview

Executives face a daily challenge of extracting key insights from an overwhelming volume of financial reports, earnings transcripts, and regulatory filings. This system addresses that need by providing:

- Natural language question answering over a corpus of TD Bank’s public financial documents  
- Fast, relevant, and reliable results grounded in the source material  
- A user-friendly interface for experimentation and insight exploration

## 🧠 Key Features

- **Retrieval-Augmented Generation (RAG):** Uses embeddings and large language models (GPT-4o and others) to deliver contextual, document-backed answers  
- **Hybrid Search:** Combines semantic (dense) and keyword (sparse) search for improved precision and recall  
- **Reranking:** Integrates Cohere Rerank and Two-Stage Reranking to surface the most relevant results  
- **Confidence-Based Abstention:** Uses DeepEval to suppress hallucinations and return only high-confidence responses  
- **Configurable Backend:** Supports multiple LLMs and infrastructures (OpenAI, Azure, Ollama)

## ⚙️ Tech Stack

- Python, Streamlit, FastAPI  
- OpenAI, Cohere, Ollama  
- Pinecone (Vector Database)  
- DeepEval for confidence scoring  
- GitHub Actions for testing and CI

## 📁 Repository Structure

```
.
├── app/                      # Streamlit front-end
├── backend/                  # Preprocessing and query logic
│   ├── chunker.py            # Page chunking logic
│   ├── summarizer.py         # Summarization using LLMs
│   ├── retriever.py          # Hybrid search and reranking
│   └── confidence_check.py   # Abstention logic using DeepEval
├── data/                     # Sample or demo documents
├── tests/                    # Unit tests
├── requirements.txt          # Dependencies
└── README.md                 # This file
```

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- Access to OpenAI, Pinecone, and Cohere APIs
- API keys configured in `.env` or environment variables

### Installation

```bash
git clone https://github.com/engie4800/dsi-capstone-spring-2025-TD-gen-ai.git
cd dsi-capstone-spring-2025-TD-gen-ai
pip install -r requirements.txt
```

### Running the App

```bash
streamlit run app/main.py
```

Optional parameters like hybrid alpha, confidence threshold, and reranker settings can be adjusted in the sidebar.

## 📊 Evaluation

We tested our system on a benchmark of 160 questions (answerable and unanswerable).  
- **Precision:** 85%  
- **Recall:** 89%  

The system abstains when confidence is low, helping ensure answers are grounded in evidence.

## 🧪 Future Work

- Domain-specific embedding improvements  
- Cloud deployment with autoscaling  
- Larger and more diverse evaluation set  
- Hyperparameter tuning for hybrid search and abstention

## 👥 Team

Developed by:  
Brianna Ta, Dai Dai, Gregor Hanuschak, Sam Gabor, Xiqian Yuan  
Mentors: Daniel Randles and Mohammad Nejad (TD Bank)

## 📄 License

This project is for academic and educational purposes. Please review the license terms before reuse.
