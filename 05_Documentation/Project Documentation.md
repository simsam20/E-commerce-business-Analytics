# Project Documentation
## E-commerce Intelligence: Revenue, Customer Behaviour & Profitability Analytics

**Project Domain:** E-commerce / Retail Analytics

**Project Type:** End-to-End Data Analytics and Business Intelligence

**Tools Used:** Python, Pandas, NumPy, Matplotlib, Seaborn and Power BI

**Dataset:** Prime Levels Global E-commerce Orders & Returns Dataset

---

# 1. Executive Summary

This project analyses e-commerce transactional data to understand business performance across revenue generation, customer behaviour, product profitability, discounting and product returns.

The project uses five interconnected datasets covering customers, products, orders, order items and returns.

The analytical process began with data auditing and cleaning, followed by exploratory data analysis in Python. The results were then translated into a three-page interactive Power BI dashboard.

The analysis identified Electronics as the largest revenue and gross-profit contributor, Beauty as the category with the highest gross margin, and Apparel as the category with the highest return rate.

The findings demonstrate why revenue alone is not sufficient to evaluate business performance. Profitability, return exposure, customer behaviour and discounting must also be considered.

# 2. Business Context and Problem Statement

An e-commerce business needs to increase sales and profitability while reducing product returns and improving customer retention.

However, different product categories can contribute differently to revenue and profit. A high-revenue category may have a lower margin, while a high-margin category may contribute less absolute profit.

Similarly, a category generating strong sales may also experience a high return rate, reducing the value of its sales performance.

The business therefore requires an integrated analysis of sales, products, customers, profitability and returns.

**Problem statement:**

How can an e-commerce business use transactional and customer data to identify revenue opportunities, improve profitability, understand return behaviour and make better business decisions?

# 3. Project Objectives

The main objectives were:

1. Evaluate overall sales and revenue performance.
2. Identify high-performing product categories, brands and products.
3. Compare revenue contribution with gross-profit contribution.
4. Examine category-level profitability and margins.
5. Understand customer acquisition and purchasing behaviour.
6. Identify major return reasons and high-return categories.
7. Investigate the relationship between discounts and gross margins.
8. Develop an interactive dashboard to communicate findings.
9. Translate analytical findings into business recommendations.

# 4. Dataset Description

The project uses the Prime Levels Global E-commerce Orders & Returns dataset.

Source: https://prime-levels.com/data-hub/global-ecommerce-orders-returns-2024-2026

The dataset consists of five CSV files.

| Table | Records | Purpose |
|---|---:|---|
| Customers | 3,000 | Customer demographics and acquisition information |
| Products | 345 | Product catalogue and pricing information |
| Orders | 14,000 | Order-level transaction information |
| Order Items | 29,671 | Product-level order information |
| Returns | 2,433 | Return and refund information |

**Total records:** 49,449

## 4.1 Customers

Contains customer identifiers and information such as:

- Country and region
- Acquisition channel
- Preferred device
- Newsletter opt-in
- Signup date
- First order date

## 4.2 Products

Contains:

- Product ID
- Product name
- Category
- Brand
- List price
- Cost information
- Product activity status

## 4.3 Orders

Contains order-level information such as:

- Order ID
- Customer ID
- Order date
- Order status
- Sales channel
- Order-related fields

## 4.4 Order Items

Contains product-level transaction information, including:

- Order item ID
- Order ID
- Product ID
- Quantity
- Discount percentage
- Line revenue
- Line profit

## 4.5 Returns

Contains:

- Return identifiers
- Order item references
- Return reasons
- Refund amounts
- Restocking information

**Data note:** The dataset is synthetic. The results are intended to demonstrate analytical methods and business reasoning rather than describe an actual retailer.

# 5. Data Auditing

Before beginning the analysis, all five datasets were inspected to understand their structure and quality.

The audit covered:

- Dataset dimensions
- Column names and data types
- Missing values
- Duplicate records
- Unique identifiers
- Primary key and foreign key relationships
- Numerical distributions
- Date ranges
- Categorical value distributions

## 5.1 Data Quality Summary

| Table | Shape / Records | Key observations |
|---|---:|---|
| Customers | 3,000 | 34 missing first-order dates |
| Products | 345 | No missing values reported |
| Orders | 14,000 | 1,246 missing delivery-day values |
| Order Items | 29,671 | No missing values reported |
| Returns | 2,433 | No missing values reported |

The order table contained 1,246 missing delivery-day values, comprising 807 cancelled orders and 439 processing orders.

These missing values were treated as structurally meaningful because cancelled and processing orders do not necessarily have completed delivery durations.

The customer table contained 34 missing first-order dates. The customer data also contained zero values in the lifetime-orders field, which was considered during interpretation rather than automatically replaced.

## 5.2 Duplicate and Relationship Checks

The audit identified:

- No duplicate customer IDs.
- No duplicate product IDs.
- No duplicate order IDs.
- No duplicate order-item IDs.
- All checked foreign-key relationships passed validation.

These checks helped establish confidence in the relationships used for subsequent analysis.

# 6. Data Cleaning and Preparation

Data cleaning was carried out using Python.

