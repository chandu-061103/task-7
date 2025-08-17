



# 🛒 SuperMarket Sales Analysis

This project analyzes supermarket transaction data using **SQLite queries**.
The dataset includes sales details such as customer type, product line, city, payment method, gross income, and customer ratings.

---

## 📊 Dataset Columns

* **Invoice ID** – Unique invoice number
* **Branch** – Branch code (A, B, C)
* **City** – City where transaction happened
* **Customer type** – Member / Normal
* **Gender** – Male / Female
* **Product line** – Category of products
* **Unit price** – Price per item
* **Quantity** – Number of items purchased
* **Tax 5%** – Tax amount
* **Sales** – Total sale amount (including tax)
* **Date / Time** – Purchase date & time
* **Payment** – Payment type (Cash, Credit Card, Ewallet)
* **COGS** – Cost of goods sold
* **Gross income** – Profit from sale
* **Rating** – Customer satisfaction rating

---

## ✅ Solved SQLite Query Examples

### 1️⃣ Total Sales by Each Payment Method

```sql
SELECT Payment, ROUND(SUM(Sales), 2) AS Total_Sales
FROM SuperMarket
GROUP BY Payment
ORDER BY Total_Sales DESC;
```

**Answer:**

* Cash → `112,206.57`
* Ewallet → `109,993.11`
* Credit Card → `100,767.07`

---

### 2️⃣ Average Rating by Gender

```sql
SELECT Gender, ROUND(AVG(Rating), 2) AS Avg_Rating
FROM SuperMarket
GROUP BY Gender;
```

**Answer:**

* Female → `6.96`
* Male → `6.99`

---

### 3️⃣ Top 5 Product Lines by Total Sales

```sql
SELECT [Product line], ROUND(SUM(Sales), 2) AS Total_Sales
FROM SuperMarket
GROUP BY [Product line]
ORDER BY Total_Sales DESC
LIMIT 5;
```

**Answer:**

1. Electronic accessories → `92,459.01`
2. Sports and travel → `92,459.09`
3. Food and beverages → `92,283.07`
4. Health and beauty → `91,960.91`
5. Fashion accessories → `91,652.44`

---

### 4️⃣ Total Quantity Sold by Each City

```sql
SELECT City, SUM(Quantity) AS Total_Quantity
FROM SuperMarket
GROUP BY City
ORDER BY Total_Quantity DESC;
```

**Answer:**

* Naypyitaw → `1,852 items`
* Yangon → `1,849 items`
* Mandalay → `1,838 items`

---

### 5️⃣ Branch-wise Average Gross Income

```sql
SELECT Branch, ROUND(AVG([gross income]), 2) AS Avg_Gross_Income
FROM SuperMarket
GROUP BY Branch
ORDER BY Avg_Gross_Income DESC;
```

**Answer:**

* Branch C → `15.49`
* Branch A → `15.38`
* Branch B → `15.28`

---

## 🚀 Key Insights

* **Cash** is the most used payment method.
* **Male customers** have slightly higher average satisfaction than females.
* **Electronic accessories & Sports/Travel products** generate the highest revenue.
* **Naypyitaw city** records the most quantity of sales.
* **Branch C** achieves the highest gross income on average.

---

## 📌 Usage

1. Import the CSV into SQLite / Python (pandas + sqlite3).
2. Run the queries provided in this repository.
3. Modify queries as needed for deeper insights.


