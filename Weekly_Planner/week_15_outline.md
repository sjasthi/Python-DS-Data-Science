# Week 15: Data Summarization and Aggregation with Pandas

**Course:** Python for Data Science  
**Instructor:** Siva Jasthi (Siva.Jasthi@metrostate.edu)  
**Week:** 15  
**Topic:** Summarization and Aggregation of Data

---

## 📚 Learning Objectives

By the end of this week, students will be able to:

1. Understand the difference between summarization and aggregation
2. Perform categorical data aggregation using `.unique()`, `.nunique()`, and `.value_counts()`
3. Calculate quantitative statistics: mean, median, mode, standard deviation, variance
4. Apply aggregation functions to numerical data: sum, min, max, count
5. Use `.describe()` to generate comprehensive statistical summaries
6. Perform DataFrame-level aggregations across multiple columns
7. Calculate percentiles and interquartile ranges (IQR)
8. Compute cumulative operations (cumsum, cumprod)
9. Create derived columns for custom aggregations
10. Apply the `.groupby()` method for grouped aggregations

---

## 📋 Topics Covered

### 1. Introduction to Data Summarization
- What is data summarization and why is it important?
- The role of summarization in data analysis workflow
- Difference between summarization (describing data) and aggregation (combining data)
- When to use different summary techniques

### 2. Categorical Data Aggregation
- **Finding unique values**: Using `.unique()` to see all distinct values
- **Counting unique values**: Using `.nunique()` for quick counts
- **Frequency distributions**: Creating frequency tables with `.value_counts()`
- **Percentage distributions**: Normalizing counts with `.value_counts(normalize=True)`
- **Finding the mode**: Identifying most frequent values with `.mode()`
- **Handling missing values**: Counting nulls in categorical columns with `.isna().sum()`

### 3. Quantitative Data Aggregation
- **Measures of Central Tendency**:
  - Mean (average): `.mean()`
  - Median (middle value): `.median()`
  - Mode (most common): `.mode()`
- **Measures of Dispersion**:
  - Standard deviation: `.std()`
  - Variance: `.var()`
  - Range: `.max() - .min()`
- **Boundary Statistics**:
  - Minimum: `.min()`
  - Maximum: `.max()`
  - Sum: `.sum()`
  - Count: `.count()`
- **Advanced Statistics**:
  - Percentiles: `.quantile()`
  - Interquartile Range (IQR): Q3 - Q1
  - Skewness: `.skew()`
  - Kurtosis: `.kurt()`

### 4. Cumulative Operations
- **Cumulative Sum**: `.cumsum()` - running total
- **Cumulative Product**: `.cumprod()` - running product
- **Cumulative Max/Min**: `.cummax()`, `.cummin()`
- Use cases: tracking totals over time, compound growth

### 5. Comprehensive Summaries
- **The `.describe()` method**: One-stop summary statistics
- **Custom aggregations**: Using `.agg()` with multiple functions
- **Applying multiple functions**: `.agg(['mean', 'std', 'min', 'max'])`
- Interpreting summary statistics output

### 6. Row-wise Aggregations
- **Axis parameter**: Understanding `axis=0` (columns) vs `axis=1` (rows)
- **Row means**: Calculating average across columns for each row
- **Row sums**: Adding values across columns
- Practical use cases for row-wise operations

### 7. DataFrame-Level Aggregations
- **Shape and size**: `.shape`, `.size` - understanding dimensions
- **Overall statistics**: Applying functions to entire DataFrame
- **Missing value analysis**: `.isna().sum()`, `.isna().sum() / len(df)`
- **Column data types**: `.dtypes` for type summary
- **Memory usage**: `.memory_usage()` for resource analysis

### 8. Creating Derived Columns
- **Calculated fields**: Creating new columns from existing ones
- **Example**: Price per unit = Sales / Units
- **Aggregating derived data**: Computing statistics on calculated columns
- **Best practices**: Naming conventions and documentation

### 9. Introduction to GroupBy Operations
- **What is grouping?**: Splitting data into groups based on categories
- **Basic groupby syntax**: `df.groupby('column_name')`
- **Aggregating grouped data**: `.sum()`, `.mean()`, `.count()` after groupby
- **Finding top categories**: Using `.idxmax()` and `.idxmin()`
- **Real-world applications**: Sales by region, performance by department

