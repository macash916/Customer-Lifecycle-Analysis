# Customer-Lifecycle-Analysis
# Customer Lifecycle & Campaign Effectiveness Analysis
### E-commerce Marketing Analytics | Python · RFM · ML · Attribution

---

## Overview

A end-to-end marketing analytics project analysing **~1M transactions** from a UK-based e-commerce retailer to answer three core business questions:

1. **Who are our customers?** — RFM segmentation to identify high-value, at-risk, and lost customer tiers
2. **Who will churn?** — Predictive churn model to enable proactive retention
3. **Which channels drive value?** — Campaign attribution analysis to optimise marketing spend

Findings are translated into actionable CRM and paid media recommendations — bridging data analysis with real-world marketing strategy.

---

## Project Structure

```
├── notebooks/
│   ├── 01_eda.ipynb                  # Data cleaning & exploratory analysis
│   ├── 02_rfm_segmentation.ipynb     # RFM scoring & customer personas
│   ├── 03_churn_model.ipynb          # Churn prediction (classification)
│   └── 04_campaign_attribution.ipynb # Channel attribution & ROI analysis
├── data/
│   └── data_source.md                # Dataset info & download instructions
├── outputs/                          # Charts and model summaries
├── strategy_recommendations.md       # CRM & paid media strategy layer
└── README.md
```

---

## Notebooks

| # | Notebook | Description |
|---|---|---|
| 01 | EDA & Cleaning | Schema review, null/duplicate handling, revenue trends, purchase timing |
| 02 | RFM Segmentation | Recency/Frequency/Monetary scoring, customer persona clustering |
| 03 | Churn Model | Feature engineering, Logistic Regression vs Random Forest, ROC/AUC |
| 04 | Attribution | First-touch, last-touch, linear attribution comparison; channel ROI |

---

## Key Findings *(populated after analysis)*

- **X% of customers** generate **Y% of revenue** (Pareto analysis)
- Churn model achieved **X% AUC** — top predictors: recency, order frequency, avg basket size
- Peak purchase window: **Thursday 11am–1pm** → primary bid scheduling / email send-time window
- Win-back opportunity: **X,XXX customers** in "At Risk" segment with £XX average historical LTV

---

## Tools & Techniques

- **Python:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, Plotly
- **Techniques:** RFM Analysis, K-Means Clustering, Logistic Regression, Random Forest, Attribution Modelling
- **Marketing frameworks:** Customer Lifetime Value, Lifecycle Segmentation, Multi-touch Attribution

---

## Strategy Recommendations

See [`strategy_recommendations.md`](./strategy_recommendations.md) for CRM lifecycle flows, Google Ads audience strategy, and Klaviyo email sequence recommendations derived from the analysis.

---

## Dataset

Online Retail II — UCI Machine Learning Repository  
~1M transactions | UK-based retailer | Dec 2009 – Dec 2011  
[Download here](https://archive.ics.uci.edu/dataset/502/online+retail+ii)

---
