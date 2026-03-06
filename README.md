# Customer Lifecycle & Campaign Effectiveness Analysis
**E-commerce Marketing Analytics | Python · SQL · RFM · Machine Learning · Attribution**

---

## Overview

An end-to-end marketing analytics project analysing 1,067,371 transactions from a 
UK-based e-commerce retailer to answer four core business questions:

1. **What does our data look like?** — EDA & cleaning to build a trusted analytical foundation
2. **Who are our customers?** — RFM segmentation to identify high-value, at-risk, and lost tiers
3. **Who will churn?** — Predictive churn model to enable proactive retention
4. **Which channels drive value?** — Campaign attribution to optimise marketing spend

Findings are translated into actionable CRM and paid media recommendations — 
bridging data analysis with real-world marketing strategy using Klaviyo lifecycle 
flows and Google Ads audience targeting.

---

## Project Structure
```
├── notebooks/
│   ├── 01_eda.ipynb                  # Data cleaning & exploratory analysis
│   ├── 02_rfm_segmentation.ipynb     # RFM scoring & customer personas
│   ├── 02b_sql_analysis.ipynb        # SQL queries against transaction & RFM database
│   ├── 03_churn_model.ipynb          # Churn prediction (Logistic Regression & Random Forest)
│   └── 04_campaign_attribution.ipynb # Channel attribution & ROI analysis
├── data/
│   └── data_source.md                # Dataset info & download instructions
├── outputs/                          # Charts and model outputs
├── strategy_recommendations.md       # CRM & paid media strategy layer
└── README.md
```

---

## Notebooks

| # | Notebook | Description |
|---|---|---|
| 01 | EDA & Cleaning | Schema review, null/duplicate handling, revenue trends, purchase timing analysis |
| 02 | RFM Segmentation | Recency/Frequency/Monetary scoring, 7 customer personas, Pareto analysis |
| 02b | SQL Analysis | 8 analytical queries — JOINs, window functions, GROUP BY, cohort analysis |
| 03 | Churn Model | Logistic Regression vs Random Forest, ROC-AUC evaluation, marketing action layer |
| 04 | Attribution | First-touch, last-touch, linear attribution comparison; channel ROI |

---

## Key Findings

- **Top 20% of customers generate 77.2% of total revenue** — Pareto effect confirmed
- **Champions (25.2% of base) drive 69.2% of revenue (£12,024,330)** — highest retention priority
- **Churn model ROC-AUC: 0.777** — Logistic Regression outperformed Random Forest (0.773)
- **Frequency is the strongest churn predictor** — order behaviour beats spend value as a loyalty signal
- **512 Champions flagged as early warning** — active (avg 24 days recency) but showing drift signals
- **At Risk segment: 89 customers, avg spend £3,028, avg 493 days silent** — manual CRM override required, model underestimates churn risk due to feature design
- **Peak trading window: Thursday 11am–1pm** — primary Google Ads bid scheduling & Klaviyo send-time
- **Total revenue at risk across churn segments: £5,503,679**
- **Top international markets: Netherlands, EIRE, Germany** — European expansion priority

---

## Tools & Techniques

- **Python:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
- **SQL:** SQLite — JOINs, window functions, GROUP BY aggregations, subqueries
- **ML Techniques:** Logistic Regression, Random Forest, ROC-AUC evaluation
- **Analytics:** RFM Analysis, Churn Prediction, Multi-touch Attribution
- **Marketing Frameworks:** Customer Lifetime Value, Lifecycle Segmentation, 
Google Ads Customer Match, Klaviyo Flow Architecture

---

## Strategy Recommendations

See `strategy_recommendations.md` for:
- Klaviyo lifecycle flows mapped to each RFM segment
- Google Ads audience strategy (Customer Match, RLSA, lookalike seeds)
- Churn intervention priority list with revenue at risk per segment
- Send-time and bid scheduling recommendations from EDA timing analysis

---

## Dataset

**Online Retail II — UCI Machine Learning Repository**  
~1M transactions | UK-based retailer | Dec 2009 – Dec 2011  
[Download here](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
