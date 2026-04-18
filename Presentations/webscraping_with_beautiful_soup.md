# Learn and Help — Python DS

### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 26: Web Scraping with Beautiful Soup

**Python for Data Science (Python DS)** — Learn and Help

---

## What Is Web Scraping?

Every time you visit a website, your browser sends a **request** to a server. The server sends back an **HTML file**. Your browser renders that HTML into the pretty page you see.

Web scraping means doing the same thing — but with Python. Instead of a browser reading the HTML, your Python code reads it and **extracts the data you care about**.

```
Your Python Code
      │
      ▼  HTTP Request (using requests library)
   Web Server
      │
      ▼  HTML Response
Beautiful Soup
      │
      ▼  Parsed Data
  Pandas DataFrame
```

### Real-World Use Cases

| Use Case | What You Scrape |
|---|---|
| Sports analytics | Player stats tables from ESPN or Basketball-Reference |
| Finance | Stock prices and company data from financial sites |
| E-commerce | Product prices and reviews to compare sellers |
| Research | News headlines, publication dates, article text |
| Real estate | Property listings, prices, square footage |

---

## Setup: Installing the Libraries

You need two libraries:

```python
pip install requests beautifulsoup4
```

Then import them in your notebook:

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd
```

> **Why two libraries?** `requests` fetches the raw HTML from the internet. `beautifulsoup4` then parses and navigates that HTML. They work as a team.

---

## Step 1 — Getting HTML with `requests`

```python
import requests

url = "https://example.com"
response = requests.get(url)

# Check the status code — 200 means success
print(response.status_code)   # 200

# The raw HTML text
print(response.text[:500])    # first 500 characters
```

**Status codes to know:**

| Code | Meaning |
|---|---|
| 200 | Success — you got the page |
| 403 | Forbidden — the site blocked you |
| 404 | Not Found — bad URL |
| 429 | Too Many Requests — you're scraping too fast |

---

## Step 2 — Parsing HTML with Beautiful Soup

Once you have the HTML text, you turn it into a `BeautifulSoup` object:

```python
from bs4 import BeautifulSoup

html = response.text                          # or any HTML string
soup = BeautifulSoup(html, 'html.parser')     # parse it

print(soup.prettify()[:500])                  # nicely formatted HTML preview
```

Think of `soup` like a map of the HTML document. Now you can search and navigate it.

---

## Step 3 — Navigating Tags

### Accessing Tags Directly

```python
# Access the first occurrence of a tag
print(soup.title)          # <title>Example Domain</title>
print(soup.title.text)     # Example Domain

print(soup.h1)             # <h1>Example Domain</h1>
print(soup.h1.text)        # Example Domain

print(soup.p)              # first <p> tag
print(soup.p.text)         # its text content
```

### `.find()` — Get the First Match

```python
# Find the first tag that matches
soup.find('h1')                          # first <h1>
soup.find('p', class_='intro')           # first <p class="intro">
soup.find('div', id='main-content')      # first <div id="main-content">
```

> **Important:** Use `class_` (with an underscore) to search by CSS class. This avoids conflicting with Python's built-in `class` keyword.

### `.find_all()` — Get All Matches

```python
# Returns a list of all matching tags
all_paragraphs = soup.find_all('p')
all_links = soup.find_all('a')
all_rows = soup.find_all('tr')

# Loop through results
for p in all_paragraphs:
    print(p.text)
```

---

## Step 4 — Extracting Data from Tags

### Getting Text Content

```python
tag = soup.find('h1')
print(tag.text)          # text including child tags
print(tag.get_text())    # same thing — slightly more control

# strip whitespace
print(tag.get_text(strip=True))
```

### Getting Attribute Values

```python
# Given: <a href="https://example.com" class="link">Click here</a>

link_tag = soup.find('a')

# Method 1 — dictionary style (raises error if missing)
print(link_tag['href'])          # https://example.com

# Method 2 — .get() style (returns None if missing — safer)
print(link_tag.get('href'))      # https://example.com
print(link_tag.get('class'))     # ['link']
print(link_tag.get('data-id'))   # None (doesn't crash)
```

### Collecting All Links

```python
all_links = soup.find_all('a')

for link in all_links:
    url = link.get('href')
    text = link.get_text(strip=True)
    print(f"{text} → {url}")
```

---

## Step 5 — Searching by Class and ID

HTML example:
```html
<div class="player-card">
  <h2 class="player-name">LeBron James</h2>
  <p class="points">28.9 PPG</p>
