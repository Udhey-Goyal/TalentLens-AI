# 🚀 TalentLens-AI

An AI-powered candidate ranking platform that intelligently ranks **100,000 candidate profiles** for a given job description using semantic embeddings, structured scoring, behavioral analysis, honeypot detection, and optional LLM re-ranking.

Unlike traditional keyword matching, Redrob AI Ranker evaluates **career history, skills, behavioral signals, and semantic similarity** to identify the most suitable candidates.

---

## ✨ Features

- 🔍 Semantic candidate retrieval using Sentence Transformers
- 📊 Structured scoring based on skills and career history
- 🧠 Behavioral scoring using recruiter engagement signals
- 🚨 Honeypot candidate detection
- 🤖 Optional Claude LLM re-ranking
- ⚡ Embedding caching for fast repeated inference
- 🌐 Modern React + FastAPI web interface
- 📈 Interactive ranking visualization
- 📄 CSV export of ranked candidates

---

# 🏗️ Architecture

```
                   React Frontend
                         │
                         ▼
                  FastAPI Backend
                         │
                         ▼
                Candidate Ranking Pipeline
                         │
      ┌──────────────────┼──────────────────┐
      ▼                  ▼                  ▼
Semantic Search   Structured Score   Behavioral Score
      │                  │                  │
      └──────────────┬───┴──────────────────┘
                     ▼
            Honeypot Detection
                     ▼
          Claude LLM Re-ranking (Optional)
                     ▼
              Final Candidate Ranking
```

---

# 🛠️ Tech Stack

### Frontend

- React
- TypeScript
- Vite
- CSS

### Backend

- Python
- FastAPI
- Uvicorn

### AI / ML

- Sentence Transformers
- all-MiniLM-L6-v2
- NumPy
- Anthropic Claude API (Optional)

---

# 📂 Project Structure

```
redrob-ranker/
│
├── frontend/              # React Frontend
├── pipeline/              # Candidate ranking pipeline
│   ├── encoder.py
│   ├── feature_scorer.py
│   ├── behavioral.py
│   ├── honeypot.py
│   ├── llm_reranker.py
│   └── loader.py
│
├── server.py              # FastAPI backend
├── rank.py                # CLI ranking script
├── app.py                 # Streamlit prototype
├── requirements.txt
└── README.md
```

---

# ⚙️ Installation

Clone the repository

```bash
git clone https://github.com/Udhey-Goyal/redrob-ai-ranker.git

cd redrob-ai-ranker
```

Create a virtual environment

```bash
python -m venv venv
```

Activate it

Windows

```bash
venv\Scripts\activate
```

Linux / Mac

```bash
source venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Running the Backend

```bash
uvicorn server:app --reload --port 8000
```

Backend API

```
http://127.0.0.1:8000
```

---

# ▶️ Running the Frontend

```bash
cd frontend

npm install

npm run dev
```

Frontend

```
http://localhost:5173
```

---

# 🖥️ CLI Ranking

Rank candidates without the frontend

```bash
python rank.py \
--candidates candidates.jsonl \
--out submission.csv \
--no-llm
```

---

# 🤖 Claude LLM Support

Claude re-ranking is optional.

To enable it, configure your Anthropic API Key:

```bash
ANTHROPIC_API_KEY=YOUR_API_KEY
```

Disable LLM

```bash
python rank.py --no-llm
```

---

# 📊 Performance

- Dataset Size: **100,000 Candidates**
- Embedding Model: **all-MiniLM-L6-v2**
- Cached Embeddings Supported
- CPU-only Execution
- Repeated ranking completes in approximately **7 seconds** (with cached embeddings)

---

# 📁 Dataset

The original **100k candidate dataset** is not included because it exceeds GitHub's file size limit.

For demonstration purposes, use:

```
sample_candidates.json
```

---

# 🚀 Future Improvements

- Resume PDF Upload
- Explainable AI candidate reasoning
- Multi-job ranking
- Recruiter dashboard
- Candidate comparison view
- Authentication & database integration

---

