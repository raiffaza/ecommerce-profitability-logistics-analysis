# E-Commerce Sales, Customer & Operations Analysis (2021-2025)

An end-to-end Exploratory Data Analysis (EDA) and data quality audit of a multi-market e-commerce dataset covering **397,569 order line items** across **138,116 unique orders** from January 2021 to December 2025.

## Dataset & Schema Architecture
- **Source:** [Kaggle - E-Commerce Sales and Customer Analytics](https://www.kaggle.com/datasets/datascikhan/e-commerce-sales-and-customer-analytics?select=product_catalog.csv)
- **Merged Tables:** `order_items.csv` (base table) left-joined with `ecommerce_sales_customer_analytics_150k.csv` and `product_catalog.csv` into `E-commerce_Dataset.csv` (397,569 rows x 65 columns).
- **Granularity Rules:** Line-level metrics (`*_item`) are aggregated directly on the base table, while order-level totals (`*_order`) and customer attributes are deduplicated by `order_id` to prevent double-counting.

## Key Diagnostic Findings
1. **Structural Missing Values (Zero Rows Dropped):** All 1,651,269 null cells (6.39%) reflect business logic rather than data corruption, including 70,541 unkept orders lacking delivery/review records and 10,426 cancelled/returned orders whose coupon discounts were reset to $0.
2. **The Q4 Revenue-Profit Paradox:** Within the primary USD market (59.9% of completed orders, $90.88M net sales), monthly sales surge past $2.0M every November and December (peaking at $2.28M in Dec 2023), while monthly profit stays flat between $550K and $620K.
3. **Volume vs. Margin Inversion:** Electronics leads revenue ($19.34M | 21.3%) with the lowest margin (30.5%), whereas smaller categories like Grocery (52.6%) and Beauty & Personal Care (49.7%) deliver higher profitability efficiency.
4. **Upstream Fulfillment Bottlenecks:** Delivery delay rates sit uniformly at 14.5% to 15.0% across Economy, Standard, Express, and Same Day tiers, reducing average customer ratings by 0.51 stars (from 3.73 to 3.22).

## Repository Structure
- `E-commerce.ipynb` — Full Python notebook covering schema joins, missing value forensics, cross-field validation, and EDA visualizations.
- `E-Commerce Sales, Customer & Operations Analysis (2021-2025).pdf`

## Dataset
- You can access it from [https://www.kaggle.com/datasets/datascikhan/e-commerce-sales-and-customer-analytics?select=product_catalog.csv]
