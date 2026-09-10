# DSCI 20001 – Data Science 1

**North Hennepin Community College**  
**Instructor:** Dr. Siva Jasthi  
**Founder, President, and Chief Instructor – Learn and Help**  
**Website:** [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 3 Outline

This week, you will review two Google Colab notebooks:

1. A notebook that introduces different data sources and file formats.
2. A notebook that introduces Python's `requests` module.

You will also take the **Python Basics Test** this week.

---

## 1. Data Sources and File Formats

### Notebook

[Python DS – Data Sources and File Formats](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Presentations/Python_DS_Data__Sources_File_Formats.ipynb)

### What the Notebook Covers

#### Dataset Setup

The notebook defines a simple `Student` class containing:

- Name
- Email
- Marks

It then creates a sample collection of approximately 10 students that is used throughout the demonstrations.

#### Writing Data to Different Formats

The notebook demonstrates how to write the same student dataset to multiple file formats.

| # | Format | Example File | Primary Library / Approach |
|---|---|---|---|
| 1 | CSV | `students.csv` | Python `csv` module |
| 2 | Excel (`.xlsx`) | `students.xlsx` | `openpyxl` |
| 3 | JSON | `students.json` | `json` |
| 4 | XML | `students.xml` | `xml.etree.ElementTree` |
| 5 | HTML | `students.html` | HTML table generation |
| 6 | Pickle | `students.pkl` | `pickle` |
| 7 | Plain Text | `students.txt` | Python file I/O |
| 8 | PDF | `students.pdf` | `reportlab` |
| 9 | Word (`.docx`) | `students.docx` | `python-docx` |
| 10 | RTF | `students.rtf` | Minimal RTF written as text |
| 11 | SQL | `students.sql` | Generated SQL `INSERT` statements |
| 12 | YAML | `students.yaml` | `yaml` / PyYAML |

#### Reading Data Back from the File Formats

The notebook also demonstrates how to read or parse the corresponding files:

- **CSV** – Python `csv`
- **Excel** – `openpyxl.load_workbook`
- **JSON** – `json.load`
- **XML** – `xml.etree.ElementTree`
- **HTML** – `BeautifulSoup`
- **Pickle** – `pickle.load`
- **Plain Text** – Python file reading methods such as `readlines()` and iteration
- **PDF** – `pdfplumber`
- **Word (`.docx`)** – `python-docx`
- **RTF** – Reading and performing simple text parsing
- **SQL** – Reading the `.sql` file contents; no live database execution
- **YAML** – `yaml.safe_load`

### Key Libraries

The notebook uses several Python libraries across the examples:

- `csv`
- `json`
- `pickle`
- `xml.etree.ElementTree`
- `yaml` / PyYAML
- `openpyxl`
- `python-docx`
- `reportlab`
- `pdfplumber`
- `bs4` / `BeautifulSoup`

### Additional Data Source Concepts

The notebook also introduces different ways data can enter a Data Science application, including:

- Asking the user for input
- Generating data within a Python program
- Reading data from files
- Fetching data from an API
- Scraping data from the web
- Fetching data from a database

---

## 2. Python `requests` Module

### Notebook

[Python DS – Requests Module](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/python_DS_requests_module.ipynb)

### What the Notebook Covers

#### 1. Requests Module Basics

- Import the module:

```python
import requests
```

- Explore the functions and attributes available in the module:

```python
dir(requests)
```

#### 2. Working with a Response

Fetch a webpage using:

```python
response = requests.get(url)
```

Example URL:

```text
http://www.google.com
```

Explore important response attributes and methods, including:

- `response.status_code`
- `response.text`
- `response.headers`
- `response.url`
- `response.content`
- `response.json()`

#### 3. Sending Parameters

Learn how to send query parameters using the `params` argument.

Example:

```python
params = {"key": "value"}
response = requests.get(url, params=params)
```

#### 4. Downloading Resources

The notebook demonstrates how Python can be used to download resources such as:

- PDF files
- PowerPoint files
- Other files available through URLs

A typical pattern is:

```python
response = requests.get(url)

with open(filename, "wb") as file:
    file.write(response.content)
```

The notebook also demonstrates automating downloads for multiple files.

#### 5. Automating Downloads and Compression

The notebook introduces techniques for organizing downloaded resources.

Topics include:

- Using the `os` module to manage folders and file paths
- Creating directories
- Saving downloaded files
- Automating downloads
- Compressing downloaded files into a ZIP archive for storage or sharing

---

# Python Basics Test

You will also take the **Python Basics Test** during Week 3.

Make sure you are comfortable with the Python fundamentals covered so far before taking the test.

---

## Week 3 Checklist

By the end of Week 3, you should have completed the following:

- [ ] Review the **Data Sources and File Formats** notebook.
- [ ] Understand how the same dataset can be stored in different file formats.
- [ ] Understand how Python reads and writes common file formats.
- [ ] Review the **Python `requests` Module** notebook.
- [ ] Understand how to make an HTTP GET request.
- [ ] Understand common properties of a `Response` object.
- [ ] Understand how to send URL query parameters.
- [ ] Understand how Python can download files from the web.
- [ ] Understand basic download automation and ZIP compression.
- [ ] Complete the **Python Basics Test**.
