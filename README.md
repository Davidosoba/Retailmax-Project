# RetailMax Group Ltd. — Revenue Intelligence & Customer Profitability Optimisation

**Amdari Work Experience Programme | Data Analytics Project | June–July 2026**

---
![Project Status](https://img.shields.io/badge/Status-Completed-green)
![Programme](https://img.shields.io/badge/Programme-Amdari%20Work%20Experience-brown)
![Tools](https://img.shields.io/badge/Tools-Excel%20%7C%20Power%20BI%20%7C%20Power%20Point-darkred)

##  Table of Content

-  [Project Overview](#Project-Overview)
-  [Business Objectives](#Business-Objectives)
-  [Dataset](#Dataset)
-  [Tools & Technologies](#Tools-&-Technologies)
-  [Project Workflow](#Project-Workflow)
-  [Data Preparation Highlights](#Data-Preparation-Highlights)
-  [Data Model](#Data-Model)
-  [DAX Measures Deployed](#DAX-Measures-Deployed)
-  [Dashboard Structure](#Dashboard-Structure)
-  [Key Findings](#Key-Findings)
-  [Strategic Recommendations](#Strategic-Recommendations)
-  [Scope Limitations](#Scope-Limitations)
-  [Repository Structure](#Repository-Structure)
-  [Author](#Author)

  ---
  
## Project Overview

RetailMax Group Ltd. is a UK-based mid-market retail and consumer goods company operating 165 physical stores alongside e-commerce and marketplace channels. Despite strong sales performance, the business lacked a centralised analytical framework for understanding customer profitability, pricing effectiveness, channel performance, and revenue trends.

This project delivers a full end-to-end business intelligence solution — from raw data through to a four-page interactive Power BI dashboard, strategic insights, and actionable recommendations — to support data-driven executive decision-making at RetailMax.

---

## Business Objectives

Five analytical objectives were defined for this project:

1. **Revenue Performance Analytics** — Total revenue, gross profit, growth rates and category contributions
2. **Customer Intelligence & Segmentation** — Customer lifetime value, retention, repeat purchase behaviour and segment profitability
3. **Sales Channel Performance** — Online, Store and Marketplace comparison across revenue, profit and transaction volume
4. **Pricing & Discount Effectiveness** — Discount utilisation, revenue leakage and margin impact
5. **Executive Decision Intelligence** — Interactive Power BI dashboard for ongoing strategic monitoring

---

## Dataset

| Table | Rows | Role |
|---|---|---|
| Sales Transactions | 50,000 | Fact Table |
| Customers | 5,000 | Dimension |
| Products | 1,000 | Dimension |
| Stores | 50 | Dimension |

**Date Range:** January 2023 – December 2025

> **Note:** This project was completed as part of the Amdari Work Experience Programme.

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Excel | Data cleaning, feature engineering, date conversion |
| Power BI Desktop | Data modelling (star schema), DAX measures, dashboard |
| DAX | KPI development — revenue, profit, retention, discount metrics |
| Microsoft Word | Business intelligence report |
| Microsoft PowerPoint | Executive presentation |

---

## Project Workflow

The project followed a structured ten-step analytical methodology:

1. Business Understanding & Requirements Definition
2. Data Collection and Validation
3. Data Quality Assessment & Cleaning
4. Data Preparation & Feature Engineering
5. Data Integration & Model Preparation (Star Schema)
6. KPI Development (DAX Measures)
7. Revenue, Profitability & Pricing Analysis
8. Dashboard Development & Visualisation
9. Business Insights & Strategic Recommendations
10. Final Reporting & Project Delivery

---

## Data Preparation Highlights

The following cleaning and preparation steps were applied in Excel before loading into Power BI:

- **Date conversion:** `Date_ID` (integer format `YYYYMMDD`) converted to proper date using `=DATE(LEFT(), MID(), RIGHT())` formula
- **Null handling:** 1,268 missing Customer Region values replaced with `"Unknown"` category
- **Transaction flag:** `Transaction_Completed` column added (`Yes`/`No`) to filter completed transactions from Returned/Cancelled orders
- **Time dimensions:** `Year`, `Month`, and `Quarter` columns extracted from `Transaction_Date`
- **Gender standardisation:** Inconsistent values (`M`, `F`, `male`, `female`) standardised to `Male`/`Female` via Power Query
- **Referential integrity:** 304 transactions referencing unmatched Product IDs (1001–1010) resolved via Left Outer Join — labelled `"Unknown Product"`

---

## Data Model

A **star schema** was implemented in Power BI Desktop:

```
Date Table ──────────────────────────────────────┐
                                                  │
Customers (1) ──────────────── (*)                │
Products  (1) ──────────────── (*) Sales Transactions (Fact) ──── (*) (1) Stores
Date Table (1) ─────────────── (*)                │
                                                  ┘
```

A dedicated **Date Table** was created using `CALENDAR(DATE(2023,1,1), DATE(2025,12,31))` and marked as the official date table to enable Power BI time intelligence functions.

---

## DAX Measures Developed

| Category | Measures |
|---|---|
| Revenue Performance | Total Revenue, Total Cost, Gross Profit, Gross Profit Margin %, Previous Year Revenue, Revenue Growth Rate, Revenue Contribution % |
| Transaction Analysis | Completed Transactions, Average Transaction Value |
| Customer Intelligence | Total Customers, Retained Customers, Customer Retention Rate %, Avg Purchases Per Customer, Avg Revenue Per Customer |
| Pricing & Discount | Discount Utilization, Discount Utilization Rate %, Discounted Gross Profit, Non-Discounted Gross Profit, Revenue Leakage |
| Channel Analysis | Online Total Revenue, Marketplace Total Revenue, Store Total Revenue |

Full DAX syntax for all measures is documented in `reports/RetailMax_DAX_Measures_Library.docx`.

---

## Dashboard Structure

The Power BI dashboard consists of four pages:

| Page | Focus |
|---|---|
| Executive Overview | Headline KPIs, revenue trend, category performance, transaction health |
| Revenue Performance & Pricing | Monthly trends, category revenue contribution, discount analysis, leakage |
| Customer Intelligence | Retention, segmentation, loyalty, gender and regional distribution |
| Sales Channel Performance | Channel revenue and profit comparison, store-level profitability, regional breakdown |

---

## Key Findings

1. **Revenue Leakage Crisis** — Revenue leakage of £9.43M from discounting nearly equals total gross profit of £9.38M. RetailMax is discounting away the equivalent of its entire profit margin.

2. **Near-Universal Discounting** — 98.71% of completed transactions include a discount. Only 1.29% of sales occur at full price, generating just £229.89K gross profit versus £9.15M from discounted transactions.

3. **Online Channel Dominance** — The Online channel contributes 50.11% of total revenue and processes approximately double the transactions of Store or Marketplace individually.

4. **Strong Customer Retention** — 84.18% of customers have made 2 or more completed purchases, with an average of 3.38 purchases per customer.

5. **Flat Revenue Growth** — Year-on-year revenue growth of 0.19% (2024) and 1.54% (2025) is minimal, likely suppressed by the aggressive discounting strategy.

6. **Balanced Category Performance** — All four product categories show near-identical revenue contributions (23–27%), suggesting an undifferentiated product and pricing strategy.

---

## Strategic Recommendations

| # | Recommendation | Projected Impact |
|---|---|---|
| 1 | Restructure discounting strategy — tiered discounts for loyalty members only, cap general discounts at 5–8% | Recover ~£2.8M gross profit annually (30% margin improvement) |
| 2 | Prioritise Online channel investment — digital marketing, UX optimisation, personalisation | +£925K revenue from 5% conversion rate improvement |
| 3 | Leverage retained customers for higher purchase frequency via loyalty milestone rewards | +£3.7M revenue by increasing avg purchases from 3.38 to 4.0 |
| 4 | Resolve data quality gaps — missing regions and unmatched Product IDs | Improved targeting precision and category reporting accuracy |
| 5 | Implement category-differentiated pricing — premium positioning for Electronics and Home Appliances | +£585K–£1.13M gross profit from 3% margin improvement in top categories |

---

## Scope Limitations

- **Net Profit excluded** — Operating expense data was unavailable. Gross Profit is the most complete profitability metric in this analysis.
- **25% missing Customer Region data** — Labelled `"Unknown"` throughout. Regional analysis should be interpreted with this in mind.
- **1.15% unmatched Product IDs** — 304 transactions reference Product IDs not present in the Products table. Labelled `"Unknown Product"` and included in all financial totals.
- **Synthetic dataset** — All data is computer-generated for training purposes. Findings demonstrate analytical methodology, not real business performance.

---

## Repository Structure

```
retailmax-bi-project/
│
├── README.md
├── data/
│   ├── Sales_Transaction_Table_Cleaned.xlsx
│   ├── Customer_Table_Cleaned.xlsx
│   ├── Produt_Table.xlsx
│   └── Store_Table.xlsx
├── dashboard/
│   └── RetailMax_Dashboard.pbix
└── reports/
    ├── RetailMax_Presentation.pptx
    ├── RetailMax_Business_Intelligence_Report.docx
    ├── RetailMax_DAX_Measures_Library.docx
    ├── RetailMax_Dashboard_Blueprint.docx
    └── RetailMax_Business_Scope_and_Objectives.docx
```

---

## Author

**David**
Data Analytics | Amdari Work Experience Programme
Tools: Excel · Power BI · DAX · SQL · PostgreSQL · GitHub

---

*This project was completed as part of the Amdari Work Experience Programme.*
