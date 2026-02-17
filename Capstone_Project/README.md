# 🚚 AI-Powered Fleet Performance & Delivery Efficiency Dashboard

### 📊 Power BI Capstone Project

---

## 📌 Project Overview

This capstone project focuses on building an **AI-Driven Fleet Performance Dashboard** for a logistics company using **Power BI**.

The objective is to analyze and optimize:

* 🚛 On-Time Deliveries
* ⛽ Fuel Efficiency
* 💰 Cost per Kilometer
* 🔧 Maintenance Costs
* 📍 Destination-wise Performance

The dashboard enables data-driven decisions to improve operational efficiency and reduce transportation costs.

---

## 🏢 Business Problem

A logistics company wants to:

* Monitor delivery performance
* Identify causes of late deliveries
* Improve fuel efficiency
* Optimize route and fleet usage
* Reduce overall operational cost

This dashboard provides actionable insights to achieve these goals.

---

## 📂 Dataset Information

Source: `logistics_project_dataset.xlsx`

### 🔹 Trip_Data Table

* Trip ID
* Vehicle ID
* Driver ID
* Origin
* Destination
* Distance (km)
* Fuel Consumed (liters)
* Delivery Status (On-Time / Late)
* Delivery Date

### 🔹 Vehicle_Master Table

* Vehicle ID
* Vehicle Type
* Capacity
* Maintenance Cost

---

# 🧹 Data Cleaning & Modeling

### ✅ Data Cleaning

* Missing values in **Fuel Consumed** were handled using **Mean Imputation**
* Data types verified and corrected
* Ensured no duplicate records

### ✅ Data Modeling

* Created relationship:

  ```
  Trip_Data[Vehicle_ID] → Vehicle_Master[Vehicle_ID]
  ```

* Relationship validated in **Manage Relationships**

---

# 🧮 DAX Measures Implemented

## 1️⃣ Fuel Efficiency

```DAX
Fuel Efficiency =
DIVIDE(
    SUM('Trip_Data'[Distance_km]),
    SUM('Trip_Data'[Fuel_Consumed_L])
)
```

---

## 2️⃣ On-Time Trips

```DAX
On-Time-Trips =
CALCULATE(
    COUNT('Trip_Data'[Trip_ID]),
    'Trip_Data'[Delivery_Status] = "On-Time"
)
```

---

## 3️⃣ Total Trips

```DAX
Total-Trips =
COUNT('Trip_Data'[Trip_ID])
```

---

## 4️⃣ On-Time Delivery %

```DAX
On-Time-Delivery % =
DIVIDE([On-Time-Trips], [Total-Trips])
```

---

## 5️⃣ Fuel Cost

(Fuel Cost per liter = 100)

```DAX
Fuel Cost =
SUM('Trip_Data'[Fuel_Consumed_L]) * 100
```

---

## 6️⃣ Total Maintenance Cost

```DAX
Total Maintenance Cost =
SUM('Vehicle_Master'[Maintenance_Cost])
```

---

## 7️⃣ Cost per km

```DAX
Cost per km =
DIVIDE(
    [Fuel Cost] + [Total Maintenance Cost],
    SUM('Trip_Data'[Distance_km])
)
```

---

## 8️⃣ KPI Measures

### 🔹 Average Delivery Time

```DAX
Avg Delivery Time =
AVERAGE('Trip_Data'[Distance_km])
```

### 🔹 Average Cost per km

```DAX
Average Cost per km =
AVERAGEX(
    Trip_Data,
    [Cost per km]
)
```

---

# 📊 Dashboard Visualizations

### 📌 Operational Performance

* **Bar Chart** → On-Time Delivery % by Destination
* **Line Chart** → Fuel Efficiency Trend by Delivery Date
* **Cards** →

  * Avg Delivery Time
  * Average Cost per km

### 📌 Cost & Maintenance Analysis

* **Pie Chart** → Vehicle Type vs Average Maintenance Cost

---

# 🤖 AI-Powered Visuals

This project integrates Power BI AI features:

### 🔹 Q&A Visual

Prompt used:

> “Average Cost per km by vehicle type?”

Enables natural language query-based insights.

---

### 🔹 Key Influencers

Analyzed:

* Delivery Status
  Explained by:
* Distance (km)
* Vehicle Type
* Driver ID

Helps identify what drives late deliveries.

---

### 🔹 Decomposition Tree

Analyzed:

* Cost per km

Explained by:

* Vehicle Type
* Maintenance Cost
* Distance

Provides drill-down cost analysis.

---

# 🎯 Key Business Insights

✔ Identified destinations with lower on-time performance
✔ Measured fuel efficiency trends over time
✔ Determined cost-heavy vehicle types
✔ Analyzed drivers impacting delivery delays
✔ Evaluated maintenance cost impact on total cost

---

# 🛠 Tools & Technologies Used

* Microsoft Power BI Desktop
* DAX (Data Analysis Expressions)
* Data Modeling & Relationships
* AI Visuals (Q&A, Key Influencers, Decomposition Tree)
* Data Cleaning & Transformation

---

# 💼 Skills Demonstrated

✔ End-to-End Dashboard Development
✔ Business Problem Translation
✔ Data Cleaning & Modeling
✔ Advanced DAX Calculations
✔ Time-Based Trend Analysis
✔ AI-Driven Analytics
✔ KPI & Performance Monitoring

---

# 🚀 Outcome

Delivered an **interactive transport operations dashboard** that enables management to:

* Improve fleet utilization
* Reduce fuel & maintenance costs
* Optimize delivery timelines
* Enhance operational efficiency

---
