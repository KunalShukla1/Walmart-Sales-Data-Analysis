# 🛒 Walmart Sales Data Analysis (MySQL Project)
<p align="center">
  <img src="images/walmart-logo.png" alt="Walmart Logo" width="300">
</p>

## 📌 Project Overview
This repository contains **Walmart Sales Data** extracted from **Kaggle** and cleaned using **MySQL**.  
The primary goal of this project is to perform **Data Cleaning, Transformation, and Analysis** to gain insights into customer behavior, product performance, and overall sales trends.

---

## 📊 Dataset Information

- **Total Rows:** 1000  
- **Total Columns:** 20  
- **Data Source:** Kaggle  
- **Cleaning Tool:** MySQL  

---

## 📂 Column Details

| Column Name | Description |
|-------------|-------------|
| 🧾 `Invoice_ID` | Unique ID for each transaction |
| 👥 `Customer_Type` | Type of customer (Member / Normal) |
| 🚻 `Gender` | Gender of customer (Male / Female) |
| 🏬 `store_id` | Unique ID of Store (Branch A, B, C) |
| 🏙️ `store_location` | City where store is located (Yangon, Mandalay, Naypyitaw) |
| 📦 `Product_Line` | Category of product purchased |
| 💲 `Unit_Price` | Price of a single product unit |
| 🔢 `Quantity` | Number of products bought |
| 📉 `Cost_of_Goods_Sold_without_tax` | Cost of goods sold (before tax) |
| 💰 `Tax 5%` | Tax amount (5% of COGS) |
| 🧾 `Total_Cost` | Final bill including tax |
| 📈 `Gross_Profit` | Profit earned per transaction |
| 💳 `Payment_Mode` | Payment method (Cash, Credit Card, E-wallet) |
| 📅 `order_date` | Date of purchase |
| 🗓️ `order_Month` | Month of purchase |
| 📆 `order_Day` | Day of the week |
| ⏰ `order_Time` | Time of the transaction |
| 🌞 `order_Day_Time` | Time classification (Morning, Afternoon, Evening) |
| ⭐ `Rating` | Customer rating (out of 10) |
| 🏷️ `Rating_Type` | Rating category (Good, Very Good, Excellent) |

---

## 🛠️ Data Cleaning & Transformation (MySQL)

The dataset was **cleaned and transformed using MySQL** with the following steps:

- ✅ Removed null & duplicate values  
- ✅ Renamed ambiguous column names (e.g., *cogs ➝ Cost_of_Goods_Sold_without_tax*)  
- ✅ Extracted **Day, Month, Time, Day_Time** from `order_date` and `order_time`  
- ✅ Standardized data formats (Date, Time, Payment Methods)  
- ✅ Created a **clean dataset table** for further analysis  

---

## 🔍 Data Analysis Insights (Extracted using MySQL)

Some key insights generated from SQL queries:

- 📌 **Sales by Branch & Location** → Identified which city generates the highest sales.  
- 📌 **Top-Selling Product Lines** → Found the most popular categories (e.g., Electronics, Fashion).  
- 📌 **Gender-based Analysis** → Compared Male vs Female purchase behavior.  
- 📌 **Customer Type Analysis** → Checked if Members spend more than Normal customers.  
- 📌 **Peak Sales Time** → Discovered which time of day sales are highest.  
- 📌 **Payment Mode Preference** → Analyzed most frequently used payment methods.  
- 📌 **Profitability Analysis** → Found which product lines give the highest gross profit.  
- 📌 **Customer Ratings** → Classified satisfaction levels into Good, Very Good, Excellent.  

---

## 📊 Example SQL Queries

```sql
-- 1️⃣ Top 5 Product Lines by Sales
SELECT Product_Line, SUM(Total_Cost) AS Total_Sales
FROM WALMART_SALES_CLEAN_DATA
GROUP BY Product_Line
ORDER BY Total_Sales DESC
LIMIT 5;

-- 2️⃣ Sales by Branch
SELECT store_id, store_location, SUM(Total_Cost) AS Branch_Sales
FROM WALMART_SALES_CLEAN_DATA
GROUP BY store_id, store_location;

-- 3️⃣ Average Rating by Product Line
SELECT Product_Line, ROUND(AVG(Rating),2) AS Avg_Rating
FROM WALMART_SALES_CLEAN_DATA
GROUP BY Product_Line;
