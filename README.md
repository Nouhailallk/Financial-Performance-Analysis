# Financial Performance Analysis & Forecasting Dashboard

**Business Intelligence Project | Datheon Internship | Microsoft Power BI**

An end-to-end Business Intelligence project developed in the context of the Datheon internship, focused on analyzing corporate financial performance, identifying profitability drivers, and evaluating hypothetical business scenarios using Microsoft Power BI.

---

## 1. Business Context

Organizations need visibility into their financial performance to understand revenue generation, cost structures, and profitability across different business dimensions.

However, looking at revenue alone does not provide a complete picture of business performance. High sales do not necessarily translate into high profitability when discounts and manufacturing costs are significant.

This project addresses that challenge by developing an interactive financial performance dashboard that consolidates key financial indicators and enables users to explore profitability across products, countries, and business segments.

It also introduces What-If scenario analysis to evaluate how changes in sales, discounts, and manufacturing costs could affect financial results.

## 2. Project Objectives

The main objectives are to:

- Monitor gross sales, discounts, net sales, COGS, and profit.
- Understand revenue erosion through discounts and manufacturing costs.
- Analyze quarterly sales and profitability trends.
- Identify the most significant geographical and business-segment contributors.
- Evaluate product-level profitability and manufacturing costs.
- Calculate profitability ratios and financial KPIs.
- Build an interactive scenario analysis model to assess the impact of changing financial assumptions.
- Present findings through an interactive and user-friendly Power BI dashboard.

## 3. Dataset

**Source:** Microsoft Financial Sample Dataset

The dataset contains financial information across several business dimensions.

### Key attributes

| Category | Fields |
|---|---|
| Business dimensions | Segment, Country, Product |
| Sales information | Gross Sales, Discounts, Sales |
| Cost information | COGS, Manufacturing Price |
| Profitability | Profit |
| Operational information | Units Sold, Discount Band |
| Time dimension | Date |

The dataset supports financial analysis across products, geographical markets, business segments, and time periods.

## 4. Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Power BI | Data visualization and interactive reporting |
| Power Query | Data preparation and transformation |
| DAX | Financial calculations and analytical measures |
| Power BI Data Model | Data organization and relationship management |
| Excel | Source data |

## 5. Data Preparation & Modelling

### Data Preparation

Power Query was used as the data preparation environment to organize the source data for reporting.

The preparation workflow focused on ensuring that the financial dataset and date information could support consistent analysis.

### Data Modelling

A dedicated data model was developed to support the dashboard's analytical requirements.

The model includes:

- **Financials:** Main financial fact table containing sales, discounts, COGS, profit, and business dimensions.
- **Dim Date:** Dedicated date dimension supporting year, quarter, and monthly analysis.

The date dimension is connected to the financial fact table through the Date field, enabling time-based filtering and analysis.

### Data Model View

<img width="886" height="440" alt="image" src="https://github.com/user-attachments/assets/4fbae63c-aebc-40a1-91cc-4e626140fcb2" />


*The model view illustrates the relationship between the financial fact table and the date dimension.*

## 6. Key Performance Indicators (KPIs)

The dashboard uses DAX measures to calculate and monitor the following financial indicators.

| KPI | Business Purpose |
|---|---|
| Gross Sales | Total sales before discounts |
| Total Discounts | Total discount amount |
| Net Sales | Revenue after discounts |
| Total COGS | Total cost of goods sold |
| Total Profit | Profit generated after COGS |
| Gross Profit Margin | Profit as a percentage of net sales |
| COGS Ratio | Proportion of net sales consumed by COGS |
| Segment Margin | Profitability ratio evaluated by business segment |

### Core DAX Measures

```dax
Gross Sales =
SUM(Financials[Gross Sales])

Total Discounts =
SUM(Financials[Discounts])

Net Sales =
SUM(Financials[Sales])

Total COGS =
SUM(Financials[COGS])

Total Profit =
SUM(Financials[Profit])

Gross Profit % =
DIVIDE([Total Profit], [Net Sales], 0)

COGS Ratio =
DIVIDE([Total COGS], [Net Sales], 0)

Segment Margin =
DIVIDE([Total Profit], [Net Sales], 0)
```

*Segment Margin uses the current segment filter context to calculate profitability for each segment.*

## 7. Dashboard Overview

The dashboard is organized into three main analytical areas:

### Financial Performance Monitoring

- Gross Sales, Discounts, Net Sales, COGS, and Profit KPIs.
- Gross Profit Margin and COGS Ratio.
- Quarterly Sales & Profit Trend.
- Revenue Erosion Waterfall.

### Business Performance Analysis

- Net Sales by Country.
- Net Sales by Segment.
- Profit by Product (Top 5).
- Segment Margin Analysis.
- Manufacturing Cost Analysis (COGS).

### Interactive Scenario Forecasting

Three What-If parameters allow users to adjust:

- Sales Growth
- Discount Change
- Manufacturing Cost Change

The scenario model dynamically recalculates:

- Forecast Net Sales
- Forecast COGS
- Forecast Gross Profit
- Forecast Gross Profit %

The report also includes interactive filters for Quarter, Country, Segment, and Product.

### Dashboard Preview

<img width="774" height="436" alt="image" src="https://github.com/user-attachments/assets/a1c5bdc6-991e-41d9-a696-6004d7d271f2" />


## 8. Key Business Insights

The following findings are based on the financial results displayed in the dashboard.

### 8.1 Overall Financial Performance

