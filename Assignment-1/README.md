# 📊 Power BI Assignment 1 – E-Commerce Sales Analysis

## 📌 Project Overview

This project focuses on **Data Transformation, Data Modeling, and Data Analysis** using Power BI.

The objective is to analyze E-Commerce sales data by importing multiple datasets, transforming data in Power Query, creating relationships, and performing aggregations to generate meaningful business insights.

---

## 📂 Dataset Files Used

* `List of Orders.csv`
* `Order Details.csv`
* `Sales Target.csv`
  

---

## 🔹 Import Process

* Imported all CSV files into **Power BI Desktop**
* Opened datasets in **Power Query Editor**
* Verified data types and column formats
* Restricted *List of Orders* to first **500 rows**

---

## 🔄 Data Transformation Steps

### ✅ Data Cleaning & Formatting

* Converted **Order Date** to `Date` data type
* Changed **Amount** and **Target** columns to `Fixed Decimal Number`
* Formatted **CustomerName** column to Proper Case
* Merged **State + City** columns → Created new column **Location (City, State)**

### ✅ Custom Columns Created

* **Profit Margin**

  ```
  Profit Margin = Profit / Amount
  ```
* **Profit Status**

  * Profit < 0 → Loss
  * Profit = 0 → Break-Even
  * Profit > 0 → Profit

### ✅ Handling Data Quality

* No missing or null values found
* Removed duplicate rows (Row count reduced after cleaning)

---

## 🔗 Data Merging (Joins)

* Merged **List of Orders** + **Order Details**
* Created new table: `Orders Data`
* Join based on: `Order ID`

---

## 📊 Sorting & Filtering

* Sorted orders by **Order Date (Descending)** to analyze recent trends
* Filtered data for **Tamil Nadu** for regional analysis
* Applied filters on State, Category, and Order Date

---

## 📈 Grouping & Aggregation

* Count of Orders by `Order ID`
* Average Profit by `Category`
* Total Amount by `Sub-Category`
* Total Target Amount by `Month`

---

## 🧩 Data Modeling

### Relationships Created:

1. `List of Orders` → `Order Details`

   * Relationship Key: **Order ID**

2. `Order Details` → `Sales Target`

   * Relationship Key: **Category**
   * Relationship set as **Active**

---

## 🛠 Tools Used

* Microsoft Power BI Desktop
* Power Query Editor
* Data Modeling (Relationships)
* Aggregations & Grouping
* Sorting & Filtering Techniques

---

## 📌 Key Learning Outcomes

* Hands-on experience in **Data Transformation**
* Understanding of **Data Modeling & Relationships**
* Handling duplicates and data validation
* Creating calculated columns and conditional logic
* Performing aggregation and trend analysis

---
