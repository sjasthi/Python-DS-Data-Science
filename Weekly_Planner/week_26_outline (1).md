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
| Beautiful Soup Guide | Markdown | `week_26_beautifulsoup.md` |
| Beautiful Soup Examples | Jupyter Notebook | `week_26_beautifulsoup.ipynb` |
| Interactive Playbook & Quiz | HTML | `week_26_playbook.html` |
| Lab Exercises | Markdown | `week_26_lab.md` |
| Beautiful Soup Docs | External | [beautiful-soup-4.readthedocs.io](https://beautiful-soup-4.readthedocs.io/en/latest/) |
| Requests Library Docs | External | [docs.python-requests.org](https://docs.python-requests.org/en/latest/) |
| W3Schools HTML Tables | External | [www.w3schools.com/html/html_tables.asp](https://www.w3schools.com/html/html_tables.asp) |
| GitHub Repo | External | [github.com/sjasthi/Python-DS-Data-Science](https://github.com/sjasthi/Python-DS-Data-Science) |

### Recommended YouTube Tutorials

* **Tech With Tim** — "Beautiful Soup Tutorial — Web Scraping in Python" (clear, beginner-friendly)
* **freeCodeCamp** — "Python Web Scraping with Beautiful Soup" (project-based)
* **Corey Schafer** — "Python Tutorial: Web Scraping with BeautifulSoup and Requests" (well-paced)
* **NetworkChuck** — "you need to learn Web Scraping RIGHT NOW!!" (engaging, practical)

## Lesson Flow (80 minutes)

| Time | Activity | Details |
| --- | --- | --- |
| 0–5 min | **Warm-Up** | "Last week you built HTML by hand. Today Python reads it for you!" Quick poll: what kind of data would you want to scrape from the web? (sports stats, movie ratings, prices?) |
| 5–15 min | **What is Web Scraping?** | Explain the concept: HTTP request → HTML response → parse → extract data. Show the big picture diagram in the playbook. Introduce `requests` + `beautifulsoup4`. |
| 15–25 min | **Parsing HTML** | Walk through `BeautifulSoup(html, 'html.parser')`. Show `.prettify()`. Demo finding tags in a simple HTML string. Connect directly to Week 25 HTML knowledge. |
| 25–40 min | **Finding Elements** | Deep-dive on `.find()` vs `.find_all()`. Searching by tag name, `class_`, `id`, attributes. Extracting `.text` and `.get('href')`. Live coding in Colab. |
| 40–55 min | **Scraping Tables → DataFrames** | Walk through scraping an HTML table row-by-row. Build a DataFrame from the extracted data. Show `pd.read_html()` as a shortcut and discuss its limitations. |
| 55–65 min | **Ethics & Real-World Scraping** | Discuss robots.txt, rate limiting, terms of service. Quick demo of `time.sleep()`. Talk about what is and isn't acceptable to scrape. |
| 65–75 min | **Lab Time** | Students work on Lab Exercises 1–5 in Colab. Circulate and help with tag navigation and DataFrame construction. |
| 75–80 min | **Quiz & Wrap-Up** | Students complete the 15-question quiz in the playbook. Screenshot score for Google Classroom. Preview Week 27. |

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

* **Quiz:** 15 questions (5 Web Scraping Basics, 5 Finding & Extracting, 5 Tables & DataFrames) — screenshot submission to Google Classroom
* **Lab:** Exercises 1–5 completed in Google Colab (link to notebook submitted via Google Classroom)

## Looking Ahead

* **Week 27:** APIs and JSON — fetching structured data directly from web APIs (a cleaner alternative to scraping when APIs are available)

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
