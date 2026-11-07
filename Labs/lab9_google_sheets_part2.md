# Lab 9: Google Sheets Part 2 — School Snack Shop

**Week 9:** November 14, 2026  
**Points:** 20  
**Estimated time:** 40–50 minutes  
**Prerequisite:** [Lab 8](lab8_google_sheets_part1.md)

## Your Mission

The snack shop manager wants to know which categories sell the most and collect the most money. Use the **same workbook and data from Lab 8** to create a category summary, a PivotTable, and a chart. Finish with a recommendation.

You will practice COUNTIF, SUMIF, AVERAGEIF, COUNTIFS, absolute references, PivotTables, and charts.

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

## Part A: Reopen and Check (5 minutes)

1. Open **YourName_SnackShop_Labs8_9**.
2. Confirm that **Snack_Data** holds the original A1:E31 dataset and **Sales** holds A1:F31 with Revenue calculated in F2:F31.
3. Check that the first revenue formula is `=D2*E2`, and total Units_Sold is 574.
4. If you missed Lab 8, import its data and complete its revenue calculation before continuing.
5. Create a tab named **Lab9_Analysis**. Keep all Lab 8 tabs.
6. Create a tab named **Lab9_Answers** with columns **Question**, **Result / formula**, and **Explanation**. Record Q1–Q10 here.

## Part B: Compare Categories (10 minutes)

On **Lab9_Analysis**, enter these headings and category names:

| Cell | Enter |
|---|---|
| A1 | Category |
| B1 | Record count |
| C1 | Total units sold |
| D1 | Total revenue ($) |
| E1 | Average units per record |
| A2 | Fruit |
| A3 | Snacks |
| A4 | Drinks |

Enter these formulas:

```excel
B2: =COUNTIF(Sales!$C$2:$C$31,A2)
C2: =SUMIF(Sales!$C$2:$C$31,A2,Sales!$E$2:$E$31)
D2: =SUMIF(Sales!$C$2:$C$31,A2,Sales!$F$2:$F$31)
E2: =AVERAGEIF(Sales!$C$2:$C$31,A2,Sales!$E$2:$E$31)
```

Enter only the formula beginning with `=`; labels such as `B2:` identify destination cells.

1. Select B2:E2 and fill down through row 4.
2. Format D2:D4 as US dollar currency and E2:E4 to one decimal place.
3. In A6, type **Totals**. In B6, C6, and D6, use SUM to add the corresponding rows 2–4. Leave E6 blank: adding averages is not a useful total.
4. In A7, type **Revenue check**. In D7, enter `=D6=SUM(Sales!F2:F31)`. It should return TRUE.

Answer on **Lab9_Answers**:

- **Q1:** Why are source ranges locked with dollar signs while A2 is not?
- **Q2:** Which category sold the most units? Which collected the most revenue? Include both totals.
- **Q3:** What does “Record count” mean? Explain why it is different from “Total units sold.”

## Part C: Ask a More Specific Question (10 minutes)

**Q4:** On how many item-day records did **Drinks** sell **at least 25 units**?

```excel
=COUNTIFS(Sales!C2:C31,"Drinks",Sales!E2:E31,">=25")
```

**Q5:** What percentage of the Drinks records meet that condition?

Divide Q4's result by the number of Drinks records, using COUNTIF or a link to the summary table. Format the result as a percentage. Do not multiply by 100 and also use percentage formatting.

This is a percentage of **records**, not a percentage of all drink units sold.

**Q6:** Create your own question with two conditions, such as a day and a minimum quantity, or a category and a minimum revenue. Record the question, COUNTIFS formula, and result. Use filters on Practice to check your answer, then restore all rows.

## Part D: Build a PivotTable (10 minutes)

1. Select **Sales!A1:F31**, including the headers.
2. Choose **Insert → Pivot table**, place it on a new sheet, and rename the tab **Lab9_Pivot**.
3. In the Pivot table editor, add **Category** under Rows.
4. Add **Units_Sold** under Values; summarize by **SUM**.
5. Add **Revenue** under Values; summarize by **SUM**.
6. Format the revenue results as US dollar currency.
7. Compare the totals for each category and the grand totals with Lab9_Analysis.

