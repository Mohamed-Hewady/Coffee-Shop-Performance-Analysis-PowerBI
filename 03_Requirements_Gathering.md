# Requirements Gathering

## 1. Introduction

The requirements gathering phase defines what the Power BI dashboard should achieve and how different users can benefit from it.

For this project, the main goal is to analyze the sales performance of Maven Roasters using transaction-level sales data from January 2023 through June 2023. The dashboard should help users understand revenue trends, customer purchasing patterns, store performance, peak hours, busiest days, and product performance.

The requirements are divided into:

- Stakeholder Analysis
- User Stories
- Use Cases
- Functional Requirements
- Non-Functional Requirements

---

## 2. Stakeholder Analysis

Stakeholders are the individuals or groups who can benefit from the sales performance dashboard. Each stakeholder has different information needs based on their role in the business.

| Stakeholder | Description | Needs |
|---|---|---|
| Business Owner | Responsible for overall business performance and growth | Needs to monitor total revenue, sales trends, and overall business performance |
| Store Manager | Responsible for managing daily store operations | Needs to identify peak hours and busiest days to improve staff scheduling and service planning |
| Sales Manager | Responsible for tracking sales performance | Needs to compare sales by store location, month, and product category |
| Operations Manager | Responsible for improving operational efficiency | Needs to understand customer activity patterns by time and location |
| Product Manager | Responsible for product performance evaluation | Needs to identify best-selling products, low-performing products, and high-revenue categories |
| Data Analyst / BI User | Responsible for analyzing and presenting business data | Needs a clean, interactive, and accurate dashboard for analysis and reporting |

---

## 3. User Stories

User stories describe the needs of the dashboard users in a simple and practical way.

1. As a business owner, I want to view total revenue so that I can evaluate the overall business performance.

2. As a business owner, I want to track monthly sales trends so that I can understand whether revenue is increasing or decreasing over time.

3. As a store manager, I want to identify the busiest days of the week so that I can plan staffing and operations more effectively.

4. As a store manager, I want to identify peak sales hours so that I can prepare for high-demand periods.

5. As a sales manager, I want to compare sales performance across store locations so that I can identify the best-performing branch.

6. As a product manager, I want to analyze product sales so that I can identify best-selling and least-selling products.

7. As an operations manager, I want to understand sales patterns by hour and weekday so that I can improve daily operational planning.

8. As a dashboard user, I want to filter the report by date, location, and product category so that I can focus on specific areas of analysis.

---

## 4. Use Cases

Use cases describe how users interact with the Power BI dashboard to achieve specific goals.

| Use Case | User | Description | Expected Outcome |
|---|---|---|---|
| View Sales Overview | Business Owner | The user views total revenue, total transactions, total quantity sold, and average order value | User understands overall sales performance |
| Analyze Monthly Sales Trends | Business Owner / Sales Manager | The user reviews sales performance from January to June 2023 | User identifies sales growth, decline, or fluctuations |
| Compare Store Locations | Sales Manager / Operations Manager | The user compares revenue and transactions across the three store locations | User identifies the best and weakest performing locations |
| Analyze Busiest Days | Store Manager | The user checks which weekdays generate the highest sales activity | User improves staff scheduling and daily planning |
| Analyze Peak Hours | Store Manager / Operations Manager | The user reviews sales by hour of the day | User identifies high-demand operating hours |
| Evaluate Product Performance | Product Manager | The user reviews product sales by category, type, and product detail | User identifies best-selling and low-performing products |
| Filter Dashboard Data | Dashboard User | The user applies filters by date, store location, or product category | Dashboard visuals update based on selected filters |

---

## 5. Functional Requirements

Functional requirements describe the main functions that the Power BI dashboard must provide.

The dashboard should be able to:

1. Display total revenue generated from all transactions.

2. Display total number of transactions.

3. Display total quantity sold.

4. Calculate and display Average Order Value (AOV).

5. Show monthly revenue trends from January 2023 to June 2023.

6. Show sales performance by store location.

7. Compare revenue across the three Maven Roasters locations.

8. Analyze sales by product category.

9. Analyze sales by product type and product detail.

10. Identify best-selling products based on quantity sold.

11. Identify products with lower sales performance.

12. Analyze sales distribution by weekday.

13. Analyze sales distribution by hour of the day.

14. Identify peak operating hours.

15. Identify busiest days of the week.

16. Provide slicers or filters for date, store location, and product category.

17. Allow dashboard visuals to update interactively based on user selections.

18. Present KPIs clearly using cards or summary visuals.

19. Use suitable charts for trend analysis, comparison, and product performance.

20. Provide clear dashboard pages for different analysis areas.

---

## 6. Non-Functional Requirements

Non-functional requirements describe the quality standards that the dashboard should meet.

| Requirement | Description |
|---|---|
| Usability | The dashboard should be easy to understand and simple to navigate |
| Performance | Dashboard visuals should load smoothly and respond quickly to filters |
| Accuracy | All KPI calculations should be correct and validated against the source dataset |
| Reliability | The dashboard should provide consistent results when filters are applied |
| Maintainability | Measures, columns, and visuals should be clearly named and organized |
| Visual Clarity | Charts should have clear titles, labels, and readable formatting |
| Interactivity | Users should be able to interact with slicers and visuals easily |
| Scalability | The dashboard structure should allow future expansion if more data becomes available |
| Accessibility | The report should use readable colors, clear fonts, and understandable layouts |
| Data Consistency | Data types should be correctly formatted, especially date, time, and sales amount fields |

---

## 7. Data Requirements

The dashboard requires transaction-level sales data for Maven Roasters.

The required data fields include:

| Data Field | Purpose |
|---|---|
| Transaction Date | Used for monthly and daily sales analysis |
| Transaction Time | Used for hourly and peak time analysis |
| Store Location | Used to compare sales performance across locations |
| Product Category | Used to analyze category-level performance |
| Product Type | Used to analyze product group performance |
| Product Detail | Used to identify specific product performance |
| Quantity | Used to calculate total quantity sold |
| Unit Price | Used to understand item pricing |
| Sales Amount | Used to calculate total revenue |

---

## 8. Dashboard Requirements

The Power BI dashboard should be organized into clear pages to make the analysis easy to understand.

| Dashboard Page | Purpose |
|---|---|
| Executive Overview | Provides a summary of key sales KPIs and overall performance |
| Time Analysis | Analyzes monthly sales trends, busiest days, and peak hours |
| Store Performance | Compares revenue and transactions across store locations |
| Product Performance | Analyzes product categories, best-selling products, and low-performing products |

---

## 9. Summary

The requirements gathering phase defines the main users, needs, and expected functions of the Maven Roasters Power BI dashboard.

The dashboard should help stakeholders analyze sales trends, store performance, product performance, busiest days, peak hours, and key sales KPIs. These requirements ensure that the final dashboard is useful, interactive, accurate, and aligned with the project objectives.