| Indicator | Result |
|---|---:|
| Gross Sales | 127.93M |
| Total Discounts | 9.21M |
| Net Sales | 118.73M |
| Total COGS | 101.83M |
| Total Profit | 16.89M |
| Gross Profit Margin | 14.23% |
| COGS Ratio | 85.77% |

**Finding:**

The COGS ratio of 85.77% indicates that a substantial proportion of net sales is consumed by the cost of goods sold.

This leaves a profit margin of approximately 14.23%, highlighting the importance of monitoring manufacturing costs and improving cost efficiency.

### 8.2 Segment Profitability Analysis

The segment analysis reveals significant differences in profitability.

| Segment | Net Sales | Total Profit | Margin |
|---|---:|---:|---:|
| Government | 52.50M | 11.39M | 21.69% |
| Small Business | 42.43M | 4.14M | 9.77% |
| Enterprise | 19.61M | -0.61M | -3.13% |
| Midmarket | 2.38M | 0.66M | 27.71% |
| Channel Partners | 1.80M | 1.32M | 73.13% |

**Key findings:**

- Government is the largest revenue contributor, generating approximately 52.50M in net sales and 11.39M in profit.
- Small Business generates substantial revenue but has a relatively low profit margin of 9.77%.
- Enterprise operates at a negative margin of -3.13%, indicating that its reported COGS exceeds its net sales.
- Channel Partners records the highest margin at 73.13%, although its revenue contribution is comparatively small.
- Midmarket achieves a 27.71% margin on a relatively small revenue base.

### 8.3 Geographical Performance

The country analysis identifies the United States and Canada among the leading contributors to net sales, followed by France, Germany, and Mexico.

The geographical breakdown provides a basis for comparing market contributions and identifying opportunities for further investigation.

### 8.4 Product Performance

The Top 5 product analysis highlights the products generating the highest profit.

Paseo leads the displayed ranking, followed by VTT, Amarilla, Velo, and Montana.

This helps identify important contributors to overall product profitability.

### 8.5 Manufacturing Cost Analysis

The manufacturing cost analysis compares quarterly COGS with the COGS ratio.

The analysis helps identify how manufacturing costs evolve over time and how their relationship with net sales affects profitability.

## 9. Business Recommendations

Based on the findings, the following actions are recommended for further business investigation.

| Finding | Recommendation |
|---|---|
| High overall COGS ratio | Investigate manufacturing costs, procurement efficiency, and product-level cost drivers. |
| Negative Enterprise margin | Conduct a detailed review of Enterprise pricing, discounting, and cost allocation. |
| Low Small Business margin | Evaluate opportunities to improve pricing and reduce costs while maintaining sales volume. |
| Strong Government profitability | Analyze the factors behind its profitability and assess opportunities to maintain and grow this performance. |
| High Channel Partners margin | Investigate whether the profitability drivers can be replicated in other segments, while considering its smaller revenue base. |
| Differences in product profitability | Prioritize further analysis of product-level costs and profit contributions. |

These recommendations are analytical proposals based on the observed results; they are not confirmed operational causes.

## 10. What-If Scenario Analysis

An interactive scenario model was developed to explore the sensitivity of financial performance to changes in three key business assumptions.

### Scenario Parameters

| Parameter | Description |
|---|---|
| Sales Growth | Adjusts gross sales by a user-defined percentage |
| Discount Change | Adjusts the total discount amount |
| Manufacturing Cost Change | Adjusts COGS |

### Calculation Logic

The scenario model follows this financial logic:

1. Forecast Gross Sales = Actual Gross Sales × (1 + Sales Growth)
2. Forecast Discounts = Actual Discounts × (1 + Discount Change)
3. Forecast Net Sales = Forecast Gross Sales − Forecast Discounts
4. Forecast COGS = Actual COGS × (1 + Manufacturing Cost Change)
5. Forecast Gross Profit = Forecast Net Sales − Forecast COGS
6. Forecast Gross Profit % = Forecast Gross Profit / Forecast Net Sales

Users can modify the assumptions through interactive sliders and immediately observe the impact on forecast financial indicators.

**Important:** This is a What-If sensitivity analysis based on user-defined assumptions. It is not a statistical forecasting model and does not account for factors such as price elasticity, product mix changes, or external economic conditions.

## 11. Project Limitations

The analysis is subject to the limitations of the available dataset:

- No budget or target values are available for an actual-versus-budget comparison.
- No dedicated manufacturing cost-center information is available.
- Scenario analysis applies percentage changes uniformly to the selected financial measures.
- The scenario model does not incorporate statistical forecasting, market demand, or price elasticity.
- Findings reflect the available dataset and should not be interpreted as a complete assessment of a real company's operations.

## 12. Conclusion

This project demonstrates how financial data can be transformed into an interactive Business Intelligence solution.

By combining data preparation, dimensional modelling, DAX calculations, financial KPIs, and What-If scenario analysis, the dashboard provides a structured view of financial performance and profitability drivers.

It also demonstrates how analytical findings can support further business investigation and more informed financial decision-making.

---

## 13. Repository Structure

```text
Financial-Performance-Analysis/
│
├── Financial_Performance_Dashboard.pbix
│
├── README.md
│
├── Screenshots/
│   ├── dashboard_overview.png
│   └── data_model.png
│
└── Dataset/
    └── Financial_Sample.xlsx
```

## 14. Project Context

**Developed as part of the Datheon internship.**

**Technologies:** Microsoft Power BI | DAX | Power Query | Excel

