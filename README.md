# Task-6-Sales-Trend-Analysis-Using-Aggregations
The goal is to analyze **monthly revenue** and **order volume** from the `online_sales` dataset using SQL.

---

## 🧰 Tools Used
- PostgreSQL (can be adapted for MySQL or SQLite)
- SQL for data analysis

---

## 📊 Objectives
- Group sales data by **month** and **year**
- Calculate **monthly revenue** and **order volume**
- Identify the **top 3 months** by total revenue

---

## 📝 SQL Queries Used

```sql
-- Monthly revenue and order volume
SELECT 
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders
FROM 
    online_sales
GROUP BY 
    EXTRACT(YEAR FROM order_date),
    EXTRACT(MONTH FROM order_date)
ORDER BY 
    year, month;

-- Top 3 months by revenue
SELECT 
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue
FROM 
    online_sales
GROUP BY 
    EXTRACT(YEAR FROM order_date),
    EXTRACT(MONTH FROM order_date)
ORDER BY 
    total_revenue DESC
LIMIT 3;
```

---

## 📂 Files Included
- `sales_trend_analysis.sql`: SQL script with queries
- `monthly_revenue_and_orders.csv`: Mock result of monthly revenue and order volume
- `Image of results.png`:  result of top 3 revenue months
- `README.md`: This file

---

