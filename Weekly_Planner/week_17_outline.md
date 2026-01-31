# Week 17: Pandas Concat, Merge & Join Operations

## 📚 Overview
Learn how to combine multiple DataFrames using pandas' three primary methods: concat, merge, and join.

---

## 🎯 Learning Objectives
By the end of this week, students will be able to:
- Use `pd.concat()` to stack DataFrames vertically and horizontally
- Apply `pd.merge()` to combine DataFrames based on common columns
- Utilize `.join()` method for index-based DataFrame combinations
- Choose the appropriate method for different data combination scenarios

---

## 📖 Topics Covered

### 1. **Concat (Concatenation)**
- Vertical concatenation (axis=0) - stacking rows
- Horizontal concatenation (axis=1) - adding columns
- Using `ignore_index` parameter

### 2. **Merge**
- Inner merge - keep only matches
- Left merge - keep all left DataFrame rows
- Right merge - keep all right DataFrame rows
- Outer merge - keep everything
- Specifying merge keys with `on` parameter

### 3. **Join**
- Index-based joining
- Difference between merge and join
- Join types (inner, left, right, outer)

---

## 📚 Resources

### Presentation
[Pandas Concat, Merge & Join - Presentation](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/7_python_ds_concat_merge_join.md)

### Hands-On Tutorial
[Colab Notebook - Concat, Merge & Join Tutorial](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/7_pandas_concat_merge_join_tutorial.ipynb)

### Assessment
[Interactive Playbook & Quiz](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/pandas_ds_concat_merge_join_interactive_playbook_and_quiz.html)

---

## ✅ Assignment
1. Complete the Interactive Playbook & Quiz
2. Submit quiz screenshot to Google Classroom

---

## 💡 Key Takeaways
- **Concat**: Best for stacking similar DataFrames
- **Merge**: Best when combining DataFrames with common columns
- **Join**: Best when combining DataFrames using their index
