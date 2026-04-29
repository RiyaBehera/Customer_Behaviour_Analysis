# 🛍️ Customer Shopping Behavior Analysis

A full-stack data analysis project uncovering spending patterns, customer segments, product preferences, and subscription behavior from 3,900 retail transactions — using **Python**, **PostgreSQL**, and **Power BI**.

---

## 📌 Project Overview

This project performs end-to-end analysis of customer shopping data to answer key business questions and generate actionable recommendations. The pipeline covers data cleaning in Python, structured querying in SQL, and interactive visualization in Power BI.

---

## 📂 Dataset

| Attribute | Details |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing Data | 37 values in `Review Rating` |

**Feature groups:**
- **Demographics** — Age, Gender, Location, Subscription Status
- **Purchase Details** — Item, Category, Amount (USD), Season, Size, Color
- **Behavior** — Discount Applied, Previous Purchases, Frequency, Review Rating, Shipping Type

---

## 🔧 Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![pandas](https://img.shields.io/badge/pandas-Data%20Wrangling-150458?logo=pandas)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-SQL-336791?logo=postgresql)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi)

---

## 🧹 Data Preparation (Python)

Steps performed during EDA and cleaning:

1. **Data Loading** — Imported dataset using `pandas`
2. **Exploration** — Used `df.info()` and `.describe()` for structure and statistics
3. **Missing Value Imputation** — Filled missing `Review Rating` values with the **median rating per product category**
4. **Column Standardization** — Renamed all columns to `snake_case`
5. **Feature Engineering**
   - `age_group` — binned customer ages into groups
   - `purchase_frequency_days` — derived from purchase frequency data
6. **Redundancy Check** — Confirmed `discount_applied` and `promo_code_used` were redundant; dropped `promo_code_used`
7. **Database Integration** — Loaded cleaned DataFrame into **PostgreSQL** for SQL analysis

---

## 🗄️ SQL Analysis (PostgreSQL)

Ten business questions answered via structured queries:

| # | Analysis | Key Finding |
|---|---|---|
| 1 | Revenue by Gender | Male: $157,890 · Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers used discounts yet spent above average |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| 4 | Shipping Type Comparison | Express avg $60.48 vs Standard avg $58.46 |
| 5 | Subscribers vs Non-Subscribers | Similar avg spend (~$59.50–$59.87); non-subscribers dominate volume |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| 7 | Customer Segmentation | Loyal: 3,116 · Returning: 701 · New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | Repeat Buyers & Subscriptions | 2,518 repeat buyers are non-subscribers vs 958 subscribers |
| 10 | Revenue by Age Group | Young Adults: $62,143 (highest contributor) |

---

## 📊 Power BI Dashboard

An interactive dashboard was built with the following KPIs and visuals:

- **KPI Cards** — Total Customers (3.9K), Avg Purchase Amount ($59.76), Avg Review Rating (3.75)
- **Donut Chart** — Subscription status split (27% Yes / 73% No)
- **Bar Charts** — Revenue and Sales by Category, Revenue and Sales by Age Group
- **Slicers** — Filter by Subscription Status, Gender, Category, Shipping Type

---

## 💡 Business Recommendations

- **Boost Subscriptions** — Only 27% of customers subscribe; promote exclusive perks to drive conversion
- **Customer Loyalty Programs** — Reward repeat buyers to migrate them into the "Loyal" segment
- **Review Discount Policy** — Products like Hat and Sneakers show ~50% discount rates; balance sales boosts against margin erosion
- **Product Positioning** — Feature top-rated items (Gloves, Sandals, Boots) prominently in campaigns
- **Targeted Marketing** — Focus spend on Young Adults and Express-shipping users, who show higher revenue contribution

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/RiyaBehera/customer-shopping-behavior.git
cd customer-shopping-behavior

# Install dependencies
pip install pandas sqlalchemy psycopg2

# Run the analysis notebook / script
python analysis.py
```

> Make sure PostgreSQL is running and update the connection string in the script before executing.

---

## 📁 Project Structure

```
├── data/
│   └── shopping_behavior.csv        # Raw dataset
├── notebooks/
│   └── eda_cleaning.ipynb           # Python EDA & cleaning
├── sql/
│   └── business_queries.sql         # All 10 SQL analyses
├── dashboard/
│   └── customer_behavior.pbix       # Power BI dashboard file
├── analysis.py                      # Main pipeline script
└── README.md
```
