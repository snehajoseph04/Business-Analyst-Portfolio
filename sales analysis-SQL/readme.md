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
```

### 2. Win Rate per Rep

```sql
SELECT r.rep_name,
       COUNT(CASE WHEN d.deal_stage = 'Closed Won' THEN 1 END) * 100.0 / COUNT(*) AS win_rate
FROM deals d
JOIN reps r ON d.rep_id = r.rep_id
GROUP BY r.rep_name
ORDER BY win_rate DESC;
```

### 3. Top 5 Industries by Revenue

```sql
SELECT c.industry,
       SUM(d.amount) AS total_revenue
FROM deals d
JOIN customers c ON d.customer_id = c.customer_id
WHERE d.deal_stage = 'Closed Won'
GROUP BY c.industry
ORDER BY total_revenue DESC
LIMIT 5;
```

### 4. Average Deal Size per Region

```sql
SELECT region,
       AVG(amount) AS avg_deal_size
FROM deals
WHERE deal_stage = 'Closed Won'
GROUP BY region
ORDER BY avg_deal_size DESC;
```

### 5. Monthly Quota Achievement per Rep

```sql
SELECT r.rep_name,
       DATE_FORMAT(d.closed_date, '%Y-%m') AS month,
       SUM(d.amount) / r.quota * 100 AS quota_achievement
FROM deals d
JOIN reps r ON d.rep_id = r.rep_id
WHERE d.deal_stage = 'Closed Won'
GROUP BY r.rep_name, month
ORDER BY month;
```

