# Lab 8: Google Sheets Part 1 — School Snack Shop

**Week 8:** November 7, 2026  
**Points:** 20  
**Estimated time:** 40–50 minutes  
**Tools:** Browser, Google account, and Google Sheets. Excel is not required.

## Your Mission

Help the school snack shop understand its sales. Import data, calculate revenue, and explore which items sold well. Keep your workbook for [Lab 9](lab9_google_sheets_part2.md).

You will practice:

- Importing and formatting a spreadsheet.
- Multiplication and filling formulas down.
- SUM, COUNT, COUNTA, AVERAGE, MIN, MAX, and COUNTIF.
- Sorting and filtering complete records.
- Explaining findings with numbers.

## Shared Dataset: School Snack Shop

Imagine helping run a school snack shop for one week. Your job is to find out what sold well and how much money the shop collected.

This is **fictional practice data created for these labs**. The same **30 records** are used in Lab 8 and Lab 9: six items sold on each of five school days. Each row is **one item's sales for one day**, not one purchase or one student.

| Column | Header | Meaning |
|---|---|---|
| A | Day | Monday through Friday |
| B | Item | Name of the item sold |
| C | Category | Fruit, Snacks, or Drinks |
| D | Unit_Price | Price of one item in US dollars |
| E | Units_Sold | Number of that item sold that day |
| F (you create) | Revenue | Unit price multiplied by units sold |

**Revenue** means money collected from sales. It is not profit: we do not have the shop's costs.

