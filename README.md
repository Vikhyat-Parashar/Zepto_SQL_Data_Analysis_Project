🛒 Zepto Product Data Analysis (SQL-Based Retail Analytics Project)

🔍 Business Problem

A quick-commerce platform (like Zepto) needs to optimize:

Product pricing strategy
Inventory management
Discount effectiveness
Category-level performance

Key question:
“How can product data be leveraged to maximize revenue, improve inventory decisions, and identify high-value products?”

📁 Dataset Overview
Product-level dataset containing:
Category, Product Name
MRP & Discounted Price
Discount %
Inventory (available quantity)
Product weight
Stock availability
🛠️ Tech Stack
SQL (MySQL) → Data cleaning & analysis

⚙️ Project Workflow

1. Data Exploration
Checked total number of records
Identified:
Null values
Duplicate product entries
Unique product categories
Analyzed stock availability (in-stock vs out-of-stock)
2. Data Cleaning
Removed invalid records (MRP = 0)
Converted pricing units (paise → rupees)
Ensured consistency across price-related fields

👉 Example:

UPDATE zepto
SET mrp = mrp / 100.0,
    discountedSellingPrice = discountedSellingPrice / 100.0;

3. SQL-Based Business Analysis

Executed multiple real-world business queries:

🔑 Key Analyses:

1. Best Discounted Products

Identified top 10 products with highest discount %

2. High-Value Out-of-Stock Items

Found expensive products unavailable in inventory

3. Revenue Estimation

Calculated total potential revenue per category
SELECT category,
SUM(discountedSellingPrice * availableQuantity) AS total_revenue
FROM zepto
GROUP BY category;

4. Pricing Strategy Insights

Products with high MRP but low discounts

5. Category-Level Discount Trends

Top categories offering highest average discounts

6. Unit Economics (Price per Gram)

Identified best-value products based on price/weight

7. Product Segmentation

Categorized products into:
Low
Medium
Bulk

8. Inventory Weight Analysis

Total inventory weight per category
📊 Key Insights & Findings
Some high-MRP products remain out of stock, indicating demand-supply mismatch
Certain categories consistently offer higher discounts, affecting margins
Price-per-gram analysis reveals true value products, not visible via MRP alone
Inventory is unevenly distributed across categories
Duplicate SKUs exist → potential catalog inefficiency

💡 Business Recommendations
📦 Restock high-MRP out-of-stock products to avoid revenue loss
💰 Optimize discount strategy for high-margin categories
📊 Promote best-value (low price/gram) products
🧹 Clean duplicate product listings for better catalog efficiency
📈 Balance inventory across categories based on demand

📈 Deliverables
SQL scripts for data cleaning & analysis
