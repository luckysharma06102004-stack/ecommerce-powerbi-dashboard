
# E-Commerce Sales Analysis using Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-green?style=for-the-badge)
![Internship](https://img.shields.io/badge/MS%20Elevate-AICTE%20Internship-blue?style=for-the-badge)

## Project Overview

An interactive Power BI dashboard built to analyse e-commerce sales data from platforms like **Flipkart**, **Amazon**, and **Meesho**. The dashboard consolidates over 1,00,000+ order records and provides actionable business insights through interactive visualisations.

---

## Problem Statement

The Indian e-commerce industry generates millions of transactions daily but businesses struggle to derive timely insights from raw data. Decision-makers face challenges in identifying top-selling categories, understanding regional trends, tracking delivery performance, and monitoring return rates. This project addresses that gap with a unified Power BI dashboard.

---

## Dashboard Preview

![Dashboard Preview](dashboard_screenshot.png)

---

## Key Insights

| Metric | Value |
|---|---|
| Total Revenue | ₹48.6 Crore (FY 2022–23) |
| Total Orders | 1,02,340 |
| Top Category | Electronics (32% of revenue) |
| Highest Return Rate | Fashion (14.7%) |
| Avg Delivery Time | 4.2 days |
| Peak Sales Period | October–November (Diwali) — 3.2x spike |
| Top States | Maharashtra, Karnataka, Delhi (45% of orders) |

---

## Dashboard Pages

1. **Overview** — KPI cards, monthly revenue trend, category split
2. **Category Analysis** — Revenue and return rate by product category
3. **Regional Map** — State-wise order distribution across India
4. **Delivery Performance** — Average delivery days by region and platform

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Power BI Desktop | Dashboard development |
| Power Query (M Language) | Data cleaning and transformation |
| DAX | KPI measures and time intelligence |
| CSV Dataset | Source data (Kaggle e-commerce dataset) |
| Star Schema | Data modelling |

---

## DAX Measures Used

```dax
-- Total Revenue
Total Revenue = SUMX(Orders, Orders[Quantity] * Orders[Unit Price])

-- Month-over-Month Growth
MoM Growth = 
DIVIDE(
    [Current Month Revenue] - [Prev Month Revenue],
    [Prev Month Revenue]
)

-- Return Rate
Return Rate % = 
DIVIDE(
    COUNTROWS(FILTER(Orders, Orders[Status] = "Returned")),
    COUNTROWS(Orders)
) * 100

-- Average Delivery Days
Avg Delivery Days = 
AVERAGEX(Orders, DATEDIFF(Orders[Order Date], Orders[Delivery Date], DAY))
```

---

## Data Model

```
ORDERS (Fact Table)
    ├── Products (Dimension)
    ├── Customers (Dimension)
    ├── Calendar (Dimension)
    └── Region (Dimension)
```

---

## Project Report

The full project report (PPT converted to PDF) is included in this repository.

📄 [View Project Report (PDF)](ecommerce_powerbi_project.pdf)

---

## References

1. Microsoft Corporation. (2024). Power BI Documentation. https://learn.microsoft.com/en-us/power-bi/
2. Kaggle Inc. (2023). E-Commerce Sales Dataset. [https://www.kaggle.com/datasets/ecommerce-sales-data](https://www.kaggle.com/datasets/thedevastator/unlock-profits-with-e-commerce-sales-data)
3. Ferrari, A., & Russo, M. (2019). The Definitive Guide to DAX. Microsoft Press.
4. NASSCOM. (2023). Indian E-Commerce Industry Report.
5. Kimball, R., & Ross, M. (2013). The Data Warehouse Toolkit. Wiley.

---

## Internship Details

- **Program:** Microsoft Elevate — AICTE Internship (Feb 2026)
- **Topic:** E-Commerce Sales Analysis using Power BI
- **Submitted by:** Lucky Sharma
- **Institution:** Kalinga Institute of Industrial Technology
- **Department:** Computer Science & Engineering

---

*Built as part of the MS Elevate AICTE Internship Program, February 2026.*
