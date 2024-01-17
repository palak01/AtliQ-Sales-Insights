# AtliQ-Sales-Insights


AtliQ-Sales-Insights: Data Analysis for AtliQ Hardware

# Business Overview:
AtliQ Hardware is a leading computer hardware and peripherals supplier in India, with a head office in Delhi and regional offices across the country. 

Business Issue - 
The sales director faces challenges in tracking dynamic marketing growth, requiring accurate insights for informed decision-making.

# Tools Used:

1. SQL Queries (MySQL Workbench): Extracted insights from the data.
2. Power BI: Used for ETL processes and visualizations to generate actionable insights.

   
# Data Analysis Using SQL:
1. Show Customer Records:
```
SELECT * FROM customers;
```
2. Total Number of Customers:
```
SELECT COUNT(*) FROM customers;
```

3. Transactions for Chennai Market (Market Code: Mark001):
```
SELECT * FROM transactions WHERE market_code='Mark001';
```

4. Distinct Product Codes Sold in Chennai:
```
SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';
```

5. Transactions in US Dollars:
```
SELECT * FROM transactions WHERE currency="USD";
```

6. Transactions in 2020 Joined by Date Table:
```
SELECT transactions.*, date.* FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020;
```
7. Total Revenue in 2020:
```
SELECT SUM(transactions.sales_amount) FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020 AND (transactions.currency = "INR\r" OR transactions.currency = "USD\r");
```
8. Total Revenue in January 2020:
```
SELECT SUM(transactions.sales_amount) FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020 AND date.month_name = "January" AND (transactions.currency = "INR\r" OR transactions.currency = "USD\r");
```
9. Total Revenue in 2020 in Chennai:
```
SELECT SUM(transactions.sales_amount) FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020 AND transactions.market_code = "Mark001";
```
