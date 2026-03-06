# Strategy Recommendations
**Project:** Customer Lifecycle & Campaign Effectiveness Analysis  
**Author:** Amrit Sharma  
**Date:** March 2026  

---

## Executive Summary

Analysis of 779,425 transactions across 5,878 customers reveals a highly concentrated revenue base with significant retention risk. Champions (25.2% of customers) generate 69.2% of total historical revenue — £12M of £17.4M. A Customer Lifetime Value model projects £6.7M in forward 12-month portfolio value, of which £4.8M (71.4%) is concentrated in Champions alone. £445,269 in projected forward CLV is at measurable churn risk across customers with >50% churn probability. The findings support a differentiated CRM strategy: protect the top, recover the middle, suppress the bottom.

---

## Key Findings

### 1. Revenue is dangerously concentrated — in both historical and forward terms

69.2% of total historical revenue comes from Champions alone. The CLV model confirms this concentration extends into projected future value: Champions generate 71.4% of the 12-month forward portfolio (£4.8M of £6.7M) from just 25% of customers. This is more extreme than a standard Pareto distribution.

Customer 18102 alone accounts for £580,987 in historical spend.

**Implication:** Champion retention is not a CRM priority among many — it is the single highest-leverage activity in the business. Every pound spent retaining a Champion protects approximately £3,230 in projected 12-month CLV.

---

### 2. £445K in forward CLV is at measurable churn risk

The churn model flags 3,275 customers with >50% churn probability. Their combined projected 12-month CLV is £445,269. This replaces the £5.5M "revenue at risk" figure from the churn notebook — that figure represented historical spend, not forward value. £445K is the actual financial case for retention campaign investment.

| Segment | Customers | CLV 12M Total | Mean CLV 12M | Portfolio Share |
|---|---|---|---|---|
| Champions | 1,482 | £4,786,184 | £3,230 | 71.4% |
| Loyal Customers | 1,221 | £697,630 | £571 | 10.4% |
| Need Attention | 551 | £507,002 | £920 | 7.6% |
| At Risk | 89 | £300,206 | £3,373 | 4.5% |
| Lost | 1,523 | £250,593 | £165 | 3.7% |
| New Customers | 184 | £97,726 | £531 | 1.5% |
| Potential Loyal | 828 | £66,921 | £81 | 1.0% |

**Total projected portfolio CLV: £6,706,263 (12M) · £10,714,196 (24M)**

---

### 3. At Risk customers have near-Champion CLV — and are being missed by automation

89 customers carry a mean CLV of £3,373 — nearly identical to Champions (£3,230). Their historical purchase frequency was high; they simply have not returned. The churn model assigns only 35.2% churn probability to this segment because Recency was excluded from features to prevent data leakage — a known model blind spot.

These 89 customers cannot be adequately flagged by automated scoring. They require a manual CRM override. Each one individually justifies bespoke personalised outreach — not an automated campaign.

**Action:** Export this segment from Notebook 03, cross-reference with `data/top50_priority_retention.csv`, and assign to a personal win-back sequence outside automated flows. Exclude from all paid channels during this window.

---

### 4. Top 50 customers account for 37.9% of total projected portfolio CLV

The CLV model identifies 50 customers whose combined 12-month projected value is £2,544,523 — 37.9% of the entire portfolio. These customers should be known by name in the CRM. Their details are exported to `data/top50_priority_retention.csv`.

**Implication:** A personalised retention programme for 50 people protects nearly £2.5M in projected annual revenue. The cost-benefit case for white-glove treatment of this cohort is clear.

---

### 5. Frequency predicts churn better than spend

The churn model's feature importance analysis shows Frequency (0.41) outperforms Monetary value as a loyalty signal. A customer who spent £5,000 in a single order is more likely to churn than a customer who spent £500 across 10 orders.

**Implication:** CRM re-engagement triggers should be frequency-based — lapsed purchase intervals — not spend-based. Reward programmes should incentivise repeat visits, not minimum basket size.

---

### 6. Paid Search is the primary revenue-driving channel across all attribution models

Attribution analysis across first-touch, last-touch, and linear models consistently ranks Paid Search first (30–34% share) and Email second (24–27%). Paid Search performs strongly on both first-touch (£0.73M) and last-touch (£0.78M) — indicating it functions as both an acquisition and conversion channel.

**Implication:** Always-on Paid Search investment is justified. Burst or seasonal-only strategy would undermine both acquisition and conversion performance simultaneously.

---

### 7. Linear attribution reveals hidden mid-funnel value

When credit is distributed equally across all touchpoints, Direct and Organic together account for £2.09M — value that single-touch models suppress. Social remains consistently low across all three models (8–10%), suggesting genuine underperformance rather than measurement bias.

---

## Recommended Actions

### CRM Strategy (Klaviyo)

