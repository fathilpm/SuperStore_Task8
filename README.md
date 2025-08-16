# 📊 Superstore Sales Performance Dashboard – Power BI

This project is a fully interactive and visually polished Power BI dashboard built to analyze and present sales data from a fictional Superstore. It provides insights into product performance, customer behavior, and regional sales trends using dynamic visuals and DAX-powered logic.

---

## 📁 Dataset Overview

- **Source**: Kaggle / Sample Superstore Dataset (https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting)
- **Columns Used**: Order ID, Order Date, Product Name, Category, Sub-Category, Sales, Customer ID, Region, State
- **Rows**: ~10,000

---

## 🚀 Features

- 📌 **KPI Cards**: Total Revenue, Orders, Unique Customers, Average Order Value
- 📦 **Top Sub-Categories & Products** by Sales
- 🗓 **Monthly Sales Trends** by Category
- 🗺️ **Geographic Sales Distribution** (State-wise)
- 🔁 **Repeat Customer Count** calculation using DAX
- 📅 **Slicers** for Year and Month navigation
- 🎨 Custom background and clean layout with aligned headings

---

## ⚙️ DAX Highlights

```DAX
-- Average Order Value
Average Order Value = DIVIDE(SUM('train'[Sales]), DISTINCTCOUNT('train'[Order ID]))

-- Repeat Customer Count
Repeat Customers = 
CALCULATE(
    DISTINCTCOUNT('train'[Customer ID]),
    FILTER(
        VALUES('train'[Customer ID]),
        CALCULATE(DISTINCTCOUNT('train'[Order ID])) > 1
    )
)
