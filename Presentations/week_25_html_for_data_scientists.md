# Learn and Help — Python DS
### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# HTML for Data Scientists

## Why Do Data Scientists Need HTML?

When data scientists collect data from websites — a process called **web scraping** — they need to understand how web pages are built. Every website you visit is made of **HTML** (HyperText Markup Language). Think of HTML as the **skeleton** of a web page: it defines what content is on the page and how it is organized.

Next week, we will use a Python library called **Beautiful Soup** to extract data from HTML pages. But first, we need to learn how to read and understand HTML — just like you need to understand the layout of a grocery store before you can find what you need!

---

## 1. What is HTML?

**HTML** stands for **HyperText Markup Language**.

- **HyperText** — text that links to other text (like clicking a link on a website)
- **Markup** — special symbols (called **tags**) that tell the browser how to display content
- **Language** — a set of rules the browser understands

HTML is **not** a programming language like Python. It does not have loops, variables, or functions. Instead, it is a **markup language** — it labels and organizes content.

### Analogy: HTML is Like a Labeled Box

Imagine you are organizing your room. You put books in a box labeled "Books," toys in a box labeled "Toys," and clothes in a box labeled "Clothes." HTML works the same way — every piece of content on a web page goes inside a **labeled container** called a **tag**.

---

## 2. HTML Tags — The Building Blocks

An HTML **tag** is a label wrapped in angle brackets: `< >`.

Most tags come in **pairs** — an **opening tag** and a **closing tag**:

```
<tagname>Content goes here</tagname>
```

- Opening tag: `<tagname>`
- Closing tag: `</tagname>` (notice the `/`)
- Content: whatever is between the two tags

### Example

```html
<p>This is a paragraph.</p>
```

The `<p>` tag tells the browser: "This is a paragraph of text."

### Self-Closing Tags

A few tags do not need a closing tag because they don't wrap around content:

```html
<br>       <!-- Line break -->
<hr>       <!-- Horizontal line -->
<img src="photo.jpg" alt="A photo">  <!-- Image -->
```

---

## 3. The Structure of an HTML Document

Every HTML page follows the same basic skeleton:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Page Title</title>
  </head>
  <body>
    <h1>Welcome!</h1>
    <p>This is my first web page.</p>
  </body>
</html>
```

| Section | Purpose |
|---------|---------|
| `<!DOCTYPE html>` | Tells the browser this is an HTML5 document |
| `<html>` | The root — everything lives inside this tag |
| `<head>` | Metadata (title, settings) — not visible on the page |
| `<title>` | The text shown on the browser tab |
| `<body>` | All the visible content on the page |

### Analogy: The HTML Tree

HTML is organized like a **family tree**. The `<html>` tag is the grandparent. It has two children: `<head>` and `<body>`. Inside `<body>`, there can be many children like `<h1>`, `<p>`, `<ul>`, and so on. This tree structure is called the **DOM** (Document Object Model).

```
html
├── head
│   └── title
└── body
    ├── h1
    ├── p
    └── ul
        ├── li
        ├── li
        └── li
```

---

## 4. Common HTML Tags

### Headings

HTML has six heading levels, from largest (`<h1>`) to smallest (`<h6>`):

```html
<h1>Main Heading</h1>
<h2>Sub Heading</h2>
<h3>Smaller Heading</h3>
```

### Paragraphs

```html
<p>This is a paragraph of text.</p>
<p>This is another paragraph.</p>
```

### Links (Anchors)

```html
<a href="https://www.google.com">Visit Google</a>
```

- `href` is an **attribute** — it tells the browser where the link goes

### Images

```html
<img src="cat.jpg" alt="A cute cat" width="300">
```

- `src` — the file path or URL of the image
- `alt` — text description (shown if image can't load)

### Line Break and Horizontal Rule

```html
<p>Line one<br>Line two</p>
<hr>
```

---

## 5. Lists

### Unordered List (bullet points)

```html
<ul>
  <li>Apples</li>
  <li>Bananas</li>
  <li>Cherries</li>
</ul>
```

### Ordered List (numbered)

```html
<ol>
  <li>Wake up</li>
  <li>Brush teeth</li>
  <li>Eat breakfast</li>
</ol>
```

---

## 6. Tables — Important for Data Scientists!

Tables are one of the most important HTML elements for data scientists because **a lot of data on the web is stored in HTML tables**.

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>City</th>
  </tr>
  <tr>
    <td>Alice</td>
    <td>14</td>
    <td>Atlanta</td>
  </tr>
  <tr>
    <td>Bob</td>
    <td>13</td>
    <td>Boston</td>
  </tr>
</table>
```

| Tag | Meaning |
|-----|---------|
| `<table>` | The entire table |
| `<tr>` | A table **row** |
| `<th>` | A table **header** cell (bold, centered) |
| `<td>` | A table **data** cell |

