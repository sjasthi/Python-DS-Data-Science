# 🗺️ Pathways to Success: A Data-Driven Study of Student Opportunities Across America

**Learn and Help | [www.learnandhelp.com](https://www.learnandhelp.com)**  
**Python for Data Science — Final Project | Class of 2026**  
**Academic Year: 2025–2026**

---

## Project Overview

In this final project, you will work on a comprehensive study of opportunities for middle and high school students across the United States. Each student is assigned a set of U.S. states for data review and enrichment. Collectively, the class will cover all 50 states.

A **starter dataset of approximately 850 programs** has already been collected and will be provided to you as an Excel file. Your job is to:

1. **Review** the existing data for your assigned states — check for accuracy, completeness, and quality
2. **Enrich** the dataset by adding any missing programs, opportunities, or corrections
3. **Analyze** the complete dataset to answer all 25 research questions
4. **Present** your findings to the class in a clear, professional format

---

## Project Goal

By the end of this project, we will have a polished, nationwide dataset of student opportunities — verified and enriched by the whole class working together. This project will develop your data collection, cleaning, analysis, and visualization skills, and produce insights that are genuinely valuable for educators, students, and parents across the country.

---

## 📋 State Assignments

50 states are divided across 8 students. Each student reviews existing data and adds new programs for their assigned states.

| # | Student | Assigned States | # States |
|---|---|---|---|
| 1 | **Amaira Srivastava** | Alabama, Alaska, Arizona, Arkansas, California, Colorado | 6 |
| 2 | **Ayush** | Connecticut, Delaware, Florida, Georgia, Hawaii, Idaho | 6 |
| 3 | **Bhargav Kodali** | Illinois, Indiana, Iowa, Kansas, Kentucky, Louisiana | 6 |
| 4 | **Dakshin Gorugantu** | Maine, Maryland, Massachusetts, Michigan, Minnesota, Mississippi | 6 |
| 5 | **Eesha Gorugantu** | Missouri, Montana, Nebraska, Nevada, New Hampshire, New Jersey | 6 |
| 6 | **Eli Muthyala** | New Mexico, New York, North Carolina, North Dakota, Ohio, Oklahoma | 6 |
| 7 | **Lakshya Sri** | Oregon, Pennsylvania, Rhode Island, South Carolina, South Dakota, Tennessee, Texas | 7 |
| 8 | **Saketh Gorugantu** | Utah, Vermont, Virginia, Washington, West Virginia, Wisconsin, Wyoming | 7 |

> **All students** should also identify **2–3 national programs** (programs available across all states) to add to the shared dataset under the state value `USA`.

---

## 25 Research Questions

You must answer **all 25 questions** as part of your final project. Use the combined class dataset (all 50 states) for your analysis.

| # | Research Question |
|---|---|
| 1 | What types of opportunities (STEM, Arts, Sports, Leadership, etc.) are most common across U.S. states? |
| 2 | Which states offer the highest number of programs for middle and high school students? |
| 3 | Which states provide the most free or funded opportunities vs. fee-based programs? |
| 4 | Are there regional differences (e.g., East Coast vs. Midwest vs. West Coast) in the types of opportunities offered? |
| 5 | What is the average cost of participation across programs? |
| 6 | Do states with larger populations (California, Texas, New York, etc.) offer proportionally more programs? |
| 7 | Which grade levels (middle school vs. high school) have more opportunities? |
| 8 | Are application deadlines evenly distributed through the year, or clustered in certain months? |
| 9 | Which states provide unique flagship programs (e.g., Governor's STEM Challenge, Junior Olympics)? |
| 10 | How do programs vary in focus — academic enrichment vs. sports vs. arts vs. leadership? |
| 11 | Which states offer more state-funded vs. privately-funded opportunities? |
| 12 | Are there correlations between eligibility requirements (GPA, residency, essays) and the prestige of programs? |
| 13 | How accessible are these opportunities for rural vs. urban students? |
| 14 | Are there gaps in opportunities for certain categories (e.g., few arts programs compared to STEM)? |
| 15 | Which programs are national in scope but administered at the state level (e.g., Science Olympiad)? |
| 16 | What recommendations can we make to educators and policymakers to increase student access? |
| 17 | What percentage of opportunities are available inside schools vs. requiring outside effort? |
| 18 | Do certain states lean more heavily on external university or organization programs? |
| 19 | Are scholarship opportunities mainly accessed outside school systems? |
| 20 | Which types of opportunities dominate each state? |
| 21 | Which fields are underrepresented (e.g., lots of STEM but few Arts)? |
| 22 | Are most competitions outside school? Are most scholarships tied to academics or sports? |
| 23 | Do certain fields (Math, Science, Arts, Sports, Leadership, etc.) correlate with higher availability of scholarships compared to clubs or competitions? |
| 24 | How do state-level opportunities compare with national programs in terms of accessibility, prestige, and participation rates? |
| 25 | What additional question do **you** want to ask and answer from the dataset? (Student-designed question) |

---

## Implementation Phases

The project is divided into five phases, each worth **25 points** (total: **125 points**).

---

### Phase 1: Data Review & Enrichment *(25 points)*

**Starter Dataset:** A shared Excel file with approximately 850 programs across all 50 states will be provided by your instructor.

**Your Task:**

For your assigned states:
- [ ] Open the starter Excel file and filter to your assigned states
- [ ] Review each existing row for accuracy — check program names, websites, costs, deadlines, and categories
- [ ] Fix any errors or missing fields you find
- [ ] Add **new programs** not already in the dataset:
  - Minimum **3–5 new programs per state** (if not already covered)
  - At least **one flagship statewide program** per state (e.g., Governor's STEM Challenge, State Science Fair)
  - **2–3 national programs** under state = `USA`
- [ ] Verify that all website links are working and accurate

**Data Fields to Complete (for any new rows you add):**

| Field | Description | Valid Values / Examples |
|---|---|---|
| **State** | Name of state or USA (if national) | Alabama, Texas, Minnesota … or USA |
| **Program / Opportunity Name** | Official title of the opportunity | DECA, HOSA, UMTYMP, Governor's STEM Challenge, National Merit Scholarship |
| **Grade Levels** | Grade range of eligibility | 6–8, 9–12, 7–12, "Middle School," "High School," or specific (e.g., 11th–12th only) |
| **Eligibility Requirements** | Criteria for participation | Residency (MN only), GPA (3.0+), application, essay, audition, minority status, open to all |
| **Cost / Funding** | Cost to participate and how it's funded | Free, $50 membership fee, scholarship-supported, school-funded, privately-funded |
| **Deadlines** | Application / registration deadlines | "Oct 15," "Spring Semester," "Rolling admission," "Varies by chapter" |
| **Website / Link** | Official program webpage or reliable source | URL (must be a working link) |
| **Category (Type)** | Defines the form of the opportunity | Club, Scholarship, Competition, Volunteer/Service, Academic Program, Other |
| **Field (Area of Focus)** | Subject or domain of the opportunity | Math, Science, Technology, Coding, Arts, Sports, Leadership, Business, Health, Medicine, Multidisciplinary |
| **Delivery Context** | How students access the opportunity | At School, Through School, Outside School |
| **Notes** | Extra details or context | Prestige (national vs. state-level), selective admission, travel required, online vs. in-person, special benefits (stipends, college credit) |

**Category Reference:**

- **Club** — DECA, HOSA, Math Club, NHS
- **Scholarship** — academic, sports, minority-based
- **Competition** — hackathon, Olympiad, data science contest
- **Volunteer / Service** — community volunteering, NHS service projects
- **Academic Program** — PSEO, CIS, AP, UMTYMP
- **Other** — anything that doesn't fit above

**Delivery Context Reference:**

- **At School** — school-run programs (DECA, HOSA, NHS)
- **Through School** — facilitated by school but external (PSEO, CIS, AP)
- **Outside School** — independent programs (UMTYMP, external hackathons, private scholarships)

---

### Phase 2: Exploratory Data Analysis — EDA *(25 points)*

Perform basic analysis of the **complete class dataset** (all 50 states combined).

Answer questions such as:
- How many total opportunities are in the dataset?
- Which categories (STEM, Arts, Sports, Leadership) are most common?
- Are opportunities evenly distributed across grade levels?
- Which states have the most / fewest programs?
- What is the breakdown of free vs. paid programs?

**Deliverable:** A Google Colab notebook with:
- Data loading (`pd.read_excel()` or `pd.read_csv()`)
- `.describe()`, `.value_counts()`, `.groupby()` summaries
- Written observations for each finding

---

### Phase 3: Data Visualizations *(25 points)*

Create visualizations to explore and communicate your findings.

**Required Visualizations (minimum 5):**

| Chart Type | Suggested Use |
|---|---|
| Bar chart | Opportunities by category or by state |
| Pie chart | Free vs. paid programs breakdown |
| Horizontal bar | Top 10 states by number of programs |
| Line chart / timeline | Deadlines distributed across months |
| Grouped bar | Middle school vs. high school opportunities by category |

**Bonus visualizations:**
- Choropleth map of program density by state (use `plotly.express`)
- Heatmap of field × delivery context

**Deliverable:** All visualizations included in your Colab notebook with proper titles, axis labels, and color choices.

---

### Phase 4: Data Analysis & Summary *(25 points)*

Conduct deeper analysis guided by all **25 research questions**. For each question:
- Write a short paragraph or bullet-point answer (2–5 sentences)
- Include at least one supporting chart or statistic
- Where applicable, make a **recommendation** for teachers, mentors, parents, students, or policymakers

**Deliverable:** A written summary report (2–3 pages, Google Doc or PDF) addressing all 25 questions.

---

### Phase 5: Final Presentation *(25 points)*

Present your findings to the class and demonstrate what you learned.

**Presentation Must Include:**

- [ ] **Introduction** — What is the Pathways project? What question(s) did you focus on?
- [ ] **Your assigned states** — Summary of what you found / added
- [ ] **Key insights** — Your 3–5 most interesting findings from the full dataset
- [ ] **Visualizations** — Walk through at least 3 charts
- [ ] **Your Question 25** — The question you designed and answered
- [ ] **Recommendations** — What should educators, students, or policymakers do differently?

> 🎯 **Presentation Time:** 7–10 minutes per student  
> 📹 **Format:** Live in-class presentation during Week 30

---

## Submission Requirements

Submit all deliverables through **Google Classroom** by the deadlines on the course schedule.

| # | Deliverable | Format | Notes |
|---|---|---|---|
| 1 | **Enriched Excel File** | `.xlsx` | Your assigned states with reviewed + added rows |
| 2 | **EDA Notebook** | Google Colab `.ipynb` | Phase 2 analysis with summary stats |
| 3 | **Visualizations** | Inside Colab notebook | Minimum 5 charts, labeled and titled |
| 4 | **Analysis & Summary Report** | Google Doc or PDF | All 25 questions answered |
| 5 | **Final Presentation** | Google Slides or PowerPoint | 7–10 minutes, presented in Week 30 |

**File Naming Convention:**  
All submitted files must follow this format:  
`LastName_FirstName_Pathways_[Deliverable].ext`

> Example: `Srivastava_Amaira_Pathways_EDA.ipynb` or `Kodali_Bhargav_Pathways_Report.pdf`

**Late submissions will result in grade deductions. Submit early if possible.**

---

## 🗓️ Project Timeline

| Week | Dates | Milestone |
|---|---|---|
| **Week 27** | Apr 25 – May 1 | Review starter dataset · Identify gaps · Begin data enrichment |
| **Week 28** | May 2 – May 8 | Complete data enrichment · Begin EDA (Phase 2) |
| **Week 29** | May 9 – May 15 | Complete visualizations (Phase 3) · Write analysis report (Phase 4) |
| **Week 30** 🎤 | May 16 – May 22 | **FINAL PRESENTATIONS** |

---

## 💡 Tips for Success

- **Start with the data** — filter the Excel to your states first. Understand what's already there before adding anything.
- **Check the links** — broken website links are one of the easiest things to fix and the most common data quality issue.
- **Think like a middle schooler** — when reviewing programs, ask: "Would a 7th grader in that state know about this? Could they actually apply?"
- **Use pandas to explore** — don't just read the Excel visually. Load it in Colab and run `.value_counts()` on your states to spot gaps quickly.
- **Answer Q25 with something you genuinely find interesting** — the best final projects have one question the student cared about answering.

---

## Grading Summary

| Phase | Description | Points |
|---|---|---|
| Phase 1 | Data Review & Enrichment | 25 |
| Phase 2 | Exploratory Data Analysis | 25 |
| Phase 3 | Data Visualizations | 25 |
| Phase 4 | Data Analysis & Summary (all 25 questions) | 25 |
| Phase 5 | Final Presentation | 25 |
| **Total** | | **125** |

---

*This project is part of the Python DS curriculum at Learn and Help.*  
*© 2026 Learn and Help | [www.learnandhelp.com](https://www.learnandhelp.com)*  
*Questions? Reach out through Google Classroom.*
