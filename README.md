
# 🛒 Walmart Sales & Operations Dashboard

_A comprehensive Power BI dashboard project analyzing Walmart’s sales performance, product profitability, customer behavior, and employee efficiency using a dimensional retail dataset._

---

## 📌 Table of Contents
- <a href="#overview">Overview</a>
- <a href="#business-problem">Business Problem</a>
- <a href="#dataset">Dataset</a>
- <a href="#data-model">Data Model</a>
- <a href="#tools--technologies">Tools & Technologies</a>
- <a href="#dashboard-pages">Dashboard Pages</a>
- <a href="#key-kpis">Key KPIs</a>
- <a href="#dashboard-features">Dashboard Features</a>
- <a href="#project-structure">Project Structure</a>
- <a href="#dax-measures">DAX Measures</a>
- <a href="#business-insights">Business Insights</a>
- <a href="#how-to-use">How to Use</a>
- <a href="#future-enhancements">Future Enhancements</a>
- <a href="#author">Author</a>

---

<h2 id="overview">Overview</h2>

This project presents an interactive Walmart Sales & Operations Dashboard built in Power BI using a star schema retail dataset. The objective is to transform raw retail transaction data into meaningful business insights that support strategic and operational decision-making.

---

<h2 id="business-problem">Business Problem</h2>

Retail businesses generate large volumes of transactional data daily. Without structured analysis, it is difficult to identify:
- High-performing product categories
- Revenue-driving regions
- Customer purchasing behavior
- Employee productivity
- Profitability trends
- Sales growth opportunities

---

<h2 id="dataset">Dataset</h2>

The project uses a dimensional retail dataset containing:
- **FactSales, DimCustomer, DimProduct, DimDate, DimGeography, DimEmployee**

Information includes sales transactions, products, categories, customers, regions, locations, employees, order quantities, and profits.

---

<h2 id="data-model">Data Model</h2>

A star schema model was created in Power BI with **FactSales** at the center, linked to all Dimension tables. This structure improves filtering efficiency and supports scalable reporting.

---

<h2 id="tools--technologies">Tools & Technologies</h2>

- **Power BI** (Dashboarding & Reporting)
- **DAX** (Data Analysis Expressions)
- **Power Query** (Data Transformation)
- **Microsoft Excel/CSV** (Data Source)

---

<h2 id="dashboard-pages">Dashboard Pages</h2>

1. **Sales Overview:** High-level performance summary.
2. **Product Analysis:** Product-level performance and profitability.
3. **Customer & Geography:** Segmentation and geographic distribution.
4. **Employee Performance:** Productivity and operational efficiency tracking.

---

<h2 id="key-kpis">Key KPIs</h2>

- Total Revenue, Total Profit, Profit Margin %
- Total Orders, Average Order Value
- Revenue per Product/Customer/Employee
- Sales Growth %, Target Achievement %

---

<h2 id="dashboard-features">Dashboard Features</h2>

- Interactive slicers and filters
- Cross-filtering between visuals
- Dynamic KPI calculations
- Geographic analysis
- Responsive dashboard layout

---

<h2 id="project-structure">Project Structure</h2>

```bash
walmart-sales-dashboard/
│
├── README.md
├── data/
│   ├── FactSales.csv
│   ├── DimCustomer.csv
│   └── ...
├── dashboard/
│   └── Walmart_Sales_Dashboard.pbix
└── docs/
    └── project-report.pdf

```

---

* **Total Revenue:** `SUM(FactSales[SalesAmount])`
* **Total Profit:** `SUM(FactSales[Profit])`
* **Profit Margin %:** `DIVIDE([Total Profit], [Total Revenue], 0)`
* **YoY Growth %:** `DIVIDE([Total Revenue] - [Revenue LY], [Revenue LY], 0)`

---

* Clothing and Accessories contribute the highest revenue.
* Revenue is evenly distributed across regions.
* Bronze-tier customers contribute the highest sales volume.
* Significant variance in employee productivity indicates training opportunities.

---

1. Download the repository and dataset files.
2. Open the `.pbix` file in Power BI Desktop.
3. Ensure data sources point to the correct local file path.
4. Interact with slicers to view performance metrics.

---

* Implementing AI-driven insights and forecasting.
* Developing a customer churn prediction model.
* Adding real-time data integration.

---

**Ansh Bherwani** Data Analyst | Business Intelligence Enthusiast

🔗 [LinkedIn](https://www.linkedin.com/in/ansh-bherwani-0ab541263/)

📧 [anshbherwani24@gmail.com]()

```

```
