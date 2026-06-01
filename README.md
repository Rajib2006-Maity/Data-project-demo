# Data-project-demo
This my second Data Analyst project
# 📊 Indian Stock Market — Data Analysis Capstone Project

> **Bluestock Fintech Internship
> A complete end-to-end data analysis project on 12 NSE-listed stocks (Jan 2023 – Dec 2024)

---

## 🗂️ Project Structure

```
Stock_Market_Analysis/
│
├── data/
│   ├── generate_dataset.py     ← Synthetic dataset generator
│   ├── stock_data.csv          ← 6,264 rows × 10 columns
│   └── stock_market.db         ← SQLite database
│
├── notebooks/
│   ├── eda_analysis.py         ← Full EDA with 10 charts
│   └── ml_model.py             ← Price prediction (LR + RF)
│
├── sql/
│   ├── sql_analysis.py         ← 10 business SQL queries
│   └── (analysis_queries.sql)  ← Raw SQL reference file
│
├── flask_app/
│   └── app.py                  ← REST API with 8 endpoints
│
├── images/                     ← All 12 generated charts
├── reports/                    ← Final report (add here)
├── requirements.txt
└── README.md
```

---

## 📦 Dataset

| Field | Value |
|---|---|
| **Stocks** | RELIANCE, TCS, HDFCBANK, INFY, ICICIBANK, HINDUNILVR, SBIN, BAJFINANCE, WIPRO, TITAN, MARUTI, SUNPHARMA |
| **Sectors** | Energy, IT, Banking, FMCG, Finance, Consumer, Auto, Pharma |
| **Period** | Jan 2023 – Dec 2024 (522 trading days × 12 stocks) |
| **Total Rows** | 6,264 |
| **Columns** | Date, Stock, Sector, Open, High, Low, Close, Volume, Turnover_Cr, Market_Cap |

---

## 📈 EDA — 10 Charts Generated

| # | Chart | Description |
|---|-------|-------------|
| 1 | Price Trends + MA | Close price with 20-day & 50-day moving averages |
| 2 | Sector Avg Price | Horizontal bar chart by sector |
| 3 | Correlation Heatmap | Stock-to-stock close price correlation |
| 4 | Daily Return Distribution | Boxplot per stock |
| 5 | Monthly Volume Heatmap | Trading activity across months |
| 6 | Sector Volume Donut | Market share by trading volume |
| 7 | Volatility Comparison | 20-day rolling std deviation |
| 8 | Yearly Return (2023 vs 2024) | Grouped bar comparison |
| 9 | Top 10 Best Days | Highest single-day returns |
| 10 | Summary Dashboard | 4-panel overall view |

---

## 🗃️ SQL Analysis — 10 Queries

| # | Query |
|---|-------|
| Q1 | Top 5 stocks by average trading volume |
| Q2 | Sector-wise average closing price |
| Q3 | Bullish days % per stock |
| Q4 | Most volatile stocks (price range) |
| Q5 | Top 10 highest volume days |
| Q6 | Monthly avg close for IT sector (2024) |
| Q7 | Best single-day gain per stock |
| Q8 | Total market cap by sector |
| Q9 | Stocks above 200-day average |
| Q10 | Quarter-wise volume trend |

---

## 🌐 Flask REST API — 8 Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | API info & route listing |
| GET | `/stocks` | All stocks with latest close |
| GET | `/summary` | Dataset-level statistics |
| GET | `/top-gainers?n=5` | Top N stocks by avg daily return |
| GET | `/sector` | Sector aggregated stats |
| GET | `/stock/<symbol>` | Individual stock deep-dive |
| GET | `/compare?stocks=TCS,INFY` | Side-by-side comparison |
| GET | `/search?q=banking` | Search by name or sector |

### Run the API
```bash
cd flask_app
python app.py
# Visit: http://127.0.0.1:5000
```

---

## 🤖 ML Models (Bonus)

Two models trained to predict **next-day closing price**:

- **Linear Regression** — Best on INFY (R² = 0.9764)
- **Random Forest** — Best on ICICIBANK (R² = 0.9474)

Features engineered: MA_5, MA_20, MA_50, 1d/5d returns, rolling volatility, volume ratio, high-low range.

---

## 🔍 Key Business Insights

| Insight | Finding |
|---------|---------|
| 📈 Best daily return | **SBIN** (+0.156%/day avg) |
| 📉 Worst daily return | **HDFCBANK** (-0.082%/day avg) |
| ⚡ Most volatile | **MARUTI** (₹14,064 price range) |
| 🏆 Best sector | **Auto** (highest avg return) |
| 🟢 Most bullish | **SBIN** (53.4% green days) |
| 💰 Highest market cap | **Auto sector** (₹19.3L Cr) |
| 📦 Highest volume | **SUNPHARMA** (6.39M avg/day) |
| 📅 2024 vs 2023 | Turnover grew 20%+ across all quarters |

---

## ⚙️ Setup & Run

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/Stock_Market_Analysis.git
cd Stock_Market_Analysis

# 2. Install dependencies
pip install -r requirements.txt

# 3. Generate dataset
python data/generate_dataset.py

# 4. Run EDA (saves 10 charts to images/)
python notebooks/eda_analysis.py

# 5. Run SQL analysis
python sql/sql_analysis.py

# 6. Train ML models
python notebooks/ml_model.py

# 7. Start Flask API
python flask_app/app.py
```

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| Data | Pandas, NumPy |
| Visualisation | Matplotlib, Seaborn |
| Database | SQLite3 |
| API | Flask |
| ML | scikit-learn (Linear Regression, Random Forest) |


