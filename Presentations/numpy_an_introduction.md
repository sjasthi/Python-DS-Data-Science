# Introduction to NumPy 🔢

Welcome to the world of NumPy! Get ready to supercharge your Python skills with one of the most powerful tools in data science.

## What is NumPy?

**NumPy** (Numerical Python) is a Python library that helps us work with numbers efficiently. Think of it as a calculator on steroids! 💪

Instead of working with numbers one at a time, NumPy lets you work with thousands or even millions of numbers at once. This makes it perfect for data science, where we often deal with huge amounts of data.

## Why Use NumPy?

1. **Speed**: NumPy is 10-100x faster than regular Python lists
2. **Convenience**: Perform operations on entire datasets with one line of code
3. **Power**: It's used by professionals at NASA, Netflix, Google, and more!

## Getting Started

First, we need to import NumPy. The standard way is:

```python
import numpy as np
```

Why `np`? It's shorter to type, and everyone in the data science community uses it!

## NumPy Arrays: The Foundation

The main tool in NumPy is the **array**. It's like a Python list, but way more powerful.

### Creating Arrays

```python
# From a Python list
my_array = np.array([1, 2, 3, 4, 5])
print(my_array)
# Output: [1 2 3 4 5]

# Create an array of zeros
zeros = np.zeros(5)
print(zeros)
# Output: [0. 0. 0. 0. 0.]

# Create an array of ones
ones = np.ones(5)
print(ones)
# Output: [1. 1. 1. 1. 1.]

# Create a range of numbers
range_array = np.arange(0, 10, 2)  # Start, stop, step
print(range_array)
# Output: [0 2 4 6 8]

# Create evenly spaced numbers
spaced = np.linspace(0, 1, 5)  # Start, stop, how many numbers
print(spaced)
# Output: [0.   0.25 0.5  0.75 1.  ]
```

### 2D Arrays (Matrices)

Arrays can have multiple dimensions. A 2D array is like a table or spreadsheet:

```python
# Create a 2D array
matrix = np.array([[1, 2, 3],
                   [4, 5, 6],
                   [7, 8, 9]])
print(matrix)
# Output:
# [[1 2 3]
#  [4 5 6]
#  [7 8 9]]

# Create a 3x3 array of zeros
zeros_2d = np.zeros((3, 3))

# Create a 2x4 array of random numbers
random_array = np.random.rand(2, 4)
```

## Array Math: The Magic! ✨

Here's where NumPy gets awesome. You can do math on entire arrays at once!

### Basic Operations

```python
arr = np.array([1, 2, 3, 4, 5])

# Add 10 to every number
print(arr + 10)
# Output: [11 12 13 14 15]

# Multiply every number by 2
print(arr * 2)
# Output: [ 2  4  6  8 10]

# Square every number
print(arr ** 2)
# Output: [ 1  4  9 16 25]

# Array math with two arrays
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
print(arr1 + arr2)
# Output: [5 7 9]
```

### Try This: Temperature Converter 🌡️

```python
# Convert Fahrenheit to Celsius
fahrenheit = np.array([32, 68, 86, 104])
celsius = (fahrenheit - 32) * 5/9
print(celsius)
# Output: [ 0. 20. 30. 40.]
```

## Useful Array Functions

```python
data = np.array([23, 45, 12, 67, 89, 34, 56])

# Basic statistics
print(np.mean(data))    # Average: 46.57
print(np.median(data))  # Middle value: 45.0
print(np.max(data))     # Largest: 89
print(np.min(data))     # Smallest: 12
print(np.sum(data))     # Total: 326
print(np.std(data))     # Standard deviation

# Find positions
print(np.argmax(data))  # Position of max value: 4
print(np.argmin(data))  # Position of min value: 2
```

## Slicing and Indexing

Access parts of your array just like Python lists, but with superpowers!

```python
arr = np.array([10, 20, 30, 40, 50])

# Get one element
print(arr[0])      # Output: 10

# Get a slice
print(arr[1:4])    # Output: [20 30 40]

# Get every other element
print(arr[::2])    # Output: [10 30 50]

# 2D array indexing
matrix = np.array([[1, 2, 3],
                   [4, 5, 6],
                   [7, 8, 9]])

print(matrix[1, 2])     # Row 1, Column 2: 6
print(matrix[0, :])     # First row: [1 2 3]
print(matrix[:, 1])     # Second column: [2 5 8]
```

