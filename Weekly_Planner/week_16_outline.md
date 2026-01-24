# Week 16: Split-Apply-Combine, Group By & Pivots 📊

## 🎯 Learning Objectives

By the end of this week, students will be able to:
- Understand the Split-Apply-Combine concept for data analysis
- Use `groupby()` to group data and perform aggregate operations
- Create pivot tables to reshape and summarize data
- Apply multiple aggregation functions to grouped data
- Transform data from long to wide format and vice versa

## 📚 Topics Covered

### 1. **Split-Apply-Combine Concept** 🔄
- What is Split-Apply-Combine?
- Breaking data into groups (Split)
- Applying functions to each group (Apply)
- Combining results back together (Combine)
- Real-world applications and examples

### 2. **GroupBy Operations** 👥
- Basic `groupby()` syntax
- Grouping by single and multiple columns
- Common aggregation functions (sum, mean, count, min, max)
- Using `agg()` for multiple aggregations
- Filtering groups with `filter()`

### 3. **Pivot Tables** 🔄
- Introduction to pivot tables
- Creating pivot tables with `pivot_table()`
- Specifying index, columns, and values
- Choosing aggregation functions
- Handling missing values in pivots

### 4. **Practical Applications** 💡
- Analyzing sales data by category
- Computing statistics by groups
- Creating summary reports
- Reshaping data for visualization
- Comparing different groups

## 📖 Course Materials

### **Interactive Colab Notebook**
Work through examples and practice exercises:
- [pandas Split-Apply-Combine, GroupBy & Pivots Notebook](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/6_pandas_Split_Apply_Combine_groupby_pivots.ipynb)

### **Interactive Playbook & Quiz** 🎮
Test your understanding with hands-on activities:
- [GroupBy and Pivot Playbook & Quiz](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/python_ds_groupby_pivot_playbook_and_quiz.html)

## 📝 Assignment (Due This Week)

### **Pandas GroupBy and Pivots Lab**
Apply your knowledge to real-world data analysis problems:
- [GroupBy and Pivots Lab](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/python_ds_pandas_groupby_and_pivots_lab.ipynb)


## 🔑 Key Concepts to Master

1. **Split-Apply-Combine Pattern**: The fundamental approach to group-based data analysis
2. **GroupBy Syntax**: `df.groupby('column_name').agg_function()`
3. **Aggregation Functions**: sum(), mean(), count(), min(), max(), std()
4. **Pivot Table Structure**: Rows (index), Columns, Values, and Aggregation function
5. **Data Reshaping**: Converting between different data layouts

## 🔮 Looking Ahead: Next Week's Topics

**Week 17 Preview - Advanced Data Transformation**

Next week, we'll explore more powerful pandas tools for data manipulation:
- **`cut()` & `qcut()`**: Binning continuous data into categories
- **`apply()`**: Applying custom functions to data
- **`melt()`**: Converting wide data to long format
- **`stack()`**: Reshaping multi-level data
- **`crosstab()`**: Creating cross-tabulation tables

## 📌 Important Reminders

- ✅ Complete the Colab notebook exercises
- ✅ Take the interactive quiz
- ✅ Submit the GroupBy and Pivots Lab by end of week
- ✅ Review aggregation functions and their uses
- ✅ Ask questions if any concept is unclear!

## 🤔 Questions to Think About

1. When would you use `groupby()` instead of a pivot table?
2. How can the Split-Apply-Combine pattern help in real-world data analysis?
3. What happens when you group by multiple columns?
4. How do pivot tables make data easier to understand?

---

**Remember**: GroupBy and Pivots are powerful tools for summarizing and analyzing data. They help you find patterns and insights that aren't obvious in raw data! 🚀

*Keep practicing, and don't hesitate to ask questions during class!*
