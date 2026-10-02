# E-Commerce Subscription Customer Analytics: RFM Segmentation & Behavioral Intelligence

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![KNIME](https://img.shields.io/badge/KNIME-2596be?style=for-the-badge&logo=knime&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

## Executive Summary
This project delivers an end-to-end Customer Intelligence framework for an E-Commerce Subscription platform. By combining automated data processing in **KNIME Analytics Platform** with interactive modeling in **Power BI**, the project analyzes customer transaction logs to segment subscribers based on **Recency, Frequency, and Monetary (RFM)** behavior. 

The dashboard enables business stakeholders to reduce churn, target high-potential customers, and optimize promotional budgets across 400 analyzed accounts generating $15.05K in total revenue over 1,221 transactions.

---

## Technical Stack & Workflow Architecture

### Data Processing Architecture:
`CSV Raw Data` ➔ `Excel (Initial Prep)` ➔ `KNIME Workflow (ETL & Binning)` ➔ `Power BI Desktop (DAX & Visualization)`

### Technologies & Tools Used:
* **Microsoft Excel:** Raw data inspection, missing value handling, structural sanitization.
* **KNIME Analytics Platform:** Advanced ETL pipeline automation, date arithmetic, group-by aggregations, numeric binning, and rule-based RFM scoring.
* **Power BI Desktop:** Relational modeling, DAX measures, custom visuals, dynamic page navigation, analytics quadrant styling.

---

## Data Engineering & Analytics Techniques

### 1. KNIME Analytics Workflow
The ETL data transformation workflow was built using the following key nodes:
* `CSV Reader`: Ingested raw e-commerce transaction logs.
* `String to Date&Time`: Standardized transaction timestamps into ISO date formats.
* `Date&Time Difference`: Calculated exact days elapsed between transaction date and snapshot reference date (**Recency**).
* `GroupBy`: Aggregated transaction records at the `customer_id` level to measure total transactions (**Frequency**) and aggregate spend (**Monetary Value**).
* `Column Renamer`: Standardized column headers for data model consistency.
* `Numeric Binner`: Assigned relative quartile/rank scores (1-5) to Recency, Frequency, and Monetary metrics.
* `Rule Engine`: Categorized customers into operational segments (*Champions*, *Value Customers*, *Need Attention*, *At Risk*, *About to Sleep*, *New/Promising*, *Lost Customers*) based on combined RFM score boundaries.

### 2. Power BI Data Modeling & DAX Measures
* Custom explicit DAX metrics created for **Average Sales per Customer**, **Total Revenue**, **Total Transactions**, and **Customer Segment Percentages**.
* Scatter plot quadrant modeling using X/Y constant reference lines to highlight purchase frequency vs. monetary value trade-offs.

---

## Dashboard Structure & Features

### Page 1: Executive Overview & Segment Distribution
* **Executive Metrics:** Total Revenue ($15,048), Total Customers (400), Total Transactions (1,221), and Average Spend per Customer ($15.04).
* **Segment Share (Pie Chart):** Distribution of subscribers across 7 behavioral buckets.
* **Top Revenue Generators:** Stacked bar breakdown identifying revenue volume by segment.

### Page 2: Frequency & Value Analysis
* **Frequency Value Baskets:** Categorizes customer density into High, Medium, and Low frequency buckets.
* **High Frequency / Low Spend Scatter Plot:** Bivariate visualization mapping `Frequency_Value` against `Monetary_Value` to locate upsell opportunities.

### Page 3: Recent High-Potential Buyers
* Detailed tabular view listing customers with high recency/frequency metrics to support targeted marketing list exports.

---

## Business Interpretation & Strategic Recommendations

### Key Insights:
1. **Value Customers dominate the user base:** Representing **42.75% of customers (171 users)**, this group generates the highest total volume ($6.025K aggregate revenue) with an average order spend of $15.04.
2. **Champions demonstrate top account value:** 79 customers (19.75% of total) average **$37.78 in spend per account**, exhibiting low recency and high overall engagement.
3. **Low Monetary / High Frequency Discrepancy:** A distinct cohort of subscribers orders frequently (4-5 orders) but spends under $15 per order.

### Actionable Business Recommendations:
* **Implement Minimum Order Value (MOV) Incentives:** Offer free shipping or tier discounts for order baskets exceeding $25 to increase average spend among high-frequency/low-value subscribers.
* **Proactive At-Risk Retention:** Trigger automated email sequences ("We miss you" offers) for customers moving into the *About to Sleep* (57 customers) or *At Risk* segments before churn occurs.
* **VIP Loyalty Program Expansion:** Create early-access beta feature lists for *Champions* to maintain high retention rates and incentivize word-of-mouth referrals.
