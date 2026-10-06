# Market Basket Analysis & Automated Retail Strategy Pipeline

## Executive Summary

This project delivers an end-to-end data processing, analytics, and automated reporting pipeline for retail cross-selling strategies using **KNIME Analytics Platform** and **Microsoft Excel**.

By processing transaction histories across **3,196 unique customers** and **7,959 purchase events**, the pipeline mined key product association rules (using the **Apriori Algorithm**). The mined insights are automatically formatted and exported directly to an executive-ready Excel file (`MBA.xlsx`) to optimize product placement, bundle promotions, and targeted promotional campaigns.

---

## 🎯 Business Problem & Strategic Solution

### 1. The Business Problem
Retailers and e-commerce platforms frequently encounter three core operational challenges:
* **Stagnant Average Order Value (AOV):** Customers purchase single or standalone items without exploring complementary products.
* **Ineffective Cross-Selling & Bundling:** Promotional bundles and cross-sell recommendations are often created using subjective intuition rather than empirical purchase behavior.
* **Manual Data Processing Overhead:** Merging, cleaning, and extracting association patterns from massive transaction logs takes hours of manual work, making frequent strategy updates unsustainable.

### 2. How This Project Solves It
* **Data-Driven Association Mining:** Automatically identifies hidden purchase dependencies and co-occurrence patterns across 15 core product categories using the Apriori association rule algorithm.
* **End-to-End Pipeline Automation:** Eliminates manual processing by constructing an automated KNIME workflow (`CSV Ingestion` ➔ `Grouping` ➔ `Rule Mining` ➔ `Filtering` ➔ `Export`).
* **Actionable Marketing Deliverables:** Programmatically converts raw graph/set collections into formatted Excel workbooks (`MBA.xlsx`) that store managers and e-commerce marketers can immediately use for bundling and cart recommendation triggers.

---

## Technical Stack & Architecture

### Data Processing Pipeline Architecture:
`Transaction CSV (7,959 records)` ➔ `Excel / Data Cleaning` ➔ `KNIME Workflow Automation` ➔ `Formatted Excel Export (MBA.xlsx)`

### Tools Used:
* **Microsoft Excel (`MBA.xlsx`):** Initial data preparation, data validation, and automated export destination structured for executive marketing decisions.
* **KNIME Analytics Platform:** Visual workflow engine for automated transaction grouping, candidate itemset generation, association rule mining, and data type conversion.

### Skills Used:
* **Market Basket Analysis (MBA):** Applying data mining methods to uncover purchasing associations between multi-item baskets.
* **Apriori Algorithm & Rule Mining:** Evaluating candidate itemsets through statistical thresholds (**Support**, **Confidence**, and **Lift**).
* **ETL & Data Pipeline Automation:** Building reproducible end-to-end data pipelines from raw CSV ingestion to clean report generation.
* **Data Cleansing & Transformation:** Handling schema mismatches, string manipulation, and converting set collection data structures to tab-delimited text.
* **Retail & E-Commerce Strategy:** Translating data-driven rule metrics into revenue-generating business tactics (cart upsells, promotional bundles, and point-of-sale store layout optimizations).

---

## Key Analytics Metrics & Findings

The **Association Rule Learner** evaluated cross-category itemsets to identify cross-selling synergies:

| Rule Antecedent (Items Bought Together) | Rule Consequent | Support | Confidence | Lift | Strategic Action |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **`rolls,buns` + `shopping bags`** | `whole milk` | 1.00% | 41.03% | **1.251** | Checkout counter product pairing |
| **`other vegetables` + `shopping bags`** | `whole milk` | 1.13% | 40.91% | **1.248** | Bundle discount at point-of-sale |
| **`pastry` + `other vegetables`** | `whole milk` | 1.10% | 38.89% | **1.186** | In-store aisle layout optimization |
| **`citrus fruit` + `other vegetables`** | `whole milk` | 1.10% | 38.89% | **1.186** | Cross-category promotional coupons |
| **`rolls,buns` + `sausage`** | `whole milk` | 1.03% | 36.67% | **1.118** | Multi-buy combo meal deal |

* **Highest Confidence Pair:** Customers purchasing **Rolls/Buns + Shopping Bags** have a **41.03% probability** of also purchasing **Whole Milk** ($\text{Lift} = 1.251$).
* **Top Multi-Category Driver:** **Other Vegetables** paired with **Shopping Bags** or **Pastry** consistently increases the likelihood of **Whole Milk** orders by **18% to 25%** over baseline probability.
