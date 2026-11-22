# E-commerce Intelligence: Revenue, Customer Behaviour & Profitability Analytics

An end-to-end data analytics portfolio project exploring e-commerce performance through sales, customer behaviour, product profitability, discounting and product returns.

**Tools:** Python | Pandas | NumPy | Matplotlib | Seaborn | Power BI

**Project type:** Exploratory Data Analysis, Business Intelligence and Data Visualisation

---

## 1. Project Overview

E-commerce businesses generate large amounts of transactional data, but raw data alone does not explain why some product categories perform better than others, where profits are generated, or what drives product returns.

This project analyses a multi-table e-commerce dataset to investigate business performance and translate data into actionable insights.

The analysis focuses on five key areas:

- Revenue and sales performance
- Customer behaviour and acquisition
- Product and category performance
- Gross profitability and discounting
- Product returns and refund exposure

The objective is to move beyond descriptive statistics and develop business-oriented recommendations that can support more informed decisions.

## 2. Business Problem

An e-commerce business wants to grow revenue and profitability while reducing product returns and improving customer performance.

However, management needs answers to questions such as:

- Which product categories generate the highest revenue?
- Which categories contribute the most gross profit?
- Are high-revenue categories necessarily the most profitable?
- Which products and brands contribute most to sales?
- Which countries and sales channels generate revenue?
- What are the most common reasons for product returns?
- Which product categories experience the highest return rates?
- How does gross margin vary across discount levels?
- Which customer acquisition channels bring in the largest customer base?

This project addresses these questions using Python-based analysis and an interactive Power BI dashboard.

## 3. Dataset

