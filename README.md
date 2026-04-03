# 🛒 Zepto Data Analysis Project

This project focuses on analyzing product data from a quick-commerce platform (Zepto-like dataset) using SQL. It covers **data cleaning, exploration, and business insights generation**.

---

## 📂 Dataset

The dataset contains product-level information such as:

* SKU ID
* Product Name
* Category
* MRP (Maximum Retail Price)
* Discount Percentage
* Selling Price
* Quantity Available
* Weight
* Stock Status

📁 SQL Script: 

---

## 🧱 Database Setup

```sql
CREATE TABLE zepto (
    sku_id SERIAL PRIMARY KEY,
    category VARCHAR(120),
    name VARCHAR(150) NOT NULL,
    mrp NUMERIC(8,2),
    discountPercent NUMERIC(5,2),
    availableQuantity INTEGER,
    discountedSellingPrice NUMERIC(8,2),
    weightInGms INTEGER,
    outOfStock BOOLEAN,
    quantity INTEGER
);
```

---

## 📥 Data Import

```sql
COPY zepto(Category, name, mrp, discountPercent, availableQuantity,
discountedSellingPrice, weightInGms, outOfStock, quantity)
FROM 'zepto_v2.csv'
CSV HEADER;
```

---

## 🔍 Data Exploration

* Count total records
* View sample data
* Check null values
* Identify unique categories
* Stock availability analysis

---

## 🧹 Data Cleaning

* Removed products with zero price
* Converted price from **paise → rupees**
* Ensured no null or invalid entries

---

## 📊 Business Insights (SQL Queries)

### 🔥 Top Analysis Performed

1. **Top 10 Best Discounted Products**
2. **High MRP but Out-of-Stock Products**
3. **Estimated Revenue by Category**
4. **Premium Products with Low Discount**
5. **Top Categories with Highest Average Discount**
6. **Best Value Products (Price per Gram)**
7. **Product Segmentation (Low / Medium / Bulk)**
8. **Total Inventory Weight per Category**

---

## 💡 Example Insight

```sql
SELECT category,
SUM(discountedSellingPrice * availableQuantity) AS total_revenue
FROM zepto
GROUP BY category
ORDER BY total_revenue;
```

👉 Helps identify which category generates the most revenue.

---

## 🛠️ Tech Stack

* SQL (PostgreSQL / MySQL compatible)
* Data Cleaning
* Data Analysis
* Business Intelligence Concepts

---

## 🚀 Key Learnings

* Writing efficient SQL queries
* Data cleaning techniques
* Business-driven data analysis
* Extracting insights from raw datasets

---

## 📌 Future Improvements

* Build Power BI / Tableau dashboard
* Add Python (Pandas) analysis
* Automate ETL pipeline
* Deploy as a data analytics project

---

## 🙌 Author

**Ratnesh Kumar**
B.Tech (AI & Data Science)

---

Just say 👍
