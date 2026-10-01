# BrewMetrics Coffee Co. — Business Intelligence

A version-controlled Power BI solution for analyzing sales performance across cities, store formats, products, and time.

## Project Overview

BrewMetrics Coffee Co. is a Business Intelligence solution developed using Power BI to analyze coffee sales across different cities, store formats, products, and time periods. The project uses a star-schema data model and DAX measures to support sales analysis, product ranking, growth analysis, and cumulative sales tracking.

The solution was developed as a version-controlled BI project using GitHub, with GitHub Copilot used to assist with DAX development and documentation.

## Dataset

The dataset contains 15,482 sales transactions covering April to July 2026.

The main fields include:

- Date
- City
- Store Format
- Category
- Item
- Quantity
- Unit Price
- Sales Amount

## Data Model

The Power BI solution follows a star-schema structure consisting of:

- `fact_sales` — central transaction fact table containing sales and transaction-level measures.
- `Dim_Date` — date dimension used for time-based analysis.
- `Dim_City` — city dimension used for geographical sales analysis.
- `Dim_Product` — product and category dimension used for product analysis.
- `Dim_Store` — store and store-format dimension used for store-level analysis.

The dimensions are connected to the fact table using appropriate keys and relationships.

## DAX Measures

The following measures were created for analysis:

### Total Sales

Calculates the total sales amount across the selected context.

### MoM Growth %

Calculates month-over-month sales growth to identify changes in sales performance between months.

### Running Total Sales

Calculates cumulative sales over time to understand the progression of total sales.

### Product Sales Rank

Uses `RANKX` to rank products according to their sales performance.

## Dashboard Analysis

The Power BI dashboard contains visualizations for:

- Overall sales performance
- Monthly sales trends
- City-wise sales performance
- Product performance
- Cold Brew seasonal sales trends
- City and store-format analysis
- Interactive filtering using slicers
- City → Store Format drill-down analysis

## Key Insights

- The dataset contains 15,482 transactions with total sales of approximately ₹40.66 lakh.
- Bengaluru recorded the highest city-level sales at approximately ₹11.20 lakh, followed by Chennai at ₹10.55 lakh, Hyderabad at ₹9.69 lakh, and Coimbatore at ₹8.23 lakh.
- Cold Brew sales increased from approximately ₹2.77 lakh in April to ₹3.01 lakh in May, before declining to approximately ₹1.85 lakh in June.
- July contains only one day of data, so its sales should not be directly compared with the complete months of April, May, and June.

## Version Control

GitHub was used to maintain the development history of the Power BI project. Major stages were tracked through separate commits, including:

1. Initial project setup
2. Data model and schema development
3. DAX measure development
4. Dashboard development
5. Documentation and finalization

This provides a traceable history of the BI solution rather than treating the Power BI report as a single final file.

## Tools Used

- Power BI Desktop
- Power BI Project (`.pbip`)
- Power Query
- DAX
- GitHub
- GitHub Copilot
- Visual Studio Code

## Project Outcome

The completed solution provides an interactive and version-controlled BI environment for analyzing BrewMetrics Coffee Co.'s sales performance. It combines structured data modeling, DAX-based analytics, interactive Power BI visualizations, and Git-based version control to support data-driven business analysis.
