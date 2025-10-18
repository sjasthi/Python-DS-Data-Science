# 🚢 Titanic Dataset Analysis - Google Sheets Assignment

## Overview
This assignment will help you develop essential Google Sheets skills for data analysis using the famous Titanic dataset. You will explore data, perform statistical analysis, and use advanced Google Sheets functions.

**Total Points:** 25 (1 point per question)

---

## 📥 Getting the Dataset into Google Sheets

**Dataset Source:** [Titanic Data CSV](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/datasets/titanic_data.csv)

### Instructions to Import CSV into Google Sheets:

#### **Option 1: IMPORTDATA Function (Easiest)**
1. Open a new Google Sheet
2. In cell A1, type: `=IMPORTDATA("https://raw.githubusercontent.com/sjasthi/Python-DS-Data-Science/main/datasets/titanic_data.csv")`
3. Press Enter and wait a few seconds for the data to load
4. ✅ Done! The data will automatically update if the source changes

#### **Option 2: File Import**
1. Download the CSV file:
   - Go to: https://github.com/sjasthi/Python-DS-Data-Science/blob/main/datasets/titanic_data.csv
   - Click **"Raw"** button
   - Right-click → **"Save As"** → Save as `titanic_data.csv`
2. Open Google Sheets → **File** → **Import**
3. **Upload** tab → Select your CSV file
4. Choose **"Replace spreadsheet"** or **"Insert new sheet(s)"**
5. Click **"Import data"**

#### **Option 3: Direct URL Import**
1. Open Google Sheets
2. **File** → **Import** → **URL** tab
3. Paste: `https://raw.githubusercontent.com/sjasthi/Python-DS-Data-Science/main/datasets/titanic_data.csv`
4. Click **"Import data"**

---

## 📋 Dataset Columns
Your dataset contains the following columns:
- **Id**: Passenger ID
- **Survived**: 0 = No, 1 = Yes
- **Pclass**: Passenger Class (1 = 1st, 2 = 2nd, 3 = 3rd)
- **Name**: Passenger name
- **Sex**: Male or Female
- **Age**: Age in years (some values are missing)
- **SibSp**: Number of siblings/spouses aboard
- **Parch**: Number of parents/children aboard
- **Ticket**: Ticket number
- **Fare**: Ticket fare
- **Cabin**: Cabin number (many values are missing)
- **Embarked**: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

---

## 🧩 Part A – Data Exploration (Basic Google Sheets Skills)
*Focus: COUNT, COUNTA, COUNTIF, COUNTIFS, and basic data exploration*

1. **How many passengers are in the dataset?**
   - 📗 **Google Sheets Tip:** Use `=COUNTA(A2:A)` to count non-empty cells in column A (Id column)

2. **How many people survived?**
   - 📗 **Google Sheets Tip:** Use `=COUNTIF(B2:B, 1)` where B is the Survived column

3. **How many males and females were on board?**
   - 📗 **Google Sheets Tip:** `=COUNTIF(E2:E, "male")` and `=COUNTIF(E2:E, "female")`

4. **How many passengers traveled in each passenger class (1st, 2nd, and 3rd)?**
   - 📗 **Google Sheets Tip:** Use `=COUNTIF(C2:C, 1)` for 1st class, similar for 2nd and 3rd

5. **How many passengers are missing age values?**
   - 📗 **Google Sheets Tip:** `=COUNTBLANK(F2:F)` where F is the Age column

6. **How many passengers are missing cabin information?**
   - 📗 **Google Sheets Tip:** `=COUNTBLANK(K2:K)` where K is the Cabin column

7. **How many passengers embarked from each port (C, Q, and S)?**
   - 📗 **Google Sheets Tip:** `=COUNTIF(L2:L, "C")` for Cherbourg, similar for Q and S

8. **What is the most common embarkation port?**
   - 📗 **Google Sheets Tip:** Use `=INDEX(L2:L, MODE(MATCH(L2:L, L2:L, 0)))` or visually identify from Q7

