# Sales Data Analysis with Python

A practical Python project developed to analyze retail sales data, calculate key revenue metrics, and derive actionable business insights.

## 📊 Project Overview
The script processes product sales data (Laptops, Mice, Keyboards) to automate financial calculations and identify product performance.

### Key Metrics Calculated:
* **Total Revenue:** 17,650 MAD
* **Revenue by Product:**
  * **Laptop:** 16,000 MAD (90.65% of total revenue)
  * **Mouse:** 1,050 MAD (5.95% of total revenue)
  * **Keyboard:** 600 MAD (3.40% of total revenue)

## 💻 Python Implementation

```python
products = ["Laptop", "Mouse", "Keyboard", "Laptop", "Mouse"]
prices = [8000, 150, 300, 8000, 150]
quantities = [1, 3, 2, 1, 4]

total_sales = 0
sales_by_product = {}

# Calculate total sales and sales per product
for i in range(len(products)):
    sale = prices[i] * quantities[i]
    total_sales += sale

    if products[i] in sales_by_product:
        sales_by_product[products[i]] += sale
    else:
        sales_by_product[products[i]] = sale

# Identify best-selling product
best_product = max(sales_by_product, key=sales_by_product.get)

print("Sales by product:", sales_by_product)
print("Total sales:", total_sales, "MAD")
print("Best product:", best_product, "-", sales_by_product[best_product], "MAD")

# Calculate sales percentage by product
print("\nSales percentage by product:")
for product in sales_by_product:
    percentage = (sales_by_product[product] / total_sales) * 100
    print(f"{product}: {round(percentage, 2)}%")
