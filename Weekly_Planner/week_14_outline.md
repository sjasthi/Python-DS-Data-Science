# Week 14: Accessing, Filtering and Traversing DataFrames

**Course:** Python for Data Science  
**Instructor:** Siva Jasthi  
**Week:** 14  
**Topic:** Accessing, Filtering and Traversing DataFrames

---

## Learning Objectives

By the end of this week, students will be able to:

1. Access individual columns, rows, and cells in a pandas DataFrame
2. Select multiple columns and rows efficiently
3. Understand and apply the difference between `loc` and `iloc` accessors
4. Traverse DataFrame rows using multiple iteration methods
5. Traverse DataFrame columns using different techniques
6. Filter DataFrames based on conditions and criteria
7. Choose the most appropriate method for accessing and traversing data based on use case

---

## Topics Covered

### 1. Accessing Columns in DataFrames
- Accessing a single column using bracket notation: `df['column_name']`
- Accessing a single column using dot notation: `df.column_name`
- Understanding when to use bracket vs dot notation
- Selecting multiple columns: `df[['col1', 'col2', 'col3']]`
- Working with column subsets for analysis

### 2. Accessing Rows in DataFrames
- Accessing a single row by index position
- Selecting a range of rows using slicing
- Accessing specific rows by index labels
- Extracting first and last rows: `head()`, `tail()`
- Random row sampling with `sample()`

### 3. Understanding loc vs iloc
- **loc**: Label-based indexing
  - Syntax: `df.loc[row_label, column_label]`
  - Accessing rows by index labels
  - Selecting rows and columns by names
  - Using boolean conditions with loc
- **iloc**: Integer position-based indexing
  - Syntax: `df.iloc[row_position, column_position]`
  - Accessing rows by integer position
  - Selecting rows and columns by position numbers
  - Slicing with iloc
- When to use loc vs iloc
- Combining row and column selection

### 4. Accessing Individual Cells
- Accessing a cell using loc: `df.loc[row_label, column_label]`
- Accessing a cell using iloc: `df.iloc[row_position, column_position]`
- Accessing cells using at and iat for faster single value access
- Modifying cell values

### 5. Filtering DataFrames
- Boolean indexing with conditions
- Single condition filtering: `df[df['column'] > value]`
- Multiple condition filtering with AND (`&`) and OR (`|`)
- Using `isin()` for membership testing
- Filtering with string methods: `str.contains()`, `str.startswith()`
- Combining filters with `query()` method
- Negating conditions with `~` (NOT operator)

### 6. Traversing DataFrame Rows
- **Using index iteration**
  - Iterating through row indices
  - Accessing row data using index
- **Using loc for iteration**
  - Systematic row access with loc
- **Using iloc for iteration**
  - Position-based row iteration
- **Using iterrows()**
  - Returns index and Series for each row
  - When to use iterrows()
  - Performance considerations
- **Using itertuples()**
  - Returns named tuples for each row
  - Faster than iterrows()
  - Accessing row data as attributes
- Comparing iteration methods: performance and use cases

### 7. Traversing DataFrame Columns
- **Using items() method**
  - Returns column name and column data as Series
  - Iterating through all columns
- **Using dictionary-style key access**
  - Column names as keys
  - Programmatic column access
- **Using column list iteration**
  - Iterating through `df.columns`
  - Processing columns selectively

### 8. Best Practices for DataFrame Access
- Choosing the right access method for your task
- Performance considerations: vectorized operations vs loops
- Avoiding common pitfalls with chained indexing
- Using copy() vs view when modifying data
- When to use iteration vs vectorized operations

---

## Weekly Assignment

**Assignment:** Pandas Accessing, Filtering and Traversing DataFrames  
**Due Date:** End of Week 14  
**Points:** 25  
**Link:** [pandas_ds_assignment_data_accessing_and_filtering.ipynb](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/python_ds_assignment_pandas_data_accessing_and_filtering.ipynb)

### Assignment Overview:
Students will practice various methods of accessing, filtering, and traversing DataFrames using real-world datasets. They will demonstrate proficiency with loc, iloc, boolean filtering, and different iteration techniques.

---

## Resources

### Required Materials:
- **Main Notebook:** [4_pandas_accessing_filtering_and_traversing_dataframe.ipynb](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/4_pandas_accessing_filtering_and_traversing_dataframe.ipynb)
- **Assignment:** [pandas_accessing_filtering_traversing.md](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/pandas_accessing_filtering_traversing.md)

### Additional Resources:
- Pandas Documentation: [Indexing and Selecting Data](https://pandas.pydata.org/docs/user_guide/indexing.html)
- Pandas Documentation: [Iteration](https://pandas.pydata.org/docs/user_guide/basics.html#iteration)
- Real Python: [Pandas DataFrame: Working with Data](https://realpython.com/pandas-dataframe/)
- Pandas Documentation: [Boolean Indexing](https://pandas.pydata.org/docs/user_guide/indexing.html#boolean-indexing)
- DataCamp: [Pandas loc vs iloc](https://www.datacamp.com/tutorial/pandas-loc-vs-iloc)

---

## Key Concepts Summary

### Quick Reference: loc vs iloc

| Feature | loc | iloc |
|---------|-----|------|
| **Indexing Type** | Label-based | Integer position-based |
| **Syntax** | `df.loc[row_label]` | `df.iloc[row_position]` |
| **Row Selection** | By index label | By integer position (0, 1, 2...) |
| **Column Selection** | By column name | By column position |
| **Slicing** | Inclusive of end | Exclusive of end |
| **Use Case** | When you know labels | When you know positions |

### Iteration Methods Comparison

| Method | Returns | Speed | Use Case |
|--------|---------|-------|----------|
| **Index iteration** | Index values | Fast | When you only need indices |
| **iterrows()** | (index, Series) | Slower | When you need index and row data |
| **itertuples()** | Named tuple | Faster | When you need row data with attribute access |
| **Vectorized** | N/A | Fastest | Always prefer when possible |

---

## Practical Tips

1. **Always prefer vectorized operations** over row-by-row iteration when possible
2. **Use iloc for position-based access** when working with numerical indices
3. **Use loc for label-based access** when working with meaningful index labels
4. **Choose itertuples() over iterrows()** when you need to iterate rows for better performance
5. **Use boolean indexing** for filtering instead of loops
6. **Avoid chained indexing** (e.g., `df[df['A'] > 5]['B']`) - use loc instead
7. **Test with small datasets first** when learning new access methods

---

## Common Patterns

### Filtering Pattern
```python
# Single condition
df[df['Age'] > 30]

# Multiple conditions (AND)
df[(df['Age'] > 30) & (df['Fare'] < 50)]

# Multiple conditions (OR)
df[(df['Sex'] == 'male') | (df['Pclass'] == 1)]

# Using isin()
df[df['Embarked'].isin(['S', 'C'])]
```

### Safe Cell Access
```python
# Using loc (label-based)
value = df.loc[5, 'Age']

# Using iloc (position-based)
value = df.iloc[5, 2]

# Using at/iat (fastest for single values)
value = df.at[5, 'Age']
value = df.iat[5, 2]
```

### Efficient Iteration
```python
# Avoid this (slow)
for index in df.index:
    value = df.loc[index, 'Age']
    
# Prefer this (faster)
for row in df.itertuples():
    value = row.Age

# Best: vectorized (fastest)
df['Age_doubled'] = df['Age'] * 2
```
