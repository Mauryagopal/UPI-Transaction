

# UPI Transaction-Dashboard

### Dashboard Link :https://app.powerbi.com/links/SaLKudmwxi?ctid=bad12864-913e-4b99-87d6-b8d2ad459e27&pbi_source=linkShare&bookmarkGuid=66099459-7f0b-4c89-8064-8d16f3b74884

## Problem Statement

This dashboard provides a comprehensive analysis of financial transaction data for banks, merchants, and customers. It is designed to help stakeholders, including financial institutions and merchants, understand transaction trends, customer demographics, and monetary flows across various cities and currencies.



### Steps followed 

Step 1: Load the dataset into Power BI Desktop. The dataset is an Excel file containing transaction details.

Step 2: Open Power Query Editor. In the View tab under the Data Preview section, enable the following options:
- Column Distribution
- Column Quality
- Column Profile

Step 3: By default, the profile is generated for the first 1000 rows only. Update this setting to "Column profiling based on the entire dataset" to ensure a complete data analysis.

Step 4: Data inspection revealed that none of the columns had errors or empty values, making the dataset clean and ready for use.

Step 5: Using DAX, add a calculated column to categorize the age groups as follows:
- A1 for ages less than 25
- A2 for ages less than 35 but greater than or equal to 25
- A3 for ages 35 and above

The DAX formula for the new column:\

Age Group = 
IF('Table'[Age] < 25, "A1",
    IF('Table'[Age] < 35, "A2", "A3"))\

Step 6: Add a calculated measure to compute average remaining balance or transaction amounts. Ensure that any null values in the relevant columns are excluded, as they account for less than 1% of the data.

Step 7: Switch to the Report View. In the View tab, select a theme to apply to the report for better visualization.

Step 8: Create a column chart visualization for "Balance by Month" to represent the total remaining balance month-wise for the year 2024. Use the "Transaction Date Month" field on the X-axis and the "Sum of Remaining Balance" on the Y-axis.

Step 9: Add slicers to filter the report dynamically. Slicers were created for the following fields:
- Bank Name Sent
- Bank Name Received
- City
- Age Groups (using the new DAX column created)\
- Device Type
- Merchant Name
- Payment Method
- Purpose
- Status

Step 10: Create a table visualization to display city-wise and currency-wise transaction amounts and remaining balances. Add the following fields:\
- City
- Currency
- Month
- Amount
- Remaining Balance

Step 11: Highlight critical data points in the table visualization by using conditional formatting. Specific months and cities were visually emphasized to indicate trends or high transaction values.

Step 12: Add toggle buttons or additional charts to switch between visualizations (e.g., line chart and column chart for balances) to improve interactivity.
