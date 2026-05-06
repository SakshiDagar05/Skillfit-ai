# SkillFit AI — Mobile-First Multilingual Video Assessment

![Theme](https://img.shields.io/badge/Theme-5%20AI%20SkillFit-cyan)
![Hackathon](https://img.shields.io/badge/Hackathon-AI%20For%20Bharat-blue)
![IIT](https://img.shields.io/badge/IIT-Bangalore-orange)
![Language](https://img.shields.io/badge/Kannada%20First-green)

---

## Team

| Name | Role |
|---|---|
| Sakshi Dagar | AI/ML & NLP |
| Veera Tyagi | Backend & Integration |
| Abhyudit Sharma | Frontend & Vision AI |

---

## Problem Statement

**Theme 5 — AI SkillFit: Video Assessment for Workforce Fitment**

Karnataka's workforce screening is broken:
- Fragmented and manual screening processes
- Language barriers for Kannada-speaking candidates and dialects
- Text-based forms not suitable for low-literacy candidates
- Cannot handle high-volume candidate intake
- Risk of duplicate, fraudulent, or AI-assisted submissions
- No actionable workforce classification system

---

## Our Solution

**SkillFit AI** is an AI-powered, mobile-first platform that conducts video interviews at scale, assesses candidate responses, ensures authenticity, and classifies candidates into actionable workforce categories.

### Core Pipeline
```
Natural Interaction → Reliable Assessment → Trustable Verification → Scalable Fitment
```

---

## Live Demo

**https://sakshidagar05.github.io/skillfit-ai/**

---

## Architecture

```
index.html (Frontend)
      |
      | candidate uploads video
      | POST /analyze
      |
backend/main.py (FastAPI Server)
      |
      |-- transcribe.py    --> Whisper ASR (Kannada speech to text)
      |-- nlp_scorer.py    --> Answer quality scoring (IndicBERT)
      |-- ai_detector.py   --> AI agent / ChatGPT usage detection
      |-- vision.py        --> Face, liveness, eye contact (MediaPipe)
      |
      Returns JSON --> Frontend displays Fitment Report
```

---

## 6 Modules Built

| Module | Description |
|---|---|
| 1. AI Video Interview | Mobile-first AI agent in Kannada, Hindi, English. Record live, upload video, or use WhatsApp. |
| 2. Response Assessment | NLP + Speech + Vision. 6-dimension explainable score. |
| 3. Face & Voice Validation | Liveness detection, audio clarity, continuity, manipulation check. |
| 4. Integrity Detection | Tab switching detection, AI agent usage detection, duplicate check, Aadhaar verification. |
| 5. Candidate Fitment | 5-category classification mapped to blue-collar, polytechnic, semi-skilled roles. |
| 6. Admin Dashboard | Government portal — filter by district, language, category. Shortlist and flag candidates. |

---

## 3 Login Portals

| Portal | For |
|---|---|
| Candidate Portal | Job seekers — choose role, language, record or upload interview |
| Government Admin | Karnataka Govt — review all candidates, district filters, export reports |
| HR Recruiter | Companies — view shortlists, score cards, schedule interviews |

---

## Datasets Used

| Dataset | Purpose |
|---|---|
| AI4Bharat IndicVoices | Kannada speech recognition and dialect training |
| Common Voice Mozilla | Multilingual ASR training |
| HC3 Hello-SimpleAI | AI-generated text detection |
| SQuAD 2.0 | Answer relevance scoring |
| IndicGLUE | Indian language NLP benchmark |
| MPIIGaze | Eye contact and gaze detection |
| FaceForensics++ | Deepfake and manipulation detection |
| LFW Pairs | Duplicate face detection |

---

## AI Models Used

| Model | Task |
|---|---|
| openai/whisper-large-v3 | Kannada and multilingual ASR |
| ai4bharat/indic-bert | Answer scoring and NLP |
| Hello-SimpleAI/chatgpt-detector-roberta | AI response detection |
| MediaPipe Face Mesh | Eye contact, liveness, face detection |
| Librosa | Speech analysis, filler words, vocal confidence |

---

## Languages Supported

- Kannada (Primary — dialect-aware including Dharwad, Belagavi, Mysuru)
- Hindi
- English
- Telugu
- Tamil

---

## Candidate Classification

| Category | Score | Action |
|---|---|---|
| Job-Ready | 80-100 | Direct placement |
| Requires Training | 55-79 | Upskilling recommended |
| Manual Verification | 40-54 | Human review needed |
| Low Confidence | 20-39 | Poor quality submission |
| Suspected Fraud | 0-19 | Duplicate or AI-assisted |

---

## Project Structure

```
skillfit-ai/
|
|-- index.html                   # Full frontend prototype (all 6 modules)
|-- README.md                    # This file
|-- requirements.txt             # Python dependencies
|-- INSTRUCTIONS.md              # How to run step by step
|
|-- backend/
|   |-- main.py                  # FastAPI server — connects all modules
|   |-- transcribe.py            # Whisper ASR — Kannada speech to text
|   |-- nlp_scorer.py            # NLP answer quality scoring
|   |-- ai_detector.py           # AI agent and ChatGPT detection
|   |-- vision.py                # Face, liveness, eye contact analysis
|   |-- classifier.py            # Workforce fitment classification
|
|-- datasets/
|   |-- download_datasets.py     # One-click dataset download script
|
|-- models/                      # Trained model files stored here
|
|-- presentation/
    |-- SkillFit_AI_v2_AIForBharat.pptx
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Backend | FastAPI, Python 3.11 |
| Speech AI | OpenAI Whisper fine-tuned on Kannada |
| NLP | AI4Bharat IndicBERT, HuggingFace Transformers |
| Vision AI | MediaPipe, OpenCV |
| Audio Analysis | Librosa |
| AI Detection | RoBERTa-based classifier |
| Deployment | GitHub Pages (frontend), Uvicorn (backend) |

---

## How to Run

### Option 1 — Frontend Only (No Setup Needed)
1. Download index.html
2. Double-click to open in Chrome
3. Full prototype works immediately

### Option 2 — Full Stack with AI Backend

```bash
# Clone the repo
git clone https://github.com/YOUR-USERNAME/skillfit-ai
cd skillfit-ai

# Create virtual environment
python -m venv skillfit-env

# Activate — Windows:
skillfit-env\Scripts\activate

# Activate — Mac/Linux:
source skillfit-env/bin/activate

# Install all dependencies
pip install -r requirements.txt

# Download datasets (first time only — takes 15-20 mins)
python datasets/download_datasets.py

# Start the backend server
cd backend
uvicorn main:app --reload --port 8000

# Open frontend in browser
# Double-click index.html  OR  run:
python -m http.server 5500
# Then open: http://localhost:5500/index.html
```

Backend runs at: http://localhost:8000
API Docs: http://localhost:8000/docs

---

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | /analyze | Upload video, returns full fitment report |
| GET | /health | Check if backend is running |
| GET | /docs | Auto-generated Swagger API documentation |

---

## Impact

- 500M+ India's addressable workforce
- 70% reduction in screening time
- 5 languages supported
- 8 seconds per candidate analysis
- 6 explainable score dimensions
- 5 workforce classification categories

---

## Acknowledgements

- AI4Bharat for IndicBERT and IndicVoices datasets
- OpenAI for Whisper ASR model
- Google MediaPipe for face mesh and gaze detection
- HuggingFace for model hosting and Transformers library
- IIT Bangalore and AI For Bharat for the hackathon platform

---

*AI FOR BHARAT Hackathon | IIT Bangalore | Theme 5 — AI SkillFit*
*Team: Sakshi Dagar | Veera Tyagi | Abhyudit Sharma*