**Champions — VIP Retention Flow**  
512 early-warning Champions showing 38.5% churn probability. Mean CLV £3,230. Trigger: exclusivity and early access messaging. No discounts — this segment is price-insensitive and discount exposure erodes perceived brand value. Thursday 9–11am send window aligned to EDA peak trading hours.

**Loyal Customers — Loyalty Reward Flow**  
1,221 customers, CLV £697,630, 44.5% predicted churn. Highest absolute forward CLV risk after Champions. Trigger: loyalty milestone reward at defined purchase interval. Goal: extend frequency, not increase basket size.

**Need Attention — Urgent Re-engagement**  
551 customers, CLV £507,002. Time-limited offer with clear expiry. Urgency framing performs well for this segment — they respond to scarcity signals rather than relationship messaging.

**At Risk — Manual Personal Outreach (Priority Override)**  
89 customers, mean CLV £3,373 — nearly matching Champions. Personalised win-back email referencing specific purchase history. Suppress from all paid channels during outreach period. This cohort must be handled manually — the automated model underestimates their churn risk due to the Recency exclusion in the churn model feature set.

**Lost — Final Win-Back Then Suppress**  
1,523 customers, mean CLV only £165, 73.5% predicted churn. One final win-back attempt with a meaningful incentive (20% discount — used once only, this segment only). If no response within 30 days, suppress permanently from all paid and email activity.

---

### Google Ads Strategy (£12,500/month)

**Campaign 01 — Champions Retention (£3,500/mo)**  
Upload 512-customer Customer Match list. Brand and category search terms. Bid modifier +30%. Target ROAS 600%. Thursday 9am–1pm +25% bid boost aligned to EDA peak trading window.

**Campaign 02 — Loyal RLSA Boost (£4,000/mo)**  
Add Loyal Customers as RLSA audience with +20% bid adjustment. Target CPA £18. Maximise search visibility for this segment — they are actively looking.

**Campaign 03 — Win-Back Display (£3,500/mo)**  
Separate Display campaign targeting Need Attention list. Three-phase creative sequence: new arrivals → seasonal range → time-limited offer. Frequency cap 3 impressions/day. Target CPA £18.

**Campaign 04 — Lost Suppression (£1,500/mo)**  
Add Lost segment as negative audience across all campaigns. Removes CPM/CPC waste and improves overall campaign quality score immediately.

**At Risk — Excluded from all paid campaigns**  
89 customers receive bespoke Klaviyo outreach only. Paid impressions on a customer receiving a personal email add cost without incrementality. Given their mean CLV of £3,373, mis-handling this cohort is the highest-cost mistake available in the campaign plan.

---

### Budget Reallocation Recommendation

Social underperforms consistently (8–10% attribution share across all three models). Reallocate Social budget to:
- **Paid Search** — highest and most consistent attribution across all models
- **Email infrastructure** — Klaviyo flow build and A/B testing delivers compounding returns as CLV grows over the 24-month horizon

---

## CLV Model Methodology

**Model type:** Survival-weighted Discounted Cash Flow  
**Horizon:** 12 months and 24 months  
**Discount rate:** 10% annual (0.83% monthly) — standard marketing CLV convention reflecting cost of capital  
**Inputs per customer:** AOV (Monetary ÷ Frequency), purchase rate (Frequency ÷ active_days × 30), monthly churn probability  
**Churn conversion:** 90-day model output converted to monthly: P(monthly) = 1 − (1 − P90d)^(1/3) — prevents 3× overstatement of monthly risk  
**Survival decay:** P(alive) multiplied by (1 − monthly churn) at each month m, accumulated over the full horizon  
**Output files:** `data/rfm_with_clv.csv` (all 5,878 customers with CLV columns), `data/top50_priority_retention.csv` (priority CRM list)

**Production note:** BG/NBD + Gamma-Gamma (lifetimes library) would be applied to raw transaction-level data in a production environment. The survival-DCF approach was chosen here because the input dataset is aggregated to customer-level RFM.

---

## General Methodology Notes

**Dataset:** Online Retail II (UCI Machine Learning Repository) — 1,067,371 raw transactions, UK-based gift and homeware retailer, 2009–2011.

**Cleaning:** 22.77% of rows removed — missing Customer IDs, duplicates, and returns. Final dataset: 779,425 transactions across 5,878 identified customers.

**RFM Segmentation:** Quintile-based scoring (1–5) across Recency, Frequency, and Monetary dimensions. Seven segments assigned using industry-standard RFM segment mapping.

**Churn Model:** Logistic Regression (ROC-AUC 0.777) trained on Frequency, F_Score, and M_Score. Recency excluded to prevent data leakage — churn defined as Recency > 90 days. Random Forest tested (ROC-AUC 0.773) but Logistic Regression selected for interpretability.

**Attribution:** Channels simulated based on segment behavioural patterns from EDA. Three models compared: first-touch, last-touch, linear. Real-world implementation would use GA4 API or platform-level attribution data.

**SQL:** Eight analytical queries run against a local SQLite database (785,303 rows across two tables) confirming Python findings independently.
