# Learn and Help — Python DS
### [www.learnandhelp.com](https://www.learnandhelp.com)

---

# Week 25: HTML for Data Scientists

## Course
**Python for Data Science (Python DS)** — Learn and Help

## Topic
Introduction to HTML (HyperText Markup Language) for data scientists. Students learn to read and understand the structure of web pages — tags, attributes, nesting, tables, and the DOM — as preparation for web scraping with Beautiful Soup in Week 26.

## Prior Knowledge
- Weeks 22–24: Matplotlib, Seaborn, and Plotly visualizations
- Students have been using HTML-based interactive playbooks throughout the course
- Basic Python data structures (lists, dictionaries)

## Learning Objectives
By the end of this lesson, students will be able to:
1. Explain what HTML is and why data scientists need to understand it
2. Identify the basic skeleton of an HTML document (`<!DOCTYPE>`, `<html>`, `<head>`, `<body>`)
3. Read and write common HTML tags: headings, paragraphs, links, images, lists
4. Build an HTML table using `<table>`, `<tr>`, `<th>`, and `<td>` tags
5. Explain the purpose of `<div>` and `<span>` as container elements
6. Use `id` and `class` attributes and explain why they matter for scraping
7. Describe the DOM (Document Object Model) as a tree structure
8. Use the browser's "Inspect" / "View Source" tool to explore real web page HTML

## Resources

| Resource | Type | Link |
|----------|------|------|
| HTML for Data Scientists (Presentation) | Markdown | `week_25_html_for_data_scientists.md` |
| Interactive Playbook & Quiz | HTML | `week_25_html_playbook.html` |
| HTML Lab Exercises | Markdown | `week_25_html_lab.md` |
| W3Schools HTML Tutorial | External | [www.w3schools.com/html](https://www.w3schools.com/html/) |
| W3Schools Tryit Editor | External | [Tryit Editor](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_default) |
| CodePen | External | [codepen.io](https://codepen.io/) |

### Recommended YouTube Tutorials
- **freeCodeCamp** — "HTML Full Course for Beginners" (free, comprehensive, project-based)
- **The Net Ninja** — "HTML & CSS Crash Course" playlist (short, well-organized videos)
- **SuperSimpleDev** — "HTML & CSS Full Course – Beginner to Pro" (step-by-step)
- **Traversy Media** — "HTML Crash Course For Absolute Beginners" (clear, practical)

## Lesson Flow (80 minutes)

| Time | Activity | Details |
|------|----------|---------|
| 0–5 min | **Warm-Up** | "You've been using HTML playbooks for weeks — today you learn what's under the hood!" Quick poll: who has ever right-clicked and hit "View Source" on a website? |
| 5–15 min | **What is HTML?** | Walk through the presentation: HTML = skeleton of a web page. Analogy: labeled boxes. Tags, opening/closing. Show the basic HTML document skeleton. |
| 15–25 min | **Common Tags** | Demonstrate headings, paragraphs, links, images, lists. Students follow along in the Playbook Concepts tab. |
| 25–40 min | **Tables Deep Dive** | Tables are the #1 structure data scientists scrape. Walk through the Tables & Scraping tab in the playbook. Build a table together. Connect to Pandas DataFrames. |
| 40–50 min | **Attributes, Divs & the DOM** | Explain `id`, `class`, `href`, `src`. Show `<div>` and `<span>` as containers. Draw the DOM tree. Emphasize: "This is what Beautiful Soup navigates!" |
| 50–60 min | **Inspect & View Source** | Live demo: go to a real website, right-click → Inspect. Find tags, classes, and table structures. Students try it on their own devices. |
| 60–70 min | **Lab Time** | Students work on Lab Exercises 1–4 using CodePen or W3Schools Tryit Editor. Circulate and help. |
| 70–80 min | **Quiz & Wrap-Up** | Students complete the 15-question quiz in the playbook. Screenshot scores for Google Classroom. Preview: "Next week we use Python + Beautiful Soup to extract data from pages like these!" |

## Key Vocabulary

| Term | Definition |
|------|-----------|
| HTML | HyperText Markup Language — the language that structures web page content |
| Tag | A label in angle brackets that defines an element (e.g., `<p>`, `<h1>`) |
| Attribute | Extra information inside an opening tag (e.g., `class="intro"`, `id="header"`) |
| DOM | Document Object Model — the tree structure of an HTML document |
| `id` | A unique identifier for one element on a page |
| `class` | A group label that multiple elements can share |
| Nesting | Placing tags inside other tags (parent–child relationships) |
| Self-closing tag | A tag with no closing pair (e.g., `<br>`, `<img>`, `<hr>`) |
| View Source | A browser feature that shows the raw HTML of any web page |
| Web Scraping | Using code to automatically extract data from web pages |

## Assessment
- **Quiz:** 15 questions (5 HTML Basics, 5 Tags & Structure, 5 Tables & Scraping) — screenshot submission to Google Classroom
- **Lab:** Exercises 1–7 completed in an online HTML editor

## Looking Ahead
- **Week 26:** Web Scraping with Beautiful Soup — students will use Python to programmatically extract data from the HTML structures they learned this week

---

*Python for Data Science is offered by **Learn and Help** ([www.learnandhelp.com](https://www.learnandhelp.com)) — empowering students through technology and service.*
