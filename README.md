# medical-ai

A machine learning project that predicts diseases based on symptoms and explains them using AI.

## What it does

You enter symptoms and it tells you what disease you might have along with a confidence score. It also gives a plain english explanation using an LLM.

## Tech used

- Python
- scikit-learn (Random Forest, XGBoost)
- MLflow for experiment tracking
- ChromaDB + LangChain for RAG pipeline
- Google Gemini for explanations
- FastAPI to serve the model

## Setup

```bash
git clone https://github.com/rizzi13/medical-ai.git
cd medical-ai
pip install -r requirements.txt
```

## Project structure

```
medical-ai/
├── notebooks/     # one notebook per day
├── src/           # source code (model, rag, api)
├── data/          # datasets (not committed)
└── requirements.txt
```

## Progress

- [x] Day 4 - EDA and data exploration
- [ ] Day 5 - Data cleaning
- [ ] Day 6 - Feature engineering
- [ ] Day 7 - Model training

> Note: This is for educational purposes only, not medical advice.
