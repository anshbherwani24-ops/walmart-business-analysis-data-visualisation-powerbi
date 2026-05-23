# 🛒 Walmart Sales & Operations Dashboard

_A comprehensive Power BI dashboard project analyzing Walmart’s sales performance, product profitability, customer behavior, and employee efficiency using a dimensional retail dataset._

---

# 📌 Table of Contents
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

This project presents an interactive Walmart Sales & Operations Dashboard built in Power BI using a star schema retail dataset. The dashboard provides a 360-degree business overview covering revenue performance, product profitability, customer segmentation, geographic analysis, and employee productivity.

The objective of this project is to transform raw retail transaction data into meaningful business insights that support strategic and operational decision-making.

---

## Business Problem

Retail businesses generate large volumes of transactional data daily. Without structured analysis, it becomes difficult to identify:

- High-performing product categories
- Revenue-driving regions
- Customer purchasing behavior
- Employee productivity
- Profitability trends
- Sales growth opportunities

This dashboard addresses these challenges by converting retail data into actionable visual insights.

---

## Dataset

The project uses a dimensional retail dataset containing:

- FactSales
- DimCustomer
- DimProduct
- DimDate
- DimGeography
- DimEmployee

The dataset includes information related to:

- Sales transactions
- Products and categories
- Customers
- Regions and locations
- Employees
- Order quantities and profits

---

## Data Model

A star schema model was created in Power BI.

### Relationships

- FactSales → DimCustomer
- FactSales → DimProduct
- FactSales → DimDate
- FactSales → DimGeography
- FactSales → DimEmployee

This structure improves filtering efficiency and supports scalable reporting.

---

## Tools & Technologies

- Power BI
- DAX (Data Analysis Expressions)
- Power Query
- CSV Dataset
- Data Modeling
- Microsoft Excel

---

## Dashboard Pages

### 📊 Page 1: Sales Overview

Provides a high-level business performance summary.

#### Visuals Used

- KPI Cards
- Revenue Trend Line Chart
- Revenue by Region Donut Chart
- Revenue vs Profit by Category
- Orders by Category

---

### 📦 Page 2: Product Analysis

Analyzes product-level performance and profitability.

#### Visuals Used

- Treemap
- Scatter Plot
- Top 10 Products Bar Chart
- Product Performance KPIs

---

### 👥 Page 3: Customer & Geography Insights

Focuses on customer segmentation and geographic distribution.

#### Visuals Used

- Geographic Map
- Customer Segment Distribution
- Top Customers Analysis
- Regional Performance Matrix

---

### 👨‍💼 Page 4: Employee Performance

Tracks employee productivity and operational efficiency.

#### Visuals Used

- Employee Revenue Bar Chart
- Sales Target Gauge
- Employee Contribution Donut Chart
- Detailed Performance Table

---

## Key KPIs

The dashboard includes:

- Total Revenue
- Total Profit
- Profit Margin %
- Total Orders
- Average Order Value
- Revenue per Product
- Revenue per Customer
- Orders per Customer
- Revenue per Employee
- Sales Growth %
- Target Achievement %

---

## Dashboard Features

- Interactive slicers and filters
- Cross-filtering between visuals
- Dynamic KPI calculations
- Geographic analysis
- Product profitability analysis
- Employee performance tracking
- Business-focused storytelling
- Responsive dashboard layout

---

## Project Structure

```bash
walmart-sales-dashboard/
│
├── README.md
├── data/
│   ├── FactSales.csv
│   ├── DimCustomer.csv
│   ├── DimDate.csv
│   ├── DimEmployee.csv
│   ├── DimGeography.csv
│   └── DimProduct.csv
│
├── dashboard/
│   └── Walmart_Sales_Dashboard.pbix
│
├── images/
│   └── dashboard-preview.png
│
└── docs/
    └── project-report.pdf
```

---

## DAX Measures

### Total Revenue

```DAX
Total Revenue = SUM(FactSales[SalesAmount])
```

### Total Profit

```DAX
Total Profit = SUM(FactSales[Profit])
```

### Total Orders

```DAX
Total Orders = COUNTROWS(FactSales)
```

