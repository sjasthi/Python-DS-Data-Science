# Learn and Help — Python DS
### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 26 Assignment: Web Scraping with Beautiful Soup

**Python for Data Science (Python DS)** — Learn and Help
**Total Points: 25**

> **Instructions:** Complete all exercises in Google Colab. Run each code cell and verify your output matches the expected results. Submit your Colab notebook link via Google Classroom when finished. Partial credit is awarded for code that runs but produces incorrect output. No credit is awarded for code that does not run.

---

## Grading Summary

| Exercise | Topic | Points |
|----------|-------|--------|
| Exercise 1 | Parse and Explore | 3 |
| Exercise 2 | `.find()` and `.find_all()` | 5 |
| Exercise 3 | Extracting Text and Attributes | 5 |
| Exercise 4 | Scraping a Table into a DataFrame | 8 |
| Exercise 5 | Real Web Scraping | 2 |
| Reflection | Conceptual Questions | 2 |
| **Total** | | **25** |

---

## Assignment Setup

Run this cell first in your Colab notebook before starting any exercise:

```python
!pip install beautifulsoup4 --quiet

import requests
from bs4 import BeautifulSoup
import pandas as pd
import time

print("✅ Ready to scrape!")
```

> **Add your name in a Markdown cell at the top of your notebook before submitting.**

---

## Exercise 1 — Parse and Explore *(3 points)*

**Topic:** Creating a `BeautifulSoup` object and accessing tags directly.

Use the HTML below to answer the questions that follow.

```python
html = """
<!DOCTYPE html>
<html>
  <head><title>My Movie List</title></head>
  <body>
    <h1>Top 3 Movies of All Time</h1>
    <p class="intro">These are considered classics by film critics worldwide.</p>
    <p class="detail">Ratings are based on IMDb and Rotten Tomatoes scores.</p>
    <h2>Science Fiction</h2>
    <p>2001: A Space Odyssey is widely regarded as a masterpiece.</p>
  </body>
</html>
"""

soup = BeautifulSoup(html, 'html.parser')
```

**Tasks — write code to find each of the following (0.75 pt each):**

1. The text inside the `<title>` tag → should print `My Movie List`
2. The text inside the `<h1>` tag → should print `Top 3 Movies of All Time`
3. The text of the **first** `<p>` tag → should print `These are considered classics by film critics worldwide.`
4. The text inside the `<h2>` tag → should print `Science Fiction`

**Expected output:**
```
My Movie List
Top 3 Movies of All Time
These are considered classics by film critics worldwide.
Science Fiction
```

> **Grading:** 0.75 pt per correct output (4 tasks × 0.75 = 3 pts)

---

## Exercise 2 — `.find()` and `.find_all()` *(5 points)*

**Topic:** Using `.find()` and `.find_all()` to locate specific elements.

```python
html2 = """
<html><body>
  <h2 class="sport">Basketball</h2>
  <h2 class="sport">Soccer</h2>
  <h2 class="sport">Baseball</h2>
  <p class="intro">All three sports have global fan bases.</p>
  <p class="detail">Basketball was invented in 1891.</p>
  <p class="detail">Soccer is the world's most popular sport.</p>
  <p class="detail">Baseball has been called America's pastime.</p>
</body></html>
"""

soup2 = BeautifulSoup(html2, 'html.parser')
```

**Tasks (points noted per task):**

1. *(1 pt)* Use `.find()` to get the **first** `<h2>` tag and print its text.
2. *(1.5 pts)* Use `.find_all()` to get **all** `<h2>` tags. Print the count and the text of each one.
3. *(1 pt)* Use `.find()` with `class_='intro'` to print the intro paragraph text.
4. *(1.5 pts)* Use `.find_all()` to get **all** `<p class="detail">` tags and print the text of each one.

**Expected output:**
```
First sport: Basketball
Found 3 sports:
  - Basketball
  - Soccer
  - Baseball
Intro: All three sports have global fan bases.
Details:
  - Basketball was invented in 1891.
  - Soccer is the world's most popular sport.
  - Baseball has been called America's pastime.
```

> **Grading:** See point values per task above. Partial credit awarded for correct logic with minor output formatting differences.

---

## Exercise 3 — Extracting Text and Attributes *(5 points)*

**Topic:** Pulling `.text`, `.get()`, and attribute values from tags.

```python
html3 = """
<html><body>
  <a href="https://www.nba.com" class="league" data-sport="basketball">NBA</a>
  <a href="https://www.mlb.com" class="league" data-sport="baseball">MLB</a>
  <a href="https://www.nfl.com" class="league" data-sport="football">NFL</a>
  <a href="https://www.fifa.com" class="league" data-sport="soccer">FIFA</a>
</body></html>
"""

soup3 = BeautifulSoup(html3, 'html.parser')
```

**Tasks:**

1. *(3 pts)* Find **all** `<a>` tags and print a formatted table showing the league name, URL, and sport:

```
League   URL                          Sport
------   ---------------------------  ----------
NBA      https://www.nba.com          basketball
MLB      https://www.mlb.com          baseball
NFL      https://www.nfl.com          football
FIFA     https://www.fifa.com         soccer
```

2. *(2 pts)* Use `.get('data-sport')` inside a loop to find and print **only** the links where the sport is `"basketball"` or `"football"`.

> **Hint:** Use an `if` statement inside your loop to filter by sport.

