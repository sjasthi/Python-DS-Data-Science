# Matplotlib vs Plotly vs Seaborn: A Comparison Guide

**Course:** Python for Data Science | **Organization:** Learn and Help ([learnandhelp.com](http://www.learnandhelp.com))

---

## Course Notebooks

Explore these Colab notebooks for hands-on practice with each library:

| Notebook | Library Focus | Link |
|----------|--------------|------|
| Seaborn Visualizations (Breast Cancer Dataset) | Seaborn + Matplotlib | [Open in GitHub](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/6_matplotlib_seaborn_visualizations_breast_cancer_dataset.ipynb) |
| Plotly Introduction | Plotly + Matplotlib | [Open in GitHub](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/matplotlib/7_matplotlib_plotly_Introduction.ipynb) |

---

## Introduction to Matplotlib

Matplotlib is Python's foundational plotting library, created in 2003 by John Hunter. It provides a MATLAB-like interface for creating static, publication-quality visualizations. Matplotlib offers fine-grained control over every element of a plot, making it the go-to choice for scientific publications and data analysis.

**Key Features:**
- Comprehensive 2D plotting capabilities (line plots, scatter plots, bar charts, histograms, etc.)
- Extensive customization options for every visual element
- Multiple rendering backends for different output formats
- Large ecosystem with extensions like seaborn and pandas plotting
- Works seamlessly in Jupyter notebooks, scripts, and applications

## Introduction to Plotly

Plotly is a modern, interactive graphing library that creates web-based visualizations using JavaScript (specifically D3.js and Plotly.js). Released in 2012, it specializes in interactive, shareable plots that work in web browsers, Jupyter notebooks, and dashboards.

**Key Features:**
- Interactive plots with hover tooltips, zooming, panning, and selection by default
- 3D plotting capabilities and specialized chart types (sunburst, sankey, etc.)
- Easy export to HTML for web sharing
- Integration with Dash for building web applications
- Supports both imperative (graph objects) and declarative (express) APIs

## Introduction to Seaborn

Seaborn is a statistical data visualization library built on top of Matplotlib. Created by Michael Waskom and first released in 2012, Seaborn provides a high-level interface for drawing attractive and informative statistical graphics. It is designed to work closely with pandas DataFrames, making it especially convenient for exploring and understanding datasets.

**Key Features:**
- Beautiful default themes and color palettes — plots look polished right away
- Built-in support for statistical plots (box plots, violin plots, pair plots, heatmaps, etc.)
- Tight integration with pandas DataFrames — pass column names directly
- Automatic estimation and plotting of statistical relationships (regression lines, distributions)
- Functions for visualizing distributions (`histplot`, `kdeplot`, `displot`) and relationships (`scatterplot`, `lmplot`, `pairplot`)
- Easy faceting — split plots by categories using `col` and `row` parameters

---

## Comparison Table

| Feature | Matplotlib | Plotly | Seaborn |
|---------|-----------|--------|---------|
| **Created** | 2003 | 2012 | 2012 |
| **Built On** | Own rendering engine | D3.js / Plotly.js | Matplotlib |
| **Interactivity** | Static by default | Interactive by default | Static by default (inherits from Matplotlib) |
| **Learning Curve** | Steeper, more verbose syntax | Easier for basic plots with Plotly Express | Easiest for statistical plots |
| **Customization** | Extremely granular control | Good control, but some limitations | Moderate — themes and palettes are easy; deep tweaks fall back to Matplotlib |
| **Performance** | Fast for static plots, handles large datasets well | Can be slower with very large datasets | Similar to Matplotlib (uses it under the hood) |
| **Output Format** | PNG, PDF, SVG, etc. | HTML, PNG, PDF, SVG | PNG, PDF, SVG, etc. (same as Matplotlib) |
| **3D Plotting** | Basic 3D support | Excellent 3D support | No built-in 3D support |
| **Statistical Plots** | Manual setup required | Some built-in stats (trendlines, box plots) | Excellent — built-in regression, distributions, pair plots |
| **DataFrame Integration** | Requires extracting columns | Works well with DataFrames | Best-in-class — pass column names directly |
| **Default Aesthetics** | Plain, requires styling effort | Modern and polished | Beautiful out of the box |
| **File Size** | Small image files | Larger HTML files (includes JavaScript) | Small image files (same as Matplotlib) |
| **Community** | Massive, established community | Growing, active community | Large, especially in data science and academia |
| **Best For** | Publications, reports, precise control | Dashboards, exploration, web sharing | Statistical analysis, exploratory data analysis (EDA) |

---

## When to Use Matplotlib

Choose Matplotlib when you need:
- **Publication-quality static figures** for academic papers, reports, or books
- **Precise control** over every aspect of your visualization
- **Small file sizes** for figures (PNG, PDF, SVG)
- **Integration with scientific Python stack** (NumPy, SciPy, pandas)
- **Complex custom visualizations** requiring low-level control
- **Offline rendering** without JavaScript dependencies
- **Consistent styling** with scientific conventions

**Example Use Cases:**
- Research papers and academic publications
- Automated report generation with static images
- Embedded plots in LaTeX documents
- Custom statistical visualizations
- Large-scale data analysis where speed matters

## When to Use Plotly

Choose Plotly when you need:
- **Interactive exploration** of data with zooming, panning, and hover details
- **Web-based dashboards** using Plotly Dash
- **3D visualizations** that users can rotate and explore
- **Easy sharing** via HTML files or online platforms
- **Quick prototyping** with minimal code using Plotly Express
- **Modern, polished aesthetics** out of the box
- **Real-time updates** in web applications

**Example Use Cases:**
- Interactive data dashboards for stakeholders
- Exploratory data analysis in Jupyter notebooks
- Web-based data visualization applications
- 3D scientific visualizations
- Presentations where interactivity adds value
- Sharing analyses with non-technical users

## When to Use Seaborn

Choose Seaborn when you need:
- **Quick, attractive statistical plots** without heavy customization work
- **Exploratory data analysis (EDA)** — understanding distributions, relationships, and patterns
- **Categorical data visualizations** like box plots, violin plots, and count plots
- **Correlation heatmaps** to see relationships across many variables at once
- **Pair plots** to visualize all pairwise relationships in a dataset
- **Regression visualizations** with automatic trend lines and confidence intervals
- **Clean, professional styling** with minimal effort

**Example Use Cases:**
- Exploring a new dataset to understand its structure and distributions
- Comparing groups (e.g., tumor types, student performance by grade level)
- Building heatmaps to find correlations in data
- Visualizing the spread and outliers in data with box or violin plots
- Quickly generating multi-panel plots split by category
- Data science workflows where pandas DataFrames are the primary data structure

---

## Can You Use All Three?

Absolutely! Many data scientists use all three libraries, and they complement each other well:

- Use **Matplotlib** for final publication figures and when you need pixel-level control
- Use **Seaborn** for fast, beautiful statistical plots during data exploration — it builds on Matplotlib, so you can always add Matplotlib commands to fine-tune a Seaborn plot
- Use **Plotly** for interactive exploration and web-based sharing

A common workflow looks like this:
1. **Explore** the data with Seaborn (pair plots, heatmaps, distributions)
2. **Dive deeper** interactively with Plotly (hover over points, zoom in on patterns)
3. **Polish** the final figures with Matplotlib for a report or publication

---

## Quick Syntax Comparison

### Matplotlib — Line Plot
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 6))
plt.plot(x, y, color='blue', linewidth=2)
plt.xlabel('X Axis')
plt.ylabel('Y Axis')
plt.title('My Plot')
plt.grid(True)
plt.show()
```

### Plotly Express — Line Plot
```python
import plotly.express as px

