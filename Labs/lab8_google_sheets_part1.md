# Lab 8: Google Sheets for Data Analysis — Part 1

**Week 8:** November 7, 2026  
**Estimated time:** 35–45 minutes  
**Tools:** A browser, a Google account, and Google Sheets. Excel is not required.

## Goal

Import a small dataset, use basic formulas, and explore records with sorting and filtering. Keep your workbook for [Lab 9](lab9_google_sheets_part2.md).

By the end, you should be able to:

- Identify numeric and categorical columns.
- Import data and format a spreadsheet.
- Use COUNT, COUNTA, COUNTIF, AVERAGE, MIN, and MAX.
- Distinguish sorting records from filtering records.
- Record formulas and explain findings.

## Shared Dataset: Iris Flowers

We will use the **same 30 records for Lab 8 and Lab 9**. Iris is a standard dataset used to learn data analysis and machine learning. Each row describes one flower.

This teaching subset contains the **first 10 records of each species** in [Seaborn's Iris CSV](https://github.com/mwaskom/seaborn-data/blob/master/iris.csv). Measurements and species labels are unchanged. The full source has 150 records; this lab uses 30. This is a small, deliberately selected subset, so describe findings as applying to these records.

| Column | Meaning | Type / unit |
|---|---|---|
| A: sepal_length | Length of a sepal (outer flower part) | Number, cm |
| B: sepal_width | Width of a sepal | Number, cm |
| C: petal_length | Length of a petal | Number, cm |
| D: petal_width | Width of a petal | Number, cm |
| E: species | Flower species | Text: setosa, versicolor, virginica |

**Included data:** [iris_google_sheets_labs.csv](iris_google_sheets_labs.csv)  
**Raw CSV:** https://raw.githubusercontent.com/sjasthi/Python-DS-Data-Science/main/Labs/iris_google_sheets_labs.csv

There are 30 data rows plus one header row. The original data occupies **A1:E31**. All four measurement columns are complete.

## Part A: Create Your Workbook (10 minutes)

1. Open [Google Sheets](https://sheets.google.com/) and create a blank spreadsheet.
2. Name it **YourName_Iris_Labs8_9**.
3. Download the included CSV: open its GitHub page, choose **Raw** or **Download raw file**, and save it as a CSV.
4. In Sheets, choose **File → Import → Upload**, select the CSV, and import it with comma as the separator. Use the option to insert a new sheet if offered.
5. Rename the imported tab **Iris_Data**. Remove an unused empty tab if one remains.
6. Confirm that headers occupy A1:E1 and the last data row is 31. If everything appears in one column, reimport with comma as the separator.
7. Bold the header, freeze the first row, and resize columns so headers are readable. Format A2:D31 as numbers with two decimal places.
8. Keep **Iris_Data** unchanged. Duplicate it and name the copy **Practice**.
9. Create a tab named **Lab8_Answers** with columns **Question**, **Result / formula**, and **Explanation**. Put answer formulas in column B.

### Copy-and-Paste Alternative

Instead of downloading, copy the tab-separated block below into cell A1 of an empty **Iris_Data** tab. It contains exactly the same data as the CSV. Do not import it a second time if you already imported the CSV.

```tsv
sepal_length	sepal_width	petal_length	petal_width	species
5.1	3.5	1.4	0.2	setosa
4.9	3.0	1.4	0.2	setosa
4.7	3.2	1.3	0.2	setosa
4.6	3.1	1.5	0.2	setosa
5.0	3.6	1.4	0.2	setosa
5.4	3.9	1.7	0.4	setosa
4.6	3.4	1.4	0.3	setosa
5.0	3.4	1.5	0.2	setosa
4.4	2.9	1.4	0.2	setosa
4.9	3.1	1.5	0.1	setosa
7.0	3.2	4.7	1.4	versicolor
6.4	3.2	4.5	1.5	versicolor
6.9	3.1	4.9	1.5	versicolor
5.5	2.3	4.0	1.3	versicolor
6.5	2.8	4.6	1.5	versicolor
5.7	2.8	4.5	1.3	versicolor
6.3	3.3	4.7	1.6	versicolor
4.9	2.4	3.3	1.0	versicolor
6.6	2.9	4.6	1.3	versicolor
5.2	2.7	3.9	1.4	versicolor
6.3	3.3	6.0	2.5	virginica
5.8	2.7	5.1	1.9	virginica
7.1	3.0	5.9	2.1	virginica
6.3	2.9	5.6	1.8	virginica
6.5	3.0	5.8	2.2	virginica
7.6	3.0	6.6	2.1	virginica
4.9	2.5	4.5	1.7	virginica
7.3	2.9	6.3	1.8	virginica
6.7	2.5	5.8	1.8	virginica
7.2	3.6	6.1	2.5	virginica
```

If the pasted block stays in column A, select the pasted cells and use **Data → Split text to columns**, choosing Tab or automatic detection. Confirm A1:E31 before continuing.

## Part B: Describe the Data with Formulas (15 minutes)

Enter one answer per row on **Lab8_Answers**. Label each answer Q1–Q8. Use formulas that reference **Iris_Data**, so sorting Practice does not affect your work.

| Question | Task | Hint |
|---|---|---|
| Q1 | How many flowers are recorded? | COUNT on a measurement column |
| Q2 | How many species labels are present? | COUNTA on column E |
| Q3 | What is the average sepal length? | AVERAGE on column A |
| Q4 | What is the shortest petal length? | MIN on column C |
| Q5 | What is the longest petal length? | MAX on column C |
| Q6 | How many flowers are setosa? | COUNTIF on column E |
| Q7 | How many flowers are versicolor? | COUNTIF on column E |
| Q8 | How many flowers are virginica? | COUNTIF on column E |

**Worked example for Q1:**

```excel
=COUNT(Iris_Data!A2:A31)
```

For COUNTIF, the species criterion is text, such as `"setosa"`. Format average and measurement results to two decimal places while retaining the underlying formula.

**Think about it:** Why might COUNT and COUNTA give different results on the species column? Explain in one sentence.

## Part C: Sort and Filter (10 minutes)

Work only on **Practice**.

1. Select the complete table **A1:E31** and create a filter using **Data → Create a filter**.
2. Use the sepal length header's filter menu to sort **Z → A** (largest to smallest). Keep all columns together.
3. **Q9:** Record the largest sepal length and its species.
4. Filter species to **setosa** only.
5. **Q10:** How many records remain visible? What do you notice about their petal lengths?
6. Restore all species in the filter. Confirm that all 30 records are visible again.

**Important:** COUNT and AVERAGE on ordinary ranges still include rows hidden by a filter. For this activity, count the visible records directly; in Lab 9, use conditional formulas to summarize specific groups.

## Part D: Reflect and Save (5 minutes)

On **Lab8_Answers**, write:

- **Q11:** Two observations supported by your calculations. Include a number and unit where relevant.
- **Q12:** One question about species differences you would like to investigate in Lab 9.

### Check Your Setup

- Q1 and Q2 should both be **30**.
- Q6, Q7, and Q8 should add to Q1.
- There should be no missing measurement cells in A2:D31.
- The original Iris_Data tab should still have 30 data rows.

## What to Submit

Submit your Google Sheets link through the usual course submission channel. Give your instructor viewer access and test the link. Your workbook should contain:

- **Iris_Data:** unchanged source records.
- **Practice:** your sorting/filtering work, with all species visible at the end.
- **Lab8_Answers:** Q1–Q12, with formulas for Q1–Q8 and written explanations.

Keep this same workbook for Lab 9. Follow the instructor's announced submission deadline.

## Help

[Google Sheets Tutorial for Beginners — Kevin Stratvert](https://www.youtube.com/watch?v=TENAbUa-R-w): data entry at 7:46, formulas at 19:54, sorting/filtering at 33:57.

[Continue to Lab 9: Part 2](lab9_google_sheets_part2.md)
