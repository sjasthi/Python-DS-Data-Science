# Learn and Help — Python DS

### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 26 Lab: Web Scraping with Beautiful Soup

**Python for Data Science (Python DS)** — Learn and Help

> **Instructions:** Complete all exercises in Google Colab. Run each code cell and verify your output matches the expected results. Submit your Colab notebook link via Google Classroom when finished.

---

## Lab Setup

Run this cell first in your Colab notebook:

```python
!pip install beautifulsoup4 --quiet

import requests
from bs4 import BeautifulSoup
import pandas as pd
import time

print("✅ Ready to scrape!")
```

---

## Exercise 1 — Parse and Explore (Beginner)

**Topic:** Creating a BeautifulSoup object and accessing tags directly.

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

**Tasks — write code to find:**

1. The text inside the `<title>` tag → should print `My Movie List`
2. The text inside the `<h1>` tag → should print `Top 3 Movies of All Time`
3. The first `<p>` tag text → should print `These are considered classics by film critics worldwide.`
4. The `<h2>` tag text → should print `Science Fiction`

**Expected output:**
```
My Movie List
Top 3 Movies of All Time
These are considered classics by film critics worldwide.
Science Fiction
```

---

## Exercise 2 — `.find()` and `.find_all()` (Beginner–Intermediate)

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

**Tasks:**

1. Use `.find()` to get the first `<h2>` tag and print its text.
2. Use `.find_all()` to get all `<h2>` tags. Print the count and each one's text.
3. Use `.find()` with `class_='intro'` to print the intro paragraph text.
4. Use `.find_all()` to get all `<p class="detail">` tags and print each one's text.

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

---

## Exercise 3 — Extracting Text and Attributes (Intermediate)

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

1. Find all `<a>` tags and print a formatted table:

```
League   URL                          Sport
------   ---------------------------  ----------
NBA      https://www.nba.com          basketball
MLB      https://www.mlb.com          baseball
NFL      https://www.nfl.com          football
FIFA     https://www.fifa.com         soccer
```

2. Use `.get('data-sport')` to find and print only the links where sport is `"basketball"` or `"football"`.

**Hint:** Use `.get('data-sport')` inside a loop. Filter with an `if` statement.

---

## Exercise 4 — Scraping a Table into a DataFrame (Intermediate)

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

**Tasks:**

1. Find the table using its `id="movies"` attribute.
2. Extract headers from all `<th>` tags.
3. Loop through data rows (skip the header row!) and collect all `<td>` values.
4. Build a Pandas DataFrame from the collected data.
5. Convert `Rank` and `IMDb Rating` to numeric types.
6. Answer these questions using Pandas:
   - What is the average IMDb rating?
   - Which movie was released earliest?
   - Which director appears more than once? (Hint: look at the data!)

**Expected DataFrame:**

```
   Rank                     Title  Year              Director  IMDb Rating
0     1  The Shawshank Redemption  1994        Frank Darabont          9.3
1     2             The Godfather  1972  Francis Ford Coppola          9.2
2     3           The Dark Knight  2008    Christopher Nolan          9.0
3     4              12 Angry Men  1957          Sidney Lumet          9.0
4     5          Schindler's List  1993      Steven Spielberg          9.0
```

---

## Exercise 5 — Real Web Scraping (Advanced)

**Topic:** Fetching and scraping a live Wikipedia table.

> ⚠️ **Note:** This exercise requires internet access. Make sure you're connected.

**Tasks:**

1. Use `requests.get()` to fetch this Wikipedia page:
   `https://en.wikipedia.org/wiki/List_of_highest-grossing_films`

2. Check the status code — make sure it's `200`.

3. Use `pd.read_html()` to quickly read the first table from the page.

4. Display the first 10 rows of the table.

5. Using Pandas, answer:
   - How many films in the table grossed over $2 billion worldwide?
   - What year appears most often in the Top 10?

6. **Bonus:** Use BeautifulSoup (not `pd.read_html`) to manually extract the film title and worldwide gross from the first 5 rows of the same table. Print them in a formatted list.

**Expected output (partial):**
```
Status code: 200

Top 10 highest-grossing films:
[first 10 rows of table]

Films grossing over $2 billion: [answer]
```

---

## Reflection Questions

Answer these in a markdown cell in your notebook:

1. What is the difference between `.find()` and `.find_all()`? When would you use each?

2. Why do we use `class_` (with an underscore) in Beautiful Soup instead of `class`?

3. Why is it important to add `time.sleep()` when scraping multiple pages?

4. What is `robots.txt` and why should you check it before scraping a website?

5. When would you use `pd.read_html()` instead of manually parsing with Beautiful Soup?

---

## Submission Checklist

Before submitting to Google Classroom, make sure:

- [ ] All 5 exercises have code cells with output visible
- [ ] Reflection questions are answered in markdown cells
- [ ] Your name is at the top of the notebook
- [ ] The notebook runs cleanly from top to bottom (Runtime → Restart and Run All)
- [ ] You copied your Colab share link and pasted it into Google Classroom

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