> **Grading:** Task 1 — 3 pts (1 pt correct loop, 1 pt correct attribute extraction, 1 pt formatted output). Task 2 — 2 pts (1 pt correct filter logic, 1 pt correct output).

---

## Exercise 4 — Scraping a Table into a DataFrame *(8 points)*

**Topic:** The full table-scraping pattern: find → headers → rows → DataFrame.

```python
html4 = """
<html><body>
<table id="movies">
  <tr><th>Rank</th><th>Title</th><th>Year</th><th>Director</th><th>IMDb Rating</th></tr>
  <tr><td>1</td><td>The Shawshank Redemption</td><td>1994</td><td>Frank Darabont</td><td>9.3</td></tr>
  <tr><td>2</td><td>The Godfather</td><td>1972</td><td>Francis Ford Coppola</td><td>9.2</td></tr>
  <tr><td>3</td><td>The Dark Knight</td><td>2008</td><td>Christopher Nolan</td><td>9.0</td></tr>
  <tr><td>4</td><td>12 Angry Men</td><td>1957</td><td>Sidney Lumet</td><td>9.0</td></tr>
  <tr><td>5</td><td>Schindler's List</td><td>1993</td><td>Steven Spielberg</td><td>9.0</td></tr>
</table>
</body></html>
"""

soup4 = BeautifulSoup(html4, 'html.parser')
```

**Tasks (points noted per task):**

1. *(1 pt)* Find the table using its `id="movies"` attribute.
2. *(1 pt)* Extract headers from all `<th>` tags and store them in a list.
3. *(2 pts)* Loop through the **data rows only** (skip the header row!) and collect all `<td>` cell values. Store each row as a list.
4. *(1 pt)* Build a Pandas DataFrame from the collected data using the headers list as column names.
5. *(1 pt)* Convert the `Rank` column to integer and the `IMDb Rating` column to float.
6. *(2 pts)* Use Pandas to answer the following questions (print each answer with a label):
   - What is the **average IMDb rating**?
   - Which movie was **released earliest** (lowest year)?
   - Which director appears **more than once** in the table?

**Expected DataFrame:**
```
   Rank                     Title  Year              Director  IMDb Rating
0     1  The Shawshank Redemption  1994        Frank Darabont          9.3
1     2             The Godfather  1972  Francis Ford Coppola          9.2
2     3           The Dark Knight  2008     Christopher Nolan          9.0
3     4              12 Angry Men  1957          Sidney Lumet          9.0
4     5          Schindler's List  1993      Steven Spielberg          9.0
```

> **Grading:** See point values per task above. For Task 6, each correct answer is worth 0.67 pts (rounded). Partial credit given for correct code with minor logical errors.

---

## Exercise 5 — Real Web Scraping *(2 points)*

**Topic:** Fetching and scraping a live Wikipedia table.

> ⚠️ **Note:** This exercise requires internet access. Make sure you are connected in Colab.

**Tasks:**

1. *(0.5 pt)* Use `requests.get()` to fetch the following Wikipedia page and verify the status code is `200`:
   `https://en.wikipedia.org/wiki/List_of_highest-grossing_films`
2. *(0.5 pt)* Use `pd.read_html()` to read the first table from the page and display the **first 10 rows**.
3. *(0.5 pt)* Using Pandas, answer: **How many films grossed over $2 billion worldwide?**
4. *(0.5 pt)* Using Pandas, answer: **What year appears most often in the Top 10?**

**Expected output (partial):**
```
Status code: 200

Top 10 highest-grossing films:
[first 10 rows of the DataFrame]

Films grossing over $2 billion: [your answer]
Most common year in Top 10: [your answer]
```

> **Grading:** 0.5 pt per task. Full credit requires printed output. If the Wikipedia page structure has changed and `pd.read_html()` fails, document the error in a Markdown cell for partial credit.

---

## Reflection Questions *(2 points)*

Answer **all five** questions in a **Markdown cell** in your notebook. Write in complete sentences.

1. What is the difference between `.find()` and `.find_all()`? When would you use each?
2. Why do we use `class_` (with an underscore) in Beautiful Soup instead of `class`?
3. Why is it important to add `time.sleep()` when scraping multiple pages?
4. What is `robots.txt` and why should you check it before scraping a website?
5. When would you use `pd.read_html()` instead of manually parsing with Beautiful Soup?

> **Grading:** 2 pts total — 0.4 pt per question. Full credit requires a clear, accurate, and complete answer in your own words.

---

## Submission Checklist

Before submitting to Google Classroom, verify the following:

- [ ] Your **name** is in a Markdown cell at the top of the notebook
- [ ] **All 5 exercises** have code cells with output visible beneath them
- [ ] **Reflection questions** are answered in a Markdown cell (not a code cell)
- [ ] The notebook runs **cleanly from top to bottom** (Runtime → Restart and Run All)
- [ ] You have copied your **Colab share link** and pasted it into Google Classroom

---

## Point Recap

| Exercise | Description | Points |
|----------|-------------|--------|
| Exercise 1 | Parse and Explore (4 tasks × 0.75 pt) | 3 |
| Exercise 2 | `.find()` and `.find_all()` | 5 |
| Exercise 3 | Extracting Text and Attributes | 5 |
| Exercise 4 | Scraping a Table into a DataFrame | 8 |
| Exercise 5 | Real Web Scraping | 2 |
| Reflection | Conceptual Questions (5 × 0.4 pt) | 2 |
| **Total** | | **25** |

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
