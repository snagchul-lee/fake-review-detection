# Fake Review Detection for Korean E-Commerce

> Detecting fake reviews on Naver Smart Store using a hybrid KoBERT + BiLSTM architecture

**Status:** 🔄 In Progress (Model Validation Phase)
**Type:** Capstone Design Project · Individual

---

## Overview

Online fake reviews distort consumer decision-making and undermine platform trust.
This project builds a **Korean-language fake review detection system** targeting product reviews on **Naver Smart Store** — one of Korea's largest e-commerce platforms.

### The Challenge
- Korean NLP requires specialized models (KoBERT, not BERT)
- Fake reviews are intentionally written to appear genuine
- Class imbalance: genuine reviews far outnumber fake ones

---

## Architecture

```
Raw Review Text (Korean)
        ↓
   Preprocessing
   (tokenization, cleaning)
        ↓
   KoBERT Encoder
   (semantic understanding — "what does this mean?")
        ↓
   BiLSTM Layer
   (sequential pattern detection — "how is it written?")
        ↓
   Binary Classifier
   (Fake / Genuine)
```

**Why KoBERT + BiLSTM?**
- **KoBERT** captures deep semantic meaning of Korean text
- **BiLSTM** captures writing patterns and sequential dependencies that KoBERT alone may miss
- Combining both improves robustness against sophisticated fake reviews

---

## Data

| Source | Method | Notes |
|---|---|---|
| Naver Smart Store | Naver API + Web crawling | Product reviews across multiple categories |

*Data details and preprocessing pipeline described in `/notebooks/01_data_collection.ipynb`*

---

## Project Structure

```
fake-review-detection/
├── README.md
├── notebooks/
│   ├── 01_data_collection.ipynb      # API crawling & data collection
│   ├── 02_preprocessing.ipynb        # Text cleaning & tokenization
│   └── 03_model_training.ipynb       # KoBERT + BiLSTM training
├── src/
│   ├── crawl.py                      # Naver API crawler
│   ├── preprocess.py                 # Preprocessing pipeline
│   └── model.py                      # Model architecture
├── data/
│   └── .gitkeep                      # Raw data not included (privacy)
└── requirements.txt
```

---

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| NLP Model | KoBERT (SKTBrain), BiLSTM |
| Framework | HuggingFace Transformers, PyTorch |
| ML | scikit-learn |
| Data Collection | Naver API, requests, BeautifulSoup |
| Environment | Jupyter Notebook, VS Code, Cursor AI |

---

## Current Progress

- [x] Research design & problem definition
- [x] Data collection pipeline (Naver API crawling)
- [x] Text preprocessing & tokenization
- [x] KoBERT + BiLSTM model architecture implementation
- [ ] Model validation & performance evaluation
- [ ] Threshold optimization & error analysis
- [ ] Final report

---

## Background

This project is part of the **Capstone Design** course at KOREATECH.
It is also closely related to my research interest in **AI-powered marketing analytics** and **consumer behavior analysis**.

---

*For questions or collaboration: andy26566242@gmail.com*
