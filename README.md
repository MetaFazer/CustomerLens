# ??? CustomerLens — Retail Customer Behavior Analysis

A complete end-to-end data analytics project that analyzes retail customer shopping behavior using **Python**, **SQL**, and **Power BI** to uncover actionable business insights.

---

## ?? Project Overview

This project simulates a real-world data analyst workflow — from raw data to a business-ready dashboard. The goal was to understand *who* the customers are, *what* they buy, *how often* they shop, and *what drives* their spending.

**Dataset:** 3,900 retail customers with 18 attributes including age, gender, purchase amount, product category, shipping type, payment method, and review ratings.

---

## ?? Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python (Pandas, SQLAlchemy) | Data cleaning & database loading |
| PostgreSQL | Data storage & SQL analysis |
| SQL | Business question analysis |
| Power BI | Interactive dashboard |

---

## ??? Project Structure

```
CustomerLens/
¦
+-- Customer_Shopping_Behavior_Analysis.ipynb   # Python data cleaning & DB upload
+-- customer_behavior_sql_queries.sql           # 10 business SQL queries
+-- customer_behavior_dashboard.pbix            # Power BI dashboard
+-- customer_shopping_behavior.csv              # Raw dataset
+-- Customer Shopping Behavior Analysis.pdf     # Project report
+-- Customer-Shopping-Behavior-Analysis.pptx   # Presentation deck
+-- Business Problem Document.pdf              # Problem statement
```

---

## ?? How It Works

### Step 1 — Data Cleaning (Python)
- Loaded the raw CSV dataset using Pandas
- Filled missing review ratings using the **median rating of each product category**
- Renamed columns to a clean, consistent format
- Created two new columns:
  - `age_group` — grouped customers as Young Adult, Adult, Middle-aged, Senior
  - `purchase_frequency_days` — converted text frequency (e.g. "Weekly") to numbers (e.g. 7 days)
- Removed a redundant column (`promo_code_used`) that was 100% identical to `discount_applied`

### Step 2 — Database Upload (PostgreSQL + SQLAlchemy)
- Connected Python to a local PostgreSQL database
- Loaded the cleaned data into a table called `customer`
- **3,900 rows successfully inserted**

### Step 3 — Business Analysis (SQL)
Wrote 10 SQL queries to answer real business questions:

| # | Business Question |
|---|------------------|
| Q1 | Total revenue by gender |
| Q2 | Customers who used discounts but spent above average |
| Q3 | Top 5 products by review rating |
| Q4 | Average spend: Standard vs Express shipping |
| Q5 | Do subscribers spend more than non-subscribers? |
| Q6 | Which products have the highest discount usage? |
| Q7 | Customer segments: New, Returning, and Loyal |
| Q8 | Top 3 products in each category |
| Q9 | Are repeat buyers more likely to subscribe? |
| Q10 | Revenue contribution by age group |

### Step 4 — Dashboard (Power BI)
Built an interactive dashboard with:
- Revenue breakdown by category, gender, and age group
- Product performance & review ratings
- Shipping type comparison
- Customer loyalty segmentation
- Dynamic filters by season, location, and subscription status

---

## ?? Key Findings

- ?? **Young Adults** generate the most revenue ($62,143), but **Seniors** are the least engaged
- ?? **Subscribed customers** have slightly lower average spend — a good opportunity to add exclusive perks
- ?? Over **3,100 customers are "Loyal"** (10+ previous purchases), showing strong retention
- ?? Customers who use **Express shipping** tend to spend more ($60.48 avg) vs Standard ($58.46 avg)
- ?? **Hats** have the highest discount usage rate (50%) — possible over-discounting risk

---

## ?? How to Run This Project

### Prerequisites
- Python 3.x
- PostgreSQL (running locally)
- Power BI Desktop (for the `.pbix` file)

### Steps

1. **Clone the repository**
```bash
git clone https://github.com/MetaFazer/CustomerLens.git
cd CustomerLens
```

2. **Install Python dependencies**
```bash
pip install pandas sqlalchemy psycopg2-binary
```

3. **Set up PostgreSQL**
   - Create a database called `customer_behavior`
   - Update the connection details in the notebook (username, password, port)

4. **Run the Jupyter Notebook**
   - Open `Customer_Shopping_Behavior_Analysis.ipynb`
   - Run all cells to clean data and load it into PostgreSQL

5. **Run the SQL queries**
   - Open `customer_behavior_sql_queries.sql` in pgAdmin or any SQL client
   - Execute queries against the `customer_behavior` database

6. **Open the Power BI Dashboard**
   - Open `customer_behavior_dashboard.pbix` in Power BI Desktop
   - Connect it to your local PostgreSQL database to refresh data

---

## ?? License

MIT — Feel free to fork, star ?, and use in your own portfolio.
