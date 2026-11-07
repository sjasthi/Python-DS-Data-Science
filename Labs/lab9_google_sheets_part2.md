# Lab 9: Google Sheets for Data Analysis — Part 2

**Week 9:** November 14, 2026  
**Estimated time:** 40–50 minutes  
**Prerequisite:** [Lab 8](lab8_google_sheets_part1.md)

## Goal

Reuse your Iris workbook to compare species with conditional formulas, build a PivotTable, and communicate a finding with a chart.

By the end, you should be able to:

- Use COUNTIF, COUNTIFS, and AVERAGEIF.
- Copy formulas using absolute and relative references.
- Cross-check a summary table against a PivotTable.
- Create a labeled column chart.
- Explain findings and the limits of a small dataset.

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

## Part A: Reopen and Check (5 minutes)

1. Open **YourName_Iris_Labs8_9** from Lab 8. Do not create a different dataset.
2. Confirm that **Iris_Data** contains the original five columns in A1:E31 and all 30 data rows.
3. If you missed Lab 8, use its import instructions or copy-and-paste data to create Iris_Data first.
4. Create a new tab named **Lab9_Analysis**. Preserve your Lab 8 answers.

## Part B: Build a Species Summary (10 minutes)

On **Lab9_Analysis**, enter this structure:

| Cell / range | Enter |
|---|---|
| A1 | Species |
| B1 | Flower count |
| C1 | Average petal length (cm) |
| D1 | Average sepal length (cm) |
| A2 | setosa |
| A3 | versicolor |
| A4 | virginica |

Enter these formulas in row 2:

```excel
B2: =COUNTIF(Iris_Data!$E$2:$E$31,A2)
C2: =AVERAGEIF(Iris_Data!$E$2:$E$31,A2,Iris_Data!$C$2:$C$31)
D2: =AVERAGEIF(Iris_Data!$E$2:$E$31,A2,Iris_Data!$A$2:$A$31)
```

The labels `B2:`, `C2:`, and `D2:` identify destination cells; enter only the formula beginning with `=`.

1. Select B2:D2 and drag the fill handle down through row 4.
2. Format C2:D4 to two decimal places.
3. In A6, type **Total flowers**. In B6, calculate `=SUM(B2:B4)`.
4. In A7, type **Check against source**. In B7, enter `=B6=COUNTA(Iris_Data!E2:E31)`. It should return TRUE.

**Q1:** Why are the data ranges locked with dollar signs while A2 is not?

**Q2:** Which species has the greatest average petal length in these records? Give the value in centimeters.

## Part C: Analyze Multiple Conditions (10 minutes)

Below the summary, use **A10:C16** for labels, answer formulas, and explanations.

- **Q3:** How many virginica flowers have petal length **greater than 5 cm**?
- **Q4:** What percentage of virginica flowers meet that condition?

Use this pattern for Q3:

```excel
=COUNTIFS(Iris_Data!E2:E31,"virginica",Iris_Data!C2:C31,">5")
```

For Q4, divide Q3's result by the number of virginica flowers, using a formula or the summary cell. Format the result as a percentage. Do not multiply by 100 and also apply percentage formatting.

**Q5:** Write your own question with two conditions involving species and one measurement. Record the question, a COUNTIFS formula, and the result. Check the result using filters on Practice.

**Q6:** Is a rule such as “petal length > 5 cm means virginica” proven for all Iris flowers by this lab? Explain using the size and selection of our dataset.

## Part D: Create and Check a PivotTable (10 minutes)

1. Select **Iris_Data!A1:E31**, including the headers.
2. Choose **Insert → Pivot table** and place it on a new sheet. Rename that sheet **Lab9_Pivot**.
3. In the Pivot table editor, add **species** under Rows.
4. Add **petal_length** under Values and change **Summarize by** to **AVERAGE**.
5. Add **species** under Values and summarize by **COUNTA** to count flowers.
6. Format average petal lengths to two decimal places.
7. Compare all three species averages and counts with **Lab9_Analysis!A1:C4**.

**Q7:** Record whether the PivotTable and formula summary agree. If they do not, check the source range, aggregation setting, and criteria spelling before proceeding.

**Self-check:** Each species should have 10 records. Average petal length for setosa should display as **1.45 cm**. Use this as a check after doing your own work.

## Part E: Create a Chart and Interpret It (10 minutes)

1. On Lab9_Analysis, select **A1:A4** and **C1:C4** as nonadjacent ranges. You can use Ctrl (Windows) or Command (Mac) to select both.
2. Choose **Insert → Chart** and select a **Column chart**.
3. In the chart's Setup panel, confirm that **species** is the horizontal axis and **average petal length** is the only series. Remove flower count if Sheets includes it.
4. If selecting nonadjacent ranges is difficult, create an adjacent two-column chart table in F1:G4. Link its entries to the species and average petal length cells using formulas, then chart that table.
5. Title the chart **Average Petal Length by Species — 30-Flower Subset**.
6. Label the horizontal axis **Species** and the vertical axis **Average petal length (cm)**. Start the vertical axis at zero.

Below the chart, answer:

- **Q8:** Describe two comparisons using numbers and units.
- **Q9:** Explain why comparing averages tells us more about petal length than comparing counts in this particular dataset.
- **Q10:** What additional data would help you investigate your findings further?

## Optional Extension: Text Functions

In **Practice**, add a column F named **Species prefix**. Enter `=LEFT(E2,3)` in F2 and fill down through F31. Explain what the formula extracts and whether a three-letter prefix is guaranteed to identify every possible species uniquely. Leave Iris_Data unchanged.

## What to Submit

Submit the **same workbook link** used for Lab 8 through the usual course submission channel, with instructor viewer access. Keep all Lab 8 tabs and include:

- **Lab9_Analysis:** summary formulas, Q1–Q10 answers, and the labeled chart.
- **Lab9_Pivot:** species counts and average petal lengths.

Follow the instructor's announced submission deadline. These mini labs are separate practice from Assignment 6.

## Final Checklist

- [ ] Same 30 Iris records used in both labs.
- [ ] Summary formulas copied correctly and source count check returns TRUE.
- [ ] Conditional count and percentage use the intended denominator.
- [ ] PivotTable agrees with the summary for all three species.
- [ ] Chart shows averages, species labels, and centimeters.
- [ ] Findings refer to this subset rather than all Iris flowers.
- [ ] Original data and Lab 8 work are preserved.
- [ ] Instructor can open the link.

## Connection to Python

These activities prepare you for pandas: COUNTIFS resembles filtering plus counting, AVERAGEIF resembles grouped averages, and a PivotTable resembles `groupby()` or `pivot_table()`.

## Help

[Google Sheets Tutorial for Beginners — Kevin Stratvert](https://www.youtube.com/watch?v=TENAbUa-R-w): charts at 36:39 and PivotTables at 39:09.

[Google Sheets Formulas Tutorial — Kevin Stratvert](https://www.youtube.com/watch?v=9TVmdFtmbbo)

[Back to Lab 8: Part 1](lab8_google_sheets_part1.md)
