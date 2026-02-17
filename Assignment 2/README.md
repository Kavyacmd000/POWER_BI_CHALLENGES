# 📊 Power BI Assignment 2 – DAX & Data Visualization

## 🛒 E-Commerce Sales Analysis

---

## 📌 Project Overview

This project focuses on applying **DAX (Data Analysis Expressions)** and building advanced **data visualizations** in Power BI to analyze E-Commerce sales performance.

The goal of this assignment is to:

* Create calculated columns
* Define DAX measures
* Perform time intelligence analysis (YTD)
* Compare actual sales vs targets
* Build insightful and interactive dashboards

---

## 📂 Dataset Files Used

* `List of Orders.csv`
* `Order Details.csv`
* `Sales Target.csv`


---

## 🔗 Data Modeling

Before visualization, relationships were established between:

* **List of Orders ↔ Order Details**

  * Key: `Order ID`

* **Order Details ↔ Sales Target**

  * Key: `Category`

Relationships were verified in **Manage Relationships** and set as Active.

---

# 🧮 DAX Calculated Columns

### 1️⃣ Category Type

Combined Category and Sub-Category:

```DAX
Category Type = 
CONCATENATE('Order Details'[Category], "-" & 'Order Details'[Sub-Category])
```

---

### 2️⃣ Revenue per Order

```DAX
Revenue = 
'Order Details'[Amount] * 'Order Details'[Quantity]
```

---

### 3️⃣ Sales Category (Above / Below Average)

```DAX
Sales Category = 
IF(
    'Order Details'[Amount] > 'Order Details'[Average of Amount],
    "Above Average",
    "Below Average"
)
```

---

# 📏 DAX Measures

### 🔹 Order Count

```DAX
Order Count = 
COUNT('Order Details'[Order ID])
```

---

### 🔹 Average Profit (Delhi)

```DAX
Avg Profit Delhi = 
CALCULATE(
    AVERAGE('Order Details'[Profit]),
    'List of Orders'[City] = "Delhi"
)
```

---

### 🔹 Year-to-Date (YTD) Sales

```DAX
YTD Sales = 
CALCULATE(
    SUM('Order Details'[Amount]),
    DATESYTD('List of Orders'[Order Date])
)
```

---

# 📊 Data Visualizations Created

### 📌 Sales Target Achievement by Category

* Clustered Column Chart
* Compares Actual Sales vs Target

---

### 📌 Max Profit Margin by Sub-Category

* Donut Chart
* Highlights most profitable sub-categories

---

### 📌 Monthly Sales Trend

* Line Chart
* Displays sales growth over time

---

### 📌 Profit vs Quantity Comparison

* Scatter Chart
* Analyzes relationship between quantity sold and profitability

---

### 📌 Total Sales vs Target Cards

* Card Visual → Total Sales
* Card Visual → Total Target
* Multi-row Card → Minimum Target per Segment

---

### 📌 Sales Performance Matrix

* Matrix Visual
* Compares actual sales vs targets across categories and months

---

### 📌 Geographic Sales Analysis

* Map Visualization
* Displays total sales by city

---

### 📌 Sales Distribution by Sub-Category

* Treemap Visualization
* Shows revenue contribution by sub-category

---

### 📌 Order Count by State

* Funnel Chart
* Visualizes order distribution across states

---

# 🛠 Tools Used

* Microsoft Power BI Desktop
* DAX (Data Analysis Expressions)
* Time Intelligence Functions
* Interactive Dashboard Design
* Data Modeling & Relationships

---

# 🎯 Key Skills Demonstrated

✔ DAX Calculated Columns
✔ DAX Measures
✔ Time Intelligence (YTD)
✔ Conditional Logic
✔ Sales vs Target Comparison
✔ Geographic Analysis
✔ Business Performance Reporting

---
