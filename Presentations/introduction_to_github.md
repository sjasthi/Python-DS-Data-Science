# GitHub Introduction for Students

*Prepared for Learn and Help students*

Welcome! This guide covers the basics of GitHub so you can store your code, track your work, and collaborate with others. You do not need any prior experience.

---

## Table of Contents

1. [Git vs. GitHub](#1-git-vs-github)
2. [Key Vocabulary](#2-key-vocabulary)
3. [Setting Up](#3-setting-up)
4. [Your First Repository](#4-your-first-repository)
5. [The Core Workflow](#5-the-core-workflow-clone-edit-commit-push-pull)
6. [Branches](#6-branches)
7. [Pull Requests](#7-pull-requests)
8. [Forking](#8-forking)
9. [README Files and Markdown](#9-readme-files-and-markdown)
10. [Issues](#10-issues)
11. [Privacy and Security](#11-privacy-and-security)
12. [Common Commands Cheat Sheet](#12-common-commands-cheat-sheet)
13. [Tips and Next Steps](#13-tips-and-next-steps)

---

## 1. Git vs. GitHub

| | Git | GitHub |
|---|---|---|
| **What it is** | A version-control tool | A website that hosts Git projects |
| **Where it runs** | On your computer | Online |
| **What it does** | Tracks changes to your files | Backs up, shares, and helps teams collaborate |

Think of Git as the "save history" engine and GitHub as the place where you keep a copy online.

---

## 2. Key Vocabulary

| Term | Meaning |
|---|---|
| **Repository (repo)** | A project folder that holds your files and their full history |
| **Commit** | A saved snapshot of your work, with a short message |
| **Clone** | Copy a repo from GitHub to your computer |
| **Push** | Send your local commits up to GitHub |
| **Pull** | Download changes from GitHub to your computer |
| **Branch** | A separate line of work, used to try things safely |
| **Merge** | Combine one branch into another |
| **Pull request (PR)** | A request to review and merge your changes |
| **Fork** | Your own copy of someone else's repo |
| **Issue** | A task, bug report, or question attached to a repo |

---

## 3. Setting Up

1. **Create an account** at [github.com](https://github.com). Choose a username you would be comfortable showing to a college or employer.
2. **Turn on two-factor authentication** in *Settings → Password and authentication*.
3. **Install Git** from [git-scm.com](https://git-scm.com/downloads), or install [GitHub Desktop](https://desktop.github.com/) if you prefer a visual app.
4. **Tell Git who you are** (one time only):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## 4. Your First Repository

1. On GitHub, click the **+** in the top-right corner and choose **New repository**.
2. Give it a name such as `my-first-repo`.
3. Choose **Public** or **Private**.
4. Check **Add a README file**.
5. Click **Create repository**.

You now have a project online.

---

## 5. The Core Workflow: Clone, Edit, Commit, Push, Pull

```bash
# 1. Copy the repo to your computer
git clone https://github.com/YOUR-USERNAME/my-first-repo.git
cd my-first-repo

# 2. Make changes to your files, then check what changed
git status

# 3. Stage the changes you want to save
git add .

# 4. Save a snapshot with a clear message
git commit -m "Add my name to the README"

# 5. Send it to GitHub
git push

# Later: get the newest changes from GitHub
git pull
```

**Good commit messages** are short and say what changed: "Fix typo in README" is better than "stuff."

---

## 6. Branches

A branch lets you work on something without touching the main version of your project.

```bash
git switch -c my-new-feature   # create and move to a new branch
# ...make changes, add, commit...
git push -u origin my-new-feature
git switch main                # go back to the main branch
```

When your work is ready, you merge it into `main`, usually through a pull request.

---

## 7. Pull Requests

A pull request says: *"I made changes on my branch. Please review them and merge them in."*

1. Push your branch to GitHub.
2. Click **Compare & pull request** on the repo page.
3. Write a short title and description of what you changed.
4. Teammates review, comment, and approve.
5. Click **Merge pull request**.

---

## 8. Forking

Use a fork when you want to change a project you do not own.

1. Click **Fork** at the top-right of the repo.
2. Clone *your* fork to your computer.
3. Make changes on a branch and push them.
4. Open a pull request back to the original repo.

---

## 9. README Files and Markdown

Your `README.md` is the front page of your project. A good README includes:

- **What** the project does
- **How** to run it
- **Who** made it

It is written in **Markdown**, a simple formatting language:

```markdown
# Big Heading
## Smaller Heading
**bold**  *italic*
- bullet item
[link text](https://example.com)
`inline code`
```

---

## 10. Issues

Issues work like a shared to-do list. Use them to:

- Report bugs
- Suggest features
- Assign tasks to teammates
- Track what is done (close the issue when finished)

Tip: mention an issue in a commit message, such as `Fix login bug, closes #3`, and GitHub will close it automatically when merged.

---

## 11. Privacy and Security

- **Never commit** passwords, API keys, tokens, or personal information. Deleted commits can often still be recovered.
- Use a **`.gitignore`** file to keep private or unnecessary files out of your repo.
- Use a **strong, unique password** and keep **two-factor authentication** on.
- Check whether a repo is **public** or **private** before you push.
- Remember that a public repo is visible to everyone, including future schools and employers.

---

## 12. Common Commands Cheat Sheet

| Command | What it does |
|---|---|
| `git clone <url>` | Copy a repo to your computer |
| `git status` | See what has changed |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save a snapshot |
| `git push` | Upload commits to GitHub |
| `git pull` | Download the latest changes |
| `git switch -c <name>` | Create and switch to a new branch |
| `git switch <name>` | Switch to an existing branch |
| `git log --oneline` | View commit history |
| `git diff` | See exactly what changed |

---

## 13. Tips and Next Steps

- **Commit often.** Small, frequent commits are easier to understand and undo.
- **Pull before you push** when working with a team.
- **Try GitHub Desktop** if the command line feels unfamiliar.
- **Pin your best projects** on your profile so it works as a portfolio.
- **Apply for the [GitHub Student Developer Pack](https://education.github.com/pack)** for free tools and benefits.
- **Ask for help.** Everyone gets stuck on Git at first, including professionals.

### Practice Exercise

1. Create a new repo called `hello-github`.
2. Clone it to your computer.
3. Edit the README to add your name and one thing you want to learn.
4. Commit and push your change.
5. Create a branch, make another change, and open a pull request.

### Helpful Resources

- [GitHub Docs: Hello World](https://docs.github.com/en/get-started/start-your-journey/hello-world)
- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [Learn Git Branching (interactive)](https://learngitbranching.js.org/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)

---

*Happy coding!*
