# Strategy Recommendations
**Project:** Customer Lifecycle & Campaign Effectiveness Analysis  
**Author:** Amrit Sharma  
**Date:** March 2026  

---

## Executive Summary

Analysis of 779,425 transactions across 5,878 customers reveals a highly concentrated revenue base with significant retention risk. Champions (25.2% of customers) generate 69.2% of total revenue — £12M of £17.4M. A further £5.5M in annual revenue is at measurable churn risk across four segments. The findings support a differentiated CRM strategy: protect the top, recover the middle, suppress the bottom.

---

## Key Findings

### 1. Revenue is dangerously concentrated

69.2% of total revenue comes from Champions alone. This is not unusual for e-commerce but it creates structural fragility — the loss of even a small number of top-tier customers has outsized revenue impact. Customer 18102 alone accounts for £580,987.

**Implication:** Champion retention is not a CRM priority among many — it is the single highest-leverage activity in the business.

---

### 2. £5.5M in annual revenue is at measurable churn risk

The churn model identifies five segments requiring active intervention, totalling £5,503,679 in revenue at risk:

| Segment | Customers | Revenue at Risk | Avg Churn Probability |
|---|---|---|---|
| Champions (Early Warning) | 512 | £940,416 | 38.5% |
| Loyal Customers | 1,221 | £2,510,046 | 44.5% |
| Need Attention | 551 | £1,129,337 | 46.0% |
| At Risk | 89 | £269,453 | 35.2%* |
| Lost | 1,523 | £654,427 | 73.5% |

*At Risk probability is model-underestimated due to recency exclusion — see Section 4.

---

### 3. Frequency predicts churn better than spend

The churn model's feature importance analysis shows Frequency (0.41) outperforms Monetary value as a loyalty signal. A customer who spent £5,000 in a single order is more likely to churn than a customer who spent £500 across 10 orders.

**Implication:** CRM re-engagement triggers should be frequency-based — lapsed purchase intervals — not spend-based. Reward programmes should incentivise repeat visits, not minimum basket size.

---

### 4. At Risk customers require manual CRM override

89 customers carry an average recency of 493 days — completely silent — but the model assigns only 35.2% churn probability because it correctly identifies their historical purchase frequency as high. This is not a model error. Recency was excluded from features to prevent data leakage, creating a known blind spot.

These 89 customers spent an average of £3,028 and represent £269,453 in historically high-value revenue that has gone silent. The model cannot flag them adequately. A manual CRM override is required.

**Action:** Export this segment directly from Notebook 03 and assign to a personal win-back sequence outside of automated flows.

---

### 5. Paid Search is the primary revenue-driving channel across all attribution models

Attribution analysis across first-touch, last-touch, and linear models consistently ranks Paid Search first (30–34% share) and Email second (24–27%). Critically, Paid Search performs strongly on both first-touch (£0.73M) and last-touch (£0.78M) — indicating it functions as both an acquisition and conversion channel, not just top-of-funnel.

**Implication:** Always-on Paid Search investment is justified. Burst or seasonal-only strategy would undermine both acquisition and conversion performance simultaneously.

---

### 6. Linear attribution reveals hidden mid-funnel value

When credit is distributed equally across all touchpoints, Direct and Organic together account for £2.09M — value that single-touch models suppress by attributing everything to the first or last interaction. Social, by contrast, remains consistently low across all three models (8–10%), suggesting genuine underperformance rather than measurement bias.

---

## Recommended Actions

### CRM Strategy (Klaviyo)

**Champions — VIP Retention Flow**  
512 early-warning Champions showing 38.5% churn probability despite recent activity. These are occasional buyers in the Champion tier, not core buyers (avg spend £1,833 vs £8,114 full Champion average). Trigger: exclusivity and early access messaging. No discounts — this segment is price-insensitive and discount exposure erodes perceived brand value.

**Loyal Customers — Loyalty Reward Flow**  
1,221 customers, £2.5M at risk, 44.5% predicted churn. Highest absolute revenue risk of any single segment. Trigger: loyalty milestone reward at defined purchase interval. Goal: extend frequency, not increase basket size.

**Need Attention — Urgent Re-engagement**  
551 customers who have shown purchase intent historically but are drifting. Time-limited offer with clear expiry. Urgency framing performs well for this segment — they respond to scarcity signals rather than relationship messaging.

**At Risk — Manual Personal Outreach**  
89 customers, manually prioritised. Personalised win-back email referencing their purchase history. Suppress from all paid channels during outreach period — the cost-per-click on a customer already receiving a personal email is wasted spend.

**Lost — Final Win-Back Then Suppress**  
1,523 customers at 73.5% predicted churn. One final win-back attempt with a meaningful incentive. If no response within 30 days, suppress permanently from all paid and email activity. Continuing to spend on this segment beyond one attempt delivers negative ROI.

---

### Google Ads Strategy

**Champions (Early Warning) — Customer Match Remarketing**  
Upload 512-customer list as a Customer Match audience. Target with brand and category terms. Bid modifier +30%. These customers are still active — the goal is to intercept the next purchase before a competitor does.

**Loyal Customers — RLSA Bid Boost**  
Add Loyal Customers as an RLSA (Remarketing Lists for Search Ads) audience with +20% bid adjustment. They are searching — ensure visibility is maximised when they do.

**Need Attention — Win-Back Display Campaign**  
Separate Display campaign targeting Need Attention list. Frequency cap at 3 impressions per day to avoid fatigue. Creative should focus on new arrivals or seasonal ranges — remind them what they are missing, not what they spent before.

**At Risk — Suppress from Paid**  
Exclude At Risk segment from all paid activity during personal outreach window. Paid impressions on a customer receiving a personal email add cost without incrementality.

**Lost — Exclude Entirely**  
Add Lost segment as a negative audience across all campaigns. These customers are suppressing CTR, increasing CPCs, and wasting budget. Removing them improves overall campaign efficiency immediately.

---

### Budget Reallocation Recommendation

Based on attribution analysis, Social underperforms consistently (8–10% share across all three models). This is not a measurement artefact — it is consistent across first-touch, last-touch, and linear models, meaning Social is neither acquiring nor converting customers effectively.

Reallocate Social budget to:
- **Paid Search** — highest and most consistent attribution across all models
- **Email infrastructure** — Klaviyo flow build and A/B testing investment delivers compounding returns

---

## Methodology Notes

**Dataset:** Online Retail II (UCI Machine Learning Repository) — 1,067,371 raw transactions, UK-based gift and homeware retailer, 2009–2011.

**Cleaning:** 22.77% of rows removed — missing Customer IDs (cancellations and guest checkouts), duplicates, and returns. Final dataset: 779,425 transactions across 5,878 identified customers.

**RFM Segmentation:** Quintile-based scoring (1–5) across Recency, Frequency, and Monetary dimensions. Seven segments assigned using industry-standard RFM segment mapping.

**Churn Model:** Logistic Regression (ROC-AUC 0.777) trained on Frequency, F_Score, and M_Score. Recency excluded to prevent data leakage — churn defined as Recency > 90 days. Random Forest tested (ROC-AUC 0.773) but Logistic Regression selected for marginal performance advantage and interpretability.

**Attribution:** Channels simulated based on segment behavioural patterns from EDA. Three models compared: first-touch, last-touch, linear. Real-world implementation would use GA4 API or platform-level attribution data.

**SQL:** Eight analytical queries run against a local SQLite database (785,303 rows across two tables) confirming Python findings independently.
