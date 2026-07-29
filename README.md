# Overview

The **Loan Portfolio Analytics Dashboard** is an interactive Power BI project developed to analyze the performance and risk of a consumer loan portfolio. It provides a centralized view of lending o[...]

The dashboard enables users to assess portfolio performance, monitor lending trends, and identify high-risk borrower segments through interactive visualizations and dynamic filtering. It supports d[...]

This project demonstrates an end-to-end business intelligence workflow, covering data preparation, data modeling, DAX measure development, time intelligence, and interactive dashboard design. By tr[...]

---

## Dashboard Preview

### Executive Dashboard
<img width="1294" height="724" alt="Executive Dashboard" src="https://github.com/user-attachments/assets/38c966e5-4485-4b27-9a74-fb4c9cbd57bf" />

### Borrower Profile & Portfolio Analysis
<img width="1296" height="723" alt="Borrower Profile   Portfolio Analysis" src="https://github.com/user-attachments/assets/17d58e1d-626f-4a3d-b6d2-fa400338fd39" />

### Credit Risk Analysis
<img width="1288" height="734" alt="Credit Risk Analysis" src="https://github.com/user-attachments/assets/f1451359-6f39-405e-b59f-2e53ceaa572d" />

### Loan Purpose Analysis (Drill-through)
<img width="1290" height="718" alt="Loan Purpose Analysis" src="https://github.com/user-attachments/assets/47f5d0ae-b933-4087-8073-3105f0d514d3" />

---

# Project Overview

Financial institutions manage thousands of loans issued to borrowers with varying financial backgrounds and risk profiles. Understanding portfolio performance and identifying high-risk borrower se[...]

This dashboard provides an interactive solution to monitor key lending metrics, analyze borrower characteristics, evaluate portfolio risk, and investigate loan details using drill-through analysis[...]

---

# Dataset

The dashboard is built using a loan portfolio dataset containing **255,347 loan records** and **19 attributes**.

### Key Dataset Attributes

| Category | Attributes |
|----------|------------|
| Borrower Information | Age, Income, Education, Employment Type, Marital Status |
| Loan Information | Loan Amount, Interest Rate, Loan Term, Loan Purpose |
| Credit Risk | Credit Score, Debt-to-Income Ratio (DTI), Default Status |
| Additional Information | Mortgage, Dependents, Co-Signer, Loan Date |

---

# Data Preparation & Modeling

The dataset was transformed and modeled within Power BI by:

- Creating a dedicated **Date Table** for Time Intelligence analysis.
- Establishing relationships between the Date Table and the loan dataset.
- Creating calculated columns to segment borrowers into meaningful business categories.
- Developing reusable DAX measures for KPIs and trend analysis.
- Organizing measures into dedicated measure tables for improved model readability.

---

# Date Table

A dedicated Date Table was created using **CALENDAR()** and marked as the model's Date Table to enable Power BI Time Intelligence functions.

It includes:

- Date
- Day
- Month
- Month Name
- Quarter
- Year

The Date Table is related to the **Loan Date** field in the main dataset.

---

# Calculated Columns

The following calculated columns were created to improve business segmentation and reporting.

| Calculated Column | Purpose |
|-------------------|---------|
| **Age Groups** | Categorizes borrowers into Teen, Adult, Middle Age Adult, and Senior Citizen. |
| **Income Bracket** | Segments borrowers into Low, Medium, and High Income categories. |
| **Credit Score Categories** | Groups borrowers based on creditworthiness. |
| **DTI Categories** | Categorizes borrowers using Debt-to-Income ratio ranges. |

---

# DAX Measures

| Measure | Description |
|---------|-------------|
| **Total Loans** | Total number of loans issued. |
| **Total Loan Amount** | Sum of all loan amounts. |
| **Total Defaults** | Total number of defaulted loans. |
| **Default Rate** | Percentage of defaulted loans. |
| **Average Loan Amount** | Average loan amount across the portfolio. |
| **Average Interest Rate** | Average interest rate of issued loans. |
| **Average Credit Score** | Average borrower credit score. |
| **Average DTI** | Average Debt-to-Income Ratio. |
| **YOY Loan Amount Change** | Year-over-Year percentage change in total loan amount. |
| **YOY Default Loans Change** | Year-over-Year percentage change in total defaulted loans. |