### 10. Practical Applications
- **Business scenarios**: Revenue analysis, inventory management
- **Research applications**: Experimental data analysis, survey results
- **Real-world datasets**: Working with sales, census, or sports data
- **Combining techniques**: Using multiple aggregation methods together

---

## 🎯 Class Activities (90 minutes)

### **Activity 1: Categorical Exploration (15 minutes)**
**Hands-on Exercise:**
- Load the Titanic dataset
- Find unique values in 'Embarked' and 'Pclass' columns
- Calculate percentage distribution of passengers by class
- Identify the mode for 'Sex' and 'Embarked'
- Count missing values in each categorical column

**Learning Goal:** Master categorical data summarization techniques

---

### **Activity 2: Statistical Summary Challenge (20 minutes)**
**Guided Demo:**
- Calculate mean, median, and mode of 'Age' and 'Fare'
- Find the range (max - min) for numerical columns
- Compute standard deviation and variance
- Use `.describe()` to get comprehensive statistics
- Interpret what the statistics tell us about the data

**Student Practice:**
- Apply same techniques to 'SibSp' and 'Parch' columns
- Calculate IQR for 'Fare'
- Identify potential outliers using statistics

**Learning Goal:** Build confidence with numerical aggregations

---

### **Activity 3: Custom Aggregations (20 minutes)**
**Interactive Task:**
- Create a new column: 'Family_Size' = SibSp + Parch + 1
- Calculate average family size
- Create 'Fare_Per_Person' = Fare / Family_Size
- Use `.agg()` to apply multiple functions at once
- Compare results across different passenger classes

**Learning Goal:** Practice creating derived columns and custom aggregations

---

### **Activity 4: GroupBy Exploration (25 minutes)**
**Class Demonstration:**
1. Group passengers by 'Pclass' and calculate survival rate
2. Group by 'Sex' and find average age and fare
3. Find which embarkation port had the highest survival rate
4. Determine which passenger class paid the most on average
5. Identify top-performing groups using `.idxmax()`

**Student Exercise:**
- Group by multiple columns: 'Pclass' and 'Sex'
- Calculate total passengers and survival rate per group
- Find the group with highest average fare

**Learning Goal:** Master basic groupby operations for real insights

---

### **Activity 5: Wrap-up and Q&A (10 minutes)**
- Review key concepts and methods
- Common mistakes and how to avoid them
- Preview of assignment expectations
- Open questions from students

---

## 📚 Resources & Materials

### **📓 Class Notebook (Follow Along)**
- **Colab Notebook**: [5_pandas_summarization_aggregataion.ipynb](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/5_pandas_summarization_aggregataion.ipynb)
- Contains all examples demonstrated in class
- Uses the Titanic dataset for hands-on practice
- Step-by-step walkthroughs of each method

### **📝 Assignment (Due This Week)**
- **Assignment Notebook**: [pandas_summarization_aggregation_assignment.ipynb](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/pandas_summarization_aggregation_assignment.ipynb)
- **Worth**: 25 points
- **Dataset**: Sales data (Products across Regions)
- **Topics Tested**: 
  - Categorical aggregation (8 points)
  - Quantitative aggregation (10 points)
  - DataFrame-level operations (4 points)
  - Challenge: GroupBy operations (3 points)
- **Submission**: Upload completed .ipynb file with all outputs visible

### **📊 Dataset Used**
- **Primary**: Titanic dataset (891 passengers)
- **Assignment**: Sales data (24 records across 4 regions, 6 products)

---

## 🗓️ What's Due This Week?

### **✅ Assignment: Summarization and Aggregation**
- **Due**: End of Week 15
- **Format**: Jupyter Notebook (.ipynb)
- **Points**: 25
- **Key Tasks**:
  1. Find unique values and counts in categorical data
  2. Calculate statistical measures (mean, median, std, variance)
  3. Perform DataFrame-level aggregations
  4. Create derived columns (Price_Per_Unit)
  5. Use groupby to find top-selling product

### **Submission Checklist:**
- [ ] All code cells executed successfully
- [ ] All `# YOUR CODE HERE` replaced with working code
- [ ] Outputs are visible for all cells
- [ ] Name and date filled in at the top
- [ ] Notebook runs from top to bottom without errors

---

## 💡 Teaching Tips & Common Challenges

### **Common Student Mistakes:**