The objective was to make the datasets consistent and suitable for analysis while preserving meaningful information.

## 6.1 Data Type Corrections

Date-related fields were converted to appropriate datetime formats.

Boolean fields, including newsletter opt-in and product activity indicators, were standardised.

## 6.2 Missing Value Treatment

Missing values were investigated according to their meaning.

Examples:

- Missing first-order dates were retained where the available information did not justify imputing a date.
- Missing delivery durations associated with cancelled and processing orders were treated as structural rather than automatically filled.
- Other missing values were examined before deciding on treatment.

## 6.3 Feature Engineering

Product-level profitability indicators were prepared, including:

- Gross profit per unit
- Gross margin percentage

The cleaned datasets were exported separately, preserving the original CSV files.

## 6.4 Data Integration

The five tables were connected through their identifiers.

The core relationships were:

- Customers to Orders through customer ID.
- Orders to Order Items through order ID.
- Products to Order Items through product ID.
- Order Items to Returns through order-item ID.

These relationships enabled the analysis of customer, product, transaction and return information together.

# 7. Exploratory Data Analysis

The exploratory analysis was performed using Python, primarily with Pandas, NumPy, Matplotlib and Seaborn.

The analysis was divided into several business-focused areas.

## 7.1 Sales Performance Analysis

The analysis focused on:

- Delivered revenue
- Delivered order count
- Units sold
- Average order value
- Monthly revenue performance
- Revenue by product category
- Revenue by country
- Revenue by sales channel

For consistent sales reporting, delivered orders were used in the core revenue KPIs.

### Key results

| Metric | Result |
|---|---:|
| Delivered Revenue | $6,109,150.81 |
| Delivered Orders | 12,030 |
| Units Sold | 35,994 |
| Average Order Value | $507.82 |

Average order value was calculated as:

AOV = Delivered Revenue / Delivered Orders

## 7.2 Product and Category Analysis

The purpose was to understand which product categories generated the greatest revenue and gross profit.

### Delivered Revenue by Category

| Category | Revenue |
|---|---:|
| Electronics | $3,037,892.60 |
| Sports | $1,015,061.33 |
| Apparel | $921,879.37 |
| Home & Kitchen | $542,689.60 |
| Beauty | $311,049.75 |
| Toys & Games | $280,578.16 |

Electronics was the largest revenue contributor.

### Gross Profit by Category

| Category | Gross Profit |
|---|---:|
| Electronics | $686,160.62 |
| Apparel | $480,329.10 |
| Sports | $385,651.58 |
| Home & Kitchen | $217,697.86 |
| Beauty | $184,867.95 |
| Toys & Games | $125,349.52 |

Electronics also generated the highest absolute gross profit.

However, absolute gross profit and gross margin tell different stories.

### Gross Margin by Category

| Category | Gross Margin |
|---|---:|
| Beauty | 59.43% |
| Apparel | 52.10% |
| Toys & Games | 44.68% |
| Home & Kitchen | 40.11% |
| Sports | 37.99% |
| Electronics | 22.59% |

Beauty had the highest category gross margin, while Electronics had the highest absolute gross profit.

This distinction is important when evaluating product performance.

## 7.3 Customer Analysis

The customer analysis explored:

- Geographic distribution
- Acquisition channels
- Preferred devices
- Customer purchasing behaviour
- Revenue contribution by customer purchasing frequency

Regular and Frequent customers accounted for approximately 58.03% of purchasers and contributed approximately 76.22% of delivered revenue.

This indicates that repeat and frequent customers are an important contributor to business revenue.

The acquisition-channel analysis was based on customer counts. It should not be interpreted as acquisition profitability because marketing expenditure was not available.

## 7.4 Returns Analysis

Returns were analysed to identify the categories and reasons associated with product returns.

### Overall Return Performance

| Metric | Result |
|---|---:|
| Delivered Units | 35,994 |
| Returned Units | 2,882 |
| Return Rate | 8.01% |
| Refund Amount | $410,427.05 |

Return rate was calculated as:

Return Rate = Returned Units / Delivered Units × 100

### Return Rate by Category

| Category | Return Rate |
|---|---:|
| Apparel | 15.34% |
| Sports | 8.58% |
| Home & Kitchen | 5.44% |
| Toys & Games | 5.37% |
| Beauty | 4.62% |
| Electronics | 4.02% |

Apparel had the highest category return rate.

This suggests that Apparel deserves further investigation, particularly around sizing, fit and product information.

### Return Reasons

| Return Reason | Share of Returned Units |
|---|---:|
| Wrong size / fit | 29.08% |
| Not as described | 19.88% |

Together, these reasons accounted for approximately 48.96% of returned units.

This points towards potential improvements in product sizing information, descriptions and customer expectations.

## 7.5 Discount and Profitability Analysis

The analysis also examined gross margin across different discount levels.

The objective was to investigate whether higher discount levels were associated with lower gross margins.

Discount percentages were grouped into more readable intervals for visualisation.

This analysis is observational. It does not establish a causal relationship between discounts and changes in gross margin.

# 8. Key Business Findings

The major findings can be summarised as follows.

### Finding 1 — Electronics dominates revenue and absolute gross profit

