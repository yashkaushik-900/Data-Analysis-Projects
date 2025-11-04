# Vendor-Performance-Data-Analytics

📊 Vendor Performance Data Analytics
📌 Project Overview

This project provides a comprehensive Vendor Performance Analytics System to evaluate vendors’ contribution to sales, profitability, and operational efficiency. It uses large datasets of purchases, sales, invoices, and inventory records to generate insights for:

Vendor selection based on profitability

Product pricing optimization

Performance benchmarking across brands and vendors

Faster reporting & dashboarding through aggregated summary tables

🏗️ Project Architecture
1. Data Ingestion

Raw CSV files are ingested into a SQLite database (inventory.db).

Implemented scalable ingestion pipeline with chunk-based loading for large datasets.

Logging system (logs/) ensures ingestion traceability.

2. Data Sources

Inventory Data: Opening & closing inventory for stores.

Purchases: Vendor purchases with cost details.

Purchase Prices: Product-specific purchase prices.

Sales: Actual transactions with revenue and excise tax.

Vendor Invoices: Freight and PO-based vendor billing data.

3. Data Transformation & Cleaning

Created vendor_sales_summary by merging Purchases + Sales + Invoices + Prices.

Data cleaning included:

Handling missing values.

Typecasting numerical fields.

Standardizing vendor & product descriptions.

Derived new KPIs:

Gross Profit

Profit Margin (%)

Stock Turnover Ratio

Sales-to-Purchase Ratio

4. Exploratory Data Analysis (EDA)

Distribution analysis for sales, profit, and freight costs.

Outlier detection in purchase/sales data.

Correlation analysis (e.g., price vs. profit margin).

Identification of slow-moving or loss-making products.

Top vendors & brands analysis by Sales Contribution and Profitability.

📊 Key Insights

Certain premium brands contribute high revenue but lower profit margins.

Freight costs show large variations, highlighting logistics inefficiencies.

Slow-moving stock identified (purchased but unsold items).

High-margin but low-sales brands detected → candidates for promotional campaigns.

Top 10 Vendors and Top 10 Brands contribute the majority of sales.

🛠️ Tech Stack

Language: Python (Pandas, NumPy, SQLite, Matplotlib, Seaborn)

Database: SQLite

Visualization: Matplotlib, Seaborn (EDA & dashboards ready)

Logging: Python Logging module

Environment: Jupyter Notebook

📂 Project Structure
Vendor-Performance-Analytics/
│── data/                      # Raw CSV files
│── logs/                      # Ingestion & processing logs
│── notebooks/                 # Jupyter notebooks for EDA
│── scripts/                   # Python scripts (ingestion, cleaning, summary)
│   ├── ingestion_db.py
│   ├── vendor_summary.py
│── inventory.db               # SQLite database
│── README.md                  # Project Documentation

🚀 How to Run the Project

Clone the Repository

git clone https://github.com/yourusername/vendor-performance-analytics.git
cd vendor-performance-analytics


Install Dependencies

pip install -r requirements.txt


Ingest Raw Data into Database

python scripts/ingestion_db.py


Generate Vendor Summary

python scripts/vendor_summary.py


Run EDA (Jupyter Notebook)

jupyter notebook notebooks/vendor_performance_analysis.ipynb

📈 Future Enhancements

Integration with Power BI / Tableau dashboards.

Vendor performance scoring system (profitability, reliability, growth).

Predictive modeling for demand forecasting & pricing optimization.

Migration from SQLite to PostgreSQL/MySQL for scalability.

👨‍💻 Author

Yash Kaushik
📧 Email:kaushikyash453@example.com
