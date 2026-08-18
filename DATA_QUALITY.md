# Data Quality Checks

Before the Excel exploratory analysis, basic data quality checks were performed on the loan portfolio dataset.

## Dataset Summary

| Check | Result |
|---|---:|
| Total Rows | 255,347 |
| Total Columns | 19 |
| Missing Values | 0 |
| Duplicate Rows | 0 |
| Numeric Columns | 9 |
| Categorical Columns | 9 |

## Checks Performed

### 1. Missing Values

Missing values were checked for every column using Excel `COUNTBLANK()`.

**Result:** No missing values were found across the 19 columns.

### 2. Duplicate Rows

The dataset was checked for duplicate records to ensure that the same loan record was not repeated.

**Result:** 0 duplicate rows.

### 3. Dataset Structure

The dataset was reviewed to confirm the total number of rows and columns and to identify numeric and categorical fields before analysis.

### 4. Data Type Review

Columns were reviewed to ensure that numerical variables and categorical variables were suitable for the planned EDA and Power BI analysis.

## Why These Checks Matter

These checks confirm that the dataset did not require missing-value treatment or duplicate removal before proceeding with the analysis. The results were documented as part of the EDA process rather than assuming the source data was already clean.
