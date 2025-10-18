# Week 8: Excel for Data Science - Advanced Techniques & Practice

## 📅 Overview
Welcome to Week 8! This week we **continue our exploration of Excel and Google Sheets** for data analysis. Building on Week 7's foundation, we'll dive deeper into advanced functions, practice complex queries, and complete Assignment 6.

**This is the second and final week for Excel/Sheets.** Focus on mastering the techniques and completing your assignment!

---

## 🎯 Learning Objectives

By the end of this week, you will be able to:
- Master advanced Excel functions (COUNTIFS, AVERAGEIF, text functions)
- Perform complex multi-criteria analysis
- Extract and parse text data using formulas
- Apply logical operations for data filtering
- Create comprehensive data analysis reports
- Confidently use Excel/Sheets for real-world data science tasks

---

## 📚 Materials (Same as Week 7)

### 1. Course Presentation
**Excel for Data Science: An Introduction**

📄 [View Presentation](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Presentations/Excel_for_Data_Science_An_Introduction.pdf)

If you haven't reviewed this yet, please do so now. It provides important context for why Excel is essential in data science workflows.

---

### 2. Video Tutorials (Continue or Review)
**Excel Video Playlist - Technology for Teachers and Students**

🎥 [Watch Playlist](https://www.youtube.com/watch?v=UPnlqzNWKrw&list=PLlKpQrBME6xLDnoK7OovAVVsGNV55MS3K)

**Playlist Details:**
- **Total Videos:** 60
- **Video Length:** 1-2 minutes each
- **Total Time:** Approximately 2 hours

**Week 8 Strategy:**
- If you finished all videos last week → **Review videos related to your assignment questions**
- If you didn't finish → **Complete remaining videos this week**
- **Focus on:** Videos covering COUNTIFS, text functions (LEFT, RIGHT, FIND), and conditional formulas

**📌 Pro Tip:** Rewatch specific videos when you get stuck on assignment questions. Each video is only 1-2 minutes, perfect for quick reference!

---

## 📝 Assignment 6: Data Analysis Using Excel/Google Sheets

### Assignment Details (REMINDER)
- **Worth:** 50 points
- **Due Date:** October 31, 2025 (11:59 PM) ⏰ **Coming Up Soon!**
- **Dataset:** Titanic Dataset
- **Total Questions:** 25 (2 points each)

### Choose Your Platform
Complete this assignment using **either Excel OR Google Sheets**.

#### Option 1: Microsoft Excel
📄 [Excel Assignment Instructions](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/assignment_data_analysis_titanic_data_set_using_excel.md)

**Best for:** Students with Microsoft Excel (Windows or Mac)

#### Option 2: Google Sheets
📄 [Google Sheets Assignment Instructions](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/assignment_data_analysis_titanic_data_set_using_google_sheets.md)

**Best for:** Students who prefer cloud-based tools or don't have Excel

---

## 📖 Week 8 Focus Areas

This week, concentrate on mastering these advanced topics that are critical for Assignment 6:

### 🎯 Priority 1: Multi-Criteria Functions
**Functions to Master:**
- `COUNTIFS()` - Count with multiple conditions
- `AVERAGEIF()` / `AVERAGEIFS()` - Conditional averages
- `SUMIFS()` - Conditional sums

**Where you'll use them:**
- Part B: Survival rates by passenger class
- Part C: Passengers traveling alone (SibSp=0 AND Parch=0)
- Part C: Complex filtering scenarios

**Practice:** Try creating your own multi-criteria questions and solve them!

---

### 🎯 Priority 2: Text Functions
**Functions to Master:**
- `LEFT()`, `RIGHT()`, `MID()` - Extract portions of text
- `FIND()`, `SEARCH()` - Locate text within strings
- `LEN()` - Text length
- Text to Columns feature
- Wildcard matching with `COUNTIF()`

**Where you'll use them:**
- Part A: Identifying tickets with only numbers
- Part C: Extracting last names from full names
- Part C: Counting passengers by title (Mr., Mrs., Miss, Master)

**Practice:** Try extracting different parts of passenger names!

---

### 🎯 Priority 3: Data Validation & Quality
**Skills to Master:**
- Handling missing/blank values
- Counting unique values
- Using `COUNTA()` vs `COUNT()`
- `COUNTBLANK()` for missing data

**Where you'll use them:**
- Part A: Questions about missing ages and cabins
- Part A: Counting unique ticket numbers
- All sections: Ensuring your formulas handle blanks correctly

---

## 🗓️ Suggested Week 8 Schedule

### Day 1-2: Advanced Functions Deep Dive
- ✅ Focus on COUNTIFS and multi-criteria formulas
- ✅ Practice text extraction functions (LEFT, FIND, etc.)
- ✅ Work on Part C of Assignment 6 (Advanced Analysis)

### Day 3-4: Assignment Completion Sprint
- ✅ Complete any remaining assignment questions
- ✅ Double-check all formulas and answers
- ✅ Document your work with comments and clear labels
- ✅ Test edge cases (what if there are blanks, ties, etc.?)

### Day 5-6: Review & Refinement
- ✅ Review all 25 answers for accuracy
- ✅ Ensure formulas are visible/documented
- ✅ Format your spreadsheet professionally
- ✅ Add an "Answers" sheet with explanations
- ✅ Verify you've answered every question

### Day 7: Final Submission
- ✅ Final quality check
- ✅ Submit assignment before deadline (Oct 31, 11:59 PM)
- ✅ Celebrate your Excel mastery! 🎉

---

## 💡 Week 8 Success Strategies

### Tackling Difficult Questions
**Part C Questions are the most challenging!** Here's how to approach them:

#### Question 24: Most Common Last Name
**Approaches:**
1. **Text to Columns Method:**
   - Copy Name column → Data → Text to Columns → Delimiter: Comma
   - Use COUNTIF on the extracted last names
   - Find the MAX count

2. **Formula Method:**
   - Create helper column: `=LEFT(Name, FIND(",", Name)-1)`
   - Count occurrences and identify most common

3. **Google Sheets Bonus:**
   - Use `UNIQUE()` and `QUERY()` functions for elegant solution

#### Question 25: Counting by Title
**Strategy:**
- Use wildcards: `=COUNTIF(Name_Range, "*Mr.*")`
- The `*` matches any characters before/after "Mr."
- Count each title separately: Mr., Mrs., Miss, Master

**Pro Tip:** Test your formulas on a few rows first to ensure they work correctly!

---

### Common Week 8 Challenges & Solutions

#### Challenge 1: "My COUNTIFS isn't working!"
**Solutions:**
- Check that all ranges are the same size
- Ensure criteria are properly formatted (numbers vs text)
- Use absolute references ($) where needed
- Verify there are no extra spaces in criteria

#### Challenge 2: "Text functions return errors"
**Solutions:**
- Check for blank cells (use IFERROR wrapper)
- Verify the delimiter exists (e.g., comma in name)
- Test on a single cell first before applying to entire column

#### Challenge 3: "I don't know which function to use"
**Solutions:**
- Read the question carefully - keywords matter!
- "How many" → COUNT functions
- "Average" → AVERAGE functions
- "Multiple conditions" → Use functions ending in "S" (COUNTIFS, SUMIFS)
- "Extract text" → LEFT, RIGHT, MID, FIND

#### Challenge 4: "Running out of time!"
**Solutions:**
- Focus on Parts A & B first (easier questions)
- Use Google if stuck - search "Excel [your question]"
- Ask for help in office hours or discussion forum
- Part C is advanced - allocate more time for it

---

## 🔍 Quality Checklist Before Submission

### Formula Verification
- [ ] All 25 questions answered
- [ ] Formulas are visible (not just values)
- [ ] Formulas reference correct columns/ranges
- [ ] No hardcoded values (use cell references)
- [ ] Formulas handle blank/missing values correctly

### Documentation
- [ ] Created separate "Answers" sheet OR used cell comments
- [ ] Clearly labeled which cell answers which question
- [ ] Explained complex formulas
- [ ] Original data sheet remains unmodified

### Accuracy Check
- [ ] Tested formulas on sample data
- [ ] Results make logical sense
- [ ] Percentages calculated correctly
- [ ] No obvious errors or warnings

### Presentation
- [ ] Professional formatting
- [ ] Clear column headers
- [ ] Organized layout
- [ ] Easy for instructor to grade

---

## 🆘 Getting Help This Week

### Immediate Resources
1. **Video Playlist:** Rewatch specific topics (videos are 1-2 mins each)
2. **Assignment Instructions:** Both versions have helpful hints
3. **Google Search:** "Excel [function name] tutorial" is your friend
4. **Built-in Help:** Excel/Sheets have function help - click the `?` icon

### Interactive Help
1. **Office Hours:** Take advantage this week - assignment due soon!
2. **Discussion Forum:** Post questions early, help classmates
3. **Study Groups:** Team up with classmates (but submit your own work!)

### Last-Minute Help (Day Before Deadline)
- **Start Early!** Don't wait until Oct 30
- **Save frequently**
- **Submit with what you have** - partial credit is better than zero
- **Test your file opens correctly** before submitting

---

## 🔗 Quick Links Summary

| Resource | Link |
|----------|------|
| Course Presentation | [Excel_for_Data_Science_An_Introduction.pdf](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Presentations/Excel_for_Data_Science_An_Introduction.pdf) |
| Video Playlist (60 videos) | [YouTube Playlist](https://www.youtube.com/watch?v=UPnlqzNWKrw&list=PLlKpQrBME6xLDnoK7OovAVVsGNV55MS3K) |
| Assignment 6 (Excel) | [Excel Instructions](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/assignment_data_analysis_titanic_data_set_using_excel.md) |
| Assignment 6 (Google Sheets) | [Google Sheets Instructions](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/assignment_data_analysis_titanic_data_set_using_google_sheets.md) |
| Titanic Dataset (CSV) | [titanic_data.csv](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/datasets/titanic_data.csv) |

---

## 🎯 Advanced Practice (Optional Bonus)

Want to go beyond the assignment? Try these challenges:

### Challenge 1: Create a Dashboard
Build a simple visual dashboard showing:
- Total passengers by class (bar chart)
- Survival rate by sex (pie chart)
- Age distribution (histogram)

### Challenge 2: Additional Analysis
Answer these bonus questions:
- What's the average fare by passenger class?
- What's the survival rate for children (age < 18) vs adults?
- Which embarkation port had the highest survival rate?

### Challenge 3: Data Cleaning
- Identify and flag any data quality issues
- Create a "cleaned" version of the dataset
- Document your data cleaning decisions

---

## 📊 Excel Skills You've Mastered

By completing Weeks 7 & 8, you now know:

✅ **Basic Functions**
- COUNT, COUNTA, COUNTIF, COUNTBLANK
- SUM, AVERAGE, MIN, MAX
- Percentage calculations

✅ **Intermediate Functions**
- COUNTIFS, AVERAGEIF, SUMIFS (multi-criteria)
- LARGE, SMALL, RANK (sorting and ranking)
- UNIQUE, ISNUMBER (data validation)

✅ **Advanced Functions**
- LEFT, RIGHT, MID, FIND (text parsing)
- Nested IF statements
- Wildcards in COUNTIF
- Array formulas (optional)

✅ **Data Skills**
- Filtering and sorting
- Handling missing values
- Data exploration techniques
- Statistical analysis

✅ **Professional Skills**
- Documentation and comments
- Formula best practices
- Data quality checking
- Spreadsheet organization

**Congratulations!** These skills are directly applicable to real-world data science work! 🎓

---

## 🚀 Looking Ahead: Week 9

After completing Excel/Sheets, we'll return to Python and learn how:
- Pandas DataFrames are similar to Excel spreadsheets
- Many Excel functions have Pandas equivalents
- Python can automate what you did manually in Excel
- To read Excel files into Python for analysis

**The Excel skills you learned will make Pandas much easier to understand!**

---

## 📌 Critical Reminders

- ⏰ **ASSIGNMENT DUE:** October 31, 2025 (11:59 PM) - **This Week!**
- 💯 **Worth 50 Points:** Significant impact on your grade
- 📊 **Show Formulas:** Document your work clearly
- 🔄 **Final Week:** No extensions - complete by deadline
- ✅ **Submit Early:** Don't risk last-minute technical issues

---

## 💪 Motivation

You've come a long way! Excel might have seemed intimidating at first, but you're now equipped with powerful data analysis skills used by professionals worldwide.

**Remember:**
- Every data scientist uses spreadsheets
- These skills complement your Python knowledge
- Excel proficiency boosts your resume
- You're building a strong data analysis foundation

**You've got this! Finish strong! 💪📊**

---

**Questions? This is your last week for Excel help - use office hours!**

**Good luck completing Assignment 6! 🍀✨**
