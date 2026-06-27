# 🤖 Redrob AI Candidate Ranker

An AI-powered candidate ranking system that ranks job applicants based on semantic similarity, feature engineering, and optional LLM re-ranking.

## 🚀 Features

- Semantic candidate matching using Sentence Transformers
- Fast embedding caching for large datasets
- Rule-based feature scoring
- Optional Claude LLM re-ranking
- Streamlit web interface
- Handles datasets with up to 100,000 candidates efficiently

---

## 🛠️ Tech Stack

- Python 3.x
- Sentence Transformers (all-MiniLM-L6-v2)
- Anthropic Claude API (Optional)
- NumPy
- Streamlit

---

## 📂 Project Structure

```
redrob-ranker/
│
├── app.py
├── rank.py
├── requirements.txt
├── sample_candidates.json
├── validate_submission.py
│
├── pipeline/
│   ├── encoder.py
│   ├── loader.py
│   ├── behavioral.py
│   ├── feature_scorer.py
│   ├── honeypot.py
│   ├── jd_parser.py
│   └── llm_reranker.py
│
└── .gitignore
```

---

## ⚙️ Installation

Clone the repository

```bash
git clone https://github.com/Udhey-Goyal/Redrob-ranker.git
cd Redrob-ranker
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running Without LLM

```bash
python rank.py --candidates sample_candidates.json --out submission.csv --no-llm
```

This mode uses:

- Sentence Transformer embeddings
- Feature engineering
- Behavioral scoring

No API key is required.

---

## 🤖 Running With Claude LLM

Set your Anthropic API key.

Windows PowerShell

```powershell
$env:ANTHROPIC_API_KEY="YOUR_API_KEY"
```

Linux/macOS

```bash
export ANTHROPIC_API_KEY="YOUR_API_KEY"
```

Run

```bash
python rank.py --candidates sample_candidates.json --out submission.csv
```

The top-ranked candidates are re-ranked using Claude.

---

## 🧠 Pipeline

```
Candidates
      │
      ▼
Candidate Loader
      │
      ▼
Sentence Transformer Embeddings
      │
      ▼
Cosine Similarity Ranking
      │
      ▼
Feature Scoring
      │
      ▼
(Optional) Claude LLM Re-ranking
      │
      ▼
Final Ranked Candidates
```

---

## 📊 Performance

- Supports datasets with **100,000+ candidates**
- Cached embeddings reduce repeated runtime from several minutes to a few seconds
- Batch embedding generation
- Optional LLM stage for higher-quality ranking

---

## 📌 Notes

The large candidate dataset (`candidates.jsonl`) is intentionally **not included** because it exceeds GitHub's file size limits.

Use the provided sample dataset or your own candidate dataset.

---

