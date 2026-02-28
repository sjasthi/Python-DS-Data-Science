# Week 21 --- Kaggle & The Data Science Community

**Course:** Python for Data Science\
**Topics:** Introduction to Kaggle · Exploring Datasets · Learning from
Notebooks · Beginner Competitions

------------------------------------------------------------------------

## Learning Objectives

By the end of this week, students will be able to:

-   Understand what Kaggle is and why it is useful for Data Science
    students
-   Create a Kaggle account and explore datasets
-   Browse and read Kaggle Notebooks (Kernels)
-   Download datasets and use them in Google Colab
-   Understand how beginner competitions work
-   Identify ways to showcase and host their own Data Science projects

------------------------------------------------------------------------

---

## 🏆 Kaggle — Where Data Scientists and ML Practitioners Learn and Compete

### What Is Kaggle?
Kaggle (owned by Google) is the world's largest data science community with over **15 million users**. It's where companies post real-world problems, and data scientists compete to solve them — often for prize money, but always for learning.

### Why You NEED to Know Kaggle

- **Free compute** — GPU/TPU notebooks in the cloud (no local setup needed)
- **10,000+ real-world datasets** — clean, documented, and ready to use
- **Pre-written notebooks** — see how experts approach any problem
- **Competitions** — benchmark yourself against the global ML community
- **Certifications and courses** — free, hands-on ML micro-courses

### 🔍 How to Explore Kaggle (Step-by-Step)

#### Step 1: Create Your Account
1. Go to [https://www.kaggle.com](https://www.kaggle.com)
2. Click **Register** → Sign up with Google or email
3. Complete your profile — add your university and interests

#### Step 2: Explore Datasets
1. Click **Datasets** in the top navigation
2. Search for any topic you're interested in (e.g., `"housing prices"`, `"diabetes"`, `"movies"`)
3. Click a dataset to see:
   - **Overview** tab — what the data means
   - **Data** tab — preview the actual CSV/files
   - **Code** tab — notebooks others wrote using this exact dataset
   - **Discussion** tab — tips, questions, insights from the community

```
💡 Pro Tip: Before building anything from scratch, always check the 
"Code" tab on a Kaggle dataset. You'll find hundreds of notebooks 
showing different approaches to the same problem!
```

#### Step 3: Run Your First Kaggle Notebook
1. Go to **Code** → **New Notebook**
2. You get a free Jupyter-like environment with:
   - 30 hours/week of free GPU
   - Python pre-installed with sklearn, pandas, tensorflow, pytorch
3. Click **+ Add Data** to attach any Kaggle dataset

#### Step 4: Browse Competitions
1. Click **Competitions** in the nav bar
2. Filter by **Getting Started** to find beginner-friendly challenges
3. The legendary **Titanic: Machine Learning from Disaster** is where every ML practitioner starts:
   - [kaggle.com/c/titanic](https://www.kaggle.com/c/titanic)

#### Step 5: Take a Free Course
Kaggle Learn offers bite-sized, free ML courses:
- [kaggle.com/learn](https://www.kaggle.com/learn)
- Recommended path: **Intro to ML → Intermediate ML → Feature Engineering → Intro to Deep Learning**

### 📂 Downloading a Dataset to Use in Google Colab

```python
# Install the Kaggle API
!pip install kaggle

# Upload your kaggle.json API key (from kaggle.com → Account → API → Create New Token)
from google.colab import files
files.upload()  # Upload kaggle.json here

# Set up credentials
!mkdir -p ~/.kaggle
!cp kaggle.json ~/.kaggle/
!chmod 600 ~/.kaggle/kaggle.json

# Download a dataset (example: Titanic)
!kaggle competitions download -c titanic
!unzip titanic.zip

# Now load it
import pandas as pd
df = pd.read_csv('train.csv')
df.head()
```

### 🏅 Kaggle Progression Tiers
Your Kaggle profile has a public ranking system — a great motivation to keep improving:

```
Novice → Contributor → Expert → Master → Grandmaster
```

Reaching **Expert** tier in any category (Competitions, Datasets, Notebooks, or Discussions) is a strong signal to future employers.

------------------------------------------------------------------------

## Activities for This Week

### 1. Create a Kaggle Account

-   Sign up at: https://www.kaggle.com
-   Explore the homepage
-   Update profile (add bio and interests)

### 2. Explore Datasets

Students will: - Visit the Datasets section
- Search for topics they like (sports, video games, movies, climate,
space, animals)
- Preview dataset structure
- Download one dataset

### 3. Explore Notebooks (Kernels)

Students will: - Open a beginner-friendly notebook
- Identify how data is loaded
- Identify how pandas is used
- Identify what visualizations are created
- Write a short summary of what they learned

### 4. Intro to Competitions (Optional & Beginner-Friendly)

Students will: - Explore a "Getting Started" competition
- Understand prediction, leaderboard, and submission

### 5. Mini Project (In Class)

Students will: - Choose one Kaggle dataset\
- Load it into Google Colab
- Perform `.head()` and `.info()`
- Do basic cleaning
- Create one visualization
- Write 3 insights about the data

------------------------------------------------------------------------

## Resources

-   Kaggle Website: https://www.kaggle.com
-   Kaggle Learn Micro-Courses: https://www.kaggle.com/learn
-   Titanic Competition (Example):
    https://www.kaggle.com/competitions/titanic
-   Sample Kaggle Notebooks: https://www.kaggle.com/code
-   Where to get data for DS and ML: https://github.com/sjasthi/Python-DS-Data-Science/blob/main/Where_to_get_data_for_DS_and_ML.pdf

------------------------------------------------------------------------

## Lab (10 pts)

### Part 1 --- Explore (3 pts)

-   Explore kaggle to find a dataset you like
-   Describe what the dataset is about
-   Mention number of rows and columns
-   List column names

### Part 2 --- Analyze (5 pts)

-   Load dataset in Colab
-   Create at least one visualization
-   Write 3 observations

### Part 3 --- Reflect (2 pts)

-   What did you like about Kaggle?
-   What was confusing?
-   Would you try a competition? Why or why not?

------------------------------------------------------------------------

## Assignment (25 pts) – Guest Speaker Seminar

**Speaker:** [Jayanthi Suryanarayana](https://www.linkedin.com/in/jayanthi-suryanarayana-2313841/), Principal AI/ML Solution Engineer at United Health Group

**Topic:** *A Day in the Life of a Data Scientist*

**Date & Time:** March 7th, 8:00 – 9:00 PM CST

### Deliverable
Attend the seminar and submit a 4-slide PowerPoint presentation summarizing your key takeaways.

------------------------------------------------------------------------
## Big Idea of the Week

Data Science is not just coding.\
It is exploring, asking questions, and learning from others.

This week, students move from: Learning Data Science → Being part of the
Data Science community.
