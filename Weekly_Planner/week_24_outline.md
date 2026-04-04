# Learn and Help — Python DS
### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 24: Matplotlib, Plotly & Seaborn — A Comparison Guide

## Course
**Python for Data Science (Python DS)** — Learn and Help

## Topic
Comparing three popular Python visualization libraries — Matplotlib, Plotly, and Seaborn — to understand their strengths, differences, and when to use each one. Students will create visualizations with Seaborn and Plotly alongside their existing Matplotlib knowledge.

## Learning Objectives
By the end of this lesson, students will be able to:
1. Describe the purpose and history of Matplotlib, Plotly, and Seaborn.
2. Explain how Seaborn builds on top of Matplotlib to simplify statistical visualizations.
3. Explain how Plotly creates interactive, web-based visualizations using JavaScript under the hood.
4. Create visualizations using Seaborn functions such as `sns.histplot()`, `sns.boxplot()`, `sns.heatmap()`, and `sns.pairplot()`.
5. Create interactive visualizations using Plotly Express functions such as `px.scatter()`, `px.bar()`, `px.line()`, and `px.histogram()`.
6. Compare the same dataset visualized with Matplotlib, Seaborn, and Plotly side by side.
7. Identify which library is best suited for a given scenario (publications, dashboards, exploratory analysis).
8. Recognize key differences in interactivity, default aesthetics, DataFrame integration, and output formats across the three libraries.

## Prior Knowledge (Weeks 22–23 Review)
- Matplotlib basics: `plt.plot()`, `plt.bar()`, `plt.scatter()`, `plt.hist()`, `plt.boxplot()`, `plt.pie()`
- Visualizations for a single variable (Week 22): histograms, box plots, bar charts, pie charts
- Visualizations for relationships between two variables (Week 23): scatter plots, grouped bar charts, stacked bar charts, side-by-side box plots
- Customizing plots: `plt.title()`, `plt.xlabel()`, `plt.ylabel()`, `plt.legend()`, `plt.show()`

## Resources

### Comparison Guide
- [Matplotlib, Plotly, Seaborn: A Comparison Guide](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/matplotlib_vs_plotly_vs_seaborn.md)

### Colab Notebooks
- [Seaborn Visualizations (Breast Cancer Dataset)](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/6_matplotlib_seaborn_visualizations_breast_cancer_dataset.ipynb)
- [Plotly Introduction](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/7_matplotlib_plotly_Introduction.ipynb)

### Interactive Playbook & Quiz
- [Matplotlib, Plotly & Seaborn Playbook](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/matplotlib_plotly_seaborn_playbook.html)
  - **Concepts tab** — Side-by-side examples showing the same visualizations in all three libraries with runnable Python code
  - **Quiz tab** — Questions covering library selection, syntax differences, and feature comparison; students submit and screenshot their score

### Prior Week References
- [Week 22 Playbook & Quiz (Single-Variable Visualizations)](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/python_ds_matplotlib_visualizations.html)
- [Week 23 Playbook & Quiz (Two-Variable Visualizations)](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/python_ds_playbook_visualizations_for_two_variables.html)

## Lesson Outline

### 1. Warm-Up / Review (5 minutes)
- Quick recap: "Which Matplotlib function creates a scatter plot? A box plot? A bar chart?"
- Transition: "Matplotlib is powerful, but it's not the only visualization library in Python. Today we meet two more — Seaborn and Plotly — and learn when each one shines."

### 2. The Big Picture: Three Libraries (10 minutes)
- Introduce all three libraries with a brief history:
  - **Matplotlib** (2003) — the foundation; static, precise, full control
  - **Seaborn** (2012) — built on Matplotlib; beautiful defaults, great for statistics
  - **Plotly** (2012) — interactive, web-based; great for dashboards and exploration
