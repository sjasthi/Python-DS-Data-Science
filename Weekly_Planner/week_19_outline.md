# Week 19: Reading & Writing to Different Data Types using Pandas 📄📊

**Course:** Python for Data Science  
**Program:** Learn and Help (www.learnandhelp.com)  
**Instructor:** Siva Jasthi, Ph.D.  
**Week:** 19 
**Topic:** Reading and Writing to Different Data Types

---

## 🎯 Learning Objectives

By the end of this week, students will be able to:

1. Understand the importance of different file formats in data science workflows
2. Write data to multiple file formats using Python (CSV, Excel, JSON, XML, HTML, Pickle, Text, PDF, DOCX, RTF, SQL, YAML)
3. Read data from multiple file formats back into Python
4. Use Pandas to read and write data efficiently with `pd.read_csv()`, `pd.read_excel()`, `pd.read_json()`, and more
5. Create new DataFrame columns by recoding and transforming existing data
6. Export transformed DataFrames to both CSV and Excel formats
7. Choose the appropriate file format for different data science scenarios

---

## 📖 Topics Covered

### 1. **Data Sources Overview**
- Asking the user for input
- Generating data within a Python program
- Reading data from a file
- Fetching data from an API
- Scraping the web
- Fetching data from a database

### 2. **Writing Data to Different Formats**
- CSV format (using `csv` module)
- Excel format (using `openpyxl`)
- JSON format (using `json` module)
- XML format (using `xml.etree.ElementTree`)
- HTML format
- Pickle format (binary serialization)
- Text format
- PDF format (using `reportlab`)
- DOCX format (using `python-docx`)
- RTF format
- SQL format (INSERT statements)
- YAML format

### 3. **Reading Data from Different Formats**
- Reading CSV files
- Reading Excel files
- Reading JSON files
- Reading XML files
- Reading HTML files (using `BeautifulSoup`)
- Reading Pickle files
- Reading Text files
- Reading PDF files (using `pdfplumber`)
- Reading DOCX files
- Reading RTF files
- Reading YAML files

### 4. **Reading and Writing Data using Pandas**
- Reading data from files into DataFrames
- Adding new data to DataFrames
- Writing DataFrames to CSV using `df.to_csv()`
- Writing DataFrames to Excel using `df.to_excel()`
- Verifying exports by reading files back in

---

## 📚 Resources

### Colab Notebook (Walk-through in class)
📓 [Pandas: Reading & Writing to Different Data Types](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/pandas/9_pandas_reading_n_writing_to_different_data_types.ipynb)

**What it covers:**
- Creating Student objects and StudentCollection
- Writing student data to 12 different file formats
- Reading student data back from each format
- Using Pandas to read and write DataFrames

**How to use:** Open in Google Colab → Run each cell → Experiment with the code!

---

## ✅ Assignment

### 📝 Pandas Assignment: Reading, Exploring, Transforming & Writing Data (25 Points)

📓 [Assignment Notebook](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/python_ds_pandas_assignment_reading_n_writing_data.ipynb)

**Dataset:** Students Performance in Exams (from Kaggle)

**What you will do:**

| Task | Description | Points |
|------|-------------|:------:|
| Task 1 | Read the Kaggle CSV dataset into a Pandas DataFrame | 3 |
| Task 2 | Perform Exploratory Data Analysis (EDA) and answer 5 questions | 10 |
| Task 3 | Recode two columns to create `average_score` and `performance_grade` | 7 |
| Task 4 | Export the updated DataFrame to CSV and Excel formats | 5 |
| **Total** | | **25** |

**Submit to Google Classroom:**
1. Your completed notebook (.ipynb)
2. `students_updated.csv`
3. `students_updated.xlsx`

---

## 📌 Quick Checklist

- [ ] Walk through the Colab notebook in class
- [ ] Understand how to write data to CSV, Excel, JSON, and other formats
- [ ] Understand how to read data from different file formats using Python and Pandas
- [ ] Download the assignment notebook and the Kaggle dataset
- [ ] Complete all 4 tasks in the assignment
- [ ] Submit the notebook + CSV + Excel files to Google Classroom

---

## 💡 Key Takeaways

- **CSV** is the most common format for tabular data — simple and universal
- **Excel (.xlsx)** is great when you need formatting, multiple sheets, or sharing with non-programmers
- **JSON** is the go-to format for web APIs and nested data
- **Pandas makes it easy** — `pd.read_csv()`, `pd.read_excel()`, `df.to_csv()`, `df.to_excel()` handle most use cases
- **Always use `index=False`** when exporting to avoid saving unnecessary row numbers

---

## 🔮 Next Week Preview

Week 20: pandas - Working with Time Series Data

---

**Happy Coding! 🐍📊**
