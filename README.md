# Data Analytics Internship
Multi-week Data Analytics internship projects completed as part of the DecodeLabs Industrial Training Kit. Each project builds on the last — starting from raw, messy order data and progressing toward business-ready insights.

## 📌 Repository Overview

| | |
|---|---|
| **Track** | Data Analytics |
| **Organization** | DecodeLabs |
| **Tools** | Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook, openpyxl |
| **Dataset size** | 1,200 rows × 14 columns (e-commerce order data) |

## 🗂️ Repository Structure

```
├── data/
│   ├── raw/
│   │   └── Dataset_for_Data_Analytics.xlsx              # original, unmodified dataset
│   └── cleaned/
│       └── Dataset_for_Data_Analytics_CLEANED.xlsx       # Project 1 output — feeds into Project 2
├── notebooks/
│   ├── project1_data_cleaning.ipynb                      # Project 1: cleaning pipeline (executed, outputs included)
│   └── project2_eda.ipynb                                # Project 2: EDA pipeline (executed, charts included)
├── reports/
│   └── figures/                                           # exported chart images from Project 2
│       ├── distributions.png
│       ├── boxplots.png
│       ├── monthly_trend.png
│       ├── revenue_by_product.png
│       └── correlation_heatmap.png
├── requirements.txt
└── README.md
```

---

## Project 1 — Data Cleaning & Preparation 🧹

**Goal:** Transform the raw order dataset into an analysis-ready "gold standard" dataset by handling missing values, auditing for duplicates, and standardizing formats.

**Process (4 phases):**
1. **Strategic Imputation** — 309 missing `CouponCode` values imputed with `No Coupon` (no rows dropped)
2. **Integrity Audit** — checked `OrderID`/`TrackingNumber`/full rows for duplicates (0 found)
3. **Standardization** — dates → ISO 8601, text trimmed & consistently cased, monetary values rounded to 2 decimals, `TotalPrice = Quantity × UnitPrice` verified
4. **Verification Gate** — passed: 0% duplicate IDs, 0% malformed dates, 0 nulls remaining

📓 [`notebooks/project1_data_cleaning.ipynb`](notebooks/project1_data_cleaning.ipynb)

---

## Project 2 — Exploratory Data Analysis (EDA) 🔍

**Goal:** Analyze the Project 1 cleaned dataset to uncover patterns, trends, distributions, and outliers, and translate findings into business recommendations.

**Process (5 phases):**
1. **Descriptive Statistics** — mean/median/mode/std/quartiles for all numeric columns; value counts for categoricals
2. **Distribution & Shape Analysis** — histograms + skew diagnosis for Quantity, UnitPrice, TotalPrice
3. **Outlier Detection** — IQR method + boxplots; classified outliers as Signal (real large orders) vs. Noise
4. **Trend & Relationship Analysis** — monthly order/revenue trends, product/payment/referral breakdowns, Pearson correlation heatmap
5. **Synthesis** — "So What?" test translating each statistic into a business-relevant finding

**Key findings:**
- Order values are right-skewed — median is the more reliable "typical order" benchmark than mean
- All `TotalPrice` outliers are legitimate large orders (Signal), not data errors
- Clear, uneven revenue contribution by product, payment method, and referral source
- A meaningful share of orders end in `Cancelled`/`Returned` status — the largest recoverable-revenue lever identified

📓 [`notebooks/project2_eda.ipynb`](notebooks/project2_eda.ipynb)

---

## ▶️ How to Run

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install -r requirements.txt
jupyter notebook notebooks/project1_data_cleaning.ipynb
jupyter notebook notebooks/project2_eda.ipynb
```

## ✅ Status

Project 1 and Project 2 complete — dataset cleaned, verified, explored, and findings translated into actionable business recommendations.

## 👤 Author

**Reha Arif**
Data Analytics Intern, DecodeLabs
