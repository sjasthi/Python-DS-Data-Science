# Week 9: Excel for Data Analysis — Advanced Techniques and Practice

**Class date:** Saturday, November 14, 2026  
**Practice period:** November 14–20, 2026  
**Assignment deadline:** Friday, November 20, 2026, at 11:59 PM (course time)

## 📅 Overview

This is the second week of our Excel/Google Sheets unit. Building on Week 8, we will analyze multiple conditions, extract text, summarize data with PivotTables, and communicate findings with charts.

Continue using your chosen platform. **Excel and Google Sheets are both accepted for Assignment 6.**

## 🎯 Learning Objectives

By the end of this week, you should be able to:

- Use COUNTIFS, AVERAGEIF/AVERAGEIFS, and SUMIFS for conditional analysis.
- Combine conditions to identify passengers traveling alone.
- Extract last names with LEFT and FIND, and count passenger titles using wildcards.
- Calculate and validate survival rates by passenger class.
- Build a PivotTable and a chart for practice.
- Complete a clearly documented analysis with formulas and checked results.

---

## 📚 Course Materials

### Presentation
Review [Excel for Data Science: An Introduction](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Presentations/Excel_for_Data_Science_An_Introduction.pdf). This is the same course presentation used for both weeks.

### Choose Your Video Path
Use **either Excel or Google Sheets**. Follow the videos for your chosen platform; you do not need to watch both paths. Open your spreadsheet and practice as you watch. These direct YouTube tutorials replace the previous playlist; paid courses promoted by the creators are not required.

