# AtliQ-Sales-Insights
Link to dashboard: http://tinyurl.com/4vyjvfrk

# Business Overview:
AtliQ Hardware is a leading computer hardware and peripherals supplier in India, with a head office in Delhi and regional offices across the country. 

Business Issue - 
The sales director faceing challenges in tracking dynamic marketing growth, requiring accurate insights for informed decision-making.
As a result he decided to build a PowerBI Dashboard for converting the data into visual representation to make data driven decisions. So, he hired a team of data people to complete this task. 

# Tools Used:

1. SQL Queries (MySQL Workbench): Extracted insights from the data.
2. Power BI: Used for ETL processes and visualizations to generate actionable insights.

# Steps Followed in this project
 - Performed a High level analysis of data in SQL to get better understanding over the data.
 - Connected the SQL data set to PowerBI.
 - Performed ETL and data cleaning on the imported data.
 - In the currency there were two types of currencies in transactions, performed currency conversion to make all the currency type same
 - Created measure for needs and used them for creating visuals in PowerBi.
   
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

![Screenshot (18)](https://github.com/palak01/AtliQ-Sales-Insights/assets/23546595/f775df5d-d713-488e-aab1-789cfe5ef550)

UPDATED Version:
![Screenshot (19)](https://github.com/palak01/AtliQ-Sales-Insights/assets/23546595/860ec99d-e16d-4493-9ce0-a4de03e4d9da)