### Why This Matters for Scraping

When you use Beautiful Soup next week, you will write Python code like:

```python
soup.find('table')          # Find the table
soup.find_all('tr')         # Get all rows
soup.find_all('td')         # Get all data cells
```

Understanding the tag names (`table`, `tr`, `th`, `td`) is essential!

---

## 7. Divs and Spans — Containers

### `<div>` — Block Container

A `<div>` is an invisible box that **groups content together**. It takes up the full width of the page.

```html
<div>
  <h2>Section Title</h2>
  <p>Some paragraph inside this section.</p>
</div>
```

### `<span>` — Inline Container

A `<span>` is an invisible wrapper for **a small piece of text** within a line.

```html
<p>The price is <span style="color:red;">$9.99</span> today.</p>
```

### Why This Matters for Scraping

Websites often wrap important data inside `<div>` and `<span>` tags with special labels (called **classes** and **IDs**). Beautiful Soup lets you search for these labels to find the exact data you need.

---

## 8. Attributes — Extra Information on Tags

Attributes provide **additional details** about a tag. They are always written inside the opening tag.

```html
<tag attribute="value">Content</tag>
```

### Common Attributes

| Attribute | Purpose | Example |
|-----------|---------|---------|
| `id` | A unique identifier (one per page) | `<div id="header">` |
| `class` | A group label (many elements can share it) | `<p class="intro">` |
| `href` | Link destination | `<a href="url">` |
| `src` | Image or media source | `<img src="photo.jpg">` |
| `style` | Inline CSS styling | `<p style="color:blue;">` |

### Why `id` and `class` Matter for Scraping

When scraping, you often search by `class` or `id`:

```python
soup.find('div', id='main-content')
soup.find_all('p', class_='article-text')
```

---

## 9. Nesting — Tags Inside Tags

HTML tags are often **nested** inside each other, like Russian nesting dolls:

```html
<div class="card">
  <h2>Product Name</h2>
  <p>Price: <span class="price">$29.99</span></p>
  <a href="/buy">Buy Now</a>
</div>
```

### Rules of Nesting

1. Tags must be closed in the **reverse order** they were opened
2. **Correct:** `<p><strong>Bold text</strong></p>`
3. **Wrong:** `<p><strong>Bold text</p></strong>`

---

## 10. Viewing HTML in Your Browser

You can see the HTML of **any website**:

1. Open any web page in Chrome or Edge
2. **Right-click** anywhere on the page
3. Click **"Inspect"** or **"View Page Source"**
4. The HTML code appears in a panel on the side

This is exactly what Beautiful Soup does — it reads this HTML code and lets you search through it with Python.

---

## Quick Reference Card

| What | Tag | Example |
|------|-----|---------|
| Heading | `<h1>` to `<h6>` | `<h1>Title</h1>` |
| Paragraph | `<p>` | `<p>Text here</p>` |
| Link | `<a>` | `<a href="url">Click</a>` |
| Image | `<img>` | `<img src="pic.jpg">` |
| Unordered list | `<ul>` + `<li>` | `<ul><li>Item</li></ul>` |
| Ordered list | `<ol>` + `<li>` | `<ol><li>Step</li></ol>` |
| Table | `<table>`, `<tr>`, `<th>`, `<td>` | See Section 6 |
| Division | `<div>` | `<div>Group</div>` |
| Inline span | `<span>` | `<span>Word</span>` |
| Line break | `<br>` | `<br>` |
| Horizontal rule | `<hr>` | `<hr>` |

---

## Online Practice Resources

### YouTube Tutorials
- **freeCodeCamp** — "HTML Full Course for Beginners" (free, beginner-friendly, project-based)
- **The Net Ninja** — "HTML & CSS Crash Course" playlist (short, well-organized videos)
- **SuperSimpleDev** — "HTML & CSS Full Course – Beginner to Pro" (step-by-step)
- **Traversy Media** — "HTML Crash Course For Absolute Beginners" (clear and practical)

### Online Playgrounds (write & run HTML in your browser)
- **W3Schools Tryit Editor** — [www.w3schools.com/html/tryit.asp](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_default)
- **CodePen** — [codepen.io](https://codepen.io/) — write HTML/CSS/JS and see results instantly
- **JSFiddle** — [jsfiddle.net](https://jsfiddle.net/) — another popular online editor
- **W3Schools HTML Tutorial** — [www.w3schools.com/html](https://www.w3schools.com/html/) — lessons + exercises

---

## Key Takeaway

> As a data scientist, you don't need to *build* websites — you need to **read** HTML so you can **extract data** from websites using Python. Understanding tags, attributes, nesting, and tables is your foundation for web scraping with Beautiful Soup next week!

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
