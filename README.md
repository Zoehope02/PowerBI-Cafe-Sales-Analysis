# PowerBI-Cafe-Sales-Analysis
This project focused on data cleaning using a 10,000-row synthetic cafe sales dataset intentionally filled with missing values, inconsistencies, and errors to simulate real-world scenarios for cleaning and exploratory data analysis (EDA).
Here’s a clear and concise way to state your data cleaning steps:

**Data Cleaning Steps:**

1. **Handled Missing and Invalid Values:** Replaced empty values, as well as entries labeled `'unknown'` and `'error'`, with `'Other'` in the `Item`, `Location`, and `Payment Method` columns.

2. **Fixed Data Types:** Converted the `Price Per Unit` column from text to numeric by replacing period (`.`) separators with commas (`,`).

3. **Calculated Missing Totals:** For rows where `Total Spent` was null but both `Quantity` and `Price Per Unit` were valid numbers, I used the following M code to compute the missing values:

```m
if [Total Spent] = null and 
   [Quantity] <> null and 
   [Price Per Unit] <> null and 
   Value.Is([Quantity], type number) and 
   Value.Is([Price Per Unit], type number) then
    [Quantity] * [Price Per Unit]
else
    [Total Spent]
```
## How to Use
Download the `.pbix` file and open it in Power BI Desktop.
## Dashboard Preview

![Dashboard](./overview.png)
