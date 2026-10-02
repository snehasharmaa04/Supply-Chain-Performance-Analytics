# Supply-Chain-Performance-Analytics
End-to-end operational analytics &amp; ML predictive modeling on 172K+ orders to diagnose delivery bottlenecks and forecast late shipments using Python &amp; Random Forest.
> An end-to-end business intelligence and machine learning investigation analyzing *172,765 fulfillment records* to uncover systemic delivery failure points, quantify profit erosion, and deploy an automated late-delivery early alert classifier.

📄 *[Read the Full Executive Report (PDF)](./reports/Supply_Chain_Performance_Complete_Report.pdf)*

---

## 📌 Executive Summary & Key Highlights

* *Total Orders Analyzed:* 172,765 cross-border fulfillment orders (Jan 2015 – Jan 2018)
* *Overall Late Delivery Rate:* *54.71%* (Systemic issue across all operational channels)
* *Profit at Risk:* *$2.1M* tied to delayed orders out of $7.5M total profitable volume
* *Primary Bottleneck:* Severe shipping mode misconfigurations (*100% First Class* and *79.8% Second Class* delay rates)
* *Predictive ML Baseline:* Supervised Random Forest Classifier delivering *74% overall accuracy* and *78% precision* on delayed orders

---

## 📊 Core Performance Baseline (KPIs)

| Key Finding / Metric | Baseline Performance | Operational Target (12 Mo) |
| :--- | :--- | :--- |
| *Late Delivery Rate* | 54.71% | < 30.0% |
| *First Class On-Time Rate* | 0.0% (100% delayed) | > 80.0% |
| *Second Class On-Time Rate* | 20.2% | > 60.0% |
| *Profit at Risk* | $2.1M | Reduce by 40% |
| *Loss-Making Orders* | 18.7% | < 12.0% |
| *Model Predictive Accuracy* | 74.0% | > 82.0% |

---

## 🔍 Key Insights & Root Cause Analysis

1. *Shipping Mode Misalignment (Top Lever):*
   * Premium tier services fail their brand commitment: First Class has a *100% delay rate, while Second Class stands at **79.8%. Standard Class remains the most stable baseline with a **39.8% delay rate*.
2. *Narrow Regional Variance (55% – 59%):*
   * Delays cluster consistently across regions (Central Africa leading at 58.7%), confirming a company-wide operational bottleneck rather than regional infrastructure breakdown.
3. *Transaction Processing Friction:*
   * Orders stuck in PENDING (69.1% delayed) and PENDING_PAYMENT (62.6% delayed) create significant internal transit latency, cutting into carrier dispatch windows.
4. *Economic Stability:*
   * Mean profit per order remains stable at *$21 – $23* regardless of delay duration, indicating margin losses are purely volume-driven.

---

## 🤖 Machine Learning Modeling Pipeline

* *Task:* Supervised binary classification (Late_delivery_risk = 1 / 0)
* *Pipeline:*
  * Categorical feature frequency encoding
  * Stratified Train/Test split (80/20)
  * *SMOTE (Synthetic Minority Over-sampling Technique)* to balance minority on-time fulfillment records (59,030 balanced to 79,182)
  * *Random Forest Classifier* evaluation on 34,553 unseen test instances

### Model Evaluation (Test Set)
| Class | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| *Class 0 (On-Time)* | 0.68 | 0.72 | 0.70 | 14,758 |
| *Class 1 (Late)* | *0.78* | *0.75* | *0.77* | 19,795 |
| *Weighted Overall* | *0.74* | *0.74* | *0.74* | *34,553* |

---

## 🛠️ Tech Stack & Libraries Used

* *Language:* Python 3.9+
* *Data Manipulation:* pandas, numpy
* *Visualization:* matplotlib, seaborn
* *Machine Learning & Preprocessing:* scikit-learn, imbalanced-learn (SMOTE)
* *Reporting & Documentation:* Microsoft Word / Google Docs, Canva Layout Architecture
