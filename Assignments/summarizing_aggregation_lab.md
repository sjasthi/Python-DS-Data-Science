# Pandas Summarizing and Aggregation Lab
**Total Points: 10**

---

## Objective
Practice pandas data summarization and aggregation techniques including basic statistics, groupby operations, and multiple aggregation functions.

## Prerequisites
- Python 3.x
- pandas library
- numpy library

## Setup
Run the following code to create your dataset:

```python
import pandas as pd
import numpy as np

# Create sample sales data
data = {
    'Region': ['North', 'South', 'East', 'West', 'North', 'South', 'East', 'West',
               'North', 'South', 'East', 'West', 'North', 'South', 'East', 'West'],
    'Product': ['Laptop', 'Laptop', 'Laptop', 'Laptop', 'Phone', 'Phone', 'Phone', 'Phone',
                'Tablet', 'Tablet', 'Tablet', 'Tablet', 'Monitor', 'Monitor', 'Monitor', 'Monitor'],
    'Sales': [45000, 38000, 52000, 41000, 28000, 35000, 31000, 29000,
              15000, 18000, 16000, 14000, 22000, 25000, 21000, 23000],
    'Units': [30, 25, 35, 28, 140, 175, 155, 145, 75, 90, 80, 70, 88, 100, 84, 92]
}

df = pd.DataFrame(data)
print(df)
```

## Tasks

### Task 1: Basic Summary Statistics (2 points)
Calculate and display the following for the entire dataset:
- Mean sales
- Median sales
- Standard deviation of units sold
- Minimum and maximum sales values

### Task 2: Group by Region (3 points)
Group the data by Region and calculate:
- Total sales for each region
- Average units sold per region
- Display the results sorted by total sales in descending order

### Task 3: Group by Product (2 points)
Group the data by Product and find:
- The total units sold for each product
- The average sales value for each product

### Task 4: Multiple Aggregations (3 points)
Group the data by Product and calculate multiple statistics at once:
- For Sales: sum, mean, and max
- For Units: sum and mean

Display this as a nicely formatted table using the `agg()` function.

## Submission Guidelines
- Submit a Python script (.py) or Jupyter notebook (.ipynb)
- Include comments explaining your code
- Ensure all outputs are clearly labeled
- Test your code to ensure it runs without errors