- Walk through the comparison table from the guide (key differences in interactivity, aesthetics, DataFrame integration, output format)
- Analogy for middle schoolers: "Matplotlib is like building with individual LEGO bricks — total control. Seaborn is like a LEGO kit — beautiful results with less effort. Plotly is like a video game — you can interact with what you build."

### 3. Seaborn Deep Dive (20 minutes)
- Show how Seaborn simplifies Matplotlib code:
  - `sns.histplot()` vs `plt.hist()` — fewer lines, better defaults
  - `sns.boxplot()` with DataFrame column names directly
  - `sns.heatmap()` for correlation matrices
  - `sns.pairplot()` for exploring multiple variables at once
- Live demo using the Breast Cancer Dataset notebook
- Students follow along in Colab, experimenting with color palettes (`sns.set_palette()`) and themes (`sns.set_theme()`)

### 4. Plotly Deep Dive (20 minutes)
- Show how Plotly creates interactive charts:
  - `px.scatter()` — hover tooltips, zoom, pan built in
  - `px.bar()` and `px.histogram()` — interactive versions of familiar chart types
  - `px.line()` — interactive time series
- Highlight interactivity: hover over data points to see values, zoom into regions, toggle legend items
- Live demo using the Plotly Introduction notebook
- Students follow along in Colab, experimenting with hover data and color parameters

### 5. Side-by-Side Comparison Activity (10 minutes)
- Students create the **same visualization** (e.g., a scatter plot of two variables) using all three libraries
- Compare: How many lines of code? How does the default output look? Can you hover over data points?
- Class discussion: "Which version do you like best? Why?"

### 6. When to Use Which Library? (5 minutes)
- Scenario-based discussion:
  - "You're writing a research paper" → **Matplotlib** (static, publication-quality)
  - "You want to explore a new dataset quickly" → **Seaborn** (statistical plots with minimal code)
  - "You're building a web dashboard for your project" → **Plotly** (interactive, shareable HTML)
- Reinforce: all three are valuable — it's about choosing the right tool for the job

### 7. Playbook & Quiz (10 minutes)
- Students open the interactive playbook to review concepts and run code examples
- Complete the quiz in the Quiz tab
- Screenshot their score and submit to Google Classroom

## Assessment
- **Quiz** — Complete the quiz in the interactive playbook; screenshot the score panel (with name) and submit to Google Classroom.
- **Participation** — Follow along with Colab notebooks during class; experiment with at least one visualization in each library.

## Key Vocabulary

| Term | Definition |
|------|-----------|
| Matplotlib | Python's foundational plotting library for static, publication-quality visualizations |
| Plotly | An interactive graphing library that creates web-based visualizations using JavaScript |
| Seaborn | A statistical visualization library built on top of Matplotlib with beautiful defaults |
| Plotly Express (`px`) | Plotly's high-level, concise API for creating common chart types quickly |
| Interactivity | The ability to hover, zoom, pan, and click on chart elements (a Plotly feature) |
| `sns.pairplot()` | A Seaborn function that creates a grid of scatter plots for every pair of variables |
| `sns.heatmap()` | A Seaborn function that displays a matrix of values as colored cells |
| Static vs Interactive | Static charts are fixed images (Matplotlib/Seaborn); interactive charts respond to user actions (Plotly) |
| DataFrame Integration | How easily a library works with pandas DataFrames — Seaborn and Plotly excel here |
| Backend | The rendering engine a library uses to produce output (e.g., AGG for Matplotlib, D3.js for Plotly) |

## Quick Reference: Library Comparison

| Feature | Matplotlib | Seaborn | Plotly |
|---------|-----------|---------|-------|
| Interactivity | Static | Static | Interactive |
| Default Look | Plain | Beautiful | Modern |
| Code Length | More verbose | Concise | Concise |
| Best For | Publications, precise control | Statistical analysis, EDA | Dashboards, web sharing |
| DataFrame Support | Manual column extraction | Pass column names directly | Pass column names directly |
| Output | PNG, PDF, SVG | PNG, PDF, SVG | HTML, PNG, PDF |

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
