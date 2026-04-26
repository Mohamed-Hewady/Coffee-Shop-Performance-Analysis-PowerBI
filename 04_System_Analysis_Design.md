# System Analysis & Design

## 1. Introduction

This section describes the system analysis and design of the Maven Roasters Sales Performance Dashboard.

The project is designed as a Power BI business intelligence solution that transforms raw transaction-level sales data into interactive dashboards and business insights. The dashboard helps analyze revenue trends, customer purchasing patterns, store performance, product performance, busiest days, and peak sales hours.

The system is not a traditional software application with backend and frontend components. Instead, it is a data analysis and visualization system built using Microsoft Power BI, Power Query, DAX, and a structured sales dataset.

---

## 2. Problem Statement

Maven Roasters has a large volume of sales transaction data collected from three coffee shop locations in New York City. However, raw transaction records alone do not provide clear and direct insights into business performance.

Without proper analysis and visualization, it becomes difficult to answer important business questions such as:

- How is revenue changing over time?
- Which store location performs best?
- What are the busiest days of the week?
- What are the peak sales hours?
- Which products generate the highest sales?
- Which product categories contribute most to revenue?

Therefore, this project aims to transform the raw sales dataset into an interactive Power BI dashboard that helps users monitor KPIs, identify trends, and support data-driven decision-making.

---

## 3. System Objectives

The main objectives of the Power BI dashboard are:

1. Provide a clear overview of Maven Roasters' sales performance.
2. Track key sales KPIs such as total revenue, total transactions, total quantity sold, and average order value.
3. Analyze sales trends from January 2023 to June 2023.
4. Compare sales performance across the three store locations.
5. Identify the busiest days of the week.
6. Identify peak sales hours during the day.
7. Evaluate product and category performance.
8. Support business decision-making through interactive visuals and filters.

---

## 4. System Scope

The system focuses on analyzing historical sales transaction data for Maven Roasters.

### In Scope

The dashboard includes analysis of:

- Total revenue
- Total transactions
- Total quantity sold
- Average order value
- Monthly sales trends
- Sales by weekday
- Sales by hour
- Store location performance
- Product category performance
- Product-level performance
- Interactive filtering by date, store location, and product category

### Out of Scope

The dashboard does not include:

- Customer demographic analysis
- Profit margin analysis
- Cost of goods sold analysis
- Inventory forecasting
- Machine learning prediction
- Customer loyalty or retention analysis

These areas are excluded because the dataset does not contain the required fields for these types of analysis.

---

## 5. Data Model Design

The project uses a transaction-level sales dataset. Each row represents a sales transaction or product-level transaction record.

The data model is designed to support sales analysis by time, location, and product.

The main dataset is used as the central table for the Power BI report. Additional calculated columns and DAX measures are created to support analysis and visualization.

---

## 6. Main Data Fields

| Field | Description | Usage |
|---|---|---|
| Transaction Date | Date when the transaction occurred | Monthly and daily sales analysis |
| Transaction Time | Time when the transaction occurred | Hourly and peak time analysis |
| Store Location | Branch where the transaction occurred | Store performance comparison |
| Product Category | Main category of the product | Category-level sales analysis |
| Product Type | Type or group of product | Product type performance analysis |
| Product Detail | Specific product name or detail | Product-level performance analysis |
| Quantity | Number of units sold | Quantity sold calculation |
| Unit Price | Price per unit | Pricing and sales calculation |
| Sales Amount | Total transaction sales value | Revenue calculation |

---

## 7. Calculated Columns

Additional calculated columns may be created in Power BI to support time-based analysis.

| Calculated Column | Purpose |
|---|---|
| Month Name | Used to analyze sales by month |
| Month Number | Used to sort months correctly |
| Day Name | Used to analyze sales by weekday |
| Day Number | Used to sort weekdays correctly |
| Hour | Used to analyze peak sales hours |
| Revenue | Used to calculate total sales if sales amount needs to be derived |

Example calculated columns:

```DAX
Revenue = 'Sales'[Quantity] * 'Sales'[Unit Price]
```

```DAX
Hour = HOUR('Sales'[Transaction Time])
```

```DAX
Month Name = FORMAT('Sales'[Transaction Date], "MMMM")
```

```DAX
Month Number = MONTH('Sales'[Transaction Date])
```

```DAX
Day Name = FORMAT('Sales'[Transaction Date], "dddd")
```

```DAX
Day Number = WEEKDAY('Sales'[Transaction Date], 2)
```

---

## 8. DAX Measures

The dashboard uses DAX measures to calculate the main KPIs.

| Measure | Formula Logic | Purpose |
|---|---|---|
| Total Revenue | SUM of sales amount | Measures total sales value |
| Total Transactions | COUNT of transaction records or transaction IDs | Measures number of sales transactions |
| Total Quantity Sold | SUM of quantity | Measures total units sold |
| Average Order Value | Total Revenue divided by Total Transactions | Measures average revenue per transaction |

Example DAX measures:

```DAX
Total Revenue = SUM('Sales'[Sales Amount])
```

```DAX
Total Transactions = COUNTROWS('Sales')
```

```DAX
Total Quantity Sold = SUM('Sales'[Quantity])
```

```DAX
Average Order Value = DIVIDE([Total Revenue], [Total Transactions])
```

---

## 9. Data Flow Diagram Description

The data flow explains how the raw dataset is transformed into business insights inside Power BI.

### Data Flow Steps

1. The raw sales dataset is imported into Power BI.
2. Power Query is used to clean and transform the data.
3. Data types are corrected for date, time, text, and numeric fields.
4. Calculated columns are created for month, weekday, and hour analysis.
5. DAX measures are created to calculate sales KPIs.
6. Dashboard visuals are built using the cleaned data model.
7. Users interact with slicers and visuals.
8. Insights are generated from the dashboard.