9. **How many tickets contain only numeric values (no letters)?**
   - 📗 **Google Sheets Tip:** Create a helper column with `=ISNUMBER(VALUE(I2))` then count TRUEs with `=COUNTIF(helper_column, TRUE)`
   - Alternative: `=SUMPRODUCT(--(ISNUMBER(VALUE(I2:I))))`

10. **What is the total number of unique ticket numbers?**
    - 📗 **Google Sheets Tip:** `=COUNTA(UNIQUE(I2:I))` - Google Sheets has a built-in UNIQUE function!

---

## 📊 Part B – Statistical Insights (Functions, Filters, and Sorting)
*Focus: AVERAGE, AVERAGEIF, Percentages, Sorting, MIN, MAX, LARGE, SMALL*

11. **What is the average age of all passengers?**
    - 📗 **Google Sheets Tip:** `=AVERAGE(F2:F)` - automatically ignores blank cells

12. **What is the average age of survivors?**
    - 📗 **Google Sheets Tip:** `=AVERAGEIF(B2:B, 1, F2:F)` where B is Survived, F is Age

13. **What percentage of passengers survived overall?**
    - 📗 **Google Sheets Tip:** `=COUNTIF(B2:B, 1)/COUNTA(B2:B)*100`

14. **How many passengers were age 30 or older?**
    - 📗 **Google Sheets Tip:** `=COUNTIF(F2:F, ">=30")`

15. **How many passengers were under age 30?**
    - 📗 **Google Sheets Tip:** `=COUNTIF(F2:F, "<30")`

16. **How many senior citizens (age > 60) were on board?**
    - 📗 **Google Sheets Tip:** `=COUNTIF(F2:F, ">60")`

17. **What is the average fare paid by passengers?**
    - 📗 **Google Sheets Tip:** `=AVERAGE(J2:J)` where J is the Fare column

18. **What is the highest fare paid, and what is the lowest fare paid?**
    - 📗 **Google Sheets Tip:** `=MAX(J2:J)` and `=MIN(J2:J)`

19. **What are the names of 3 passengers who paid the highest fares?**
    - 📗 **Google Sheets Tip:** 
      - Method 1: Select Fare column → **Data** → **Sort sheet Z→A**
      - Method 2: Use `=LARGE(J2:J, 1)` to find highest, then `=FILTER(D2:D, J2:J=LARGE(J2:J,1))` to get names

20. **What is the survival rate (percentage) for each passenger class?**
    - 📗 **Google Sheets Tip:** For 1st class: `=COUNTIFS(C2:C, 1, B2:B, 1)/COUNTIF(C2:C, 1)*100`
    - Repeat for classes 2 and 3

---

## 🧠 Part C – Text Analysis and Logical Queries (Advanced Google Sheets)
*Focus: Multiple criteria, text functions, logical operators*

21. **How many passengers had no parents or children aboard (Parch = 0)?**
    - 📗 **Google Sheets Tip:** `=COUNTIF(H2:H, 0)` where H is Parch column

22. **How many passengers had no siblings or spouses aboard (SibSp = 0)?**
    - 📗 **Google Sheets Tip:** `=COUNTIF(G2:G, 0)` where G is SibSp column

23. **How many passengers traveled completely alone (both SibSp = 0 AND Parch = 0)?**
    - 📗 **Google Sheets Tip:** `=COUNTIFS(G2:G, 0, H2:H, 0)`

24. **What is the most common last name among passengers?**
    - 📗 **Google Sheets Guidance:**
      - **Method 1 (Helper Column):** 
        - Create helper column: `=LEFT(D2, FIND(",", D2)-1)` to extract last name
        - Use `=MODE(COUNTIF($M$2:M2, M2:M))` approach or create a frequency table
      - **Method 2 (QUERY Function):** 
        - Extract last names then use: `=QUERY(helper_column, "select Col1, count(Col1) group by Col1 order by count(Col1) desc limit 1")`
      - **Method 3 (Data → Split text to columns):**
        - Copy Name column
        - **Data** → **Split text to columns** → Choose **Comma** as separator
        - Use COUNTIF on the first name column to find most common

