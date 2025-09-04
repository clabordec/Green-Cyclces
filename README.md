# Green Cycles


# ─── README.md Template ───────────────────────────────────────────
readme = """# Green Cycles – SQL & Data Analytics

## 📌 Overview
This project supports **GreenCYCLES**, a sustainability-focused company, by building and analyzing their operational database.
As a **Data Analyst**, the goal is to:
- Structure and query customer, sales, and inventory data.
- Provide **impactful insights** to optimize business decisions.
- Develop **dashboards and reports** for stakeholders.

## 🔑 Key Features
- 📊 **Customer Analytics** – identify trends, retention, and high-value customers.
- 📦 **Inventory Optimization** – measure turnover, stock efficiency, and waste reduction.
- 💰 **Sales Insights** – highlight seasonal patterns and growth opportunities.
- 📈 **Performance Metrics** – track KPIs for long-term sustainability.

## 📂 Repo Organization
- `data/` → raw and cleaned datasets.
- `notebooks/` → step-by-step SQL & Python analyses.
- `queries/` → modular SQL scripts for reproducibility.
- `reports/` → executive summaries & visual dashboards.
- `src/` → ETL, data cleaning, and visualization tools.

## 🚀 Tech Stack
- **SQL (PostgreSQL / MySQL)** – querying and transformations.
- **Python (pandas, matplotlib, seaborn)** – analysis and visualization.
- **Jupyter Notebooks** – exploratory data analysis (EDA).
- **Power BI / Tableau (optional)** – business dashboards.

## 📊 Example Insights
- **Customer Analysis**: 65% of repeat customers drive 80% of revenue.
- **Inventory**: Reducing overstock by 12% could save ~$50K annually.
- **Sales Trends**: Peak demand occurs in Q2, suggesting targeted campaigns.

---
👉 This repo is structured for **professional analytics delivery** – making it easy for both technical teams and non-technical stakeholders to understand findings.
"""

# ─── Sample SQL File (queries/customer_queries.sql) ────────────────
customer_queries = """-- Customer Analytics Queries

-- Find top 10 customers by revenue
SELECT customer_id, SUM(total_amount) AS total_spent
FROM sales
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 10;

-- Customer retention rate
SELECT 
    COUNT(DISTINCT CASE WHEN order_date >= DATE_SUB(CURDATE(), INTERVAL 1 YEAR) THEN customer_id END) /
    COUNT(DISTINCT customer_id) AS retention_rate
FROM sales;
"""

# ─── Sample Python File (src/data_cleaning.py) ─────────────────────
data_cleaning = """import pandas as pd

def clean_sales_data(df: pd.DataFrame) -> pd.DataFrame:
    """Clean raw sales data by handling nulls and standardizing formats."""
    df = df.dropna(subset=["customer_id", "order_date", "total_amount"])
    df["order_date"] = pd.to_datetime(df["order_date"])
    df["total_amount"] = df["total_amount"].astype(float)
    return df
"""