---

## 10. Data Flow

```text
Raw Sales Dataset
        ↓
Power BI Import
        ↓
Power Query Cleaning & Transformation
        ↓
Data Type Validation
        ↓
Calculated Columns
        ↓
DAX Measures
        ↓
Data Model
        ↓
Dashboard Visuals
        ↓
Interactive Analysis
        ↓
Business Insights
```

---

## 11. Dashboard Design

The Power BI report is designed to be divided into clear dashboard pages. Each page focuses on a specific analysis area.

The dashboard pages are organized to help users move from a general overview to more detailed analysis.

---

## 12. Dashboard Pages

| Page | Purpose | Main Visuals |
|---|---|---|
| Executive Overview | Provides a high-level summary of sales performance | KPI cards, revenue trend, revenue by location |
| Time Analysis | Analyzes sales behavior over time | Monthly trend, weekday sales, hourly sales |
| Store Performance | Compares the three store locations | Bar charts, revenue comparison, transaction comparison |
| Product Performance | Evaluates product and category sales | Product category chart, best-selling products, least-selling products |

---

## 13. Page 1: Executive Overview

The Executive Overview page provides a quick summary of the overall sales performance.

### Main Components

- Total Revenue card
- Total Transactions card
- Total Quantity Sold card
- Average Order Value card
- Revenue trend over time
- Revenue by store location
- Filters for date and location

### Purpose

This page allows users to quickly understand overall business performance and monitor the most important KPIs.

---

## 14. Page 2: Time Analysis

The Time Analysis page focuses on customer purchasing patterns across different time periods.

### Main Components

- Revenue by month
- Transactions by weekday
- Revenue by weekday
- Transactions by hour
- Peak sales hour analysis

### Purpose

This page helps identify the busiest days and peak operating hours, which can support staffing and operational planning.

---

## 15. Page 3: Store Performance

The Store Performance page compares sales across the three Maven Roasters locations.

### Main Components

- Revenue by store location
- Transactions by store location
- Quantity sold by store location
- Average order value by store location

### Purpose

This page helps identify which locations perform best and whether any store requires further review or improvement.

---

## 16. Page 4: Product Performance

The Product Performance page analyzes sales by product category, product type, and product detail.

### Main Components

- Revenue by product category
- Quantity sold by product category
- Best-selling products
- Least-selling products
- Product contribution to revenue

### Purpose

This page helps understand product demand and identify which products contribute most to sales performance.

---

## 17. UI/UX Design Guidelines

The dashboard design should follow simple and clear visual principles.

| Guideline | Description |
|---|---|
| Clear Layout | Visuals should be organized and not overcrowded |
| KPI Placement | Main KPI cards should be placed at the top of the page |
| Consistent Design | Colors, fonts, and formatting should be consistent across pages |
| Easy Navigation | Dashboard pages should be clearly named |
| Clear Titles | Each visual should have a clear and meaningful title |
| Readable Labels | Chart labels should be easy to read |
| Suitable Visuals | Each chart type should match the purpose of the analysis |
| Interactive Filters | Slicers should allow users to filter by date, location, and product category |

---

## 18. Recommended Visual Types

| Analysis Area | Recommended Visual |
|---|---|
| Total Revenue | Card |
| Total Transactions | Card |
| Total Quantity Sold | Card |
| Average Order Value | Card |
| Monthly Sales Trend | Line Chart |
| Sales by Weekday | Column Chart |
| Sales by Hour | Column Chart or Line Chart |
| Revenue by Store Location | Bar Chart |
| Product Category Performance | Bar Chart or Treemap |
| Best-Selling Products | Bar Chart |
| Product Details | Table or Matrix |

---

## 19. Technology Stack

| Tool / Technology | Usage |
|---|---|
| Microsoft Power BI Desktop | Building the dashboard, data model, and report pages |
| Power Query | Cleaning and transforming the dataset |
| DAX | Creating calculated measures and KPIs |
| CSV / Excel Dataset | Source data for the analysis |
| GitHub | Hosting project documentation and files |

---

## 20. System Architecture

Since this project is a Power BI dashboard, the architecture is focused on data processing and visualization.

```text
Dataset Layer
Raw transaction dataset

        ↓

Data Preparation Layer
Power Query cleaning and transformation

        ↓

Data Modeling Layer
Calculated columns and DAX measures

        ↓

Visualization Layer
Power BI dashboard pages and visuals

        ↓

User Interaction Layer
Filters, slicers, and interactive analysis
```

---

## 21. Validation Approach

To ensure the dashboard provides accurate results, the following validation steps should be performed:

| Validation Area | Method |
|---|---|
| Revenue Calculation | Compare Power BI total revenue with manual calculation from the dataset |
| Transaction Count | Validate the number of records or transactions |
| Quantity Sold | Compare total quantity sold with dataset totals |
| Date Analysis | Check that month and weekday columns are correctly sorted |
| Filter Accuracy | Test slicers to ensure visuals update correctly |
| DAX Measures | Review formulas and test results using sample data |

---

## 22. Summary

The System Analysis and Design section explains how the Maven Roasters Power BI dashboard is structured and designed.

The dashboard transforms raw sales transaction data into a clean and interactive business intelligence report. It includes data cleaning, calculated columns, DAX measures, dashboard pages, visual design guidelines, and validation steps.

This design supports the project objectives by helping users analyze sales trends, store performance, product performance, busiest days, peak hours, and key sales KPIs.