**Source:** [Prime Levels Global E-commerce Orders & Returns Dataset](https://prime-levels.com/data-hub/global-ecommerce-orders-returns-2024-2026)

The dataset contains five interconnected CSV files:

| Dataset | Records | Description |
|---|---:|---|
| Customers | 3,000 | Customer information and acquisition details |
| Products | 345 | Product catalogue, brands, categories and pricing |
| Orders | 14,000 | Order-level transactions and status information |
| Order Items | 29,671 | Individual products purchased within orders |
| Returns | 2,433 | Returned items, refund amounts and return reasons |

**Total records analysed:** 49,449

The transaction data inspected in the audit contains order dates from January 2024 to March 2025.

**Important:** The dataset is synthetic and is used for analytical and educational purposes. Findings should not be interpreted as actual performance of a real company.

## 4. Tools and Technologies

| Tool | Application |
|---|---|
| Python | Data analysis and manipulation |
| Pandas | Data cleaning, transformation and aggregation |
| NumPy | Numerical operations |
| Matplotlib | Data visualisation |
| Seaborn | Statistical visualisation |
| Power BI | Interactive dashboard development |
| SQL / MySQL | Planned extension to the project |

## 5. Project Workflow

### Phase 1 — Business Understanding
- Defined the business problem.
- Identified key performance indicators.
- Developed business questions to guide the analysis.

### Phase 2 — Data Acquisition
- Obtained five related CSV datasets.
- Examined the structure and relationships between tables.

### Phase 3 — Data Auditing
- Checked dataset dimensions and data types.
- Examined missing values.
- Checked duplicate records and unique identifiers.
- Validated primary and foreign key relationships.

### Phase 4 — Data Cleaning and Preparation
- Converted date columns into appropriate datetime formats.
- Standardised boolean fields.
- Investigated missing values and their causes.
- Preserved structurally meaningful missing values.
- Prepared cleaned datasets for analysis.

### Phase 5 — Exploratory Data Analysis
Analysed revenue, orders, customers, products, categories, gross profit, margins, discounts and returns using Python.

### Phase 6 — Business Intelligence
Developed a three-page Power BI dashboard to present key performance indicators and business insights.

### Phase 7 — Business Recommendations
Translated analytical findings into recommendations for improving profitable growth and reducing return exposure.

## 6. Key Findings

### Revenue and Profitability

- Delivered revenue: **$6,109,150.81**
- Delivered orders: **12,030**
- Units sold: **35,994**
- Average order value: **$507.82**
- Delivered gross profit: **$2,080,056.63**
- Overall gross margin: **approximately 34.05%**

Electronics was the largest contributor to delivered revenue and absolute gross profit.

Beauty generated the highest category gross margin in the analysis, while Apparel showed a relatively high gross margin alongside substantial return exposure.

### Product Returns

- Returned units: **2,882**
- Return rate: **approximately 8.01%**
- Refund amount: **$410,427.05**

Apparel had the highest category return rate at approximately **15.34%**.

The two leading return reasons were:

- Wrong size / fit: 29.08%
- Not as described: 19.88%

Together, these accounted for approximately 48.96% of returned units.

### Customer Behaviour

Regular and Frequent customers represented approximately 58.03% of purchasers and contributed approximately 76.22% of delivered revenue.

This indicates that repeat and frequent customers represent an important revenue segment.

### Discounting and Margins

The analysis examined gross margin across discount levels. Higher discount bands showed a relationship with lower margins in the earlier analysis.

This is an observational relationship and does not establish that discounting alone caused the reduction.

## 7. Power BI Dashboard

The final report is organised into three pages.

### Page 1 — Executive Overview
Provides a high-level view of business performance through revenue, orders, units sold, gross profit, gross margin and average order value, along with category comparisons and monthly revenue trends.

### Page 2 — Sales & Customer Intelligence
Explores geographical performance, sales channels, monthly order trends, top products, brand revenue and customer acquisition mix.

### Page 3 — Returns, Profitability & Pricing
Investigates category return rates, return reasons, refund amounts, gross margin across discount levels and gross profit by category.

## 8. Business Recommendations

Based on the analysis:

1. **Review Apparel returns:** Investigate sizing information, product descriptions and fit guidance to address the high return rate.
2. **Improve product descriptions:** Focus on products associated with the 'Not as described' return reason.
3. **Protect Electronics margins:** Continue monitoring costs, pricing and product-level profitability because Electronics generates the largest absolute gross profit.
4. **Use targeted discounting:** Evaluate discount levels against gross margin instead of relying exclusively on revenue growth.
5. **Retain valuable customers:** Develop retention initiatives for Regular and Frequent customers.
6. **Monitor return-adjusted performance:** Evaluate revenue and gross profit alongside refunds to obtain a more complete picture of performance.

## 9. Limitations

- The dataset is synthetic.
- Gross profit is based on the available product-level cost and sales information and excludes unprovided operating expenses.
- Refund-adjusted gross profit is a useful analytical proxy, not audited net profit.
- Marketing expenditure is unavailable, so customer acquisition cost and acquisition ROI cannot be calculated.
- Inventory history is unavailable, so stockout and inventory optimisation conclusions cannot be established.
- Discount relationships are observational, not causal.
- Findings depend on the definitions and coverage of the supplied dataset.

## 10. Repository Structure

```text
E-commerce-Intelligence-Analytics/
│
├── 01_Data/
│   ├── Original_Data/
│   └── Cleaned_Data/
│
├── 02_Python_Analysis/
│   ├── 01_Data_Audit.ipynb
│
├── 03_PowerBI/
│   └── Ecommerce_Intelligence_Dashboard.pbix
│
├── 04_Dashboard_Screenshots/
│   ├── Executive_Overview.png
│   ├── Sales_Customer_Intelligence.png
│   └── Returns_Profitability_Pricing.png
│
├── 05_Documentation/
│   └── Project_Documentation.md
│
└── README.md
```


## 11. Project Status

Python-based data auditing, cleaning and exploratory analysis have been completed, and the three-page Power BI dashboard has been developed.


---

**Author:** Aashmeet Kaur
**Project:** E-commerce Intelligence Analytics

