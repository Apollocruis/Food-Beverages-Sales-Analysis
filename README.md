# Food-Beverages-Sales-Analysis
End-to-end sales analysis of a food and beverages business in Power BI. Tracks 17.9M revenue and 53K orders across product groups, sales channels, salespeople and seasonality, and turns the findings into actionable recommendations.

# Food and Beverages Sales Dashboard

An interactive **Power BI** dashboard that analyzes food and beverage sales across products, sales channels, salespeople and time. This README documents the dashboard's structure, key findings and recommended next steps.

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/status-complete-brightgreen)
![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-F2C811?logo=powerbi&logoColor=black)
---

## Table of Contents

- [Overview](#overview)
- [Dashboard Preview](#dashboard-preview)
- [Headline KPIs](#headline-kpis)
- [Dashboard Components](#dashboard-components)
- [Data Model](#data-model)
- [Tools Used](#tools-used)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)

---

## Overview

The dashboard gives a single-page view of sales performance and answers four core business questions:

| Question | Dimension | Visual |
|---|---|---|
| **What** is selling? | Product group and category | Top 10 product groups, category donut |
| **Who** is selling it? | Salesperson | Top 5 salespeople |
| **Where** is it selling? | Channel | Revenue by channel |
| **When** is it selling? | Month and quarter | Monthly and quarterly trends |

Two slicers (**Product Category** and **Channel**) filter every visual on the page.

## Dashboard Preview

![Dashboard](https://github.com/Apollocruis/Food-Beverages-Sales-Analysis/commit/3db5d3fdf49c726eca5a50a030adc73d0a3c7682

)

## Headline KPIs

| Metric | Value |
|---|---|
| **Total Revenue** | 17.91M |
| **Total Orders** | 53K |
| **ATP** (average transaction price) | 340.73 |
| **Total Items Sold** | ~6M |

## Dashboard Components

| Visual | Type | Purpose |
|---|---|---|
| KPI cards (x4) | Card | Total Revenue, Total Orders, ATP, Total Items Sold |
| Top 10 product group sales | Bar chart | Revenue by product group (Top N filter = 10) |
| Order by product category | Donut chart | Order split between Food and Drink |
| Total Revenue by Channel | Pie chart | Revenue share by sales channel |
| Top 5 Salesperson | Combo chart | Revenue (columns) and orders (line) per salesperson |
| Quarterly Revenue and Order | Combo chart | Revenue and orders by quarter |
| Monthly distribution of Revenue and Order | Stacked column and line | Revenue and orders by month |
| Slicers (x2) | Slicer | Product Category, Channel |

## Data Model

Three tables:

- **Sales** – transactional data (Salesperson, Channel, orders, revenue, items)
- **Product** – ProductGroup and ProductCategory
- **dateTable** – calendar table providing month and quarter

**DAX measures used:** `Total Revenue`, `Total order`, `ATP`, `Total item sold`.
## Tools Used

| Tool | Purpose |
|---|---|
| ![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoftexcel&logoColor=white) | Source data storage and initial review |
| ![Power Query](https://img.shields.io/badge/Power%20Query-F2C811?logo=powerbi&logoColor=black) | Data cleaning, transformation and loading (ETL) |
| ![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black) | Data modeling, DAX measures and dashboard design |

**Workflow:** Excel (raw data) → Power Query (clean and shape) → Power BI (model, measure, visualize)

## Key Insights

> Figures are taken from the dashboard's rounded labels, so derived values (shares, per-order amounts) are approximate.

### Products

- **Wheat Flour is the anchor product at 4.5M**, about 25% of revenue. Together with Oil (2.9M) and Yeasts (2.2M), the top three groups bring in about 9.6M, over half of total revenue.
- **The top 10 groups account for about 15.9M (~89% of revenue).** The business depends on a small product range.
- **Flour-type products (Wheat Flour, Flour, Manioc Flour) total about 7.1M (~40%)**, a notable exposure to one raw-material family.
- **Drinks are a small share:** 5K orders (9.8%) versus 47K for Food (90.2%). Liquor (1.1M) is the only drink-type group in the top 10.

| Rank | Product Group | Revenue |
|---|---|---|
| 1 | Wheat Flour | 4.5M |
| 2 | Oil | 2.9M |
| 3 | Yeasts | 2.2M |
| 4 | Flour | 1.7M |
| 5 | Liquor | 1.1M |
| 6 | Candy | 0.9M |
| 7 | Manioc Flour | 0.9M |
| 8 | Spices | 0.7M |
| 9 | Sugar | 0.5M |
| 10 | Popcorn | 0.5M |

### Channels

| Channel | Share of Revenue | Approx. Revenue |
|---|---|---|
| Retail | 48.56% | ~8.7M |
| Distributor | 34.05% | ~6.1M |
| Online | 17.39% | ~3.1M |

Retail and Distributor together drive over 80% of revenue. Online is the smallest channel but already a meaningful share.

### Order Profile

- Revenue per order is about **340**, with roughly **110 items per order**. This points to bulk or wholesale-style transactions.
- Revenue per item is about **3**, so this is a high-volume, low-unit-price business where order size drives results.

### Salespeople (Top 5)

| Salesperson | Revenue | Orders | Revenue per Order (approx.) |
|---|---|---|---|
| Carla Ferreira | 4.7M | 9.6K | ~490 |
| Julio Lima | 3.3M | 5.9K | ~559 |
| Gustavo Gomes | 2.4M | 10.0K | ~240 |
| Felipe Goncalves | 1.7M | 6.3K | ~270 |
| Leonardo Cardoso | 1.6M | 6.8K | ~235 |

- **Carla leads on revenue (4.7M)**, nearly 3x Leonardo (1.6M).
- **Julio has the highest value per order (~559)** with the fewest orders.
- **Gustavo handles the most orders (10.0K)** but ranks third on revenue because his orders are less than half the size of Carla's or Julio's.
- The top 5 account for about 13.7M (~76% of revenue) but only about 38.6K of 53K orders, so other salespeople make up the remainder.

### Seasonality

- The quarterly chart is sorted by revenue and ranks **Q4 highest, then Q3, Q2, with Q1 lowest**, so revenue builds through the year.
- Monthly revenue labels range from **0.97M to 1.89M** (average about 1.5M per month). Monthly order counts swing from about **2.7K to 6.1K**.
- Orders and revenue do not move in lockstep, which suggests order size varies considerably month to month.

## Recommendations

1. **Reduce product concentration risk.** Protect supply and pricing for Wheat Flour, Oil and Yeasts, and grow mid-tier groups (Candy, Spices, Sugar, Popcorn) through bundling and cross-selling.
2. **Grow the Drinks category.** At under 10% of orders it is the clearest expansion area. Review margins before investing, as the dashboard has no profitability data.
3. **Lift order value for Gustavo, Felipe and Leonardo.** Use the approaches of Carla and Julio as a coaching playbook. First check whether territory or customer mix explains the gap.
4. **Make more of Distributor and Online.** Formalize key-account management and volume terms for Distributor (a third of revenue). Test targeted promotions or minimum-order incentives for Online.
5. **Plan for the Q4 peak and Q1 low.** Align inventory and staffing, and investigate the causes of monthly order swings (promotions, large one-off orders, supply constraints) so they can be forecast.
6. **Fix uncategorized records.** Clean up orders without a product category at the source instead of filtering them out, and add a reconciliation check so card totals match chart totals.
