# Overview

The **Loan Portfolio Analytics Dashboard** is an interactive Power BI project that provides a comprehensive view of a consumer loan portfolio. It helps analyze lending performance, borrower characteristics, and credit risk through a collection of interactive dashboards designed for portfolio monitoring and decision-making.

The report combines key performance indicators with borrower segmentation, trend analysis, and detailed loan-level exploration. Users can evaluate lending patterns across dimensions such as income, credit score, debt-to-income ratio, age group, and loan purpose, while using interactive filters and drill-through pages to investigate specific areas of interest.

The project demonstrates an end-to-end Power BI workflow, including data preparation, data modeling, DAX measure development, time intelligence, and interactive report design. By transforming raw loan data into meaningful visualizations and business metrics, it enables stakeholders to better understand portfolio performance and identify potential areas of risk.

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

Financial institutions manage thousands of loans issued to borrowers with varying financial backgrounds and risk profiles. Understanding portfolio performance and identifying high-risk borrower segments is critical to maintaining portfolio health and supporting growth strategies.

This dashboard provides an interactive solution to monitor key lending metrics, analyze borrower characteristics, evaluate portfolio risk, and investigate loan details using drill-through analysis and influencer models.

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

# Business Insights

- The loan portfolio comprises **255,347 loans** with a total loan value of **32.577 billion**, maintaining an overall **default rate of 11.6%**.

- Borrowers with **Very Low Credit Scores** exhibit the highest default rate (**13.3%**), compared to **10.4%** for borrowers with **High Credit Scores**, highlighting a clear relationship between creditworthiness and repayment risk.

- **Low Income** borrowers have the highest default rate (**22.0%**), which is more than **twice** the rate for **High Income** borrowers (**9.5%**), making income one of the strongest indicators of default risk.

- Borrowers with a **High Debt-to-Income (DTI)** ratio have a default rate of **12.2%**, compared to **10.8%** for borrowers with **Low DTI**, indicating that higher debt burdens are associated with increased credit risk.

- Although **High Income** borrowers account for approximately **170K loans (67%)** of the portfolio, the highest default rates are observed among **Low Income** borrowers, suggesting that portfolio volume does not necessarily correspond to higher lending risk.

- Loans are distributed almost evenly across loan purposes (approximately **20%** each), yet **Business loans** record the highest default rate (**12.3%**), while **Home loans** have the lowest (**10.2%**).

- The borrower base is dominated by **Medium (36.4%)** and **High (36.1%)** credit score categories, while only **9.0%** of borrowers fall into the **Low Credit Score** category.

- The portfolio is concentrated among **Adults** and **Middle-Aged Adults**, each representing approximately **98K loans**, together accounting for nearly **77%** of all loans issued.

- Average loan amounts remain relatively consistent across borrower segments, ranging from approximately **126.7K to 128.0K**, indicating that borrower demographics have limited influence on loan size.

---

# Repository Structure

```text
Loan-Portfolio-Analytics-Dashboard
│
├── Loan Portfolio Analytics Dashboard.pbix
├── Dataset Source URL.txt
├── README.md
└── images/
    ├── Executive Dashboard.png
    ├── Borrower Profile & Portfolio Analysis.png
    ├── Credit Risk Analysis.png
    └── Loan Purpose Analysis.png
```

---

## Author

**Ali Asgar Baghdadwala**
