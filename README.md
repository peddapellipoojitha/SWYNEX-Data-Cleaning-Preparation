# SWYNEX – Data Cleaning & Preparation (Task 1)

## Project overview
This repository contains the cleaned supermarket sales practice dataset, an audit log of data-quality decisions, and summary tables prepared for basic sales analysis.

## Files
- `SWYNEX-Data-Cleaning-Preparation.xlsx` – Excel workbook with Raw Data, Cleaned Data, Cleaning Log, Summary tables, and README.
- `Cleaned_Supermarket_Sales.csv` – cleaned data in CSV format.
- `LinkedIn_Post_Draft.txt` – suggested completion post.

## Dataset
The source dataset contains 42 rows and 9 columns. After removing one exact duplicate transaction, the cleaned dataset contains 41 rows. A calculated field, `Total_Amount_INR`, is added as Quantity × Unit_Price_INR.

## Cleaning performed
1. Removed one exact duplicate row (the repeated INV005 / P005 / Soap transaction).
2. Standardized capitalization and whitespace in `Payment_Method`, `City`, `Product`, and `Category`.
3. Converted `Date` values to a consistent date type / `YYYY-MM-DD` display.
4. Kept missing values in INV021 Quantity and INV022 Unit_Price_INR blank instead of inventing values.
5. Retained INV029's negative quantity (-1) and marked it for verification; it may represent a return/refund.
6. Kept both distinct rows with Invoice_ID `INV040` because their dates and Product_IDs differ; flagged the repeated invoice ID for verification.
7. Added `Total_Amount_INR` = Quantity × Unit_Price_INR. The calculated amount is left blank when an input is missing.

## Summary findings
- Total calculated sales amount: ₹3,923.00 (includes the -₹75.00 negative transaction; excludes the two records whose amount cannot be calculated).
- Highest single calculated transaction: ₹320.00.
- Lowest single calculated transaction: -₹75.00.
- There are 39 rows with a calculable transaction amount.

**Important:** The negative quantity and repeated invoice ID are data-quality exceptions, not silently corrected. Confirm them with the data owner before using this dataset for financial reporting.

## How to use
Open the Excel workbook and review `Cleaned_Data`, `Cleaning_Log`, and the summary sheets. The `Sales_by_Product` sheet gives the product-level sum of calculated sales. The CSV can be imported into Excel, SQL, or Python.

## Tools
Excel / spreadsheet analysis. The dataset is a small practice dataset prepared for the SWYNEX internship task.