### Total Quantity

```DAX
Total Quantity = SUM(FactSales[Quantity])
```

### Profit Margin %

```DAX
Profit Margin % =
DIVIDE([Total Profit], [Total Revenue], 0)
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE([Total Revenue], [Total Orders], 0)
```

### Revenue per Customer

```DAX
Revenue per Customer =
DIVIDE([Total Revenue], [Total Customers], 0)
```

### Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(FactSales[CustomerKey])
```

### Orders per Customer

```DAX
Orders per Customer =
DIVIDE([Total Orders], [Total Customers], 0)
```

### Revenue per Employee

```DAX
Revenue per Employee =
DIVIDE([Total Revenue], DISTINCTCOUNT(DimEmployee[EmployeeKey]), 0)
```

### Orders per Employee

```DAX
Orders per Employee =
DIVIDE([Total Orders], DISTINCTCOUNT(DimEmployee[EmployeeKey]), 0)
```

### Revenue per Product

```DAX
Revenue per Product =
DIVIDE([Total Revenue], DISTINCTCOUNT(DimProduct[ProductKey]), 0)
```

### Revenue Last Year

```DAX
Revenue LY =
CALCULATE([Total Revenue], SAMEPERIODLASTYEAR(DimDate[Date]))
```

### YoY Growth %

```DAX
YoY Growth % =
DIVIDE([Total Revenue] - [Revenue LY], [Revenue LY], 0)
```

### Previous Month Revenue

```DAX
Previous Month Revenue =
CALCULATE([Total Revenue], DATEADD(DimDate[Date], -1, MONTH))
```

### MoM Growth %

```DAX
MoM Growth % =
DIVIDE([Total Revenue] - [Previous Month Revenue], [Previous Month Revenue], 0)
```

### Revenue YTD

```DAX
Revenue YTD =
TOTALYTD([Total Revenue], DimDate[Date])
```

### Revenue MTD

```DAX
Revenue MTD =
TOTALMTD([Total Revenue], DimDate[Date])
```

### Repeat Customers

```DAX
Repeat Customers =
CALCULATE(
    DISTINCTCOUNT(FactSales[CustomerKey]),
    FILTER(
        VALUES(FactSales[CustomerKey]),
        CALCULATE(COUNTROWS(FactSales)) > 1
    )
)
```

### Repeat Customer %

```DAX
Repeat Customer % =
DIVIDE([Repeat Customers], [Total Customers], 0)
```

### Churn Rate %

```DAX
Churn Rate % =
DIVIDE(
    [Previous Customers] - [Current Customers],
    [Previous Customers]
)
```

### Sales Target

```DAX
Sales Target = 100000000
```

### Target Achievement %

```DAX
Target Achievement % =
DIVIDE([Total Revenue], [Sales Target], 0)
```

### Employee Rank

```DAX
Employee Rank =
RANKX(
    ALL(DimEmployee[EmployeeName]),
    [Total Revenue],
    ,
    DESC
)
```

---

## Business Insights

Key findings from the analysis include:

- Clothing and Accessories contribute the highest revenue
- Revenue is evenly distributed across regions
- Certain products generate high revenue but low profitability
- Bronze-tier customers contribute the highest sales volume
- Employee productivity varies significantly across teams
- The business maintains a strong overall profit margin

---

## How to Use

1. Download the dataset files
2. Open Power BI Desktop
3. Load all CSV files into Power BI
4. Create relationships using the star schema model
5. Import DAX measures
6. Open the `.pbix` dashboard file
7. Interact with filters and visuals

---

## Future Enhancements

Possible improvements include:

- Forecasting and predictive analytics
- Customer churn prediction
- Dynamic drillthrough pages
- Advanced KPI benchmarking
- Real-time data integration
- AI-driven insights

---

## Author

**Ansh Bherwani**  
Data Analyst | Business Intelligence Enthusiast

- LinkedIn: https://www.linkedin.com/in/ansh-bherwani-0ab541263/
- Email: anshbherwani24@gmail.com#   w a l m a r t - b u s i n e s s - a n a l y s i s - d a t a - v i s u a l i s a t i o n - p o w e r b i  
 