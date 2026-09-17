# Retail Sales Business Intelligence Dashboard

![Portfolio preview](images/portfolio-preview.png)

## Overview

This project is an interactive **Business Intelligence dashboard built in Microsoft Power BI** to analyze retail transaction data and turn it into clear business insights.

The dashboard explores sales performance, product/category performance, order value, geographic distribution, purchasing patterns, and revenue drivers. It was developed as a **two-person academic BI project** by **Rinat Bitimbay** and **Auyelbay Arailym**.

## Business Goal

The goal was to create a dashboard that helps users quickly answer questions such as:

- How much revenue was generated?
- Which product categories and products drive sales?
- How does demand change over time?
- Which cities show stronger sales activity?
- Which products appear together within orders?
- Can non-technical users explore the data interactively?

## Dataset

The project uses a **synthetic online retail dataset obtained from GitHub**. The report contains the following fields:

- Customer ID
- Order Date
- Product Name
- Product Category
- Quantity
- Price
- Payment Method
- City

> Note: the original report identifies GitHub as the dataset source but does not preserve the exact repository URL.

## Key KPIs

| KPI | Result |
|---|---:|
| Total Sales | ~737.33K |
| Orders | 1,000 |
| Average Order Value | ~737.33 |

## Data Preparation & DAX

The project included data validation and creation of analytical fields/measures.

**Total Sales**

```DAX
Total Sales =
SUMX(
    'synthetic_online_retail_data',
    'synthetic_online_retail_data'[quantity] *
    'synthetic_online_retail_data'[price]
)
```

**OrderKey**

```DAX
OrderKey =
'synthetic_online_retail_data'[customer_id] & "-" &
FORMAT('synthetic_online_retail_data'[order_date], "yyyy-mm-dd")
```

**Average Order Value**

```DAX
Avg Order Value = DIVIDE([Total Sales], [Orders])
```

## Dashboard Analysis

### 1. Sales Overview

![Sales overview](images/sales-overview.png)

The overview combines KPI cards, category analysis, time-series analysis, and slicers to support interactive exploration of sales performance.

### 2. Descriptive Statistics

![Descriptive statistics](images/descriptive-statistics.png)

The report compares minimum, median, and maximum order values by product and uses conditional formatting to make patterns and unusual values easier to identify.

### 3. Decomposition Tree

![Decomposition tree](images/decomposition-tree.png)

A Power BI Decomposition Tree breaks down **Total Sales → Category → Product → City**, allowing users to drill into the strongest revenue contributors.

### 4. Market Basket Analysis

![Market basket analysis](images/market-basket-analysis.png)

Order-level analysis is used to inspect products appearing within the same orders and explore potential cross-selling or bundling opportunities.

### 5. Geographic Analysis

![Geographic analysis](images/geographic-analysis.png)

Sales are visualized geographically by city, helping users compare regional sales activity and identify stronger or weaker markets.

### 6. Natural-Language Q&A

![Power BI Q&A](images/powerbi-q-and-a.png)

Power BI Q&A allows users to explore the dataset with natural-language questions such as:

- *What is the total sales by city?*
- *What is the total quantity by city?*

## Main Findings

- **Electronics** generated the highest revenue among the analyzed categories.
- Within Electronics, **smartphones, tablets, and laptops** were major contributors.
- Sales quantity varied over time, with noticeable peaks in demand.
- Geographic analysis showed meaningful variation in sales activity across cities.
- The dashboard supports product, regional, and customer-behavior exploration through interactive visuals.

## Tools & Skills Demonstrated

- Microsoft Power BI
- DAX
- Business Intelligence
- Data Analysis
- Data Visualization
- Descriptive Statistics
- Decomposition Tree Analysis
- Market Basket Analysis
- Geographic Analysis
- Interactive Dashboards

## Repository Structure

```text
retail-sales-bi-dashboard/
├── README.md
├── dashboard/
│   └── Retail_Sales_BI_Dashboard.pbix
├── data/
│   └── synthetic_online_retail_data.csv
├── report/
│   └── Sales_Analysis_Report.pdf
├── images/
│   ├── portfolio-preview.png
│   ├── kpi-overview.png
│   ├── sales-overview.png
│   ├── descriptive-statistics.png
│   ├── decomposition-tree.png
│   ├── market-basket-analysis.png
│   ├── geographic-analysis.png
│   └── powerbi-q-and-a.png
└── career/
    ├── resume-project-entry.txt
    ├── linkedin-project-description.txt
    └── interview-talk-track.txt
```

## Team

This project was completed as a two-person academic project.

- **Rinat Bitimbay**
- **Auyelbay Arailym**

## Files

The repository includes the original Power BI `.pbix` file, the dataset used in the project, the written report, and dashboard screenshots for quick portfolio review.