## Boolean Indexing (Super Cool!) 😎

Filter your data based on conditions:

```python
scores = np.array([85, 92, 78, 95, 88, 73, 90])

# Find scores above 90
high_scores = scores[scores > 90]
print(high_scores)
# Output: [92 95]

# Find scores between 80 and 90
medium_scores = scores[(scores >= 80) & (scores < 90)]
print(medium_scores)
# Output: [85 88]
```

## Real-World Example: Analyzing Test Scores 📊

```python
# Five students, four tests each
test_scores = np.array([[85, 90, 78, 92],
                        [88, 85, 90, 95],
                        [75, 80, 85, 88],
                        [92, 95, 98, 96],
                        [80, 85, 82, 88]])

# Calculate each student's average
student_averages = np.mean(test_scores, axis=1)
print("Student Averages:", student_averages)

# Calculate average for each test
test_averages = np.mean(test_scores, axis=0)
print("Test Averages:", test_averages)

# Find the highest score
print("Highest Score:", np.max(test_scores))

# Which students scored above 85 average?
high_performers = student_averages > 85
print("High Performers:", high_performers)
```

## Shape and Reshape

Understanding array dimensions is important:

```python
arr = np.array([[1, 2, 3, 4],
                [5, 6, 7, 8]])

print(arr.shape)     # Output: (2, 4) - 2 rows, 4 columns
print(arr.size)      # Output: 8 - total elements

# Reshape the array
reshaped = arr.reshape(4, 2)
print(reshaped)
# Output:
# [[1 2]
#  [3 4]
#  [5 6]
#  [7 8]]

# Flatten to 1D
flat = arr.flatten()
print(flat)
# Output: [1 2 3 4 5 6 7 8]
```

## Practice Challenges 🎯

### Challenge 1: Grade Calculator
Create an array of 10 random test scores (between 60 and 100). Calculate the mean, find how many students passed (score >= 70), and give everyone a 5-point curve.

```python
# Your code here!
```

### Challenge 2: Temperature Analysis
Given this week's temperatures: [72, 68, 75, 80, 78, 82, 70]
- Find the average temperature
- Find the hottest and coldest days
- How many days were above 75°F?

```python
# Your code here!
```

### Challenge 3: Matrix Magic
Create a 5x5 multiplication table (1-5) using NumPy arrays.

```python
# Hint: Use np.arange() and array broadcasting!
```

### Challenge 4: Data Cleaning
You have this data: [25, 30, -999, 28, 32, -999, 35]
The -999 values represent missing data. Replace them with the average of the valid numbers.

```python
# Your code here!
```

## Quick Reference Card 📋

| Function | What It Does | Example |
|----------|--------------|---------|
| `np.array()` | Create an array | `np.array([1,2,3])` |
| `np.zeros()` | Array of zeros | `np.zeros(5)` |
| `np.ones()` | Array of ones | `np.ones(5)` |
| `np.arange()` | Range of numbers | `np.arange(0,10,2)` |
| `np.linspace()` | Evenly spaced numbers | `np.linspace(0,1,5)` |
| `np.mean()` | Average | `np.mean(arr)` |
| `np.max()` | Maximum value | `np.max(arr)` |
| `np.min()` | Minimum value | `np.min(arr)` |
| `np.sum()` | Sum of all values | `np.sum(arr)` |
| `np.std()` | Standard deviation | `np.std(arr)` |
| `.shape` | Array dimensions | `arr.shape` |
| `.reshape()` | Change dimensions | `arr.reshape(2,3)` |

## Key Takeaways 🔑

1. NumPy arrays are faster and more powerful than Python lists
2. You can do math on entire arrays at once
3. Use functions like `mean()`, `max()`, and `sum()` for quick analysis
4. Boolean indexing lets you filter data easily
5. Arrays can be 1D, 2D, or even higher dimensions

## What's Next?

Now that you know NumPy, you're ready to explore:
- **Pandas**: Work with data in tables (DataFrames)
- **Matplotlib**: Create awesome graphs and visualizations

Keep practicing, and you'll be a data science pro in no time! 🚀

---

*Remember: The best way to learn NumPy is by using it. Try these examples, break things, fix them, and experiment!*
