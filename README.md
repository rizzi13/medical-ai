# 🩺 Medical Diagnosis Assistant

> An end-to-end, production-grade AI system that predicts diseases from symptoms using Machine Learning, and explains diagnoses in plain English using a RAG (Retrieval-Augmented Generation) pipeline powered by LangChain, ChromaDB, and Google Gemini.

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110-green?logo=fastapi)](https://fastapi.tiangolo.com)
[![MLflow](https://img.shields.io/badge/MLflow-Tracked-orange?logo=mlflow)](https://mlflow.org)
[![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)](https://docker.com)

---

## 🎯 What It Does

A user types their symptoms (e.g. *"fever, cough, chest pain"*) and the system:

1. **Predicts** the most likely disease with confidence percentage
2. **Retrieves** relevant medical documents from a vector database (ChromaDB)
3. **Explains** the diagnosis in plain English using Google Gemini + retrieved context
4. **Suggests** next steps (consult a doctor, emergency care, etc.)

---

## 🏗️ System Architecture

```
User Input (Symptoms)
        │
        ▼
┌──────────────────┐
│  FastAPI Backend │
│   (REST API)     │
└────────┬─────────┘
         │
    ┌────┴────┐
    ▼         ▼
┌────────┐  ┌──────────────────────────┐
│  ML    │  │     RAG Pipeline          │
│ Model  │  │  ChromaDB → LangChain    │
│ (RF/   │  │  → Google Gemini LLM     │
│ XGB)   │  └──────────────────────────┘
└────────┘
    │              │
    └──────┬───────┘
           ▼
   JSON Response:
   {disease, confidence, explanation, severity, next_steps}
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **ML Models** | Scikit-learn (Random Forest, XGBoost) |
| **Experiment Tracking** | MLflow |
| **Embeddings** | HuggingFace sentence-transformers |
| **Vector Database** | ChromaDB |
| **RAG Orchestration** | LangChain |
| **LLM** | Google Gemini API |
| **API** | FastAPI + Pydantic |
| **Containerization** | Docker |
| **Deployment** | Render |

---

## 📁 Project Structure

```
medical-ai/
│
├── notebooks/                  ← Jupyter notebooks (one per day)
│   ├── Day4_EDA.ipynb
│   ├── Day5_Cleaning.ipynb
│   ├── Day6_FeatureEngineering.ipynb
│   └── ...
│
├── src/
│   ├── model/
│   │   ├── train.py            ← Model training script
│   │   └── predict.py          ← Prediction logic
│   ├── rag/
│   │   ├── embeddings.py       ← ChromaDB setup
│   │   └── pipeline.py         ← LangChain RAG chain
│   └── api/
│       └── main.py             ← FastAPI application
│
├── data/
│   └── .gitkeep               ← CSV files not committed (too large)
│
├── mlruns/                     ← MLflow experiment logs
├── requirements.txt
├── Dockerfile
└── README.md
```

---

## 📊 Model Performance

> *(Updated as experiments progress)*

| Model | Accuracy | F1 Score | Tracked In |
|-------|----------|----------|-----------|
| Decision Tree | - | - | MLflow Run #1 |
| Random Forest | - | - | MLflow Run #2 |
| XGBoost | - | - | MLflow Run #3 |

---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone https://github.com/yourusername/medical-ai.git
cd medical-ai
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Set environment variables
```bash
cp .env.example .env
# Add your GEMINI_API_KEY to .env
```

### 4. Run the API locally
```bash
uvicorn src.api.main:app --reload
```

### 5. API is live at
```
http://localhost:8000/docs
```

---

## 🗓️ Development Progress

| Day | Task | Status |
|-----|------|--------|
| Day 4 | EDA — Data Exploration | ✅ Done |
| Day 5 | Data Cleaning | 🔄 In Progress |
| Day 6 | Feature Engineering | ⏳ Upcoming |
| Day 7 | Train/Test Split | ⏳ Upcoming |
| Day 8 | Decision Tree Model | ⏳ Upcoming |
| Day 9 | Random Forest Model | ⏳ Upcoming |
| Day 10 | Model Evaluation | ⏳ Upcoming |

---

## 👨‍💻 Author

**Rishi** — Built as part of a 50-day ML + Spring Boot learning journey.

> *"Learn by building. Every line explained, every concept understood."*

---

## ⚠️ Disclaimer

This tool is for **educational purposes only**. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare provider.
