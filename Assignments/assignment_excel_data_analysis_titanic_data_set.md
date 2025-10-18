# 🚢 Titanic Dataset Analysis - Excel Assignment

## Overview
This assignment will help you develop essential Excel skills for data analysis using the famous Titanic dataset. You will explore data, perform statistical analysis, and use advanced Excel functions.

**Total Points:** 25 (1 point per question)

---

## 📋 Dataset Columns
Your dataset contains the following columns:
- **Id**: Passenger ID
- **Survived**: 0 = No, 1 = Yes
- **Pclass**: Passenger Class (1 = 1st, 2 = 2nd, 3 = 3rd)
- **Name**: Passenger name
- **Sex**: Male or Female
- **Age**: Age in years
- **SibSp**: Number of siblings/spouses aboard
- **Parch**: Number of parents/children aboard
- **Ticket**: Ticket number
- **Fare**: Ticket fare
- **Embarked**: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

---

## 🧩 Part A – Data Exploration (Basic Excel Skills)
*Focus: COUNT, COUNTA, COUNTIF, COUNTIFS, and basic data exploration*

1. **How many passengers are in the dataset?**

2. **How many people survived?**

3. **How many males and females were on board?**

4. **How many passengers traveled in each passenger class (1st, 2nd, and 3rd)?**

5. **How many passengers are missing age values?**

6. **How many passengers are missing embarkation port information?**

7. **How many passengers embarked from each port (C, Q, and S)?**

8. **What is the most common embarkation port?**

9. **How many tickets contain only numeric values (no letters)?**  
   *Hint: This is challenging! Consider using helper columns with formulas like `=ISNUMBER(VALUE(cell))` or `=SUMPRODUCT(--ISNUMBER(--Ticket_Range))`*

10. **What is the total number of unique ticket numbers?**  
    *Hint: Use Remove Duplicates on a copy of the data, or use `=SUMPRODUCT(1/COUNTIF(range,range))` for a formula approach*

---

## 📊 Part B – Statistical Insights (Functions, Filters, and Sorting)
*Focus: AVERAGE, AVERAGEIF, Percentages, Sorting, MIN, MAX, LARGE, SMALL*

11. **What is the average age of all passengers?**  
    *Note: Ignore missing values*

12. **What is the average age of survivors?**

13. **What percentage of passengers survived overall?**

14. **How many passengers were age 30 or older?**

15. **How many passengers were under age 30?**

16. **How many senior citizens (age > 60) were on board?**

17. **What is the average fare paid by passengers?**

18. **What is the highest fare paid, and what is the lowest fare paid?**

19. **What are the names of 3 passengers who paid the highest fares?**  
    *Hint: Sort by Fare in descending order, or use LARGE function with INDEX/MATCH*

20. **What is the survival rate (percentage) for each passenger class?**  
    *Show: 1st class %, 2nd class %, 3rd class %*

---

## 🧠 Part C – Text Analysis and Logical Queries (Advanced Excel)
*Focus: Multiple criteria, text functions, logical operators*

21. **How many passengers had no parents or children aboard (Parch = 0)?**

22. **How many passengers had no siblings or spouses aboard (SibSp = 0)?**

23. **How many passengers traveled completely alone (both SibSp = 0 AND Parch = 0)?**  
    *Hint: Use COUNTIFS to check multiple conditions*

24. **What is the most common last name among passengers?**  
    📘 **Guidance:**
    - **Option 1 (Text to Columns):** Copy the Name column, use Data → Text to Columns, use comma as delimiter. Last names will be in the first column.
    - **Option 2 (Formula):** Use `=LEFT(Name, FIND(",", Name)-1)` to extract last name
    - Then use COUNTIF to count occurrences and find the maximum

25. **How many passengers have titles "Mr.", "Mrs.", "Miss", and "Master" in their names?**  
    📘 **Guidance:**
    - Use COUNTIF with wildcards: `=COUNTIF(Name_Range, "*Mr.*")` 
    - The asterisk (*) is a wildcard that matches any characters
    - Count each title separately: Mr., Mrs., Miss, and Master
    - Note: Some passengers may have multiple titles or unusual formats

---

## 📝 Submission Guidelines

1. **Save your Excel file** with your answers clearly marked
2. **Use cell comments or a separate "Answers" sheet** to document your formulas
3. **Show your work** - formulas are just as important as the final answers
4. **Double-check** your counts and calculations

## 💡 Excel Tips for Success

- **Use Filter feature** (Data → Filter) to explore subsets of data
- **Create Pivot Tables** for quick summarization (optional but helpful)
- **Use named ranges** to make formulas more readable
- **CTRL+`** (backtick) shows all formulas in your worksheet
- **Test your formulas** on small samples before applying to the entire dataset

---

## 🎯 Learning Objectives

By completing this assignment, you will:
- ✅ Master essential Excel counting functions (COUNT, COUNTA, COUNTIF, COUNTIFS)
- ✅ Perform statistical calculations (AVERAGE, MIN, MAX, percentages)
- ✅ Use text functions to parse and analyze string data
- ✅ Apply filtering and sorting to large datasets
- ✅ Combine multiple criteria for complex queries

---

**Good luck! 🍀**

*Remember: Excel skills are fundamental for data science. Take your time to understand each formula rather than just finding the answer.*
