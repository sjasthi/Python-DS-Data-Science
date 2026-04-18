# Learn and Help — Python DS

### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 26: Web Scraping with Beautiful Soup

## Course

**Python for Data Science (Python DS)** — Learn and Help

## Topic

Web scraping with Beautiful Soup. Students use Python to programmatically extract data from HTML pages — tags, text, links, tables, and attributes — and load results into Pandas DataFrames for analysis.

## Prior Knowledge

* **Week 25:** HTML for Data Scientists — tags, attributes, the DOM, `id` and `class`, HTML tables
* **Weeks 22–24:** Matplotlib, Seaborn, and Plotly visualizations
* **Weeks 1–21:** Core Python, Pandas, and NumPy foundations
* Students know how to use `pip install` and Google Colab

## Learning Objectives

By the end of this lesson, students will be able to:

1. Explain what web scraping is and give two real-world use cases for data science
2. Install Beautiful Soup and import it alongside the `requests` library
3. Parse an HTML string or URL response into a `BeautifulSoup` object
4. Use `.find()` and `.find_all()` to locate tags by name, class, and id
5. Extract text content and attribute values from HTML elements
6. Scrape an HTML table and load it into a Pandas DataFrame
7. Follow a links list to understand how multi-page scraping works
8. Describe ethical guidelines for web scraping (robots.txt, rate limiting, terms of service)

## Resources

| Resource | Type | Link |
| --- | --- | --- |
| Beautiful Soup Guide | Markdown | [Web Scraping with Beautiful Soup](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Presentations/webscraping_with_beautiful_soup.md) |
| Beautiful Soup Examples 1 | Jupyter Notebook | [web\_scraping\_with\_beautiful\_soup.ipynb](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Presentations/python_ds_beautiful_soup.ipynb) |
| Beautiful Soup Examples 2 | Jupyter Notebook | [web\_scraping\_with\_beautiful\_soup.ipynb](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Presentations/python_ds_web_scraping_with_beautiful_soup.ipynb) |
| Interactive Playbook & Quiz | HTML | [Beautiful Soup](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Quizzes/beautiful_soup_playbook_and_quiz.html) |
| Assignment | Markdown | [Beautiful Soup Assignment](https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Assignments/beautiful_soup_assignment.md) |
| Beautiful Soup Docs | External | [beautiful-soup-4.readthedocs.io](https://beautiful-soup-4.readthedocs.io/en/latest/) |
| Requests Library Docs | External | [docs.python-requests.org](https://docs.python-requests.org/en/latest/) |
| W3Schools HTML Tables | External | [www.w3schools.com/html/html\_tables.asp](https://www.w3schools.com/html/html_tables.asp) |
| GitHub Repo | External | [github.com/sjasthi/Python-DS-Data-Science](https://github.com/sjasthi/Python-DS-Data-Science) |

### Recommended YouTube Tutorials

* **Tech With Tim** — [Beautiful Soup 4 Tutorial #1 - Web Scraping With Python](https://www.youtube.com/watch?v=gRLHr664tXA) (clear, beginner-friendly)
* **freeCodeCamp** — [Web Scraping with Python - Beautiful Soup Crash Course](https://www.youtube.com/watch?v=XVv6mJpFOb0) (project-based)
* **Corey Schafer** — [Python Tutorial: Web Scraping with BeautifulSoup and Requests](https://www.youtube.com/watch?v=ng2o98k983k) (well-paced)

## Key Vocabulary

| Term | Definition |
| --- | --- |
| Web Scraping | Automatically extracting data from web pages using code |
| `requests` | Python library for sending HTTP requests and getting web page content |
| `BeautifulSoup` | Python library for parsing HTML and navigating its tree structure |
| Parser | The engine that interprets raw HTML text (e.g., `'html.parser'`) |
| `.find()` | Returns the **first** matching tag in the document |
| `.find_all()` | Returns a **list** of all matching tags in the document |
| `.text` | The plain text content inside a tag, with all child tags removed |
| `.get('attr')` | Safe way to retrieve an attribute value from a tag |
| `class_` | Keyword used in Beautiful Soup to search by CSS class (avoids Python's `class` keyword conflict) |
| `robots.txt` | A file on websites that tells bots which pages they may or may not scrape |
| Rate Limiting | Adding delays between requests so you don't overload a web server |

## Assessment

* **Quiz:** 10 questions — screenshot submission to Google Classroom
* **Assignment:** Exercises 1–5 completed in Google Colab (link to notebook submitted via Google Classroom)

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