#### Microsoft Excel
| Video | Instructor | When to use it |
|---|---|---|
| [Excel Tutorial for Beginners](https://www.youtube.com/watch?v=LgXzzu68j7M) | Kevin Stratvert | Week 8: spreadsheet foundations |
| [Cleaning Data in Excel](https://www.youtube.com/watch?v=_jmiEGZ6PIY) | Alex The Analyst | Week 8: data preparation and quality |
| [Pivot Table Excel — Step-by-Step Tutorial](https://www.youtube.com/watch?v=dvbLrwD2SpA) | Kevin Stratvert | Week 9: summarizing and exploring data |
| [Full Project in Excel](https://www.youtube.com/watch?v=opJgMj1IUrc) | Alex The Analyst | Week 9: guided application; use relevant sections as needed |

The guided project is a learning resource, not an additional assignment. The Titanic assignment and the weekly lab below are graded separately.

#### Google Sheets
No Excel installation is needed. Start at [Google Sheets](https://sheets.google.com/).

| Video | Instructor | When to use it |
|---|---|---|
| [Google Sheets Tutorial for Beginners](https://www.youtube.com/watch?v=TENAbUa-R-w) | Kevin Stratvert | Main tutorial for both weeks: basics, formulas, sorting, filtering, charts, and PivotTables |
| [Google Sheets Formulas Tutorial](https://www.youtube.com/watch?v=9TVmdFtmbbo) | Kevin Stratvert | Additional formula practice across both weeks |
| [Google Sheets for Beginners — The Complete Course](https://www.youtube.com/watch?v=UvCANQhqsSw) | Technology for Teachers and Students | Alternative introduction or extra practice |

Useful chapters in Kevin's main Google Sheets tutorial:

- [7:46 — Entering data](https://www.youtube.com/watch?v=TENAbUa-R-w&t=466s)
- [19:54 — Formulas and calculations](https://www.youtube.com/watch?v=TENAbUa-R-w&t=1194s)
- [33:57 — Sorting and filtering](https://www.youtube.com/watch?v=TENAbUa-R-w&t=2037s)
- [36:39 — Charts](https://www.youtube.com/watch?v=TENAbUa-R-w&t=2199s)
- [39:09 — PivotTables](https://www.youtube.com/watch?v=TENAbUa-R-w&t=2349s)

Use the assignment instructions and built-in function help for specific functions beyond the introductory videos.

---

## 🧪 Lab 9: Google Sheets Part 2 — School Snack Shop

- **Instructions:** [Lab 9: Google Sheets Part 2](../Labs/lab9_google_sheets_part2.md)
- **Worth:** 20 points. The detailed grading rubric is included in the lab.
- **Estimated time:** 40–50 minutes.
- **Dataset:** [School snack shop CSV](../Labs/school_snack_shop.csv) — 30 fictional sales records shared by Labs 8 and 9.
- **Platform:** Google Sheets; no Excel installation is needed.

Continue in **YourName_SnackShop_Labs8_9** from Lab 8. Compare categories using conditional formulas, build a PivotTable, create a revenue chart, and make an evidence-based recommendation.

Submit the same workbook link through the usual course submission channel with instructor viewer access. Preserve your Lab 8 tabs and add the required Lab 9 analysis, PivotTable, and answers.

Follow the instructor's announced lab deadline. This **20-point lab is graded separately from the 50-point Titanic Assignment 6**.

---

## 📝 Assignment 6: Data Analysis Using Excel/Google Sheets

- **Due:** Friday, November 20, 2026, at 11:59 PM (course time).
- **Worth:** 50 points.
- **Dataset:** Titanic.
- **Questions:** 25, worth 2 points each.
- **Platform:** Complete one version using either Excel or Google Sheets.

| Resource | Link |
|---|---|
| Excel assignment | [Excel instructions](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/assignment_data_analysis_titanic_data_set_using_excel.md) |
| Google Sheets assignment | [Google Sheets instructions](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/assignment_data_analysis_titanic_data_set_using_google_sheets.md) |
| Dataset | [titanic_data.csv](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/datasets/titanic_data.csv) |

The existing assignment questions and submission instructions remain the same. Follow the version for your platform. The deadline for this academic year is **November 20, 2026**.

| Part | Questions | Focus |
|---|---|---|
| A: Data Exploration | 1–10 | Counts, missing data, categories, and unique tickets |
| B: Statistical Insights | 11–20 | Averages, percentages, fares, and survival rates |
| C: Text Analysis and Logical Queries | 21–25 | Multiple criteria, last names, and passenger titles |

## 🎯 Week 9 Focus Areas

### 1. Multi-Criteria Analysis

Practice COUNTIFS with equally sized ranges, conditional averages, and percentage calculations. Apply these skills to survival rates by class and passengers with both SibSp = 0 and Parch = 0.

### 2. Text Analysis

Practice LEFT, RIGHT, MID, FIND/SEARCH, and LEN as needed. Extract the last name before the comma into a helper column, build a frequency table, and identify the most common last name. Use COUNTIF with wildcards to count titles.

For example, if the passenger name is in D2, try:

```excel
=LEFT(D2,FIND(",",D2)-1)
```

Check the actual column locations in your workbook before copying formulas.

### 3. PivotTables and Charts

- Excel students: watch the PivotTable tutorial and relevant sections of the full project.
- Google Sheets students: use the charts and PivotTables chapters in the main tutorial.
- Practice summarizing passenger counts by class and creating a labeled chart.
- Compare a PivotTable result with a formula result as a cross-check.

These are practice activities; follow the existing assignment instructions for graded deliverables.

---

## 🗓️ Suggested Week 9 Schedule

| Dates | Focus | Activities |
|---|---|---|
| November 14–15 | Conditional and text functions | Resolve Week 8 questions. Practice multi-criteria formulas and text extraction. Continue Parts B and C. Begin Lab 9 in your Lab 8 snack shop workbook. |
| November 16–17 | Summaries and application | Follow the PivotTable/chart resources for your platform. Excel students can use the full project for guided practice. Complete Lab 9 (20 points), including its PivotTable, chart, and recommendation. Complete remaining assignment questions. |
| November 18–19 | Review | Check all 25 answers, formula ranges, missing values, and percentage calculations. Explain complex formulas and organize the Answers sheet. |
| Friday, November 20 | Submit | Follow your platform's existing submission instructions. Check the file or sharing access and submit by 11:59 PM (course time). |

## 💡 Practice and Data Quality

- Preserve the original dataset; use a working copy and separate helper columns.
- Keep entire rows together when sorting.
- Exclude the header from calculations.
- Use ranges ending at the last passenger row when counting blanks. An open-ended range can count unused rows as missing data.
- Distinguish missing ages from zero ages; do not replace missing values with zero just to simplify calculations.
- Check whether percentages are stored as fractions formatted as percentages or multiplied by 100; avoid doing both.
- Show formulas and label answers by question number.
- Use assignment hints, built-in function help, and class discussions when you get stuck.

## 🔍 Submission Checklist

- [ ] Complete Lab 9 (20 points) and submit the shared workbook link with instructor viewer access.
- [ ] Preserve Lab 8 work and include all required Lab 9 tabs.

- [ ] Answer all 25 questions.
- [ ] Label answers by question number.
- [ ] Include formulas, not just pasted results.
- [ ] Verify ranges, conditions, blanks, and percentage formatting.
- [ ] Explain complex formulas using comments or the Answers sheet.
- [ ] Preserve the original data.
- [ ] Excel: save the workbook and verify it opens.
- [ ] Google Sheets: verify the instructor can view the submitted Sheet.
- [ ] Submit by **Friday, November 20, 2026, at 11:59 PM (course time)**.

## 🆘 Getting Help

Revisit the video sections relevant to your question and consult your platform's assignment instructions. For formula errors, check range sizes, cell references, text versus numeric criteria, and missing delimiters. Ask questions early enough to leave time for review.

## 🐍 Connection to Python Data Science

Spreadsheet skills prepare you to recognize similar operations in pandas:

| Spreadsheet task | pandas concept |
|---|---|
| Import a CSV | read_csv |
| Sort and filter rows | sort_values and Boolean filtering |
| Summarize categories | groupby and aggregation |
| Build a PivotTable | pivot_table |
| Identify missing data | isna |
| Parse names | String methods |

[Previous: Week 8 outline](week_8_outline_%2811_07_26%29.md)

**Reminder:** Complete one version of Assignment 6 using Excel **or** Google Sheets.
