# Pandas Merge Operations Lab
**Total Points: 10**

---

## Objective
Master pandas merge and join operations to combine multiple datasets. Learn to use different merge types (inner, outer, left, right) and understand how to handle keys and combine related data sources.

## Prerequisites
- Python 3.x
- pandas library
- numpy library

## Setup
Run the following code to create your datasets:

```python
import pandas as pd
import numpy as np

# Customer information
customers = pd.DataFrame({
    'CustomerID': [101, 102, 103, 104, 105, 106],
    'Name': ['Alice Johnson', 'Bob Smith', 'Carol White', 'David Brown', 'Eve Davis', 'Frank Miller'],
    'City': ['NYC', 'LA', 'Chicago', 'Houston', 'Phoenix', 'NYC']
})

# Order information
orders = pd.DataFrame({
    'OrderID': [1001, 1002, 1003, 1004, 1005, 1006, 1007, 1008],
    'CustomerID': [101, 102, 101, 105, 103, 107, 102, 104],
    'OrderDate': ['2024-01-15', '2024-01-16', '2024-01-18', '2024-01-20', 
                  '2024-01-22', '2024-01-23', '2024-01-25', '2024-01-26'],
    'TotalAmount': [250.00, 180.00, 320.00, 150.00, 420.00, 90.00, 275.00, 380.00]
})

# Product details
products = pd.DataFrame({
    'ProductID': ['P1', 'P2', 'P3', 'P4', 'P5'],
    'ProductName': ['Laptop', 'Mouse', 'Keyboard', 'Monitor', 'Headphones'],
    'Price': [800, 25, 75, 300, 150]
})

# Order items (which products were in each order)
order_items = pd.DataFrame({
    'OrderID': [1001, 1001, 1002, 1003, 1003, 1004, 1005, 1006, 1007, 1008],
    'ProductID': ['P1', 'P2', 'P2', 'P1', 'P4', 'P5', 'P3', 'P2', 'P4', 'P1'],
    'Quantity': [1, 2, 3, 1, 1, 1, 2, 1, 1, 1]
})

print("Customers:")
print(customers)
print("\nOrders:")
print(orders)
print("\nProducts:")
print(products)
print("\nOrder Items:")
print(order_items)
```

## Tasks

### Task 1: Inner Merge (2 points)
Perform an **inner merge** between the `orders` and `customers` DataFrames on the `CustomerID` column.
- Display the resulting DataFrame
- How many rows are in the result? Why are some customers or orders missing?
- Include a comment explaining what an inner merge does

### Task 2: Left Merge (2 points)
Perform a **left merge** between the `orders` DataFrame (left) and `customers` DataFrame (right) on `CustomerID`.
- Display the resulting DataFrame
- Identify which order(s) have no matching customer information
- What do you notice about the customer information for OrderID 1006?

### Task 3: Outer Merge (2 points)
Perform an **outer merge** (full outer join) between `customers` and `orders` on `CustomerID`.
- Display the resulting DataFrame
- Identify which customers have never placed an order
- Identify which orders have no matching customer
- Use the `indicator=True` parameter to show the source of each row

### Task 4: Multiple Merges (2 points)
Combine multiple DataFrames to create a comprehensive report:
- Start by merging `order_items` with `products` to get product names and prices
- Then merge the result with `orders` to get order dates and totals
- Display the first 10 rows of the final DataFrame
- The result should show: OrderID, ProductID, ProductName, Price, Quantity, OrderDate, TotalAmount

### Task 5: Merge with Aggregation (2 points)
Create a summary that shows total spending per customer:
- Merge `orders` with `customers`
- Group by customer name and city
- Calculate the total amount spent by each customer
- Sort the results by total spending in descending order
- Display customers who have placed orders

## Submission Guidelines
- Submit a Python script (.py) or Jupyter notebook (.ipynb)
- Include comments explaining your code and answering the questions in each task
- Ensure all outputs are clearly labeled
- Test your code to ensure it runs without errors

## Helpful Tips
- Use `how='inner'` for inner merge (default)
- Use `how='left'` for left merge
- Use `how='right'` for right merge
- Use `how='outer'` for full outer merge
- Use `on='ColumnName'` when column names are the same in both DataFrames
- Use `left_on` and `right_on` when column names differ
- Use `indicator=True` to see which DataFrame each row came from
- You can chain multiple merge operations together
- Use `.merge()` method or `pd.merge()` function