fig = px.line(df, x='x', y='y', title='My Plot')
fig.show()
```

### Seaborn — Line Plot
```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.lineplot(data=df, x='x', y='y')
plt.title('My Plot')
plt.show()
```

> **Notice:** Seaborn uses `plt.show()` from Matplotlib because it builds on top of it. You get Seaborn's nice defaults and still have access to all of Matplotlib's customization.

---

## Quick Syntax Comparison — Scatter Plot

### Matplotlib
```python
import matplotlib.pyplot as plt

plt.scatter(df['x'], df['y'], c='blue', alpha=0.6)
plt.xlabel('X')
plt.ylabel('Y')
plt.title('Scatter Plot')
plt.show()
```

### Plotly Express
```python
import plotly.express as px

fig = px.scatter(df, x='x', y='y', title='Scatter Plot')
fig.show()
```

### Seaborn
```python
import seaborn as sns

sns.scatterplot(data=df, x='x', y='y')
plt.title('Scatter Plot')
plt.show()
```

---

## Quick Syntax Comparison — Histogram

### Matplotlib
```python
import matplotlib.pyplot as plt

plt.hist(df['values'], bins=20, color='skyblue', edgecolor='black')
plt.xlabel('Values')
plt.ylabel('Frequency')
plt.title('Histogram')
plt.show()
```

### Plotly Express
```python
import plotly.express as px

