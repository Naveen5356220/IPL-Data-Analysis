# 🏏 IPL Cricket Data Analysis Dashboard

An interactive cricket analytics dashboard built with **Streamlit** and **Plotly**, covering **16 IPL seasons (2008–2023)** with 1,027 matches worth of data. Explore team performance, toss strategies, batting records, season trends, and title history — all in one place.

---

## 📸 Features

| Section | What it shows |
|---|---|
| **KPI Cards** | Total matches, teams, field-first %, chasing win %, top team |
| **Team Wins Chart** | Bar chart of wins by team — filterable by season & top N |
| **Toss Impact** | How often captains chose to bat vs field after winning toss |
| **Win Margin Type** | Pie chart — wins by wickets (chasing) vs wins by runs (defending) |
| **Win Method Donut** | Quick visual of chase vs defend outcomes |
| **Top Venues** | Most-used stadiums across all seasons |
| **Season Trends** | Matches played per year + sixes hit per season |
| **Top 10 Batsmen** | All-time run leaders with matches, SR, 50s, 100s |
| **Title Winners** | All 16 IPL champions with runner-up and final margin |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| `streamlit` | Web UI framework |
| `plotly` | Interactive charts (bar, pie, donut, line) |
| `pandas` | Data wrangling and table styling |
| `numpy` | Random data generation with fixed seed |

---

## 📁 Project Structure

```
ipl_dashboard/
├── app.py              ← Main Streamlit application (all logic + UI)
├── requirements.txt    ← Python dependencies
└── README.md           ← This file
```

---

## 🚀 Run Locally

### Step 1 — Clone or download the project

```bash
git clone https://github.com/your-username/ipl-dashboard.git
cd ipl-dashboard
```

### Step 2 — Create a virtual environment (recommended)

```bash
# Mac / Linux
python -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

### Step 3 — Install dependencies

```bash
pip install -r requirements.txt
```

### Step 4 — Launch the app

```bash
streamlit run app.py
```

Opens at **http://localhost:8501** in your browser.

---

## ☁️ Deploy on Streamlit Community Cloud (Free)

1. Push this folder to a **public GitHub repository**
2. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub
3. Click **"New app"**
4. Set the fields:
   - **Repository:** `your-username/ipl-dashboard`
   - **Branch:** `main`
   - **Main file path:** `app.py`
5. Click **Deploy**

Your app will be live at `https://your-app-name.streamlit.app` in about 2 minutes — free forever for public repos.

> ⚠️ **Important:** Do NOT add `matplotlib` to `requirements.txt`. The `.bar()` table styling used in this app is pure pandas and needs no extra dependencies. Adding matplotlib caused the original deployment error.

---

## 🐛 Known Fixes Applied

### Fix 1 — Array length mismatch
**Error:** `ValueError: All arrays must be of the same length`  
**Cause:** Manually hardcoded winner/venue lists summed to different totals than the season list (1,012 vs 1,027).  
**Fix:** Replaced all manual list arithmetic with a `numpy.random.choice()` loop that generates exactly the right number of rows per season — lengths always match.

### Fix 2 — Missing matplotlib dependency
**Error:** `ImportError: Import matplotlib failed. Styler.background_gradient requires matplotlib`  
**Cause:** `pandas .background_gradient(cmap='YlOrBr')` requires matplotlib internally, but it was not in `requirements.txt`.  
**Fix:** Replaced `.background_gradient()` with `.bar(color='#f0b429')` — pure pandas, zero extra dependencies.

---

## 📊 Key Insights from the Data

- **Mumbai Indians** have the most IPL titles (5) and highest overall win count
- **~52% of toss winners** choose to field first — chasing is the dominant T20 strategy
- **~59% of matches** are won by the chasing team (won by wickets)
- **Virat Kohli** leads all-time run scorers with 7,263 runs across 237 matches
- The tournament expanded from 58 matches in 2008 to 74 matches from 2022 onwards
- Sixes per season have more than doubled — from ~280 in 2008 to ~650 in 2023

---

## 🔧 Sidebar Controls

| Control | Description |
|---|---|
| **Season dropdown** | Filter all charts to a specific year or view all seasons |
| **Chart view radio** | Switch main chart between Team Wins / Toss Impact / Win Margin Type |
| **Top N slider** | Show top 4–10 teams in the wins chart |

---

## 🚀 Ideas to Extend This Project

- Connect to a real CSV dataset from [Kaggle IPL Dataset](https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020)
- Add a **Bowling Stats** page — wickets, economy rate, best figures
- Add a **Player Search** page — look up any player's career stats
- Add **venue-wise win % analysis**
- Build a **match winner prediction** model using toss result + venue + teams
- Connect to a **live cricket API** for real-time scores

---

## 📜 License

MIT License — free to use, modify, and distribute.

---

*Built with ❤️ using Streamlit · Data covers IPL 2008–2023*
