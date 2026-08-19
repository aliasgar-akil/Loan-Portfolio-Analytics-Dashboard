# Overview

The **Loan Portfolio Analytics Dashboard** is an end-to-end data analytics project that combines Microsoft Excel for exploratory data analysis (EDA) with Power BI for interactive business intelligence reporting. The project analyzes a consumer loan portfolio to evaluate lending performance, borrower characteristics, and credit risk through statistical exploration, interactive dashboards, and business-focused visualizations.

The workflow begins with exploratory analysis in Excel to understand distributions, relationships, and borrower segments before transforming the cleaned data into an interactive Power BI dashboard. Users can monitor portfolio performance, analyze lending trends, identify high-risk borrower groups, and drill down to individual loan records using dynamic filters and drill-through functionality.

The project demonstrates practical skills in data preparation, data modeling, DAX measure development, time intelligence functions, exploratory data analysis, and dashboard design to convert raw loan data into actionable business insights.

---

# Business Problem

Financial institutions issue thousands of loans to borrowers with different financial backgrounds, credit profiles, and repayment capacities. Without effective analysis, it becomes difficult to monitor portfolio performance, identify high-risk borrower segments, detect lending trends, and make informed credit decisions.

---

# Project Objective

The objective of this project is to analyze a consumer loan portfolio to identify high-risk borrower segments, monitor lending performance, and uncover patterns associated with loan defaults. The resulting insights support data-driven lending decisions and effective portfolio risk management.

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

# Project Workflow

The project follows a complete analytics workflow:

1. **Data Quality Validation & Exploratory Data Analysis (Excel)**
   - Performed data quality checks for missing values and duplicate records.
   - Examined distributions of key variables using histograms.
   - Computed descriptive statistics for numerical features.
   - Performed correlation analysis between borrower attributes and default status.
   - Identified low-risk customer segments using PivotTables and interactive slicers.

2. **Business Intelligence Development (Power BI)**
   - Built a star-schema data model with a dedicated Date Table.
   - Created calculated columns for borrower segmentation.
   - Developed reusable DAX measures and time intelligence calculations.
   - Designed interactive dashboards with drill-through analysis and AI-powered visuals.

3. **Business Insights**
   - Translated analytical findings into portfolio-level insights for lending performance, borrower behavior, and credit risk.

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

# Microsoft Excel – Data Quality Validation & Exploratory Data Analysis

***Note:** The Excel workbook is not included in this repository due to its large file size. Screenshots of the exploratory data analysis have been provided below as well as in the images folder.*

Before developing the Power BI dashboard, data quality validation and exploratory data analysis (EDA) were performed in Microsoft Excel to understand the dataset, identify relationships between variables, and uncover borrower risk patterns.

## 1. Data Quality Validation

Performed initial checks to validate the dataset before analysis:

- Confirmed the dataset contains **255,347 rows and 19 columns**.
- Checked for missing values across all columns using Excel `COUNTBLANK()` and confirmed **0 missing values** across all 19 columns
- Checked for duplicate records and confirmed **0 duplicate rows**.
- Classified the dataset into numeric and categorical columns.

### Dataset Summary

<img width="254" height="175" alt="Excel-Dataset Summary" src="https://github.com/user-attachments/assets/23683dee-e038-483e-9dea-f26069525a4f" />

### Missing Values Count

<img width="362" height="510" alt="Excel-Missing Values Count" src="https://github.com/user-attachments/assets/76e8f9d9-5a6b-4f1b-bb20-ffd704858021" />

---

## 2. Descriptive Statistics

Calculated summary statistics for key numerical variables including:

- Loan Amount
- Income
- Credit Score
- Interest Rate
- Debt-to-Income Ratio (DTI)
- Age

This analysis provided measures such as mean, median, minimum, maximum, standard deviation, and quartiles to understand the overall characteristics of the loan portfolio.

