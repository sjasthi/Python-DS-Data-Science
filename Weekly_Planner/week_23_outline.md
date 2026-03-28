# Learn and Help — Python DS
### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 23: Matplotlib — Visualizations for Relationships Between Two Variables

## Course
**Python for Data Science (Python DS)** — Learn and Help

## Topic
Choosing the right matplotlib visualization to explore relationships between two variables, covering all three variable-type combinations: Quantitative vs Quantitative, Quantitative vs Qualitative, and Qualitative vs Qualitative.

## Learning Objectives
By the end of this lesson, students will be able to:
1. Identify whether a pair of variables is Quant vs Quant, Quant vs Qual, or Qual vs Qual.
2. Select the most appropriate chart type for each variable-type combination.
3. Create a **scatter plot** (`plt.scatter()`) to show the relationship between two quantitative variables.
4. Create a **line chart** (`plt.plot()`) with multiple lines to compare two quantitative series over time.
5. Create a **grouped bar chart** (`plt.bar()` with `np.arange()` offsets) to compare a quantitative variable across categories.
6. Create a **side-by-side box plot** (`plt.boxplot()` with a list of lists) to compare distributions across categories.
7. Create a **stacked bar chart** (`plt.bar()` with `bottom` parameter) to visualize two categorical variables.
8. Add proper titles, axis labels, and legends to all two-variable charts.

## Prior Knowledge (Week 22 Review)
- Visualizations for a single quantitative variable: Histogram (`plt.hist()`), Box Plot (`plt.boxplot()`), Line Chart (`plt.plot()`)
- Visualizations for a single qualitative variable: Bar Chart (`plt.bar()`, `plt.barh()`), Pie Chart (`plt.pie()`)
- Matplotlib basics: `plt.title()`, `plt.xlabel()`, `plt.ylabel()`, `plt.show()`

## Resources

### Colab Notebook
- [Matplotlib Visualizations for Relationships Between Two Variables](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/4_matplotlib_visualizations_for_relationships_between_two_variables.ipynb)

### Interactive Playbook & Quiz
- [Playbook: Visualizations for Two Variables](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/python_ds_playbook_visualizations_for_two_variables.html)
  - **Concepts tab** — Explains all three variable-type combinations with runnable Python code (powered by Pyodide)
  - **Quiz tab** — 10 questions (4 Quant×Quant, 3 Quant×Qual, 3 Qual×Qual); students submit and screenshot their score

### Prior Week References
- [Quantitative Variable Visualizations (Notebook)](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/2_matplotlib_quantitative_variable_visualizations.ipynb)
- [Categorical Variable Visualizations (Notebook)](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/3_matplotlib_categorical_variable_visualizations.ipynb)
- [Week 22 Playbook & Quiz](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/python_ds_matplotlib_visualizations.html)

## Lesson Outline

### 1. Warm-Up / Review (5 minutes)
- Quick recap: What chart would you use for a single list of test scores? (Histogram) What about favorite colors? (Bar chart)
- Transition: "Today we go further — what if we want to see how **two** variables relate to each other?"

### 2. Introduction: Three Types of Variable Pairs (10 minutes)
- Present the three combinations:
  - **Quantitative vs Quantitative** — two number columns (e.g., height vs weight)
  - **Quantitative vs Qualitative** — numbers split by a category (e.g., scores by grade level)
  - **Qualitative vs Qualitative** — two category columns (e.g., sport vs gender)
- For each combination, ask students to brainstorm real-life examples

### 3. Quantitative vs Quantitative (15 minutes)
- **Scatter Plot** — `plt.scatter(x, y)`
  - Live demo: Hours studied vs Test score
  - Discuss: positive correlation, negative correlation, no correlation
  - Key parameters: `s`, `color`, `alpha`, `marker`
- **Line Chart with Multiple Lines** — `plt.plot()` called twice
  - Live demo: City A vs City B monthly temperatures
  - Key: use `label=` and `plt.legend()`

### 4. Quantitative vs Qualitative (15 minutes)
- **Grouped Bar Chart** — `plt.bar()` with `np.arange()` offsets
  - Live demo: Average scores by subject and gender
  - Key technique: `x - width/2`, `x + width/2`, `plt.xticks()`
- **Side-by-Side Box Plot** — `plt.boxplot([list1, list2, list3])`
  - Live demo: Test scores by class period
  - Key: pass a list of lists, use `labels=` and `patch_artist=True`
  - Discuss: When to use box plots vs grouped bars (distribution vs summary)

### 5. Qualitative vs Qualitative (10 minutes)
- **Grouped Bar Chart** — same technique as above, but with count data
  - Live demo: Favorite sport by gender
- **Stacked Bar Chart** — `plt.bar()` with `bottom=` parameter
  - Live demo: Same data, stacked view
  - Discuss: grouped vs stacked — what does each one show best?

### 6. Hands-On Practice (15 minutes)
- Students open the Colab notebook and work through the examples
- Students experiment with the runnable code blocks in the playbook (modify colors, data, titles, and re-run)
- Challenge: create their own scatter plot using a dataset they choose (e.g., age vs number of apps, shoe size vs height)

### 7. Quiz (10 minutes)
- Students open the playbook Quiz tab
- Enter their name, answer all 10 questions, click Submit
- Screenshot their score panel and submit to Google Classroom

## Assessment
- **Quiz** (10 questions) — submitted as a screenshot from the playbook to Google Classroom
- **Participation** — engaging with the Colab notebook and playbook during class

## Key Vocabulary
| Term | Definition |
|------|-----------|
| Scatter Plot | A chart that uses dots to show the relationship between two quantitative variables |
| Positive Correlation | Both variables increase together (dots trend upward left to right) |
| Negative Correlation | One variable increases while the other decreases (dots trend downward) |
| Grouped Bar Chart | A bar chart with bars for different groups placed side by side |
| Stacked Bar Chart | A bar chart where bars for different groups are stacked on top of each other |
| Side-by-Side Box Plot | Multiple box plots placed next to each other to compare distributions across categories |
| `bottom` parameter | In `plt.bar()`, sets where each bar starts vertically, enabling stacking |
| `np.arange()` | Creates evenly spaced numerical positions used for placing grouped bars |

## Quick Reference: Which Chart to Use?

| Variable Combination | Best Chart(s) | Matplotlib Function |
|---|---|---|
| Quant vs Quant | Scatter Plot | `plt.scatter()` |
| Quant vs Quant (time) | Line Chart | `plt.plot()` |
| Quant vs Qual | Grouped Bar Chart | `plt.bar()` with offsets |
| Quant vs Qual | Side-by-Side Box Plot | `plt.boxplot()` |
| Qual vs Qual | Grouped Bar Chart | `plt.bar()` with offsets |
| Qual vs Qual | Stacked Bar Chart | `plt.bar(bottom=…)` |

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
