# Pandas: Exploratory Data Analysis Assignment

---

## 🎯 Learning Objectives

By completing this assignment, you will demonstrate your ability to:
- Load and inspect datasets using pandas
- Examine data structure, shape, and basic properties
- Identify and analyze missing data patterns
- Calculate descriptive statistics for numerical and categorical data
- Use pandas methods to gain insights from real-world datasets
- Document findings and observations clearly

---

## 📊 Dataset

You will analyze the **Student Performance Dataset**, which contains student achievement data across multiple subjects and various demographic factors.

**Dataset URL:** `https://raw.githubusercontent.com/datasciencedojo/datasets/master/StudentsPerformance.csv`

**Dataset Description:** This dataset contains student performance data including math, reading, and writing scores along with demographic information such as gender, ethnicity, parental education level, lunch type, and test preparation course completion. It provides rich opportunities for exploratory data analysis.

---

## 🚀 Setup Instructions

### Step 1: Create Your Google Colab Notebook
1. Go to [Google Colab](https://colab.research.google.com)
2. Create a new notebook
3. Rename it: `YourLastName_FirstName_Pandas_EDA.ipynb`

### Step 2: Import Libraries and Load Data
```python
# Import necessary libraries
import pandas as pd
import numpy as np

# Load the dataset
url = 'https://raw.githubusercontent.com/datasciencedojo/datasets/master/StudentsPerformance.csv'
df = pd.read_csv(url)

print("Dataset loaded successfully!")
print("Dataset shape:", df.shape)
```

---

## 📝 Assignment Tasks

### Part 1: Initial Data Exploration (8 points)

#### Task 1.1: Basic Dataset Information (3 points)

**Your Challenge:** Examine the basic properties of your dataset.

**Requirements:**
1. Display the first 5 and last 5 rows of the dataset
2. Print the data type of the entire dataset (should be DataFrame)
3. Show the shape of the dataset (rows and columns)
4. Calculate and display the total size of the dataset (total number of elements)
5. List all column names and their data types

**Questions to Answer:**
- How many students are included in this dataset?
- How many features (columns) does each student record have?
- What is the total number of data points in the dataset?

```python
# Your code here for Task 1.1

```

#### Task 1.2: Data Structure Analysis (3 points)

**Your Challenge:** Analyze the structure and organization of your data.

**Requirements:**
1. Display detailed information using `.info()` method
2. Show the index (row names) and explain what it represents
3. Count the number of columns using two different methods
4. Count the number of rows using two different methods
5. Identify which columns contain numerical data vs. categorical data

```python
# Your code here for Task 1.2

```

#### Task 1.3: Missing Data Investigation (2 points)

**Your Challenge:** Detect and analyze missing values in the dataset.

**Requirements:**
1. Check if there are ANY missing values in the entire dataset
2. Count missing values for each column
3. Calculate the percentage of missing values for each column
4. Identify which columns have the most missing data (if any)

```python
# Your code here for Task 1.3

```

### Part 2: Descriptive Statistics Analysis (10 points)

#### Task 2.1: Numerical Data Analysis (5 points)

**Your Challenge:** Analyze numerical columns using descriptive statistics.

**Requirements:**
1. Use `.describe()` to show statistics for ALL numerical columns
2. For the math score column specifically, calculate and display:
   - Mean, median, and mode
   - Standard deviation and variance
   - Minimum and maximum values
   - 25th and 75th percentiles
3. Identify which student has the highest math score
4. Identify which student has the lowest math score
5. Calculate how many students have math scores above the overall average

```python
# Your code here for Task 2.1

```

#### Task 2.2: Categorical Data Analysis (3 points)

**Your Challenge:** Analyze categorical/text columns in your dataset.

**Requirements:**
1. Use `.describe(include=['object'])` to analyze categorical columns
2. For each categorical column, identify:
   - Number of unique values
   - Most frequently occurring value
   - Frequency of the most common value
3. If there's a region or continent column, count how many countries belong to each region

```python
# Your code here for Task 2.2

```

#### Task 2.3: Advanced Statistical Insights (2 points)

**Your Challenge:** Generate deeper insights from the numerical data.

**Requirements:**
1. Find correlations between math score and other numerical factors (reading, writing scores)
2. Identify the top 5 performing students (by average of all three scores) and display their key metrics
3. Identify the bottom 5 performing students and display their key metrics
4. Calculate the range (max - min) for each subject score
5. Determine what percentage of students score above 80 in math

```python
# Your code here for Task 2.3

```

### Part 3: Data Quality Assessment (4 points)

#### Task 3.1: Data Consistency Check (2 points)

**Your Challenge:** Examine the consistency and quality of your data.

**Requirements:**
1. Check for any duplicate rows in the dataset
2. Verify that test scores are within a reasonable range (typically 0-100)
3. Look for any obvious data entry errors or outliers
4. Check if categorical values are consistently formatted (gender, ethnicity, etc.)

```python
# Your code here for Task 3.1

```

#### Task 3.2: Data Distribution Analysis (2 points)

**Your Challenge:** Understand how your data is distributed.

**Requirements:**
1. Calculate quartiles for the math scores
2. Identify any students that might be considered outliers (unusually high or low scores)
3. Determine the median math score and how many students fall above/below it
4. Create value counts for categorical variables like gender, ethnicity, parental education

```python
# Your code here for Task 3.2

```

### Part 4: Summary and Insights (3 points)

#### Task 4.1: Comprehensive Summary Report

**Your Challenge:** Synthesize your findings into a clear, informative summary.

**Requirements:**
Create a markdown cell that includes:

1. **Dataset Overview** (1 point):
   - Brief description of the dataset
   - Number of students and features analyzed
   - Data quality assessment summary

2. **Key Findings** (1 point):
   - Top 3 performing students and their average scores
   - Bottom 3 students and their average scores
   - Overall class performance patterns
   - Most important insight you discovered

3. **Data Quality Report** (1 point):
   - Missing data summary
   - Any data quality issues identified
   - Recommendations for data improvement (if applicable)

```python
# Create your summary report in a markdown cell below
```

---

## 💡 Helpful Hints

### Getting Started:
- Begin by exploring the data with `df.head()` and `df.info()`
- Use `df.columns.tolist()` to see all column names clearly
- Remember that `.describe()` only shows numerical columns by default

### Common Methods You'll Need:
- **Data Inspection:** `.head()`, `.tail()`, `.info()`, `.shape`, `.dtypes`
- **Missing Data:** `.isnull()`, `.isna()`, `.sum()`, `.any()`
- **Statistics:** `.describe()`, `.mean()`, `.median()`, `.std()`, `.min()`, `.max()`
- **Counting:** `.value_counts()`, `.nunique()`, `len()`
- **Sorting:** `.sort_values()`, `.nlargest()`, `.nsmallest()`

### Google Colab Tips:
- Use `Ctrl+Enter` to run the current cell
- Use `Shift+Enter` to run current cell and move to next
- Add markdown cells to document your findings
- Use `print()` statements to clearly label your outputs

---

## 📤 Submission Requirements

### What to Submit:
1. **Completed Google Colab Notebook** (.ipynb file downloaded from Colab)
2. **Share Link** to your Colab notebook (make sure sharing is enabled)

### Notebook Requirements:
- **Header Cell:** Include your name, date, and assignment title
- **Clean Code:** All code cells must run without errors
- **Clear Output:** Results should be clearly visible and labeled
- **Documentation:** Use markdown cells to explain your approach and findings
- **Complete Analysis:** All tasks must be attempted with thoughtful analysis

### Code Quality Expectations:
- Use meaningful variable names
- Include comments for complex operations
- Display results with descriptive print statements
- Organize code logically within each task

---

## 🎯 Grading Rubric (25 points total)

| Section | Points | Criteria |
|---------|--------|----------|
| **Part 1: Initial Exploration** | 8 | Correct data loading, shape analysis, structure examination |
| **Part 2: Descriptive Statistics** | 10 | Comprehensive statistical analysis, meaningful insights |
| **Part 3: Data Quality** | 4 | Thorough data consistency and distribution analysis |
| **Part 4: Summary Report** | 3 | Clear, comprehensive summary with key findings |

### Quality Indicators:
- **Excellent (90-100%):** All tasks completed with insightful analysis and clear documentation
- **Good (80-89%):** Most tasks completed correctly with adequate analysis
- **Satisfactory (70-79%):** Basic requirements met with some missing elements
- **Needs Improvement (<70%):** Significant portions incomplete or incorrect

---

## 🔍 Expected Insights

While working through this assignment, you should discover insights such as:
- Which demographic groups tend to perform better academically
- The relationship between parental education level and student performance
- How test preparation courses affect student scores
- Whether there are performance differences across different subjects
- The distribution of scores across gender and ethnicity groups

---

## ⚠️ Common Pitfalls to Avoid

- Don't assume the data is clean - always check for missing values and inconsistencies
- Remember that `.describe()` only shows numerical columns by default
- Be careful with data types - some columns that look numerical might be stored as text
- Don't forget to label your outputs clearly so they're easy to understand
- Make sure to actually answer the questions posed in each task

---

## 📚 Additional Resources

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [World Happiness Report Information](https://worldhappiness.report/)
- [Google Colab User Guide](https://colab.research.google.com/notebooks/basic_features_overview.ipynb)

---

**Remember:** The goal of exploratory data analysis is to understand your data before diving into more complex analysis. Take time to really examine what the numbers are telling you about global happiness patterns!

**Good luck with your analysis! 🌍📊**
