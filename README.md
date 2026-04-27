# DISPATCH.
### Real-time geopolitical intelligence engine

> *"The world is talking. This is what it's saying."*

**Live demo:** [hasrat-dev.netlify.app](https://hasrat-dev.netlify.app)  
**GitHub:** [github.com/hasratsi-del/DISPATCH.](https://github.com/hasratsi-del/DISPATCH.)

DISPATCH fetches live global news, scores sentiment using NLP, aggregates signals by country, and renders them on an interactive world map — with a rotating Three.js globe, three analysis modes, an AI situation report, and country search.

---

## Quickstart (one command after first setup)

```bash
export NEWS_API_KEY=a6b91b19dbec4d3cb461e157d37a6854
./start.sh
```

---

## First time setup (run once, never again)

```bash
cd ~/Downloads/dispatch-project/backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

---

## Every time you want to run it

Open a terminal and run these four commands in order:

```bash
cd ~/Downloads/dispatch-project/backend
source .venv/bin/activate
export NEWS_API_KEY=a6b91b19dbec4d3cb461e157d37a6854
python app.py
```

You should see this in your terminal — this means it's working:

```
* Serving Flask app 'app'
* Debug mode: off
WARNING: This is a development server...
* Running on all addresses (0.0.0.0)
* Running on http://127.0.0.1:5000
* Running on http://172.20.10.4:5000
Press CTRL+C to quit
```

Then open a **new terminal tab (Cmd+T)** and run:

```bash
open ~/Downloads/dispatch-project/frontend/index.html
```

The map will open in your browser and pull live data from the backend.

**To stop the backend:** Press `Ctrl+C` in the backend terminal tab.

---

## If you restart your Mac

You will need to run the four commands above again. The `.venv` folder is permanent so you never need to reinstall packages — just activate and run.

---

## Deploy (free, $0)

### Backend → Railway
1. Push the `backend/` folder to a new GitHub repo
2. Connect to [railway.app](https://railway.app) — it auto-detects Flask from `railway.toml`
3. Add `NEWS_API_KEY` as an environment variable in Railway dashboard
4. Copy your Railway URL (looks like `https://dispatch-xxx.railway.app`)

### Frontend → Netlify
1. Open `frontend/index.html` in a text editor
2. Find the line with `YOUR-RAILWAY-URL` and replace with your Railway URL
3. Drag the `frontend/` folder onto [netlify.app](https://netlify.app)

---

## How it works

```
NewsAPI (live headlines, 1000+ sources)
        ↓
Flask backend — Python
  — fetches news every 5 minutes
  — TextBlob sentiment scoring per article (-1.0 to +1.0)
  — country detection via keyword matching (100+ mappings)
  — aggregates average score per ISO country code
  — 5-minute cache to respect API rate limits
  — /api/sentiment JSON endpoint
        ↓
D3.js + Three.js frontend
  — rotating Three.js globe with live sentiment dots
  — D3 Natural Earth world map, zoom + pan
  — three map modes: Sentiment / Heat / Volume
  — hover tooltips with real clickable article links
  — AI situation report (local analysis)
  — country search with map highlight
  — intelligence briefing cards
  — full trending index ranked by coverage
```

---

## Features

| Feature | Description |
|---|---|
| **Sentiment map** | Countries colored red → gray → gold by news sentiment |
| **Heat mode** | Most extreme countries glow, signal strength bars appear |
| **Volume mode** | Which countries dominate the news cycle |
| **◈ AI Report** | One-click: global tone, stress zones, stable zones |
| **Country search** | Type any country — highlights it on map with score |
| **Live globe** | Three.js rotating globe with pulsing sentiment dots |
| **Article links** | Every tooltip has real clickable headlines |
| **Trending index** | Full ranked list of top 15 most-covered countries |

---

## Stack

| Layer | Technology |
|---|---|
| Backend | Python 3.11, Flask, TextBlob, Gunicorn |
| NLP | TextBlob sentiment analysis |
| Data | NewsAPI (live global headlines) |
| Frontend | Vanilla JS, D3.js v7, Three.js r128 |
| Deployment | Railway (backend) + Netlify (frontend) |
| Cost | **$0** |

---

## Push to GitHub

```bash
git init
git add .
git commit -m "feat: DISPATCH geopolitical intelligence engine"
git branch -M main
git remote add origin https://github.com/hasratsi-del/DISPATCH..git
git push -u origin main
```

---

## Built by

**Hasrat Singh Chauhan**  
Computing Science & Mathematics, University of Alberta  
[at-quorum.netlify.app](https://at-quorum.netlify.app) · [github.com/hasratsi-del](https://github.com/hasratsi-del)
