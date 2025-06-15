# 📊 Capstone Project - Exploratory Data Analysis using Power BI

## 🔍 Project Overview

This capstone project demonstrates comprehensive **Exploratory Data Analysis (EDA)** using **Power BI**, focusing on customer, product, order, and supplier data from a simulated retail dataset. The goal is to extract actionable insights for business strategy and operational optimization.

---

## 🗂️ Dataset Information

The dataset is composed of the following tables:
- `Customers.csv`
- `Employees.csv`
- `Orders.csv`
- `Order Details.csv`
- `Products.csv`
- `Categories.csv`
- `Shippers.csv`
- `Suppliers.csv`

These tables are related using primary and foreign keys and represent a complete retail database model.

---

## 🛠 Tools & Technologies

- **Power BI Desktop**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Data Modeling & Relationships**
- **Interactive Dashboards**
- **Charts**: Line, Bar, Tree Map, Map, pie chart etc.

---

## 📈 Key Business Questions Addressed

1. What is the average number of orders per customer?
2. Are there high-value repeat customers?
3. How do order patterns vary by city or country?
4. Can we cluster customers based on spend, frequency, and category preference?
5. Which products and categories generate the most revenue?
6. Are there patterns between product pricing, stock levels, and performance?
7. What is the average shipping duration, and how do shippers compare?
8. What are the trends in employee hiring and titles?
9. How are suppliers distributed across regions and categories?

---

## 🧠 DAX Measures Created

Examples of DAX measures used:
```DAX
CustomerOrderCount = COUNTROWS(RELATEDTABLE(Orders))

CustomerTotalSpend = 
CALCULATE(
    SUM('Order Details'[UnitPrice] * 'Order Details'[Quantity] * (1 - 'Order Details'[Discount]))
)

AvgShippingDuration = 
AVERAGEX(Orders, DATEDIFF(Orders[OrderDate], Orders[ShippedDate], DAY))
