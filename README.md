# 🛒 Walmart Sales Data Analysis (MySQL)

This project is an **Exploratory Data Analysis (EDA)** on Walmart sales data using **MySQL**.  
The dataset was downloaded from **Kaggle** and cleaned using SQL before performing detailed analysis to extract meaningful insights about sales trends, customer behavior, and product performance.

---

## 📂 Dataset

- **Source**: [Kaggle - Walmart Sales Data](https://www.kaggle.com/)
- **File Used**: `Walmart Sales Data.csv`
- **Records**: 1,000+ sales transactions
- **Fields**:
  - Invoice ID
  - Branch
  - City
  - Customer Type
  - Gender
  - Product Line
  - Unit Price
  - Quantity
  - VAT
  - Total
  - Date & Time
  - Payment Method
  - COGS
  - Gross Margin %
  - Gross Income
  - Rating

---

## 🛠 Tools & Technologies

- **MySQL**: Data cleaning, transformation, and analysis
- **Kaggle Dataset**: Data source

---

## 🔍 Steps Performed

### 1️⃣ Data Cleaning
- Removed inconsistencies, duplicates and NULL values
- Formatted dates and time
- Ensured correct data types for each column

### 2️⃣ Feature Engineering
- **`time_of_day`**: Categorized sales into Morning, Afternoon, Evening
- **`day_name`**: Extracted day of the week from transaction date
- **`month_name`**: Extracted month from transaction date
- **`product_category`**: Classified products as "Good" or "Bad" based on average sales

### 3️⃣ Exploratory Data Analysis (EDA)
Performed SQL queries to answer:
- Number of distinct cities & branches
- Most common payment method
- Top-selling product line
- Revenue trends by month
- Highest COGS month
- Product lines generating maximum revenue
- City with highest revenue
- Gender-based product preferences
- Customer types contributing most revenue
- Ratings distribution across days & time

---

## 📊 Key Insights

- **Most Common Payment Method**: E-wallet
- **Top Product Line**: Food & Beverages
- **Highest Revenue Month**: January
- **City with Highest Sales**: Naypyitaw
- **Customer Type Spending More**: Members
- **Time with Most Ratings**: Afternoon

