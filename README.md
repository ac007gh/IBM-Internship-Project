# Netflix Customer Churn & Engagement Analysis

**Author:** Astha Chourasia  
**File:** `AsthaChourasia_NetflixChurnAnalysis.ipynb`  
**Dataset:** [netflix_large_user_data.csv — Kaggle](https://www.kaggle.com/datasets/smayanj/netflix-users-database)

---

## Project Description

This project performs a complete end-to-end analysis of Netflix customer churn and engagement using a real dataset of **1,000 customers across 16 features**. The analysis is grounded entirely in the actual dataset — no results are invented or copied from other projects.

The project covers:
- Key KPI calculation and dashboard
- Exploratory Data Analysis (EDA) across all 16 features
- Churn analysis by subscription plan, region, device, genre, age, payment history, support queries, and promotional offers
- Trend and pattern analysis using cross-segment heatmaps
- An interactive Plotly dashboard
- A machine learning churn prediction model (Logistic Regression, Random Forest, Gradient Boosting)
- Feature importance analysis
- 5 Key Findings, 3 Business Risks, 3 Business Opportunities, 5 Recommended Actions

---

## Dataset

| Property | Value |
|---|---|
| File | `netflix_large_user_data.csv` |
| Rows | 1,000 |
| Columns | 16 |
| Missing Values | None |
| Target Variable | `Churn Status (Yes/No)` |
| Overall Churn Rate | **53.9%** |

**Columns in the dataset:**
`Customer ID`, `Subscription Length (Months)`, `Customer Satisfaction Score (1-10)`, `Daily Watch Time (Hours)`, `Engagement Rate (1-10)`, `Device Used Most Often`, `Genre Preference`, `Region`, `Payment History (On-Time/Delayed)`, `Subscription Plan`, `Churn Status (Yes/No)`, `Support Queries Logged`, `Age`, `Monthly Income ($)`, `Promotional Offers Used`, `Number of Profiles Created`

---

## Technologies Used

| Category | Library / Tool |
|---|---|
| Language | Python 3.9+ |
| Data Manipulation | pandas, numpy |
| Static Visualisation | matplotlib, seaborn |
| Interactive Dashboard | plotly |
| Machine Learning | scikit-learn |
| Environment | Jupyter Notebook |

---

## Project Structure

```
Netflix_Churn_Project/
│
├── AsthaChourasia_NetflixChurnAnalysis.ipynb   ← Main notebook (all code)
├── requirements.txt                       ← Python dependencies
├── AsthaChourasia_ProjectReport.docx           ← Full project report
└── README.md                              ← This file
```

---

## Setup & Run Instructions

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Place the dataset
Copy `netflix_large_user_data.csv` into the same folder as the notebook, **or** update the file path in Cell 2:
```python
df = pd.read_csv('netflix_large_user_data.csv')   # adjust path if needed
```

### 3. Launch Jupyter Notebook
```bash
jupyter notebook AsthaChourasia_NetflixChurnAnalysis.ipynb
```

### 4. Run all cells
In Jupyter: **Kernel → Restart & Run All**

---

## Key Information

### Overall Churn Rate
**53.9%** — a structural, platform-wide retention problem. No single segment is safe.

### 5 Key Findings
1. **Structural churn at 53.9%** — uniform across all plans (Basic=54.9%, Standard=53.4%, Premium=53.5%)
2. **Satisfaction does NOT predict retention** — Score 9/10 customers churn at 64% (highest of any group)
3. **Support queries 9+ = 62% churn** — the clearest single behavioral churn signal in the data
4. **7–12 month window is the highest-risk tenure** (56.8%) — the critical intervention period
5. **Young laptop/desktop users (18–39) churn most** (57%+); Smart TV users (49.7%) are stickiest

### 3 Business Risks
1. **Promo-dependency trap** — customers using 3–4 promos churn at 60%+
2. **Plan-agnostic churn erodes upsell ROI** — upgrading customers doesn't reduce churn
3. **Africa & Asia high-churn growth markets** (55.6–55.7%) — risk becoming high-exit markets

### 3 Business Opportunities
1. **Smart TV loyalty advantage** (49.7% churn) — manufacturer partnerships can lift retention
2. **Comedy as retention anchor** (46.9% churn — lowest genre) — content investment lever
3. **Older audience (50+) stronghold** (49.7–50%) — underserved, high-loyalty segment

### 5 Recommended Actions
1. Launch a **Month 7–12 Retention Programme** with personalised outreach
2. Build a **Support Escalation Churn Alert** for customers with 7+ queries
3. **Replace satisfaction surveys** with behavioral engagement metrics
4. **Redesign promo strategy** — cap at 2 per year, shift to content-value messaging
5. **Regional content localisation** investment in Africa and Asia

---

## Visualisations Produced

| Figure | Description |
|---|---|
| fig01 | Overall churn distribution (pie + bar) |
| fig02 | Churn by subscription plan |
| fig03 | Churn by region (horizontal bar) |
| fig04 | Churn by device and genre |
| fig05 | Churn by satisfaction score and engagement rate |
| fig06 | Daily watch time distribution (histogram + box plot) |
| fig07 | Support queries and churn (exact count + load bucket) |
| fig08 | Churn by subscription length group |
| fig09 | Churn by age group + age distribution |
| fig10 | Payment history and promo offers vs churn |
| fig11 | Correlation heatmap (all numerical features) |
| fig12 | Heatmap: Region × Subscription Plan |
| fig13 | Heatmap: Age Group × Device |
| fig14 | Income distribution and quartile churn |
| fig15 | Model comparison (ROC curves + metric bars) |
| fig16 | Best model confusion matrix + ROC curve |
| fig17 | Feature importance (Random Forest, top 15) |
| fig18 | Predicted churn probability distribution |
| Dashboard | Interactive Plotly 6-panel overview |

---

## Prediction Models

Three models were trained and evaluated:

| Model | Metric |
|---|---|
| Logistic Regression | Baseline linear model |
| Random Forest | Ensemble, non-linear, feature importance |
| Gradient Boosting | Sequential ensemble, high accuracy |

All models evaluated on: **Accuracy**, **ROC-AUC**, **5-fold Cross-Validation AUC**

> **Note:** AUC scores close to 0.5–0.6 across all models are analytically honest — the dataset has high inherent noise with no dominant single predictor. The model beats random classification and provides churn probability scores for risk-based intervention.

---

*Project completed as part of IBM Data Analytics Internship.*
