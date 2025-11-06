# 🍕 Pizza Sales Data Analysis

**Duration:** Aug 2025 – Oct 2025  
**Tools Used:** MySQL, Excel (Dashboard, Pivot Charts), Power Query  

---

## 📘 Project Overview
This project focuses on analyzing pizza sales data to derive key business insights.  
Using **SQL** for data querying and **Excel** for visualization, the analysis provides a complete picture of sales performance, customer preferences, and order behavior.

---

## 🧩 Problem Statement
The objective of this project is to analyze key performance indicators (KPIs) and visualize sales patterns for a pizza chain.  
By combining SQL analysis and Excel dashboards, we aim to improve business decision-making through data-driven insights.

---

## 🎯 KPI’s Requirement

We need to calculate the following KPIs to evaluate business performance:

1. **Total Revenue:**  
   The total sum of all pizza order prices.

2. **Average Order Value (AOV):**  
   Average amount spent per order, calculated as  
   `Total Revenue ÷ Total Orders`.

3. **Total Pizzas Sold:**  
   Total quantity of pizzas sold across all transactions.

4. **Total Orders:**  
   Count of unique order IDs (number of customer orders).

5. **Average Pizzas per Order:**  
   Average number of pizzas per order, calculated as  
   `Total Pizzas Sold ÷ Total Orders`.

🧠 **Purpose:**  
These KPIs help assess the company’s overall performance — understanding customer spending, sales trends, and order frequency.

---

## 📊 Charts Requirement

We visualize multiple aspects of pizza sales to uncover sales patterns and preferences.  
Each chart helps interpret the data from a business perspective.

### 1️⃣ Daily Trend for Total Orders  
- **Chart Type:** Bar Chart  
- **Insight:** Identifies busiest days (Friday & Saturday) and slowest days.

### 2️⃣ Hourly Trend for Total Orders  
- **Chart Type:** Line Chart  
- **Insight:** Reveals peak order hours (12–1 PM, 6–8 PM).

### 3️⃣ % of Sales by Pizza Category  
- **Chart Type:** Pie Chart  
- **Insight:** Shows which categories (Classic, Supreme, Veggie, Chicken) contribute most to revenue.

### 4️⃣ % of Sales by Pizza Size  
- **Chart Type:** Pie Chart  
- **Insight:** Helps understand customer preference by pizza size (Large, Medium, etc.).

### 5️⃣ Total Pizzas Sold by Pizza Category  
- **Chart Type:** Funnel / Bar Chart  
- **Insight:** Compares total pizzas sold per category.

### 6️⃣ Top 5 Best Sellers by Total Pizzas Sold  
- **Chart Type:** Horizontal Bar Chart  
- **Insight:** Highlights best-performing pizzas like *Classic Deluxe* and *Barbecue Chicken*.

### 7️⃣ Bottom 5 Worst Sellers by Total Pizzas Sold  
- **Chart Type:** Horizontal Bar Chart  
- **Insight:** Identifies least popular pizzas like *Brie Carre* and *Spinach Supreme*.

  📈 Dashboard Highlights

Built in Excel, the dashboard visualizes:

Total Revenue: $817,860

Average Order Value: $38.31

Total Pizzas Sold: 49,574

Total Orders: 21,350

Avg Pizzas per Order: 2.32

🔍 Key Insights

Classic & Large pizzas contributed nearly 46% of total revenue.

Weekend evenings (Friday & Saturday) saw the highest order volumes.

Top Sellers: Classic Deluxe, Barbecue Chicken, Hawaiian Pizza.

Lowest Seller: Brie Carre Pizza.


🚀 How to Use

Import the dataset (pizza_sales.csv) into MySQL.

Run SQL queries from Pizza_Sales_SQL_Queries.docx to generate KPIs.

Build pivot tables and charts in Excel to visualize the data.

Use filters to explore time-based and category-based sales performance.

🧾 Key Learnings

Applying SQL for business analytics and KPI computation.

Creating interactive dashboards in Excel for sales visualization.

Extracting data-driven insights for marketing and operations.

Understanding customer behavior through order time and product preference.

---

## 🧠 SQL Analysis

Some of the main SQL queries used:

```sql
-- Total Revenue
SELECT SUM(total_price) AS total_revenue FROM pizza_sales;

-- Average Order Value
SELECT SUM(total_price) / COUNT(DISTINCT order_id) AS avg_order_value FROM pizza_sales;

-- Total Pizzas Sold
SELECT SUM(quantity) AS total_pizzas_sold FROM pizza_sales;

-- Daily Trend for Orders
SELECT DAYNAME(order_date) AS order_day, COUNT(DISTINCT order_id) AS total_orders
FROM pizza_sales
GROUP BY DAYNAME(order_date);

-- Best & Worst Sellers
SELECT pizza_name, SUM(quantity) AS total_sold
FROM pizza_sales
GROUP BY pizza_name
ORDER BY total_sold DESC
LIMIT 5;



Author: Chanchal Yadav
Email: chanchal.yadav@iitgn.ac.in
