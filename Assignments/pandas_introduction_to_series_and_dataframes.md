# DSCI 2001-51 Data Science I
# Introduction to Pandas Series and DataFrames

---

## 🎯 Learning Objectives

By completing this exercise, you will be able to:
- Create and manipulate pandas Series objects
- Create DataFrames from various data sources
- Access and modify DataFrame elements using different methods
- Perform basic operations on Series and DataFrames
- Understand the relationship between Series and DataFrames
- Apply pandas methods for data exploration and basic analysis

---

## 📚 Prerequisites

**Required Reading:** Review the class notebook before starting this assignment:
[Introduction to Series and DataFrames](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/1_pandas_intro_to_series_and_dataframe.ipynb)

---

## 🚀 Setup Instructions

### Step 1: Create a New Google Colab Notebook
1. Go to [Google Colab](https://colab.research.google.com)
2. Create a new notebook
3. Rename it: `YourLastName_FirstName_Pandas_Intro_to_Series_and_Dataframe.ipynb`

### Step 2: Import Required Libraries
```python
# Import the necessary libraries
import pandas as pd
import numpy as np

# Check versions (run this to ensure compatibility)
print("Pandas version:", pd.__version__)
print("NumPy version:", np.__version__)
```

---

## 📊 Part 1: Working with Pandas Series (8 points)

### Task 1.1: Creating Series Objects (3 points)

**Your Challenge:** Create three different Series objects using the data provided below. For each Series, you must determine the appropriate method to create it and then analyze its properties.

**Data to work with:**
- **Temperature data:** `[68, 72, 75, 71, 69, 73, 76, 78, 74, 70]` (daily temperatures in Fahrenheit)
- **Student grades:** Alice: 92, Bob: 87, Charlie: 94, Diana: 89, Eve: 91
- **Daily steps:** Monday: 8500, Tuesday: 7200, Wednesday: 9100, Thursday: 6800, Friday: 7500, Saturday: 12000, Sunday: 11500

**What you need to do:**
1. Create a Series for temperature data with the name 'Temperature_F'
2. Create a Series for student grades using appropriate index labels
3. Create a Series for daily steps with day names as the index

**Questions to answer for each Series:**
- What is the shape of the Series?
- What is the data type?
- What type of index does it have?
- Print the first 3 values

```python
# Your code here for creating the three Series

# Temperature Series


# Student grades Series


# Daily steps Series


# Answer the questions for each Series

```

### Task 1.2: Series Operations (3 points)

**Your Challenge:** Using the Series you created above, perform the following operations:

1. **Temperature Analysis:**
   - Calculate mean, median, minimum, and maximum temperature
   - Convert the entire temperature Series from Fahrenheit to Celsius using the formula: C = (F - 32) × 5/9
   - Find how many days had temperature above the average

2. **Student Performance:**
   - Find students who scored above 90
   - Calculate the class average
   - Determine who scored the highest and lowest

3. **Activity Tracking:**
   - Find the day with maximum steps
   - Calculate average daily steps
   - Identify weekend vs weekday average steps

```python
# Your code here - Temperature Analysis


# Your code here - Student Performance Analysis


# Your code here - Activity Analysis

```

### Task 1.3: Series Indexing Practice (2 points)

**Your Challenge:** Practice different indexing methods on your Series:

1. Use **label-based indexing (.loc[])** to:
   - Get Wednesday's step count
   - Get Alice's and Charlie's grades
   - Get temperatures for positions 2, 4, and 6

2. Use **position-based indexing (.iloc[])** to:
   - Get the first 3 temperatures
   - Get the last 2 grades
   - Get every other step count (positions 0, 2, 4, 6)

3. Use **boolean indexing** to:
   - Find days with steps > 8000
   - Find students with grades between 88 and 93
   - Find temperatures below 70°F

```python
# Your indexing code here
# Label-based indexing (.loc[])


# Position-based indexing (.iloc[])


# Boolean indexing

```

---

## 📋 Part 2: Creating and Exploring DataFrames (10 points)

### Task 2.1: DataFrame Creation Challenge (4 points)

**Your Challenge:** Create THREE DataFrames using different methods:

**DataFrame 1: Employee Records** (Create from dictionary)
```
employee_id: 101, 102, 103, 104, 105
name: 'John Smith', 'Jane Doe', 'Bob Johnson', 'Alice Williams', 'Charlie Brown'
department: 'IT', 'HR', 'Finance', 'IT', 'Marketing'
salary: 75000, 68000, 72000, 80000, 65000
years_experience: 5, 3, 7, 6, 2
```

**DataFrame 2: Product Inventory** (Create from list of dictionaries)
```
Products: 
- Laptop: Electronics, $999.99, stock: 25
- Mouse: Electronics, $29.99, stock: 150  
- Desk Chair: Furniture, $199.99, stock: 45
- Monitor: Electronics, $299.99, stock: 30
- Keyboard: Electronics, $79.99, stock: 80
```

**DataFrame 3: Sales Matrix** (Create from NumPy array)
```
6 months (Jan-Jun) × 4 regions (North, South, East, West)
Use: np.random.seed(42) then create random integers between 100-1000
```

**Requirements:**
- Use the correct DataFrame creation method for each
- Set appropriate index and column names where needed
- Display the shape and basic info for each DataFrame

```python
# DataFrame 1: Employee Records (from dictionary)


# DataFrame 2: Product Inventory (from list of dictionaries)


# DataFrame 3: Sales Matrix (from NumPy array)
np.random.seed(42)  # Use this for reproducible results


# Display basic information for each DataFrame

```

### Task 2.2: DataFrame Exploration (3 points)

**Your Challenge:** For each DataFrame you created, perform comprehensive exploration:

**For Employee DataFrame:**
- Use `.info()` and `.describe()` 
- Count employees by department
- Check for any missing values
- List all unique departments

**For Product DataFrame:**
- Show descriptive statistics for price and stock
- Count products by category  
- Find the most expensive and cheapest products

**For Sales DataFrame:**
- Display first 3 and last 3 rows
- Show column names and index
- Calculate basic statistics

```python
# Employee DataFrame exploration


# Product DataFrame exploration


# Sales DataFrame exploration

```

### Task 2.3: DataFrame Selection and Filtering (3 points)

**Your Challenge:** Practice selecting data from your DataFrames:

1. **Column Selection:**
   - Select just employee names and salaries
   - Select product names and prices
   - Select sales data for just 'North' and 'South' regions

2. **Row Selection:**  
   - Select employees with ID 102 and 104
   - Select the first 2 products
   - Select sales data for March and April

3. **Conditional Selection:**
   - Find employees with salary > $70,000
   - Find products with stock < 50
   - Find months where North region sales > 500

```python
# Column selection exercises


# Row selection exercises


# Conditional selection exercises

```

---

## 🔧 Part 3: DataFrame Modifications and Analysis (7 points)

### Task 3.1: Adding and Modifying Columns (4 points)

**Your Challenge:** Add calculated and categorical columns to your DataFrames:

**For Employee DataFrame, add:**
- `annual_bonus`: 10% of salary
- `total_compensation`: salary + bonus
- `experience_level`: "Junior" (<3 years), "Mid-level" (3-6 years), "Senior" (>6 years)
- `salary_tier`: "Entry" (<$70K), "Mid" ($70K-$75K), "High" (>$75K)

**For Product DataFrame, add:**
- `total_inventory_value`: price × stock
- `stock_level`: "Low" (<50), "Medium" (50-100), "High" (>100)
- `price_category`: "Budget" (<$100), "Standard" ($100-$300), "Premium" (>$300)

**For Sales DataFrame, add:**
- `total_monthly_sales`: sum across all regions for each month
- `best_region`: region with highest sales for each month

```python
# Modify Employee DataFrame


# Modify Product DataFrame


# Modify Sales DataFrame

```

### Task 3.2: Aggregation and Summary Statistics (3 points)

**Your Challenge:** Create summary analyses:

1. **Department Analysis:**
   - Average salary by department
   - Count of employees by experience level
   - Highest paid employee in each department

2. **Product Category Analysis:**
   - Average price and stock by category
   - Total inventory value by category
   - Product count by stock level

3. **Regional Sales Analysis:**
   - Total sales by region (across all months)
   - Average monthly sales by region
   - Best performing month overall

```python
# Department analysis


# Product category analysis


# Regional sales analysis

```

---

## 🎯 Part 4: Challenge Questions (Bonus: +2 points)

### Challenge 1: Data Integration
Create a summary report that answers:
- Which department has the most consistent salaries (lowest standard deviation)?
- What's the relationship between experience and salary?
- Which product category is most profitable per unit of stock?

### Challenge 2: Advanced Analysis
Using your sales data:
- Which region shows the most growth from Jan to Jun?
- What's the month-to-month growth rate for each region?
- Create a "performance score" combining total sales and consistency

```python
# Challenge solutions here

```

---

## 📝 Deliverables and Submission

### What to Submit:
1. **Completed Google Colab Notebook** 
   - Download as .ipynb file
   - Name: `YourLastName_FirstName_Lab3_Pandas_Intro.ipynb`

2. **Share Your Colab Link**
   - Make sure link sharing is enabled
   - Include this link in your submission comments

### Notebook Requirements:
- All code cells must run without errors
- Include markdown cells with:
  - Your name and date at the top
  - Brief explanations of your approach for complex tasks
  - Your observations and insights from the data

### Code Quality Expectations:
- Use meaningful variable names
- Include comments for complex operations
- Display results with clear labels
- Test your code before submission

---

## 🎯 Grading Rubric (25 points + 2 bonus)

| Component | Points | What We're Looking For |
|-----------|--------|----------------------|
| **Part 1: Series** | 8 | Correct Series creation, operations, and indexing |
| **Part 2: DataFrames** | 10 | Proper DataFrame creation, exploration methods |
| **Part 3: Modifications** | 7 | Adding columns, aggregations, analysis |
| **Code Quality** | - | Clean, commented code that runs error-free |
| **Challenge Questions** | +2 | Creative problem-solving and insights |

### Detailed Grading:
- **Excellent (90-100%):** All tasks completed correctly with insightful analysis
- **Good (80-89%):** Most tasks completed with minor errors
- **Satisfactory (70-79%):** Basic requirements met with some missing elements
- **Needs Improvement (<70%):** Significant portions incomplete or incorrect

---

## 💡 Helpful Hints

### Getting Started Tips:
- Review the class notebook examples before coding
- Start with simple cases and build complexity
- Test each piece of code before moving to the next task

### Common Student Mistakes to Avoid:
- Forgetting that single column selection returns a Series, not DataFrame
- Confusing .loc[] (label-based) with .iloc[] (position-based) indexing  
- Not using parentheses for multiple conditions in boolean indexing
- Trying to modify DataFrames without assigning the result back

### When You're Stuck:
1. Check the pandas documentation
2. Print intermediate results to understand what you have
3. Break complex operations into smaller steps
4. Review similar examples from the class notebook

### Google Colab Tips:
- Use Ctrl+Enter to run current cell
- Use Shift+Enter to run cell and move to next
- Use Ctrl+M, A to add cell above
- Use Ctrl+M, B to add cell below

---

## 📚 Resources

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Class GitHub Notebook](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/1_pandas_intro_to_series_and_dataframe.ipynb)
- [Google Colab Guide](https://colab.research.google.com/notebooks/basic_features_overview.ipynb)

---

**Remember:** The goal is to learn by doing. Don't just copy examples - understand why each operation works the way it does. This foundation will be crucial for all future data science work!

**Good luck! 🐼📊**
