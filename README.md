# Supply Chain Analytics Dashboard — Power BI

An end-to-end Power BI analytics solution for analyzing sales, inventory, demand forecasting, supplier performance, and replenishment.

## 📊 Project Overview

This project transforms a simulated supply chain dataset into an interactive 5-page Power BI dashboard.

## 🎯 Project Objective

Build an end-to-end supply chain analytics solution that converts raw operational data into actionable insights across sales, inventory, demand forecasting, supplier performance, and replenishment.

The objective was to identify performance trends, operational risks, and improvement opportunities through data modeling, DAX-based KPIs, and interactive Power BI reporting.

The analysis covers:

- 50 SKUs
- 5 warehouses
- 10 suppliers
- 4 demand regions
- 91,250 daily records
- Calendar year 2024

The project follows a complete BI workflow:

**Data profiling → Data modeling → DAX measures → Dashboard development → Business insights**

## 🧱 Data Model

The data was modeled using a **star schema** consisting of:

- Fact Supply Chain
- Dim Date
- Dim Product
- Dim Warehouse
- Dim Supplier
- Dim Region

The fact table has a grain of:

**1 row per Date + SKU + Warehouse**

## 🧮 DAX & Analytics

Developed **32 DAX measures** covering:

- Sales & Revenue
- Profitability
- Inventory
- Supply Chain Operations
- Promotions
- Forecasting
- Supplier Performance
- Warehouse Performance
- Reorder & Replenishment

Key calculations include:

- Revenue
- Gross Margin %
- Inventory Turnover
- Days of Supply
- Forecast Accuracy
- Weighted MAPE
- Promotion Uplift
- Supplier Spend
- Lead Time Reliability
- Reorder Compliance %

Special attention was given to semi-additive inventory calculations and weighted forecast-error measurement.

## 📈 Dashboard Pages

### 1. Executive Summary
Provides a high-level view of:

- Revenue
- Gross Margin
- Inventory Turnover
- Forecast Accuracy
- Regional and warehouse performance
- Revenue and demand trends

![Executive Summary](screenshots/executive-summary.png)

### 2. Inventory Analytics
Focuses on:

- Inventory health
- Days of Supply
- Inventory turnover
- Reorder-point risk
- Inventory value
- SKU-level inventory analysis

![Inventory Analytics](screenshots/inventory-analytics.png)

### 3. Sales & Demand
Analyzes:

- Monthly sales trends
- Top SKUs by revenue
- Promotion effectiveness
- Forecast accuracy
- Forecast error by SKU
- Regional demand

![Sales & Demand](screenshots/sales-demand.png)

### 4. Supplier Performance
Evaluates:

- Supplier spend
- Lead time
- Lead time reliability
- Supplier order quantities
- Supplier-level performance

![Supplier Performance](screenshots/supplier-performance.png)

### 5. Operations & Logistics
Analyzes:

- Sell-through rate
- Stockout rate
- Days of Supply
- Reorder-point breaches
- Reorder compliance
- Inventory vs demand by SKU

![Operations & Logistics](screenshots/operations-logistics.png)

## 💡 Key Business Insights

### Strong profitability
Overall gross margin was approximately **33.2%** on modeled revenue of **$33.4M**.

### Significant seasonality
Revenue peaked in March at approximately **$4.23M** and fell to approximately **$1.39M** in September, representing a roughly **67% decline**.

### Promotions are effective
Units sold averaged approximately **24.9 on promotion days versus 19.5 on non-promotion days**, representing a **27.7% uplift**.

### Forecasting performs well overall
Aggregate forecast accuracy was approximately **88.1%**, with a Weighted MAPE of approximately **11.9%**.

### Major replenishment anomaly
There were **4,787 instances** where inventory fell below the reorder point, but **zero replenishment orders** were recorded, resulting in **0% reorder compliance**.

This should be treated as a potential process or data-integration issue rather than automatically interpreted as a demand problem.

## ⚠️ Data Limitations

The dataset has several limitations:

- `Stockout_Flag` never triggers in the source data.
- There is no promised-delivery-date field.
- There is no received-quantity field.
- Therefore, metrics such as **On-Time Delivery %** and **Order Fill Rate** were not fabricated from unavailable data.
- The analysis represents one calendar year of a simulated dataset, so conclusions should not be generalized beyond this dataset without additional data.

## 🛠️ Tools Used

- Power BI Desktop
- Power Query / M
- DAX
- Star-schema data modeling
- Data visualization
- Business analysis

## 📁 Repository Contents

```text
supply-chain-analytics-powerbi/
│
├── README.md
├── Supply_Chain_Analytics.pbix
│
└── screenshots/
    ├── executive-summary.png
    ├── inventory-analytics.png
    ├── sales-demand.png
    ├── supplier-performance.png
    └── operations-logistics.png