</div>
<div class="player-card">
  <h2 class="player-name">Stephen Curry</h2>
  <p class="points">26.4 PPG</p>
</div>
```

Scraping code:
```python
cards = soup.find_all('div', class_='player-card')

for card in cards:
    name = card.find('h2', class_='player-name').get_text(strip=True)
    points = card.find('p', class_='points').get_text(strip=True)
    print(f"{name}: {points}")
```

Output:
```
LeBron James: 28.9 PPG
Stephen Curry: 26.4 PPG
```

---

## Step 6 — Scraping Tables into DataFrames

HTML tables are one of the most common scraping targets. Here's the approach:

HTML table structure (from Week 25):
```html
<table id="players">
  <tr>
    <th>Name</th>
    <th>Team</th>
    <th>PPG</th>
  </tr>
  <tr>
    <td>LeBron James</td>
    <td>Lakers</td>
    <td>28.9</td>
  </tr>
  <tr>
    <td>Stephen Curry</td>
    <td>Warriors</td>
    <td>26.4</td>
  </tr>
</table>
```

Scraping the table:
```python
import pandas as pd

# Find the table
table = soup.find('table', id='players')

# Extract headers
headers = []
for th in table.find_all('th'):
    headers.append(th.get_text(strip=True))

# Extract rows
rows = []
for tr in table.find_all('tr')[1:]:   # skip the header row
    cells = tr.find_all('td')
    row = [cell.get_text(strip=True) for cell in cells]
    if row:                            # skip empty rows
        rows.append(row)

# Build the DataFrame
df = pd.DataFrame(rows, columns=headers)
print(df)
```

### Shortcut: `pd.read_html()`

Pandas has a built-in function that reads ALL tables from a URL:

```python
tables = pd.read_html("https://en.wikipedia.org/wiki/List_of_countries_by_GDP_(nominal)")
df = tables[0]   # first table on the page
print(df.head())
```

> **Limitation:** `pd.read_html()` only works for simple tables and can't filter by class or id. For complex pages, the manual Beautiful Soup approach gives you more control.

---

## Step 7 — Navigating Parent and Sibling Relationships

```python
# Given: <ul><li>Apple</li><li>Banana</li></ul>

first_item = soup.find('li')

# Go up to the parent
print(first_item.parent)          # <ul>...</ul>

# Get the next sibling
print(first_item.next_sibling)    # might be whitespace
print(first_item.find_next_sibling('li'))   # <li>Banana</li>
```

---

## Step 8 — Ethical Scraping Guidelines

| Rule | Why It Matters |
|---|---|
| **Check robots.txt** | `https://example.com/robots.txt` tells you which pages you're allowed to scrape |
| **Add delays** | Use `time.sleep(1)` between requests so you don't overload the server |
| **Respect Terms of Service** | Many sites legally prohibit scraping in their ToS |
| **Don't scrape personal data** | Avoid collecting private or personally identifiable information |
| **Use APIs when available** | If a site offers an API, use it — it's faster, cleaner, and allowed |

```python
import time

urls = ["https://example.com/page1", "https://example.com/page2"]

for url in urls:
    response = requests.get(url)
    soup = BeautifulSoup(response.text, 'html.parser')
    # ... extract data ...
    time.sleep(1)    # wait 1 second before the next request
```

---

## Quick Reference Card

| Task | Code |
|---|---|
| Install | `pip install requests beautifulsoup4` |
| Import | `from bs4 import BeautifulSoup` |
| Parse HTML | `soup = BeautifulSoup(html, 'html.parser')` |
| Find first tag | `soup.find('p')` |
| Find all tags | `soup.find_all('a')` |
| Find by class | `soup.find('div', class_='card')` |
| Find by id | `soup.find('div', id='main')` |
| Get text | `tag.get_text(strip=True)` |
| Get attribute | `tag.get('href')` |
| Table → DataFrame | `pd.read_html(url)[0]` |

---

## Common Mistakes

| Mistake | Fix |
|---|---|
| Using `class=` instead of `class_=` | Always use `class_` (underscore) in Beautiful Soup |
| Forgetting `[1:]` when looping table rows | Header row is index 0 — skip it when building data |
| Crashing on missing attributes | Use `.get('attr')` instead of `tag['attr']` |
| Scraping too fast | Add `time.sleep(1)` between requests |
| Not checking status code | Always verify `response.status_code == 200` |

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