25. **How many passengers have titles "Mr.", "Mrs.", "Miss", and "Master" in their names?**
    - 📗 **Google Sheets Guidance:**
      - Use COUNTIF with wildcards: 
        - `=COUNTIF(D2:D, "*Mr.*")` for Mr.
        - `=COUNTIF(D2:D, "*Mrs.*")` for Mrs.
        - `=COUNTIF(D2:D, "*Miss*")` for Miss
        - `=COUNTIF(D2:D, "*Master*")` for Master
      - The asterisk (*) is a wildcard that matches any characters
      - Count each title separately

---

## 📝 Submission Guidelines

1. **Share your Google Sheet** with your instructor
   - Click **Share** button (top right)
   - Set to "Anyone with the link can view" or add instructor's email
2. **Create an "Answers" sheet** with your responses and formulas
3. **Show your work** - formulas are just as important as the final answers
4. **Use cell comments** (Right-click → Comment) to explain complex formulas
5. **Double-check** your counts and calculations

---

## 💡 Google Sheets Tips for Success

### Essential Functions
- `=UNIQUE(range)` - Get unique values (great for Q10!)
- `=FILTER(range, condition)` - Filter data based on criteria
- `=QUERY(data, query)` - Powerful SQL-like queries
- `=ARRAYFORMULA()` - Apply formula to entire column at once
- `=REGEXMATCH(text, pattern)` - Pattern matching for advanced text analysis

### Keyboard Shortcuts
- **CTRL + /** (Windows) or **⌘ + /** (Mac): Show/hide formulas
- **CTRL + SHIFT + V**: Paste values only
- **CTRL + ALT + SHIFT + =**: Insert current date/time
- **Data → Create a filter**: Add filter dropdowns to headers

### Google Sheets Advantages
- ✅ **UNIQUE() function** - No need for complex Remove Duplicates
- ✅ **QUERY() function** - SQL-like data manipulation
- ✅ **ARRAYFORMULA()** - Apply formulas to entire columns automatically
- ✅ **Real-time collaboration** - Work with classmates simultaneously
- ✅ **Cloud-based** - Access from anywhere
- ✅ **IMPORTDATA()** - Live data connection to CSV files

### Data Exploration Tools
- **Data → Pivot table** - Quick summarization (optional but helpful)
- **Data → Create a filter** - Explore subsets of data
- **Explore button** (bottom right) - AI-powered insights
- **Data → Data validation** - Check data quality

---

## 🎯 Learning Objectives

By completing this assignment, you will:
- ✅ Master essential Google Sheets counting functions (COUNT, COUNTA, COUNTIF, COUNTIFS)
- ✅ Perform statistical calculations (AVERAGE, MIN, MAX, percentages)
- ✅ Use text functions to parse and analyze string data (LEFT, FIND, SPLIT)
- ✅ Apply filtering and sorting to large datasets
- ✅ Combine multiple criteria for complex queries
- ✅ Leverage Google Sheets unique features (UNIQUE, QUERY, FILTER)

---

## 🆚 Key Differences from Excel

| Task | Excel | Google Sheets |
|------|-------|---------------|
| Unique values | Remove Duplicates tool | `=UNIQUE(range)` |
| Filter data | Filter dropdown | `=FILTER(range, condition)` |
| Count unique | `=SUMPRODUCT(1/COUNTIF())` | `=COUNTA(UNIQUE(range))` |
| Import CSV | Open file dialog | `=IMPORTDATA(url)` |
| Advanced queries | Power Query | `=QUERY()` function |
| Array formulas | CTRL+SHIFT+Enter | Automatic with ARRAYFORMULA |

---

**Good luck! 🍀**

*Remember: Google Sheets skills are fundamental for data science and collaborate well with Python. Take your time to understand each formula rather than just finding the answer.*

**Questions or issues?** Google Sheets has built-in help - just type your function name and press **F1** or click the **?** icon.