1. **Confusing axis=0 and axis=1**
   - **Tip**: "axis=0 goes DOWN the rows (column-wise), axis=1 goes ACROSS the columns (row-wise)"
   - **Visual**: Draw a DataFrame on the board and show the direction

2. **Forgetting parentheses on methods**
   - **Wrong**: `df.mean` → Returns function object
   - **Right**: `df.mean()` → Executes the function
   - **Tip**: "Always use () to actually RUN the method!"

3. **Not understanding when to use which summary statistic**
   - **Mean**: Good for normal distributions, affected by outliers
   - **Median**: Better for skewed data, robust to outliers
   - **Mode**: Best for categorical or discrete data
   - **Tip**: Show examples with toy data to illustrate differences

4. **Confusion with `.groupby()` syntax**
   - Students forget to call an aggregation method after groupby
   - **Wrong**: `df.groupby('Region')` → Just creates a groupby object
   - **Right**: `df.groupby('Region').sum()` → Actually aggregates
   - **Tip**: "GroupBy is a two-step dance: group, then aggregate!"

5. **Dividing by zero errors in derived columns**
   - When creating Price_Per_Unit, if Units = 0, causes error
   - **Solution**: Check for zeros first or use `.replace(0, np.nan)`

### **Pacing Recommendations:**
- Spend extra time on `.groupby()` - it's conceptually challenging
- Use real-world analogies: "GroupBy is like sorting M&Ms by color, then counting each pile"
- Have students verbalize what they're doing before coding
- Encourage experimentation - these methods are safe to try!

### **Engagement Strategies:**
- **Poll the class**: "Which product do you think sold the most? Let's use groupby to find out!"
- **Real-world connections**: "How would Netflix use aggregation to recommend shows?"
- **Challenge questions**: "Can you find the answer in one line of code?"
- **Pair programming**: Have students work in pairs for the groupby activity

---

## 🔍 Key Takeaways

Students should leave this week able to answer:

✅ **What's the difference between .unique() and .nunique()?**
- `.unique()` returns an array of unique values
- `.nunique()` returns the count of unique values

✅ **When should I use mean vs. median?**
- Mean for normally distributed data
- Median when data has outliers or is skewed

✅ **How do I aggregate grouped data?**
- Use `.groupby('column')` followed by an aggregation method like `.sum()`, `.mean()`, `.count()`

✅ **What does .describe() tell me?**
- Count, mean, std, min, 25%, 50%, 75%, max for numerical columns

✅ **How do I create calculated columns?**
- Assign a new column using arithmetic: `df['New_Col'] = df['Col1'] / df['Col2']`

---

## 🔜 Looking Ahead: Week 16

**Next Week's Topic**: Data Cleaning and Transformation
- Handling missing values (dropna, fillna)
- Removing duplicates
- Data type conversions
- String operations
- Renaming and reordering columns

**Preparation**: Review this week's aggregation methods - we'll use them to inform our cleaning decisions!

---

## 📧 Questions?

If you have questions about this week's material:
- Office Hours: [Your office hours here]
- Email: Siva.Jasthi@metrostate.edu
- Class Discussion Forum: [Link if applicable]

---

## 📌 Quick Reference: Essential Methods

| Method | Purpose | Example |
|--------|---------|---------|
| `.unique()` | Get unique values | `df['Region'].unique()` |
| `.nunique()` | Count unique values | `df['Product'].nunique()` |
| `.value_counts()` | Frequency distribution | `df['Region'].value_counts()` |
| `.mean()` | Average | `df['Sales'].mean()` |
| `.median()` | Middle value | `df['Sales'].median()` |
| `.std()` | Standard deviation | `df['Sales'].std()` |
| `.min()` / `.max()` | Extremes | `df['Sales'].min()` |
| `.sum()` | Total | `df['Units'].sum()` |
| `.describe()` | Full summary | `df.describe()` |
| `.groupby()` | Group and aggregate | `df.groupby('Region').mean()` |
| `.agg()` | Multiple aggregations | `df.agg(['mean', 'sum'])` |
| `.cumsum()` | Cumulative sum | `df['Sales'].cumsum()` |

---

**Remember**: Summarization and aggregation help us understand our data and uncover patterns. Practice these methods often - they're the foundation of data analysis!

🎯 **Practice makes perfect!** Work through the assignment and experiment with different aggregations.
