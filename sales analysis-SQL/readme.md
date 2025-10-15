# Sales Data Analysis using SQL


**Objective:**
Analyze sales performance, revenue trends, and rep efficiency for a SaaS company using SQL.


## Dataset Overview
**Tables:**
1. `deals` – Deal details (stage, amount, region, dates)
2. `reps` – Sales rep data (quota, region, name)
3. `customers` – Customer info (industry, country)


## Key SQL Queries


### 1. Total Revenue by Month
```sql
SELECT DATE_FORMAT(closed_date, '%Y-%m') AS month,
SUM(amount) AS total_revenue
FROM deals
WHERE deal_stage = 'Closed Won'
GROUP BY month
ORDER BY month;