<img width="971" height="268" alt="Excel-Descriptive Statistics" src="https://github.com/user-attachments/assets/37f2b334-3c11-40cf-9bbd-9b1f8be13a6c" />

---

## 3. Distribution Analysis

Created boxplots and histograms to examine the distribution of:

- Loan Amount
- Income
- Credit Score
- Interest Rate
- Debt-to-Income Ratio
- Age

These visualizations helped identify the spread and concentration of borrower and loan characteristics.

<img width="653" height="597" alt="Excel-Distribution Analysis" src="https://github.com/user-attachments/assets/9dda9795-bcc7-4762-8baa-14a20814afff" />

---

## 4. Customer Risk Segmentation

Performed correlation analysis between **Default Status** and key numerical variables:

- Income
- Credit Score
- Debt-to-Income Ratio (DTI)
- Age

Conditional formatting was used to highlight positive and negative relationships with loan default.

The findings were further explored using interactive PivotTables and slicers to segment borrowers based on:

- Age Group
- Income Bracket
- Credit Score Category
- Debt-to-Income Category

This analysis helped identify lower-risk borrower segments and understand how borrower characteristics influence default risk.

<img width="1432" height="622" alt="Excel-Customer Risk Segmentation" src="https://github.com/user-attachments/assets/6c897ae2-47eb-4338-b777-67c3a5b284cf" />


---

# Power BI Data Preparation & Modeling

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

- The portfolio contains **255,347 loans** with a total loan value of **32.577 billion**, maintaining an overall **default rate of 11.6%**.

- Borrowers with **Very Low Credit Scores** have the highest default rate (**13.3%**), compared to **10.4%** for borrowers with **High Credit Scores**, highlighting the strong relationship between creditworthiness and repayment risk.

- **Low Income** borrowers exhibit the highest default rate (**22.0%**), more than **twice** that of **High Income** borrowers (**9.5%**), making income one of the strongest indicators of default risk.

- Borrowers with **High DTI** have a default rate of **12.2%**, compared with **10.8%** for borrowers with **Low DTI**, indicating that higher debt burdens are associated with greater credit risk.

- Although **High Income** borrowers account for approximately **170K loans (67%)**, the highest default rates occur among **Low Income** borrowers, suggesting that portfolio size does not necessarily correspond to higher lending risk.

- Loans are distributed almost evenly across loan purposes (approximately **20%** each), yet **Business loans** record the highest default rate (**12.3%**) while **Home loans** record the lowest (**10.2%**).

- **Medium (36.4%)** and **High (36.1%)** credit score categories make up over **72%** of the portfolio, while only **9.0%** of borrowers belong to the **Low Credit Score** category.

- Adults and Middle-Aged Adults each account for approximately **98K loans**, together representing nearly **77%** of the total loan portfolio.

- Average loan amounts remain relatively consistent across borrower segments, ranging between **126.7K** and **128.0K**, indicating that demographic characteristics have limited influence on loan size.

---

# Conclusion

Based on the analysis, borrowers with **High Income**, **High Credit Scores**, **Low Debt-to-Income (DTI) ratios**, and belonging to the **Middle-Age Adult** and **Senior Citizen** groups exhibit the lowest default rates. These findings suggest that borrowers with these characteristics represent the lowest-risk customer segment and may be prioritized during lending decisions.

---

# Repository Structure

```text
Loan-Portfolio-Analytics-Dashboard
│
├── Loan Portfolio Analytics Dashboard.pbix
├── Dataset Source URL.txt
├── README.md
│
└── images
    ├── Executive Dashboard.png
    ├── Borrower Profile & Portfolio Analysis.png
    ├── Credit Risk Analysis.png
    ├── Loan Purpose Analysis.png
    ├── Excel-Dataset Summary.png
    ├── Excel-Missing Values Count.png
    ├── Excel-Descriptive Statistics.png
    ├── Excel-Distribution Analysis.png
    └── Excel-Customer Risk Segmentation.png
```

---

## Author

**Ali Asgar Baghdadwala**
