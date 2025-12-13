# Week 13: Exploratory Data Analysis (EDA) with Pandas

**Course:** Python for Data Science  
**Instructor:** Siva Jasthi  
**Week:** 13  
**Topic:** Exploratory Data Analysis (EDA)

---

## Learning Objectives

By the end of this week, students will be able to:

1. Understand the purpose and importance of Exploratory Data Analysis in the data science workflow
2. Use pandas methods to explore and summarize datasets effectively
3. Identify data quality issues including missing values, duplicates, and outliers
4. Generate descriptive statistics to understand data distributions
5. Apply data profiling techniques to gain insights from datasets
6. Visualize data patterns using basic plotting methods
7. Formulate data-driven questions based on exploratory findings

---

## Topics Covered

### 1. Introduction to Exploratory Data Analysis
- What is EDA and why is it important?
- The EDA process in data science projects
- Types of questions EDA helps answer
- EDA vs. Formal Analysis

### 2. Initial Data Exploration
- Loading datasets with `pd.read_csv()` and other methods
- First look at data: `df.head()`, `df.tail()`, `df.sample()`
- Understanding data structure: `df.shape`, `df.columns`, `df.dtypes`
- Getting data information: `df.info()`

### 3. Descriptive Statistics
- Summary statistics with `df.describe()`
- Understanding include parameter: `describe(include='all')`
- Calculating specific statistics: `mean()`, `median()`, `mode()`, `std()`, `var()`
- Percentiles and quartiles: `df.quantile()`
- Counting unique values: `df.nunique()`, `df.value_counts()`

### 4. Data Quality Assessment
- Identifying missing values: `df.isnull()`, `df.isna()`
- Counting missing data: `df.isnull().sum()`
- Visualizing missing data patterns
- Finding duplicate rows: `df.duplicated()`, `df.drop_duplicates()`
- Data type validation and conversion

### 5. Exploring Data Distributions
- Understanding data ranges: `df.min()`, `df.max()`
- Frequency distributions with `value_counts()`
- Binning continuous data with `pd.cut()` and `pd.qcut()`
- Cross-tabulations: `pd.crosstab()`

---

## Weekly Assignment

**Assignment:** Pandas Exploratory Data Analysis  
**Due Date:** End of Week 13  
**Points:** 25  
**Link:** [pandas_exploratory_data_analysis.md](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/pandas_exploratory_data_analysis.md)

### Assignment Overview:
Students will perform a comprehensive exploratory data analysis on a provided dataset. 

---

## Resources

### Required Materials:
- **Main Notebook:** [3_pandas_Exploratory_Data_Analysis.ipynb](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/3_pandas_Exploratory_Data_Analysis.ipynb)
- **Assignment:** [pandas_exploratory_data_analysis.md](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/pandas_exploratory_data_analysis.md)

### Additional Resources:
- Pandas Documentation: [User Guide - Essential Basic Functionality](https://pandas.pydata.org/docs/user_guide/basics.html)
- Pandas Documentation: [Visualization](https://pandas.pydata.org/docs/user_guide/visualization.html)
- Real Python: [Pandas DataFrames 101](https://realpython.com/pandas-dataframe/)
- Towards Data Science: [Exploratory Data Analysis with Pandas](https://towardsdatascience.com/exploratory-data-analysis-with-pandas-508a5e8a5964)
