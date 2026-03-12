# Superstore Sales Analysis

Retail sales analysis of 9,994 transactions across 4 years, built using Microsoft Excel for data modelling and Power BI for executive reporting. The two tools were used intentionally as a pipeline — Excel handles the heavy data work, Power BI presents the findings in a format leadership can actually use.

---

## Project Overview
The dataset covers US retail orders from 2014 to 2017 across three product categories (Furniture, Office Supplies, Technology) and four regions. The goal was to move from raw transactional data to a clean, interactive executive dashboard — the same workflow a junior analyst would run in a corporate finance or operations team.

---

## Excel Workbook
File: SuperstoreData.xlsx

The workbook is structured across four sheets:

- Raw Data — 9,994 rows of transactional data formatted as an Excel Table (SalesData). Three calculated columns were added: Target Margin % (pulled via XLOOKUP), Actual Margin % (Profit ÷ Sales), and a Performance Flag (On Target / Below Target) driven by an IF comparison of the two.
- Product Lookup — A reference table mapping each product category to a target gross margin assumption (Furniture: 18%, Office Supplies: 30%, Technology: 22%). This is the lookup source for XLOOKUP.
- Pivot Analysis — Three pivot tables: regional profitability by category, a monthly sales trend across all four years, and a Top 10 products by profit ranking.
- Dashboard — A dynamic one-page summary connected to the pivot tables via slicers. Changing the year filter updates all visuals simultaneously.

Key Excel Skills Demonstrated

- XLOOKUP for cross-sheet data reconciliation (margin rates by category)
- Structured Table references (SalesData[[#This Row],[Column]])
- YEAR() extraction from date fields
- IF logic for conditional performance classification
- Pivot Tables with slicers for dynamic filtering
- Conditional formatting (red/green) on the Performance Flag column

---

## Power BI Dashboard : ![Executive Summary](Financial_Performance_Dashboard.pdf)
File: Financial_Performance_Dashboard.pdf

Built on the same Superstore dataset. The report has three pages:

- Page 1 — Executive Summary
Five KPI cards: Total Revenue ($2.30M), Profit ($286K), Profit Margin % (12%), YoY Growth % (47%), and Units Sold (37.9K). Supported by a monthly Gross Sales trend line and a Gross Sales by Segment bar chart. Year and State slicers filter the entire page.
- Page 2 — Regional Breakdown
A filled US map showing profit distribution by state, paired with a matrix table breaking down Gross Profit Margin by Segment (Consumer, Corporate, Home Office) per state. Conditional formatting highlights profitable states in green and loss-making states in red — Arizona, Colorado, and Florida are the notable underperformers.
- Page 3 — Product Deep Dive
A ranked bar chart of the top 10 products by profit (Canon imageCLASS leads at ~$25K), alongside a dual-axis chart comparing Gross Sales and Gross Profit side by side across all products. Drill-through is enabled so a product selected on any page links through to this view.

Key Power BI Skills Demonstrated

- Data modelling with a dedicated Date Table built in DAX
- Custom DAX measures: Total Revenue, Total Profit, Profit Margin %, Revenue PY (using SAMEPERIODLASTYEAR), and YoY Growth %
- Time intelligence calculations
- Map visual, matrix with conditional formatting, and drill-through navigation
- Measures table to keep the model organised

---

## Key Findings

- Office Supplies has the highest margin of the three categories despite not being the highest revenue segment — a classic volume vs. profitability trade-off
- Technology drives the most absolute profit at the regional level, led by the West
- The Central region runs at a loss on Furniture — negative profit despite reasonable sales volume, which points to discount depth rather than a demand problem
- California accounts for a disproportionate share of total profit across all three customer segments, making it the single most important state in the dataset


## Tools Used

Microsoft Excel  ·  Power BI Desktop  ·  DAX  ·  Power Query

---

## How to Use

1. Open SuperstoreData.xlsx in Microsoft Excel (2019 or later recommended for XLOOKUP support)
2. Open Financial_Performance_Dashboard.pdf to view the Power BI report export
3. To interact with the live Power BI file, import the dataset into Power BI Desktop and rebuild using the DAX measures documented above
