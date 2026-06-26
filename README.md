# 🏏 IPL Cricket Data Analysis — Streamlit Dashboard

An interactive IPL dashboard covering 16 seasons (2008–2023) with team stats, batting records, toss analysis, and title history.

## 🚀 Quick Start (Local)

```bash
# 1. Clone or download this project
cd ipl_dashboard

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the app
streamlit run app.py
```

The app opens at **http://localhost:8501**

---

## ☁️ Deploy on Streamlit Community Cloud (Free)

1. Push this folder to a **GitHub repository**
2. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub
3. Click **"New app"**
4. Select your repo, branch (`main`), and set **Main file path** to `app.py`
5. Click **Deploy** — your app will be live in ~2 minutes!

No server setup needed. Free hosting for public repos.

---

## 📁 Project Structure

```
ipl_dashboard/
├── app.py              ← Main Streamlit application
├── requirements.txt    ← Python dependencies
└── README.md           ← This file
```

---

## 📊 Features

| Section | Details |
|---|---|
| KPI cards | Matches, teams, field-first %, chasing wins %, top team |
| Team wins chart | Bar chart — filterable by season & top N teams |
| Toss impact | How often teams bat vs field after winning toss |
| Win margin type | Pie chart — wins by wickets vs runs |
| Season trends | Matches per year + sixes hit per season |
| Top 10 batsmen | Runs, matches, SR, 50s, 100s with gradient table |
| Title history | All 16 IPL champions with runner-up & margin |

---

## 🛠️ Tech Stack

- **Streamlit** — UI framework
- **Plotly Express** — interactive charts
- **Pandas** — data wrangling

---

## 📌 Extend This Project

Ideas to level up your portfolio:

- Add a real CSV dataset from [Kaggle IPL dataset](https://www.kaggle.com/datasets/patrickb1912/ipl-complete-dataset-20082020)
- Add a **player search** page
- Add **bowling stats** (wickets, economy rate)
- Connect to a live cricket API for real-time scores
- Add **machine learning** — predict match winner based on toss & venue
