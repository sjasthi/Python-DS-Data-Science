# Pandas GroupBy and Pivots Lab
**Total Points: 10**

---

## Objective
Master pandas groupby operations and pivot table creation for data analysis and reshaping. Learn to transform data between long and wide formats and perform multi-level aggregations.

## Prerequisites
- Python 3.x
- pandas library
- numpy library

## Setup
Run the following code to create your dataset:

```python
import pandas as pd
import numpy as np

# Create sample employee data
data = {
    'Department': ['Sales', 'Sales', 'Sales', 'Engineering', 'Engineering', 'Engineering',
                   'Marketing', 'Marketing', 'Marketing', 'Sales', 'Sales', 'Sales',
                   'Engineering', 'Engineering', 'Engineering', 'Marketing', 'Marketing', 'Marketing'],
    'Location': ['NYC', 'NYC', 'LA', 'NYC', 'NYC', 'LA', 
                 'NYC', 'LA', 'LA', 'LA', 'NYC', 'LA',
                 'LA', 'NYC', 'LA', 'NYC', 'NYC', 'LA'],
    'Quarter': ['Q1', 'Q2', 'Q3', 'Q1', 'Q2', 'Q3',
                'Q1', 'Q2', 'Q3', 'Q4', 'Q4', 'Q1',
                'Q4', 'Q3', 'Q2', 'Q4', 'Q3', 'Q4'],
    'Revenue': [125000, 132000, 128000, 95000, 98000, 102000,
                75000, 78000, 82000, 135000, 130000, 118000,
                105000, 99000, 96000, 79000, 81000, 85000],
    'Employees': [12, 12, 13, 8, 8, 9, 
                  6, 7, 7, 14, 13, 12,
                  9, 8, 8, 6, 7, 8]
}

df = pd.DataFrame(data)
print(df)
```

## Tasks

### Task 1: Basic GroupBy Operations (2 points)
Group the data by Department and calculate:
- Total revenue for each department
- Average number of employees per department
- Count how many records exist for each department

### Task 2: Multiple Column GroupBy (2 points)
Group the data by both Department AND Location, then:
- Calculate the total revenue for each Department-Location combination
- Find the maximum revenue achieved by each Department-Location pair
- Reset the index to make the result easier to read

### Task 3: Simple Pivot Table (2 points)
Create a pivot table that shows:
- Departments as rows
- Locations as columns
- Total revenue as values
- Display the result and identify which Department-Location combination has the highest revenue

### Task 4: Advanced Pivot Table (2 points)
Create a pivot table that shows:
- Quarters as rows
- Departments as columns
- Average revenue as values
- Include row and column totals (margins)

### Task 5: Pivot with Multiple Aggregations (2 points)
Create a pivot table that shows:
- Departments as rows
- Locations as columns
- For the values, display BOTH sum of Revenue AND mean of Employees
- Use the `aggfunc` parameter to specify multiple aggregation functions

## Submission Guidelines
- Submit a Python script (.py) or Jupyter notebook (.ipynb)
- Include comments explaining your code
- Ensure all outputs are clearly labeled
- Test your code to ensure it runs without errors

## Helpful Tips
- Use `pd.pivot_table()` for creating pivot tables
- Remember that `groupby()` returns a GroupBy object that you can aggregate
- Use `.reset_index()` to convert grouped data back to a regular DataFrame
- The `margins=True` parameter in pivot_table adds totals
- You can pass a list of functions to `aggfunc` parameter: `aggfunc=['sum', 'mean']`