- [Downloadable dataset: school_snack_shop.csv](school_snack_shop.csv)
- [Raw CSV](https://raw.githubusercontent.com/sjasthi/Python-DS-Data-Science/main/Labs/school_snack_shop.csv)

The supplied CSV contains **A1:E31**: one header row and 30 complete data rows. You will calculate column F yourself.

## Part A: Set Up Your Workbook (10 minutes)

1. Open [Google Sheets](https://sheets.google.com/) and create a blank spreadsheet.
2. Name it **YourName_SnackShop_Labs8_9**.
3. Download the dataset above. On GitHub, choose **Raw** or **Download raw file**, and save the CSV.
4. Choose **File → Import → Upload**, select the CSV, and import it with comma as the separator. Insert a new sheet if offered.
5. Rename the imported tab **Snack_Data**. Confirm headers in A1:E1 and the final record in row 31. If everything is in one column, reimport with comma as the separator.
6. Bold the headers, freeze the first row, and resize columns to show the headings.
7. Format **D2:D31** as US dollar currency and **E2:E31** as whole numbers.
8. Preserve Snack_Data as your original data. Duplicate it and name the copy **Sales**.
9. Add a tab named **Lab8_Answers**. Use columns **Question**, **Result / formula**, and **Explanation**.

### Copy-and-Paste Alternative

Instead of importing the CSV, paste the tab-separated block below into A1 of an empty **Snack_Data** tab. It is the same data. Do not add it again if you already imported the CSV.

```tsv
Day	Item	Category	Unit_Price	Units_Sold
Monday	Apple	Fruit	0.75	12
Monday	Banana	Fruit	0.50	10
Monday	Popcorn	Snacks	1.00	20
Monday	Granola Bar	Snacks	1.25	15
Monday	Water	Drinks	1.00	25
Monday	Juice Box	Drinks	1.50	18
Tuesday	Apple	Fruit	0.75	15
Tuesday	Banana	Fruit	0.50	12
Tuesday	Popcorn	Snacks	1.00	18
Tuesday	Granola Bar	Snacks	1.25	14
Tuesday	Water	Drinks	1.00	22
Tuesday	Juice Box	Drinks	1.50	20
Wednesday	Apple	Fruit	0.75	10
Wednesday	Banana	Fruit	0.50	14
Wednesday	Popcorn	Snacks	1.00	22
Wednesday	Granola Bar	Snacks	1.25	16
Wednesday	Water	Drinks	1.00	28
Wednesday	Juice Box	Drinks	1.50	19
Thursday	Apple	Fruit	0.75	14
Thursday	Banana	Fruit	0.50	11
Thursday	Popcorn	Snacks	1.00	25
Thursday	Granola Bar	Snacks	1.25	18
Thursday	Water	Drinks	1.00	30
Thursday	Juice Box	Drinks	1.50	22
Friday	Apple	Fruit	0.75	18
Friday	Banana	Fruit	0.50	16
Friday	Popcorn	Snacks	1.00	30
Friday	Granola Bar	Snacks	1.25	20
Friday	Water	Drinks	1.00	35
Friday	Juice Box	Drinks	1.50	25
```

If it stays in one column, use **Data → Split text to columns** with Tab or automatic detection. Confirm A1:E31, then complete the formatting and tab setup above.

## Part B: Calculate Revenue (10 minutes)

Work on **Sales**, leaving Snack_Data unchanged.

1. Type **Revenue** in F1.
2. In F2, enter:

```excel
=D2*E2
```

3. Press Enter. The first row's revenue should be **$9.00**: 12 apples at $0.75 each.
4. Select F2 and drag the small fill handle down through **F31**.
5. Click F3 and confirm the formula is `=D3*E3`. In F31 it should be `=D31*E31`.
6. Format F2:F31 as US dollar currency.

**Q1:** In Lab8_Answers, explain why the row numbers change when you copy the formula down.

**Q2:** Explain the difference between **units sold** and **revenue**, using the first sales row as your example.

## Part C: Answer the Shop Manager's Questions (15 minutes)

On **Lab8_Answers**, label answers Q3–Q12. Enter formulas in column B, referencing **Sales**.

| Question | Task | Hint |
|---|---|---|
| Q3 | How many daily item-sales records are there? | COUNT on Units_Sold |
| Q4 | How many item names are filled in? | COUNTA on Item |
| Q5 | How many individual items were sold during the week? | SUM on Units_Sold |
| Q6 | How much revenue did the shop collect during the week? | SUM on Revenue |
| Q7 | What is the average number of units sold per record? | AVERAGE on Units_Sold |
| Q8 | What is the lowest unit price? | MIN on Unit_Price |
| Q9 | What is the highest unit price? | MAX on Unit_Price |
| Q10 | How many records belong to Fruit? | COUNTIF on Category |
| Q11 | How many records belong to Snacks? | COUNTIF on Category |
| Q12 | How many records belong to Drinks? | COUNTIF on Category |

**Worked example for Q3:**

```excel
=COUNT(Sales!E2:E31)
```

For COUNTIF, use text in quotation marks, such as `"Fruit"`. Use the exact category spelling in the data.

**Pause and think:** Q3 counts records. Q5 counts individual items. Why are those different numbers? Also, why would COUNT and COUNTA give different results on the text in column B? Add your explanations below your answers.

## Part D: Sort and Filter (10 minutes)

1. Duplicate the completed **Sales** tab and rename the copy **Practice**.
2. On Practice, select the entire table **A1:F31** and choose **Data → Create a filter**.
3. Use the Units_Sold header's filter menu to sort **Z → A** (largest to smallest). Keep all six columns together.
4. **Q13:** Which item and day had the highest units sold in a single record? Give the units sold and revenue for that record.
5. Filter Category to **Fruit** only.
6. **Q14:** How many records are visible? Name the two fruit items.
7. Restore all categories. Confirm that all 30 records are visible.

**Note:** Ordinary SUM, COUNT, and AVERAGE formulas include rows hidden by a filter. Use the visible rows for Q14; Lab 9 introduces formulas for category-specific totals.

## Part E: Recommend One Next Step (5 minutes)

**Q15:** Write one observation supported by a number and one question to investigate in Lab 9. For example, you might ask whether the category selling the most units also earns the most revenue.

### Self-Check

Check after completing your own formulas:

- Q3 and Q4 should both be **30**.
- Q5 should be **574 units**.
- The category record counts should add to 30.
- Sales!F2 should be **$9.00**, and all 30 revenue cells should contain formulas.
- Snack_Data should still contain the original five columns.

## Grading — 20 Points

| Component | What is assessed | Points |
|---|---|---:|
| Setup and data preparation | Correct import, required tabs, original data preserved, and appropriate formatting (Part A) | 4 |
| Formulas and calculations | Revenue formulas filled correctly (2 points); correct formula-based answers to Q3–Q12 (6 points) | 8 |
| Sorting and filtering | Complete rows sorted correctly and Q13 answered (2 points); Fruit filter, Q14, and all rows restored (2 points) | 4 |
| Explanations and completeness | Q1–Q2 and pause-and-think explanations (2 points); evidence-based Q15 and a complete, clearly labeled submission (2 points) | 4 |
| **Total** | | **20** |

Partial credit is available for correct steps and formulas even when a final answer contains an error.

## What to Submit

Submit your workbook link through the usual course submission channel. Give your instructor viewer access and test the link.

Your workbook should contain:

- **Snack_Data:** original A1:E31 dataset.
- **Sales:** A1:F31 with calculated revenue.
- **Practice:** sorting/filtering work, with all records visible at the end.
- **Lab8_Answers:** Q1–Q15, formula answers for Q3–Q12, and the pause-and-think explanations.

Keep this workbook for Lab 9. Follow the instructor's announced deadline. This mini lab is separate practice from Assignment 6.

## Help

[Google Sheets Tutorial for Beginners — Kevin Stratvert](https://www.youtube.com/watch?v=TENAbUa-R-w): entering data at 7:46, formulas at 19:54, sorting/filtering at 33:57.

[Continue to Lab 9](lab9_google_sheets_part2.md)
