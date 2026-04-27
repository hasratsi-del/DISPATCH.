# DISPATCH.
Real-time geopolitical intelligence engine.

## What it does
Fetches live news → scores sentiment per article with TextBlob NLP → aggregates by country → renders on an interactive D3.js world map with a rotating Three.js globe.

## Setup

### Backend
```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
export NEWS_API_KEY=your_key_here
python app.py
```
Runs at http://localhost:5000

### Frontend
Open `frontend/index.html` in your browser while backend is running.

## Deploy
- Backend → Railway (connect backend/ folder, add NEWS_API_KEY env var)
- Frontend → Netlify (drag frontend/ folder)
- Update API_URL in frontend/index.html to your Railway URL

## Built by
Hasrat Singh Chauhan · at-quorum.netlify.app
