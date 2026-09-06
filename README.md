# Sales & Business Performance Dashboard

An interactive Power BI dashboard designed to analyze sales performance, profitability, products, customers, and regional trends using a structured data model, Power Query, and DAX.

## 📊 Project Overview

This project transforms retail sales data into an interactive business intelligence dashboard that helps users understand:

- Overall revenue and profitability
- Revenue and profit trends over time
- Category-wise performance
- Top-performing products
- Customer and regional performance
- Year-over-year growth
- Product-level performance through drill-through analysis

## 🎯 Objectives

- Build a structured Power BI data model using a star-schema approach
- Clean and transform raw data using Power Query
- Create reusable DAX measures for business KPIs
- Design an interactive multi-page dashboard
- Enable filtering through slicers
- Provide product-level drill-through analysis
- Present business trends in a clear and decision-friendly format

## 🛠️ Tools & Technologies

- **Power BI Desktop**
- **Power Query (M)**
- **DAX**
- **Microsoft Excel / CSV**
- **Star Schema Data Modeling**

## 🗂️ Data Model

The dashboard follows a star-schema structure.

### Fact Table

**Fact_Sales**

Contains transactional sales information such as:

- Order ID
- Date
- Product ID
- Customer ID
- Region ID
- Quantity
- Sales
- Cost

### Dimension Tables

- **Dim_Date** — Date and time analysis
- **Dim_Product** — Product and category information
- **Dim_Customer** — Customer attributes
- **Dim_Region** — Regional information

Relationships are established using one-to-many relationships from the dimension tables to the sales fact table.

## 🧹 Data Transformation

Power Query was used to prepare the data before loading it into the Power BI model.

Key transformations included:

- Data type validation
- Header correction
- Duplicate transaction handling
- Data cleaning
- Preparation of dimension and fact tables
- Structuring data for analytical modeling

## 📐 DAX Measures

The dashboard uses reusable DAX measures for core business metrics.

```DAX
Total Revenue = SUM(Fact_Sales[Sales])

Total Cost = SUM(Fact_Sales[Cost])

Profit = [Total Revenue] - [Total Cost]

Profit Margin = DIVIDE([Profit], [Total Revenue])

Total Quantity = SUM(Fact_Sales[Quantity])

Revenue LY =
CALCULATE(
    [Total Revenue],
    SAMEPERIODLASTYEAR(Dim_Date[Date])
)

YoY Growth =
DIVIDE(
    [Total Revenue] - [Revenue LY],
    [Revenue LY]
)


📈 Dashboard Features
Executive Overview

Provides a high-level view of business performance through:

- Total Revenue
- Profit
- Profit Margin
- YoY Growth
- Total Quantity
- Monthly Revenue Trend
- Revenue by Category
- Profit by Category
- Top 10 Products by Revenue
- Year and Category slicers
- Product & Category Analysis

Enables deeper analysis of:

- Category revenue
- Category profitability
- Product performance
- Regional revenue
- Regional profitability
- Customer segment performance
- Category profit margins
- Customer & Regional Performance

Provides analysis of:

- Customer performance
- Regional sales
- Regional profitability
- Customer segments
- Comparative business performance
- Product Details

A dedicated drill-through page allows users to select a product and analyze:

- Product Revenue
- Product Profit
- Product Profit Margin
- Product Quantity
- Revenue Trend
- Product Category
🖼️ Dashboard Preview

💡 Key Business Insights

The dashboard can be used to identify:

- High-revenue and high-profit product categories
- Products contributing significantly to overall revenue
- Changes in sales performance over time
- Differences in regional performance
- Profitability variations across categories
- Year-over-year changes in business performance


📁 Repository Structure
Sales_Business_Performance_Dashboard/
│
├── Sales_Business_Performance_Dashboard.pbix
├── dashboard-overview.png
└── README.md

🚀 How to Use
Download the .pbix file from this repository.
Open it using Power BI Desktop.
Explore the dashboard pages.
Use slicers to filter the analysis.
Select products to explore the drill-through Product Details page.

📌 Project Highlights
Built a star-schema Power BI data model
Applied Power Query transformations
Created business-focused DAX measures
Designed a multi-page interactive dashboard
Implemented slicers and drill-through functionality
Built KPI-driven visual analysis for business performance

Built with Power BI | DAX | Power Query
