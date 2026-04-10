# Marketing Analytics — Customer Retention & Churn Prediction

> RFM segmentation · churn prediction · sentiment analysis · ROI-positive retention campaign

A full-cycle marketing analytics project built on real customer data from **Snowit**, a ski resort membership platform. The goal: turn transactional and behavioural data into a targeted retention campaign that reduces seasonal churn and increases customer lifetime value.

Methodology follows **CRISP-DM** end-to-end — from business framing to deployment planning.

---

## Business Questions

Three concrete objectives drove the analysis:

1. How can average customer value be increased?
2. How can seasonal churn be reduced?
3. How can negative customer experiences be identified before they become lost revenue?

---

## Data

Provided directly by Snowit. Four interconnected tables:

| Source | Contents |
|--------|----------|
| Users & Profiles | Demographics, preferences, activity history |
| Cards | Membership type, validity, status |
| Orders & Transactions | Purchase frequency, items, promotions, payments |
| Reviews | Labeled and unlabeled customer feedback |

**Preparation:** standardised data types, median imputation for sparse numerical fields, removal of uninformative columns, consistent handling of categoricals and booleans.

---

## Models

### 1. RFM Segmentation

Customers scored on **Recency, Frequency, and Monetary** value using quartile-based binning, then grouped into actionable segments: *Champions*, *Loyal*, *At Risk*, and *Lost*.

**Finding:** the majority of the customer base required reactivation campaigns; a smaller high-value segment warranted premium, personalised outreach.

### 2. Churn Prediction

Target: active users from the previous season. Features engineered from orders, profile data, and card history.

| Model | AUC | Recall | Precision |
|-------|-----|--------|-----------|
| LightGBM ✓ | 0.82 | 89% | 81% |

**Top churn drivers:** city, last purchase recency, number of cards held, membership type, and acquisition channel.

Recall was prioritised over precision — in retention contexts, the cost of missing a churner (lost revenue) outweighs the cost of a false alarm (wasted voucher).

### 3. Sentiment Analysis

Customer reviews preprocessed with stopword removal, lemmatisation, and TF-IDF vectorisation. Three models benchmarked:

| Model | Accuracy |
|-------|----------|
| Logistic Regression ✓ | 82% |
| Random Forest | — |
| CNN | — |

**Finding:** the majority of reviews are positive. Negative reviews cluster around two themes: customer support quality and food offerings — concrete operational levers for the business.

---

## Retention Campaign

### Design

- **Target audience:** ~10,700 predicted churners
- **Offer:** 20% base voucher, scaled 10–30% based on RFM segment
- **Messaging:** personalised by sentiment profile — empathetic for frustrated users, rewarding for loyal ones at risk

### Economics

| Scenario | Retention uplift | Users saved | Net gain |
|----------|-----------------|-------------|----------|
| Conservative | +5% | 433 | ~€71k |
| Realistic | +15% | 1,299 | ~€230k |
| Optimistic | +25% | 2,165 | ~€458k |

**Campaign cost:** €25,571 (outreach + vouchers)
**ROI range:** +278% to +1,792% — profitable across all scenarios.

---

## Deployment Plan

- **Timing:** campaign launches at season start, the peak churn window, with monthly model score updates
- **Integration:** churn scores and sentiment labels feed directly into campaign targeting and messaging selection
- **Rationale:** marrying predictive scoring with personalised communication maximises retention lift while keeping campaign costs bounded

---

## Limitations & Next Steps

- **Improve churn recall further** — reducing false negatives directly translates to recovered revenue
- **A/B test messaging variants** — validate whether personalised copy actually outperforms generic offers
- **Dynamic seasonal modelling** — capture temporal patterns within the ski season rather than treating it as a single static period

---

## Stack

`Python` `LightGBM` `scikit-learn` `TF-IDF` `RFM segmentation` `churn prediction` `sentiment analysis` `CRISP-DM` `marketing analytics`
