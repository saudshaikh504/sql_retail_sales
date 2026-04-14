# Retail Sales Analysis — SQL Project

A beginner-friendly end-to-end SQL project covering database setup, data cleaning, exploration, and business-driven analysis using a retail sales dataset.

---

## Project Structure

```
├── SQL_Retail_Sales_Analysis.csv   # Raw dataset (1,999 transactions)
└── sql_query.sql                   # All SQL queries (setup → analysis)
```

---

## Database Setup

The project uses a single table, `retail_sales`, created in the `sql_project_p2` database:

| Column | Type | Description |
|---|---|---|
| `transaction_id` | INT (PK) | Unique transaction identifier |
| `sale_date` | DATE | Date of the sale |
| `sale_time` | TIME | Time of the sale |
| `customer_id` | INT | Customer identifier |
| `gender` | VARCHAR | Customer gender |
| `age` | INT | Customer age |
| `category` | VARCHAR | Product category (Clothing, Beauty, Electronics) |
| `quantity` | INT | Units sold |
| `price_per_unit` | FLOAT | Price per unit |
| `cogs` | FLOAT | Cost of goods sold |
| `total_sale` | FLOAT | Total sale amount |

---

## Data Cleaning

Before analysis, records with `NULL` values in any critical column were identified and removed to ensure data integrity.

---

## Exploratory Data Analysis

- **Total transactions:** ~1,999 records
- **Unique customers:** queried via `COUNT(DISTINCT customer_id)`
- **Product categories:** Clothing, Beauty, Electronics

---

## Business Questions Answered

| # | Question |
|---|---|
| Q1 | Retrieve all sales made on `2022-11-05` |
| Q2 | Find Clothing transactions with quantity ≥ 4 in November 2022 |
| Q3 | Calculate total sales and order count per category |
| Q4 | Find the average age of Beauty category customers |
| Q5 | List all transactions where `total_sale > 1000` |
| Q6 | Count transactions by gender within each category |
| Q7 | Find the best-selling month (by avg sale) for each year |
| Q8 | Identify the top 5 customers by total spend |
| Q9 | Count unique customers per category |
| Q10 | Segment orders into Morning / Afternoon / Evening shifts |

---

## Key SQL Concepts Used

- `CREATE TABLE`, `DROP TABLE`, `DELETE`
- Aggregate functions: `SUM`, `AVG`, `COUNT`, `ROUND`
- `GROUP BY`, `ORDER BY`, `DISTINCT`
- `WHERE` with date filtering using `TO_CHAR` and `EXTRACT`
- Window functions: `RANK() OVER (PARTITION BY ...)`
- Common Table Expressions (CTEs): `WITH ... AS (...)`
- Conditional logic: `CASE WHEN`

---

## Getting Started

1. **Set up the database** — Run the `CREATE DATABASE` and `CREATE TABLE` statements at the top of `sql_query.sql`.
2. **Import the data** — Load `SQL_Retail_Sales_Analysis.csv` into the `retail_sales` table using your preferred method (e.g., pgAdmin import, `\COPY` in psql).
3. **Run the queries** — Execute the analysis queries in order, or jump to any business question of interest.

> This project was built and tested using **PostgreSQL**.

---

## Notes

- Date filtering uses PostgreSQL's `TO_CHAR` and `EXTRACT` functions — adjust syntax if using MySQL or SQLite.