Electronics generated approximately $3.04 million in delivered revenue and $686,160.62 in gross profit.

However, its gross margin was approximately 22.59%, lower than several other categories.

**Business implication:** Monitor product-level margins and costs within Electronics rather than relying only on its revenue contribution.

### Finding 2 — Beauty has the highest gross margin

Beauty achieved a gross margin of approximately 59.43%.

Although its revenue contribution was comparatively smaller, it demonstrated strong margin performance.

**Business implication:** Investigate opportunities to expand profitable sales in Beauty while monitoring demand and customer response.

### Finding 3 — Apparel has a significant return problem

Apparel recorded the highest return rate at approximately 15.34%.

It also accounted for approximately 49.79% of returned units.

**Business implication:** Review sizing charts, fit guidance, product images and descriptions to identify opportunities to reduce avoidable returns.

### Finding 4 — Product information is an important return-related issue

Wrong size / fit and Not as described together accounted for approximately 48.96% of returned units.

**Business implication:** Improve product information and customer guidance to reduce expectation mismatches.

### Finding 5 — Repeat customers contribute a large share of revenue

Regular and Frequent customers represented approximately 58.03% of purchasers but contributed approximately 76.22% of delivered revenue.

**Business implication:** Retention initiatives and customer experience improvements may be valuable areas for further investigation.

# 9. Power BI Dashboard Development

After completing the Python analysis, the findings were translated into an interactive Power BI report.

The report contains three pages.

## Page 1 — Executive Overview

Purpose: Provide management with an overview of overall business performance.

The page includes:

- Delivered Revenue
- Total Orders
- Total Units Sold
- Delivered Gross Profit
- Gross Margin
- Average Order Value
- Monthly Delivered Revenue Trend
- Revenue Contribution by Product Category
- Gross Profit Contribution by Product Category
- Gross Margin by Product Category

## Page 2 — Sales & Customer Intelligence

Purpose: Explore sales performance and customer behaviour.

The page includes:

1. Delivered Revenue by Country
2. Delivered Revenue by Sales Channel
3. Monthly Delivered Orders Trend
4. Top 10 Products by Delivered Revenue
5. Delivered Revenue by Brand
6. Customer Acquisition Mix

## Page 3 — Returns, Profitability & Pricing

Purpose: Examine return behaviour and profitability.

The page includes:

1. Return Rate by Product Category
2. Return Reasons Distribution
3. Refund Amount by Product Category
4. Gross Margin Across Discount Levels
5. Gross Profit by Product Category

# 10. Business Recommendations

Based on the findings, the following actions are recommended for further business investigation.

## 10.1 Improve Apparel Product Information

Apparel has the highest return rate.

Potential actions:

- Improve sizing charts.
- Provide more detailed fit descriptions.
- Add clearer product images.
- Review return patterns at individual product level.

## 10.2 Monitor Category-Level Profitability

Electronics generates the largest absolute gross profit, while Beauty has the highest gross margin.

Potential actions:

- Track revenue and gross profit together.
- Investigate low-margin products.
- Review product-level costs and pricing.
- Avoid making decisions using revenue alone.

## 10.3 Improve Customer Retention

Regular and Frequent customers contribute a large share of delivered revenue.

Potential actions:

- Study repeat-purchase behaviour.
- Evaluate customer retention initiatives.
- Monitor purchase frequency and customer value over time.

## 10.4 Review Discounting Strategies

Higher discount bands showed a relationship with lower margins in the analysis.

Potential actions:

- Evaluate margin performance across discount levels.
- Identify products where discounts reduce profitability substantially.
- Consider targeted promotions rather than uniform discounting.

## 10.5 Monitor Refund Exposure

Refund amounts should be monitored alongside revenue and gross profit.

Potential actions:

- Track refund amounts by category and product.
- Identify products with unusually high return exposure.
- Investigate the most common return reasons.

# 11. Limitations and Assumptions

The following limitations should be considered when interpreting the results.

1. The dataset is synthetic and does not represent verified real-world company performance.
2. Gross profit is calculated from available transaction and product-cost fields. It does not include all business expenses.
3. Refund-adjusted gross profit is an analytical proxy, not audited net profit.
4. Marketing expenditure is unavailable, so customer acquisition cost and marketing ROI cannot be calculated.
5. Inventory history is unavailable, so inventory turnover, stockouts and replenishment performance cannot be evaluated.
6. Discount analysis identifies associations rather than causal effects.
7. Customer behaviour conclusions depend on the available customer and order fields.
8. Results should be interpreted within the observed transaction period and dataset coverage.

# 12. Conclusion

This project demonstrates how multiple interconnected e-commerce datasets can be transformed into meaningful business insights through data auditing, cleaning, exploratory analysis and dashboard development.

The analysis highlights the importance of evaluating revenue, gross profit, margins, customer behaviour and product returns together.

It also demonstrates how a business question can be translated into an analytical workflow and ultimately communicated through an interactive business intelligence dashboard.

The project provides a foundation for further work involving SQL-based analysis, advanced customer analytics, product-level return prediction and more detailed profitability modelling.

---

**End of Project Documentation**