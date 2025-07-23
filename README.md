Cost and Profitablity Analysis:


Business Problem
XYZ Delivery company based in Delhi has a problem of low revenue and high cost in the business. The goal is to identify areas where the service can reduce costs, increase revenue, and implement pricing or commission strategies that enhance profitability.

Data Overview:
The dataset food_orders_new_delhi.csv contains 1,000 entries with 12 columns, detailing food delivery orders for XYZ Delivery company in Delhi. Here's a concise overview based on the provided analysis:
Columns and Data Types: 
Order ID (int64): Unique identifier for each order.
Customer ID (object): Unique customer identifier.
Restaurant ID (object): Unique restaurant identifier.
Order Date and Time (datetime64): Timestamp of order placement.
Delivery Date and Time (datetime64): Timestamp of delivery completion.
Order Value (int64): Monetary value of the order in INR.
Delivery Fee (int64): Fee charged for delivery.
Payment Method (object): Payment type (e.g., Credit Card, Digital Wallet, Cash on Delivery).
Discounts and Offers (object): Discount details (e.g., "5% on App", "50 off Promo"), with 185 missing values initially, filled with "0.0".
Commission Fee (int64): Fee charged to restaurants.
Payment Processing Fee (int64): Fee for processing payments.
Refunds/Chargebacks (int64): Refund or chargeback amounts.

Steps :
·  Data Import and Initial Exploration: 
Loaded the dataset food_orders_new_delhi.csv using Pandas.
Examined dataset structure with info(), identifying 1,000 entries, 12 columns, and 185 missing values in the Discounts and Offers column (19.5% missing).
·  Data Cleaning: 
Filled missing values in Discounts and Offers with "0.0" to ensure no nulls remain.
Converted Order Date and Time and Delivery Date and Time columns to datetime64 format for consistent time-based analysis.
Verified cleaning by rechecking for null values and dataset structure.
·  Discount Processing: 
Created a function extract_discount to parse Discounts and Offers into numerical values (e.g., "5% on App" → 5.0, "50 off Promo" → 50.0).
Added a Discount Percentage column by applying the function to extract percentage or fixed discount values.
Calculated Discount Amount by applying discounts to Order Value: 
For percentage discounts (>1%), computed as (Order Value * Discount Percentage / 100).
For fixed discounts, used the extracted value directly.
·  Profitability Analysis: 
Filtered dataset for profitable orders (where Profit > 0, assuming Profit was calculated elsewhere in the notebook).
Calculated Commission Percentage as (Commission Fee / Order Value) * 100 for profitable orders.
Calculated Effective Discount Percentage as (Discount Amount / Order Value) * 100 for profitable orders.
Computed averages for profitable orders: 
Average Commission Percentage: 30.51%.
Average Discount Percentage: 5.87%.
·  Visualization: 
Created a bar chart using Matplotlib to compare total revenue, total costs, and total profit (values not provided in the snippet but referenced).
The chart highlighted that costs exceed revenue, resulting in a net loss.
·  Strategic Recommendation: 
Identified a "sweet spot" for profitability based on profitable orders: ~30.51% commission and ~5.87% discount.
Suggested these percentages as a guideline for pricing and commission strategies to reduce losses.



Summary:
The analysis of XYZ Delivery company's operations in Delhi reveals that high discounts are leading to significant financial losses, with total costs exceeding revenue. By examining profitable orders, an average commission percentage of 30.51% and an average discount percentage of 5.87% were identified as a potential "sweet spot" for profitability. The dataset was cleaned, with missing discount values filled and date-time formats standardized for accurate analysis. A bar chart visually confirms the gap between revenue, costs, and the resulting loss. Implementing these new commission and discount percentages could help optimize pricing strategies and enhance profitability.
