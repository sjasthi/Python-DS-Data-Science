# Learn and Help — Python DS
### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 25 Lab: HTML for Data Scientists (10 Points)

## Lab Overview

In this lab, you will practice reading and writing HTML by hand. The goal is **not** to become a web designer — it's to understand HTML structure well enough to extract data from web pages using Python next week.

**Tools you'll need:** A web browser and one of these free online editors:
- [W3Schools Tryit Editor](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_default)
- [CodePen](https://codepen.io/pen/)
- [JSFiddle](https://jsfiddle.net/)

Copy your HTML code into the editor, click Run/Preview, and see the result!

| Exercise | Topic | Points |
|----------|-------|--------|
| 1 | My First HTML Page | 1 |
| 2 | Lists | 1 |
| 3 | Build a Data Table | 2 |
| 4 | Div Containers with Classes and IDs | 2 |
| 5 | Reading Real HTML (View Source) | 1 |
| 6 | Inspect Element Practice | 1 |
| 7 | Fix the Broken HTML | 1 |
| Bonus | Build a Page That's Ready to Scrape | 1 |
| **Total** | | **10** |

---

## Exercise 1: My First HTML Page (1 point)

**Goal:** Build a complete HTML page from scratch.

Create an HTML page that contains:
1. A proper HTML skeleton (`<!DOCTYPE html>`, `<html>`, `<head>`, `<title>`, `<body>`)
2. A page title of "About Me"
3. An `<h1>` heading with your name
4. A `<p>` paragraph describing one of your hobbies
5. A horizontal line (`<hr>`)
6. An `<h2>` heading that says "My Favorite Links"
7. Two links (`<a>`) to websites you like

**Starter Code:**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>___</title>
  </head>
  <body>
    <!-- Add your content here -->
  </body>
</html>
```

---

## Exercise 2: Lists (1 point)

**Goal:** Practice creating both types of lists.

Create an HTML page with:
1. An `<h2>` heading: "My Top 3 Movies" followed by an **ordered list** (`<ol>`) with three movies
2. An `<h2>` heading: "Things I Need for School" followed by an **unordered list** (`<ul>`) with at least four items

**Challenge (included in the 1 point):** Add a **nested list** — put a `<ul>` inside one of the `<li>` items. For example, under "School Supplies" you could nest "Pencils", "Erasers", "Highlighters".

---

## Exercise 3: Build a Data Table (2 points)

**Goal:** Build an HTML table that looks like a dataset you might work with in Pandas.

Create a table with the following data:

| Planet | Distance from Sun (million km) | Number of Moons | Type |
|--------|-------------------------------|-----------------|------|
| Mercury | 57.9 | 0 | Rocky |
| Venus | 108.2 | 0 | Rocky |
| Earth | 149.6 | 1 | Rocky |
| Mars | 227.9 | 2 | Rocky |
| Jupiter | 778.5 | 95 | Gas Giant |

**Requirements:**
- Use `<table>`, `<tr>`, `<th>`, and `<td>` tags
- The first row should use `<th>` for headers
- Add `border="1"` to the `<table>` tag so you can see the grid lines

**Grading:** 1 point for correct table structure with headers. 1 point for all five data rows with correct data.

**Starter Code:**

```html
<table border="1">
  <tr>
    <th>Planet</th>
    <th>Distance from Sun (million km)</th>
    <!-- Add the other headers -->
  </tr>
  <tr>
    <td>Mercury</td>
    <td>57.9</td>
    <!-- Add the other cells -->
  </tr>
  <!-- Add the other rows -->
</table>
```

---

## Exercise 4: Div Containers with Classes and IDs (2 points)

**Goal:** Practice using `<div>`, `class`, and `id` — the attributes you'll search for when scraping.

Create HTML that looks like a product listing page. Make **three product cards**, each inside a `<div class="product">`. Each card should contain:
- An `<h3>` with the product name
- A `<p>` with a description
- A `<span class="price">` with the price
- A `<span class="rating">` with a star rating (use ⭐ emoji)

Give the entire page a wrapper `<div id="product-list">`.

**Starter Code:**

```html
<div id="product-list">

  <div class="product">
    <h3>___</h3>
    <p>___</p>
    <p>Price: <span class="price">$___</span></p>
    <p>Rating: <span class="rating">⭐⭐⭐</span></p>
  </div>

  <!-- Add two more product divs -->

</div>
```

**Think Like a Scraper (required for full credit):** After building this, answer these questions:
- What Beautiful Soup code would find **all** product cards? → `soup.find_all('div', class_='___')`
- What code would find **all** prices? → `soup.find_all('___', class_='___')`
- What code would find the wrapper by its ID? → `soup.find('div', id='___')`

**Grading:** 1 point for three correctly structured product cards with class/id attributes. 1 point for correctly answering all three "Think Like a Scraper" questions.

---

## Exercise 5: Reading Real HTML — View Source (1 point)

**Goal:** Practice reading HTML from a real web page.

1. Go to [https://en.wikipedia.org/wiki/Python_(programming_language)](https://en.wikipedia.org/wiki/Python_(programming_language))
2. Right-click on the page and select **"View Page Source"** (or press `Ctrl+U`)
3. Use `Ctrl+F` to search the source and answer these questions:

**Questions:**
1. Search for `<title>`. What text is inside the `<title>` tag?
2. Search for `<table class="wikitable"`. How many wikitables can you find?
3. Search for `<h2>`. List any three `<h2>` headings you find.
4. Search for `class="mw-headline"`. What do these span tags contain?

---

## Exercise 6: Inspect Element Practice (1 point)

**Goal:** Use the browser's Inspect tool to explore HTML structure.

1. Go to any website you like (a news site, Wikipedia, a store)
2. Right-click on a **heading** and choose **"Inspect"**
3. In the Elements panel, find and write down:
   - What tag is the heading? (`<h1>`, `<h2>`, etc.)
   - Does it have a `class` or `id` attribute?
4. Right-click on a **link** and Inspect it. Write down:
   - The `href` value
   - Any `class` attributes
5. If the page has a **table**, inspect it and note the tags: `<table>`, `<tr>`, `<th>`, `<td>`

---

## Exercise 7: Fix the Broken HTML (1 point)

**Goal:** Practice spotting and fixing HTML errors.

The following HTML has **5 errors**. Find and fix them all:

```html
<html>
  <head>
    <title>My Page<title>
  </head>
  <body>
    <h1>Welcome to my site</h2>
    <p>This is a paragraph
    <ul>
      <li>Item 1</li>
      <li>Item 2
      <li>Item 3</li>
    </ol>
    <a href="google.com">Visit Google</a>
  </body>
</html>
```

**Hint:** Look for mismatched tags, missing closing tags, and incorrect tag pairs.

---

## Bonus Challenge: Build a Page That's Ready to Scrape (+1 point)

Create a complete HTML page that represents a **class roster** with the following structure:

```html
<div id="roster">
  <h1>Python DS — Class Roster</h1>
  <table id="student-table">
    ... (at least 5 students with Name, Grade, and Favorite Language columns) ...
  </table>
  <div class="summary">
    <p>Total Students: <span id="count">5</span></p>
  </div>
</div>
```

After building it, write down the Beautiful Soup code you would use to:
1. Find the table by its ID
2. Get all rows from the table
3. Extract the text from each `<td>` cell
4. Find the total student count from the summary span

---

## Submission

Complete Exercises 1–7 for 9 points. Complete the Bonus Challenge for the full 10 points.

For each exercise, paste your HTML code into the online editor, verify it works, and save your answers.

Submit a screenshot of your completed work to **Google Classroom**.

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
