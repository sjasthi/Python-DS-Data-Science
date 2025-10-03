# Assignment
# Mastering Pandas GroupBy and Pivot Operations

---

## 🎯 Learning Objectives

By completing this exercise, you will be able to:
- Understand and implement the Split-Apply-Combine methodology using GroupBy
- Create and manipulate grouped objects for data aggregation
- Apply multiple aggregation functions to grouped data
- Use pivot tables and pivot operations for data reshaping
- Transform data between wide and long formats
- Perform complex multi-level grouping and analysis
- Create cross-tabulations and frequency tables
- Apply advanced GroupBy techniques including custom functions

---

## 📚 Prerequisites

**Required Reading:** Review the class notebook before starting this assignment:
[GroupBy and Pivot Operations](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/2_pandas_groupby_and_pivot.ipynb)

**Key Concepts to Understand:**
- Split-Apply-Combine methodology
- GroupBy object properties and methods
- Aggregation vs. Transformation vs. Filtration
- Pivot tables vs. Pivot operations
- Multi-level indexing in grouped data

---

## 🚀 Setup Instructions

### Step 1: Create a New Google Colab Notebook
1. Go to [Google Colab](https://colab.research.google.com)
2. Create a new notebook
3. Rename it: `YourLastName_FirstName_Pandas_GroupBy_and_Pivot.ipynb`

### Step 2: Import Required Libraries
```python
# Import the necessary libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Set display options for better output
pd.set_option('display.max_columns', None)
pd.set_option('display.width', None)

# Check versions
print("Pandas version:", pd.__version__)
print("NumPy version:", np.__version__)
```

---

## 🏢 Part 1: Understanding Split-Apply-Combine with GroupBy (10 points)

### Task 1.1: Creating Sample Datasets (2 points)

**Your Challenge:** Create three datasets that will serve as the foundation for all GroupBy operations in this assignment.

**Dataset 1: Sales Data**
```python
# Create comprehensive sales dataset
np.random.seed(42)

sales_data = {
    'date': pd.date_range('2023-01-01', periods=500, freq='D'),
    'salesperson': np.random.choice(['Alice', 'Bob', 'Charlie', 'Diana', 'Eve'], 500),
    'region': np.random.choice(['North', 'South', 'East', 'West'], 500),
    'product_category': np.random.choice(['Electronics', 'Clothing', 'Home', 'Books'], 500),
    'product': np.random.choice(['Laptop', 'Phone', 'Tablet', 'Shirt', 'Shoes', 'Sofa', 
                                'Chair', 'Novel', 'Textbook'], 500),
    'units_sold': np.random.randint(1, 20, 500),
    'unit_price': np.round(np.random.uniform(10, 500, 500), 2),
    'customer_type': np.random.choice(['New', 'Returning', 'Premium'], 500)
}
```

**Dataset 2: Employee Performance**
```python
# Create employee performance dataset
employee_data = {
    'employee_id': range(1, 101),
    'name': [f'Employee_{i}' for i in range(1, 101)],
    'department': np.random.choice(['IT', 'Sales', 'Marketing', 'HR', 'Finance'], 100),
    'position': np.random.choice(['Junior', 'Senior', 'Manager', 'Director'], 100),
    'salary': np.round(np.random.normal(70000, 15000, 100), 0),
    'years_experience': np.random.randint(1, 15, 100),
    'performance_score': np.round(np.random.normal(75, 10, 100), 1),
    'training_hours': np.random.randint(0, 80, 100)
}
```

**Dataset 3: Student Academic Records**
```python
# Create student academic dataset
subjects = ['Math', 'Science', 'English', 'History', 'Art']
students = [f'Student_{i}' for i in range(1, 51)]
semesters = ['Fall_2022', 'Spring_2023', 'Fall_2023', 'Spring_2024']

academic_records = []
for student in students:
    for semester in semesters:
        for subject in subjects:
            record = {
                'student_id': student,
                'semester': semester,
                'subject': subject,
                'grade': np.random.choice(['A', 'B', 'C', 'D', 'F'], p=[0.3, 0.4, 0.2, 0.08, 0.02]),
                'credits': np.random.choice([3, 4], p=[0.7, 0.3]),
                'attendance_rate': np.round(np.random.uniform(0.7, 1.0), 2)
            }
            academic_records.append(record)
```

**Your Task:**
1. Create all three DataFrames using the code above
2. Add calculated columns:
   - For sales_data: `total_revenue` = units_sold × unit_price
   - For employee_data: `salary_per_experience` = salary ÷ years_experience
   - For academic_data: Convert grades to GPA points (A=4, B=3, C=2, D=1, F=0)
3. Display basic information about each dataset

```python
# Your code here - Create the three datasets

# Sales DataFrame


# Employee DataFrame


# Academic DataFrame


# Add calculated columns and display info

```

### Task 1.2: Basic GroupBy Operations (4 points)

**Your Challenge:** Implement the Split-Apply-Combine methodology step by step.

**Part A: Understanding the Split Phase**
1. Group sales data by `region` and examine the GroupBy object
2. Group employee data by `department` and explore group keys
3. Group academic data by `semester` and understand group sizes

**Part B: Apply Phase - Single Aggregations**
1. Calculate total revenue by region
2. Find average salary by department
3. Count courses taken by semester

**Part C: Apply Phase - Multiple Aggregations**
1. For sales data: Calculate sum, mean, and count of revenue by salesperson
2. For employee data: Get min, max, and std of salary by position
3. For academic data: Calculate average GPA and attendance by student

**Part D: Combine Phase Analysis**
1. Explain what happens during the combine phase
2. Show how to access specific groups from GroupBy objects
3. Demonstrate iterating through groups

```python
# Part A: Split Phase Exploration


# Part B: Single Aggregations


# Part C: Multiple Aggregations


# Part D: Combine Phase Analysis

```

### Task 1.3: Advanced GroupBy Techniques (4 points)

**Your Challenge:** Master advanced grouping operations:

**Multi-level Grouping:**
1. Group sales by both `region` and `product_category`
2. Calculate revenue statistics for each region-category combination
3. Group employees by `department` and `position`
4. Find performance metrics for each department-position pair

**Custom Aggregation Functions:**
1. Create a custom function to calculate the revenue range (max - min) for each group
2. Apply a lambda function to find the top 2 performers in each department
3. Use agg() with custom functions to get complex summaries

**GroupBy with Transformation:**
1. Calculate each salesperson's performance relative to their region average
2. Compute z-scores for salary within each department
3. Add ranking columns within groups

```python
# Multi-level Grouping


# Custom Aggregation Functions


# GroupBy Transformations

```

---

## 📊 Part 2: Mastering Pivot Tables and Operations (8 points)

### Task 2.1: Basic Pivot Tables (3 points)

**Your Challenge:** Create meaningful pivot tables from your datasets:

**Sales Analysis Pivots:**
1. Create a pivot table showing total revenue by region (rows) and product_category (columns)
2. Make a pivot table with salesperson as rows, customer_type as columns, and units_sold as values
3. Build a time-series pivot with months as rows and regions as columns

**Employee Analysis Pivots:**
1. Pivot showing average salary by department (rows) and position (columns)
2. Create a pivot of performance scores by department and years of experience bins
3. Make a training hours analysis by department and position

**Academic Performance Pivots:**
1. Student GPA by semester (rows) and subject (columns)
2. Attendance rates by student and semester
3. Grade distribution across subjects and semesters

```python
# Sales Analysis Pivots


# Employee Analysis Pivots


# Academic Performance Pivots

```

### Task 2.2: Advanced Pivot Operations (3 points)

**Your Challenge:** Implement sophisticated pivot techniques:

**Multiple Aggregations in Pivots:**
1. Create a pivot table with multiple statistics (sum, mean, count) for sales revenue
2. Use different aggregation functions for different value columns
3. Implement margins (totals) in your pivot tables

**Pivot with Custom Functions:**
1. Create a pivot using custom aggregation functions
2. Apply percentage calculations within pivot tables
3. Use pivot tables with date/time grouping (monthly, quarterly)

**Handling Missing Data in Pivots:**
1. Create pivots with fill_value parameter
2. Demonstrate dropna parameter effects
3. Show how to handle sparse data in pivots

```python
# Multiple Aggregations in Pivots


# Pivot with Custom Functions


# Handling Missing Data

```

### Task 2.2: Pivot vs. Pivot_table vs. Crosstab (2 points)

**Your Challenge:** Understand when to use each method:

**Pivot Method:**
1. Reshape academic data from long to wide format using pivot()
2. Create a simple restructured view of sales data
3. Show limitations of pivot() method

**Pivot_table Method:**
1. Recreate the same reshaping using pivot_table()
2. Demonstrate aggregation capabilities of pivot_table()
3. Show how pivot_table() handles duplicate entries

**Crosstab Method:**
1. Create frequency tables using pd.crosstab()
2. Analyze relationships between categorical variables
3. Add margins and normalize crosstabs

```python
# Pivot Method Examples


# Pivot_table Method Examples


# Crosstab Method Examples

```

---

## 🔄 Part 3: Data Reshaping and Advanced Applications (7 points)

### Task 3.1: Melt and Stack Operations (3 points)

**Your Challenge:** Master data reshaping techniques:

**Using Melt:**
1. Transform a pivot table back to long format using melt()
2. Create a normalized dataset from wide employee data
3. Melt academic data with multiple value columns

**Using Stack/Unstack:**
1. Convert hierarchical indexes using stack()
2. Use unstack() to create pivot-like results
3. Demonstrate level parameter in stack/unstack operations

**Wide to Long Transformations:**
1. Create scenarios requiring wide-to-long conversion
2. Handle multiple variable columns in melt operations
3. Preserve identifier columns during reshaping

```python
# Melt Operations


# Stack/Unstack Operations


# Wide to Long Transformations

```

### Task 3.2: Complex Multi-Index Operations (4 points)

**Your Challenge:** Work with hierarchical data structures:

**Creating Multi-Index DataFrames:**
1. Build multi-index DataFrames from grouped operations
2. Create hierarchical columns from pivot operations
3. Construct multi-level indexes manually

**Multi-Index Navigation:**
1. Select data using multi-level indexing
2. Perform operations on specific index levels
3. Reset and set index levels appropriately

**Advanced Multi-Index Analysis:**
1. Calculate subtotals and totals in hierarchical data
2. Apply functions across different index levels
3. Create summary reports with multi-level grouping

```python
# Creating Multi-Index DataFrames


# Multi-Index Navigation


# Advanced Multi-Index Analysis

```



---

## 📝 Deliverables and Submission

### What to Submit:
1. **Completed Google Colab Notebook**
   - Download as .ipynb file
   - Name: `YourLastName_FirstName_Pandas_GroupBy_Pivot.ipynb`

2. **Analysis Report**
   - Include markdown cells with insights from each section
   - Provide business interpretations of your findings
   - Suggest actionable recommendations

3. **Share Your Colab Link**
   - Make sure link sharing is enabled
   - Include this link in your submission comments

### Notebook Requirements:
- All code cells must run without errors
- Include comprehensive markdown explanations
- Show clear understanding of split-apply-combine concepts
- Demonstrate practical applications of pivot operations
- Provide business context for technical operations

---

## 🎯 Grading Rubric (25 points + 5 bonus)

| Component | Points | What We're Looking For |
|-----------|--------|----------------------|
| **Part 1: GroupBy Mastery** | 10 | Understanding split-apply-combine, advanced grouping |
| **Part 2: Pivot Operations** | 8 | Correct pivot techniques, multiple aggregations |
| **Part 3: Data Reshaping** | 7 | Melt/stack operations, multi-index handling |
| **Real-World Applications** | 5 (Bonus) | Creative problem-solving, business insights |

### Detailed Grading Criteria:

**Excellent (90-100%):**
- Perfect implementation of all GroupBy and pivot concepts
- Demonstrates deep understanding of split-apply-combine methodology
- Creates meaningful business insights from technical operations
- Code is clean, efficient, and well-documented

**Good (80-89%):**
- Solid grasp of core concepts with minor implementation errors
- Shows understanding of when to use different techniques
- Provides adequate documentation and explanations

**Satisfactory (70-79%):**
- Basic requirements met with some conceptual gaps
- Limited application of advanced techniques
- Minimal business context provided

**Needs Improvement (<70%):**
- Significant conceptual misunderstandings
- Incomplete implementation of required techniques
- Poor code organization and documentation

---

## 💡 Key Concepts Checklist

Before submitting, ensure you can explain:

### GroupBy Concepts:
- [ ] What happens in each phase of split-apply-combine
- [ ] Difference between aggregation, transformation, and filtration
- [ ] How to apply multiple aggregation functions
- [ ] When to use custom aggregation functions
- [ ] Multi-level grouping strategies

### Pivot Concepts:
- [ ] When to use pivot() vs pivot_table() vs crosstab()
- [ ] How to handle duplicate values in pivot operations
- [ ] Creating multi-level pivot tables
- [ ] Adding margins and totals to pivots
- [ ] Normalizing and percentage calculations in pivots

### Data Reshaping:
- [ ] Converting between wide and long formats
- [ ] Using melt() effectively with multiple variables
- [ ] Stack and unstack operations on multi-index data
- [ ] Working with hierarchical indexes
- [ ] Preserving data integrity during reshaping

---

## 🔧 Troubleshooting Guide

### Common GroupBy Issues:
- **KeyError in groupby:** Check column names and case sensitivity
- **Multiple aggregation functions:** Use agg() with dictionary or list
- **Custom functions not working:** Ensure functions return appropriate data types
- **Performance issues:** Consider using categorical data for grouping columns

### Common Pivot Issues:
- **Values column required:** Pivot tables need explicit value columns
- **Duplicate entries:** Use pivot_table() instead of pivot()
- **Missing values:** Use fill_value parameter or handle NaNs explicitly
- **Memory issues:** Consider using sparse matrices for large pivot tables

### Data Reshaping Issues:
- **Lost data during melt:** Check id_vars and value_vars parameters
- **Index problems:** Reset index before reshaping operations
- **Column naming:** Use appropriate column names after reshape operations

---

## 📚 Additional Resources

- [Pandas GroupBy Documentation](https://pandas.pydata.org/docs/user_guide/groupby.html)
- [Pivot Table Guide](https://pandas.pydata.org/docs/user_guide/reshaping.html)
- [Split-Apply-Combine Paper](https://www.jstatsoft.org/article/view/v040i01)
- [Data Reshaping Techniques](https://pandas.pydata.org/docs/user_guide/reshaping.html)

---

## 🏆 Success Tips

1. **Start Simple:** Begin with basic groupby operations before moving to complex multi-level grouping
2. **Visualize the Process:** Draw out the split-apply-combine steps for complex operations
3. **Practice with Small Data:** Test your logic on small subsets before applying to full datasets
4. **Document Your Logic:** Explain why you chose specific aggregation functions
5. **Think Business Context:** Always connect technical operations to real-world applications
6. **Test Edge Cases:** Consider how your code handles missing data and empty groups

**Remember:** GroupBy and Pivot operations are the foundation of data analysis. Master these concepts, and you'll be able to extract insights from any dataset efficiently and effectively!

**Good luck! 📊🔍**
