Project 3: SQL Data Analysis
DecodeLabs Industrial Training | Data Analytics | Batch 2026

📌 Project Overview
This project focuses on SQL Data Analysis — the process of writing structured queries to extract meaningful insights from a raw dataset. Instead of just viewing spreadsheets, this project demonstrates the ability to filter, group, sort, and aggregate data using pure SQL logic. Every query written here answers a real business question using relational database principles.

🎯 Goal
Use SQL queries to extract insights from a dataset.

✅ Key Requirements

Write SELECT queries
Use WHERE, ORDER BY, GROUP BY
Perform basic aggregations (COUNT, SUM, AVG)


🛠️ Key Skills Used

SQL Fundamentals
Querying Data
Filtering and Grouping
Data Aggregation
MySQL Workbench


📂 Project Structure
Project3_SQL/
│
├── dataset.xlsx                   # Original dataset (1200 rows, 14 columns)
├── screenshots/                   # Screenshots of all queries and results
│   ├── 1_SELECT.png
│   ├── 2_WHERE.png
│   ├── 3_ORDER_BY.png
│   ├── 4_GROUP_BY.png
│   ├── 5_COUNT.png
│   ├── 6_SUM.png
│   └── 7_AVG.png
└── README.md                      # Project documentation

🗄️ Database Details
PropertyDetailsDatabasedecodelabsTable Nameproject3Total Records1,200 rowsTotal Columns14 columnsTool UsedMySQL Workbench

📋 Table Schema
Column NameData TypeDescriptionOrderIDTEXTUnique order identifierDateTEXTDate of the orderCustomerIDTEXTUnique customer identifierProductTEXTProduct nameQuantityINTNumber of items orderedUnitPriceDOUBLEPrice per unitShippingAddressTEXTDelivery addressPaymentMethodTEXTMode of paymentOrderStatusTEXTCurrent order statusTrackingNumberTEXTShipment tracking IDItemsInCartINTTotal items in cartCouponCodeTEXTDiscount coupon appliedReferralSourceTEXTSource of customer referralTotalPriceDOUBLEFinal order total

🔍 Queries Executed
1. SELECT — View Datasql
SELECT * FROM project3 LIMIT 10;

SELECT OrderID, Product, Quantity, TotalPrice, OrderStatus
FROM project3;
2. WHERE — Filter Data
sqlSELECT * FROM project3
WHERE OrderStatus = 'Delivered';

SELECT * FROM project3
WHERE TotalPrice > 2000;

SELECT * FROM project3
WHERE Product = 'Laptop'
AND OrderStatus = 'Shipped';

3. ORDER BY — Sort Datasql
SELECT OrderID, Product, TotalPrice
FROM project3
ORDER BY TotalPrice DESC;

SELECT OrderID, Product, TotalPrice
FROM project3
ORDER BY TotalPrice ASC;

4. GROUP BY — Group Datasql
SELECT Product, COUNT(*) AS TotalOrders
FROM project3
GROUP BY Product;

SELECT OrderStatus, COUNT(*) AS TotalOrders
FROM project3
GROUP BY OrderStatus;

5. COUNT — Count Recordssql
SELECT COUNT(*) AS TotalOrders
FROM project3;

SELECT Product, COUNT(*) AS TotalOrders
FROM project3
GROUP BY Product
ORDER BY TotalOrders DESC;

6. SUM — Total Revenuesql
SELECT SUM(TotalPrice) AS TotalRevenue
FROM project3;

SELECT Product, SUM(TotalPrice) AS TotalRevenue
FROM project3
GROUP BY Product
ORDER BY TotalRevenue DESC;

7. AVG — Average Valuessql
SELECT AVG(TotalPrice) AS AvgOrderValue
FROM project3;

SELECT Product, AVG(TotalPrice) AS AvgOrderValue
FROM project3
GROUP BY Product
ORDER BY AvgOrderValue DESC;

📊 Key Results from Queries
InsightResultTotal Orders1,200Total Revenue₹13,64,761.96Average Order Value₹1,053.97Highest Order Value₹3,456.40Top Revenue ProductChair (₹1,95,620)Most Ordered ProductPrinter (181 orders)Top Referral SourceInstagram (259 orders)Most Used PaymentOnline (258 orders)Most Cancelled Orders250 orders cancelledBest Avg Order ValueCredit Card (₹1,127)

💡 Business Insights

Chair and Printer generate the highest total revenue — priority products for the business
Instagram is the strongest marketing channel bringing the most customers and revenue
Credit Card users spend the most per order on average
Cancellation rate is high (250 out of 1200) — needs business attention
FREESHIP coupon is the most popular discount — customers prefer free shipping over percentage discounts
Laptop has the highest average order value per product (₹1,110)


💡 What I Learned

How to write SELECT queries to retrieve specific data
How to use WHERE to filter rows based on conditions
How to use ORDER BY to sort results in ascending and descending order
How to use GROUP BY to organize data into categories
How to use COUNT, SUM, and AVG to generate business metrics
How SQL execution order works: FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY
The difference between WHERE (filters rows) and HAVING (filters groups)