---

# Time Intelligence

Time Intelligence measures were implemented using a dedicated Date Table.

Functions used include:

- `CALCULATE()`
- `DIVIDE()`
- `SAMEPERIODLASTYEAR()`

These measures enable Year-over-Year comparisons for:

- Loan Amount
- Defaulted Loans

---

# Dashboard Pages

## 1. Executive Dashboard

Provides a high-level overview of the overall loan portfolio through interactive KPIs and trend analysis.

### Visuals Included

- KPI Cards
  - Total Loans
  - Total Loan Amount
  - Average Interest Rate
  - Average Credit Score
  - Default Rate
  - Average DTI
- Default Rate by Year
- Loan Amount by Purpose
- Default Rate by Loan Purpose
- Default Rate by Credit Score Categories
- Interactive slicers for:
  - Year
  - Employment Type
  - Education

---

## 2. Borrower Profile & Portfolio Analysis

Analyzes borrower demographics and portfolio composition.

### Visuals Included

- Total Loans & Average Loan Amount by Age Groups
- Total Loans by Credit Score Categories
- Total Loans by Income Bracket
- Average Loan Amount by Education
- Total Loans by Marital Status

---

## 3. Credit Risk Analysis

Focuses on identifying portfolio risk trends and the factors contributing to loan defaults.

### Visuals Included

- Year-over-Year Loan Amount Change
- Year-over-Year Default Loans Change
- Default Rate by DTI Categories
- Default Rate by Income Brackets
- Decomposition Tree
- Key Influencers

---

## 4. Loan Purpose Analysis (Drill-through)

A drill-through page providing detailed analysis for the selected loan purpose.

### Visuals Included

- Average Loan Amount
- Median Loan Amount
- Average Loan Term
- Average Interest Rate
- Detailed Loan Records Table

This page allows users to investigate individual loan records associated with a selected loan purpose directly from the Executive Dashboard.

---

## Business Insights

This section summarizes the key actionable insights surfaced by the dashboard visuals and what they mean for stakeholders.

- Portfolio composition and performance
  - The portfolio is diverse across borrower age, income, and loan purposes, with a mix of small-to-medium consumer loans and higher-value loans concentrated in specific borrower segments.
  - Use the Executive Dashboard slicers (Year, Employment Type, Education) to monitor how portfolio composition shifts over time and across segments.

- Risk concentration
  - Default exposures are disproportionately concentrated among borrowers with lower credit-score categories and higher DTI buckets. Filtering the Credit Risk Analysis page quickly highlights these segments as higher-risk.
  - Certain loan purposes (e.g., personal loans and credit card consolidation) show higher default rates in the drill-through Loan Purpose Analysis—consider tightening underwriting or pricing for these purposes.

- Customer segmentation and product performance
  - High average loan amounts are concentrated in higher-income and specific age groups. These segments drive a large portion of portfolio dollar volume and are important for growth-focused strategies.
  - Lower-income segments have smaller loan sizes but higher default incidence, suggesting a need for adjusted underwriting, tailored products, or enhanced servicing for affordability.

- Time trends and early warning signals
  - Year-over-Year visuals indicate periods of rising loan originations; monitor YOY Default Loans Change alongside YOY Loan Amount Change to detect whether growth is accompanied by deteriorating credit quality.
  - Use the Key Influencers and Decomposition visuals to identify leading indicators of default (e.g., rising DTI, falling credit scores, specific employment types) and build targeted early-warning rules.

- Operational recommendations
  - Strengthen underwriting for identified high-risk loan purposes and low credit-score/high-DTI segments.
  - Implement targeted collections strategies and early interventions for segments flagged by Key Influencers.
  - Consider pricing adjustments (interest rate or fees) for higher-risk loan purposes to maintain risk-adjusted returns.
  - Expand products and cross-sell opportunities in high-value segments (higher income and strong credit score cohorts) to drive profitable growth.

- How stakeholders should use the dashboard
  - Executives: track portfolio-level KPIs and YOY trends for strategy and capital planning.
  - Risk teams: use Credit Risk Analysis and drill-throughs to monitor emerging credit issues and adjust policies.
  - Product teams: analyze performance by loan purpose and borrower segment to refine product features and pricing.
  - Operations: use borrower-level drill-through to prioritize collections and customer outreach.

---
