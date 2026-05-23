```markdown
# 🛒 Walmart Business Analysis Dashboard

_A comprehensive Power BI dashboard project analyzing Walmart’s sales performance, product profitability, customer behavior, and employee efficiency using a dimensional retail dataset._

---

## 📌 Table of Contents
- [Overview](#overview)
- [Business Problem](#business-problem)
- [Dataset](#dataset)
- [Data Model](#data-model)
- [Tools & Technologies](#tools--technologies)
- [Dashboard Pages](#dashboard-pages)
- [Key KPIs](#key-kpis)
- [Dashboard Features](#dashboard-features)
- [Project Structure](#project-structure)
- [DAX Measures](#dax-measures)
- [Business Insights](#business-insights)
- [How to Use](#how-to-use)
- [Future Enhancements](#future-enhancements)
- [Author](#author)

---

## Overview
This project presents an interactive Walmart Sales & Operations Dashboard built in Power BI using a star schema retail dataset. The dashboard provides a 360-degree business overview covering revenue performance, product profitability, customer segmentation, geographic analysis, and employee productivity. The objective is to transform raw retail transaction data into meaningful business insights that support strategic and operational decision-making.

---

## Business Problem
Retail businesses generate large volumes of transactional data daily. Without structured analysis, it is difficult to identify high-performing product categories, revenue-driving regions, customer behavior, employee productivity, profitability trends, and sales growth opportunities. This dashboard addresses these challenges by converting retail data into actionable visual insights.

---

## Dataset
The project uses a dimensional retail dataset containing **FactSales**, **DimCustomer**, **DimProduct**, **DimDate**, **DimGeography**, and **DimEmployee**. It includes information related to sales transactions, product categories, customer demographics, regional data, and employee metrics.

---

## Data Model
A star schema model was created in Power BI with **FactSales** as the central table, connected to all Dimension tables (**DimCustomer**, **DimProduct**, **DimDate**, **DimGeography**, **DimEmployee**). This structure improves filtering efficiency and supports scalable reporting.

---

## Tools & Technologies
* **Power BI** (Dashboarding & Reporting)
* **DAX** (Complex Calculations & Measures)
* **Power Query** (Data Transformation)
* **Excel/CSV** (Source Data)

---

## Dashboard Pages
1. **Sales Overview:** High-level performance summaries, revenue trends, and regional analysis.
2. **Product Analysis:** Treemaps, scatter plots, and top-performing product metrics.
3. **Customer & Geography:** Geographic maps, segment distribution, and customer ranking.
4. **Employee Performance:** Productivity tracking, sales target gauges, and contribution analysis.

---

## Key KPIs
Total Revenue, Total Profit, Profit Margin %, Total Orders, Average Order Value, Revenue per Customer, Revenue per Employee, YoY Growth %, and Target Achievement %.

---

## Dashboard Features
Interactive slicers, cross-filtering, dynamic KPI calculations, geographic mapping, product profitability analysis, and responsive layouts.

---

## Project Structure
```bash
walmart-sales-dashboard/
├── README.md
├── data/ (FactSales, DimCustomer, DimDate, DimEmployee, DimGeography, DimProduct)
├── dashboard/ (Walmart_Sales_Dashboard.pbix)
├── images/ (dashboard-preview.png)
└── docs/ (project-report.pdf)

```

---

## DAX Measures

* **Total Revenue:** `SUM(FactSales[SalesAmount])`
* **Total Profit:** `SUM(FactSales[Profit])`
* **Profit Margin %:** `DIVIDE([Total Profit], [Total Revenue], 0)`
* **Total Customers:** `DISTINCTCOUNT(FactSales[CustomerKey])`
* **YoY Growth %:** `DIVIDE([Total Revenue] - [Revenue LY], [Revenue LY], 0)`
* **Target Achievement %:** `DIVIDE([Total Revenue], [Sales Target], 0)`
*(Plus various others for MoM growth, YTD, MTD, and employee/product-specific rankings)*

---

## Business Insights

* Clothing and Accessories are top revenue drivers.
* Revenue is balanced regionally but profitability varies.
* High-volume products often have lower margins.
* Bronze-tier customers represent the largest segment by volume.
* Significant variance in employee productivity indicates opportunities for training.

---

## How to Use

1. Download the repository and dataset files.
2. Open the `.pbix` file in Power BI Desktop.
3. Ensure data sources point to the correct file path.
4. Use the slicers on the dashboard to interact with different regions and timeframes.

---

## Future Enhancements

* Implementing AI-driven insights and forecasting.
* Developing a customer churn prediction model.
* Adding real-time data integration.

---

## Author

**Ansh Bherwani** | Data Analyst

* **LinkedIn:** [Ansh Bherwani](https://www.linkedin.com/in/ansh-bherwani-0ab541263/)
* **Email:** anshbherwani24@gmail.com

```

```