**Q7:** Do the PivotTable and formula summary agree for all three categories? If not, check the data range and make sure values are summarized by SUM.

**Self-check:** Fruit revenue should be **$83.25**. The grand totals should be **574 units** and **$598.00 revenue**. Check after building your own summary.

## Part E: Make a Chart and a Recommendation (10 minutes)

### Build the Chart

On **Lab9_Analysis**, create an adjacent chart table:

| Cell | Enter |
|---|---|
| G1 | Category |
| H1 | Revenue ($) |
| G2 | `=A2` |
| H2 | `=D2` |

1. Fill G2:H2 down through row 4.
2. Select **G1:H4**, choose **Insert → Chart**, and use a **Column chart**.
3. Confirm Category is the horizontal axis and Revenue is the only series.
4. Title it **School Snack Shop: Weekly Revenue by Category**.
5. Label the horizontal axis **Category** and the vertical axis **Revenue (US dollars)**. Start the vertical axis at zero.

### Explain Your Findings

On Lab9_Answers:

- **Q8:** Compare two categories using revenue amounts. How much more revenue did one collect?
- **Q9:** Recommend one action for the shop manager, supported by a number. Name one extra piece of information you would want before deciding what to stock next week.
- **Q10:** Can we tell which category made the most **profit**? Explain what information is missing.

Remember: these are fictional sales for one week. They do not prove what every school or future week will be like.

## Optional Extensions

Choose one if time permits:

- **Daily totals:** Create a second PivotTable with Day as Rows and SUM of Revenue as Values. Order the days Monday through Friday rather than alphabetically.
- **Text practice:** In Practice, add G1 as **Item prefix**, enter `=LEFT(B2,3)` in G2, and fill down. Explain why a short prefix is not guaranteed to be a unique item name.

## Grading — 20 Points

| Component | What is assessed | Points |
|---|---|---:|
| Setup and data preparation | Same dataset and workbook reused, Lab 8 work preserved, and required Lab 9 tabs created (Part A) | 2 |
| Formulas and calculations | Category summary, totals, and revenue check (3 points); Q4–Q6 conditional formulas and percentage calculation (3 points) | 6 |
| PivotTable and chart | Correct category PivotTable, SUM settings, and cross-check in Q7 (4 points); accurate, labeled revenue chart (4 points) | 8 |
| Explanations and completeness | Clear Q1–Q3 explanations (2 points); evidence-based Q8–Q10, recommendation, and complete submission (2 points) | 4 |
| **Total** | | **20** |

Partial credit is available for correct steps and formulas even when a final answer contains an error. Optional extensions are ungraded and are not required for full credit.

## What to Submit

Submit the **same workbook link** used for Lab 8 through the usual course submission channel, with instructor viewer access.

Keep your Lab 8 tabs and include:

- **Lab9_Analysis:** category summary, totals, check formula, and labeled chart.
- **Lab9_Pivot:** total units and revenue by category.
- **Lab9_Answers:** Q1–Q10, including formulas for Q4–Q6.

Follow the instructor's announced deadline. These mini labs are separate practice from Assignment 6.

## Final Checklist

- [ ] Both labs use the same 30 snack shop records.
- [ ] Original data and Lab 8 answers are preserved.
- [ ] All Sales revenue values are calculated with formulas.
- [ ] Summary formulas copy correctly and the revenue check returns TRUE.
- [ ] Percentage uses the number of Drinks records as its denominator.
- [ ] PivotTable agrees with the formula summary.
- [ ] Chart shows dollars rather than units sold.
- [ ] Recommendation includes evidence, and revenue is distinguished from profit.
- [ ] Instructor can open the link.

## Connection to Python

In pandas, multiplying columns calculates revenue, filtering plus counting answers multiple-condition questions, and `groupby()` can summarize units and revenue by category.

## Help

[Google Sheets Tutorial for Beginners — Kevin Stratvert](https://www.youtube.com/watch?v=TENAbUa-R-w): charts at 36:39 and PivotTables at 39:09.

[Google Sheets Formulas Tutorial — Kevin Stratvert](https://www.youtube.com/watch?v=9TVmdFtmbbo)

[Back to Lab 8](lab8_google_sheets_part1.md)