fig = px.histogram(df, x='values', nbins=20, title='Histogram')
fig.show()
```

### Seaborn
```python
import seaborn as sns

sns.histplot(data=df, x='values', bins=20, kde=True)
plt.title('Histogram')
plt.show()
```

> **Bonus:** Seaborn's `histplot` can overlay a KDE (kernel density estimate) curve with just `kde=True` — something that takes extra work in Matplotlib.

---

## Quick Syntax Comparison — Box Plot

### Matplotlib
```python
import matplotlib.pyplot as plt

plt.boxplot([group1, group2, group3], labels=['A', 'B', 'C'])
plt.title('Box Plot')
plt.show()
```

### Plotly Express
```python
import plotly.express as px

fig = px.box(df, x='category', y='values', title='Box Plot')
fig.show()
```

### Seaborn
```python
import seaborn as sns

sns.boxplot(data=df, x='category', y='values')
plt.title('Box Plot')
plt.show()
```

---

## Seaborn-Only Highlights

Seaborn offers several plot types that are unique or significantly easier compared to the other two libraries:

### Pair Plot — Visualize All Pairwise Relationships
```python
import seaborn as sns

sns.pairplot(df, hue='species')
plt.show()
```
One line of code generates a grid of scatter plots and histograms for every pair of numeric columns, colored by category. This would take dozens of lines in Matplotlib.

### Heatmap — Correlation Matrix
```python
import seaborn as sns

sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()
```
Seaborn makes it effortless to visualize which variables are correlated.

### Violin Plot — Distribution + Box Plot Combined
```python
import seaborn as sns

sns.violinplot(data=df, x='category', y='values')
plt.title('Violin Plot')
plt.show()
```
Shows the full distribution shape alongside summary statistics — a richer view than a box plot alone.

---

## The Big Picture: How They Relate

```
┌─────────────────────────────────────────────────────┐
│                    MATPLOTLIB                        │
│              (The Foundation Layer)                   │
│         Low-level control, static plots              │
│                                                      │
│    ┌──────────────────────┐                          │
│    │      SEABORN          │                         │
│    │  (Built ON Matplotlib)│                         │
│    │  Statistical plots,   │                         │
│    │  beautiful defaults   │                         │
│    └──────────────────────┘                          │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│                     PLOTLY                            │
│            (Independent Library)                      │
│      Interactive, web-based, uses JavaScript          │
└─────────────────────────────────────────────────────┘
```

**Key Relationship:** Seaborn is NOT a replacement for Matplotlib — it is a layer on top of it. Every Seaborn plot is a Matplotlib figure underneath. Plotly, on the other hand, is a completely separate library with its own rendering engine.

---

## Summary: Choosing the Right Tool

| I want to... | Use... |
|--------------|--------|
| Create a static figure for a report or paper | **Matplotlib** |
| Quickly explore distributions and relationships in a dataset | **Seaborn** |
| Build an interactive chart users can hover over, zoom, and pan | **Plotly** |
| Make a correlation heatmap | **Seaborn** |
| Build a web dashboard | **Plotly** (with Dash) |
| Visualize 3D data interactively | **Plotly** |
| Create a pair plot to see all variable relationships | **Seaborn** |
| Have full pixel-level control over a plot | **Matplotlib** |
| Make a quick, attractive plot with minimal code | **Seaborn** or **Plotly Express** |
| Share an interactive chart as an HTML file | **Plotly** |

---

## Conclusion

All three libraries are excellent, and each has a clear strength. Matplotlib gives you total control and is the foundation of Python visualization. Seaborn makes statistical exploration fast and beautiful by building on Matplotlib. Plotly brings interactivity and web-ready charts to the table. Your choice depends on what you need: control (Matplotlib), statistical insight (Seaborn), or interactivity (Plotly). The best data scientists know when to reach for each one.

---

*Learn and Help — [learnandhelp.com](http://www.learnandhelp.com) — Empowering the next generation of data scientists*
