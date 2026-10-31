# Introduction to Visual Studio Code (VS Code)

*Prepared for Learn and Help middle and high school students*

VS Code is a free code editor from Microsoft. Programmers around the world use it to write, run, and fix code. In this guide you will install it, set it up, turn on GitHub Copilot (an AI coding helper), and connect it to GitHub so you can do the core loop: **clone → edit → commit → push → pull**.

> **Before you start:** GitHub accounts require you to be at least 13 years old. If you are younger, ask your teacher or a parent about the right way to use GitHub, and do these steps together with an adult.

---

## Table of Contents

1. [What Is VS Code?](#1-what-is-vs-code)
2. [Installing VS Code](#2-installing-vs-code)
3. [A Quick Tour of the Screen](#3-a-quick-tour-of-the-screen)
4. [Configuring VS Code](#4-configuring-vs-code)
5. [Installing Python (Optional)](#5-installing-python-optional)
6. [Installing Git](#6-installing-git)
7. [Signing In to GitHub from VS Code](#7-signing-in-to-github-from-vs-code)
8. [Turning On GitHub Copilot](#8-turning-on-github-copilot)
9. [The Core Loop in VS Code](#9-the-core-loop-in-vs-code)
10. [Using Copilot Responsibly](#10-using-copilot-responsibly)
11. [Troubleshooting](#11-troubleshooting)
12. [Keyboard Shortcuts Cheat Sheet](#12-keyboard-shortcuts-cheat-sheet)
13. [Practice Exercise](#13-practice-exercise)

---

## 1. What Is VS Code?

| Term | Meaning |
|---|---|
| **Code editor** | A program for writing code, with helpful colors and hints |
| **Extension** | An add-on that gives VS Code new abilities (like Python support or Copilot) |
| **Workspace / Folder** | The project folder you have open in VS Code |
| **Terminal** | A text window inside VS Code where you type commands |

VS Code is **not** the same as Visual Studio. VS Code is the lighter, free editor we use here.

---

## 2. Installing VS Code

1. Go to **[code.visualstudio.com](https://code.visualstudio.com)**.
2. Click the **Download** button for your computer (Windows, Mac, or Linux). The site usually detects this automatically.
3. Run the installer.
   - **Windows:** Open the downloaded `.exe` file. Accept the agreement and keep clicking **Next**. On the "Select Additional Tasks" screen, check **Add to PATH** and **Add "Open with Code" action** (these are handy), then click **Install**.
   - **Mac:** Open the downloaded `.zip`, then drag **Visual Studio Code** into your **Applications** folder.
   - **Chromebook / school laptops:** If you can't install programs, ask your teacher. You can also try the browser version at **[vscode.dev](https://vscode.dev)**.
4. Open VS Code. You should see a **Welcome** tab.

---

## 3. A Quick Tour of the Screen

| Area | What it does |
|---|---|
| **Activity Bar** (far left icons) | Switch between Explorer, Search, Source Control, Run, and Extensions |
| **Explorer** | Shows the files and folders in your project |
| **Editor** (center) | Where you write code |
| **Terminal / Panel** (bottom) | Run commands and see program output |
| **Status Bar** (very bottom) | Shows your current branch, errors, and Copilot status |
| **Command Palette** | Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (Mac) and type what you want to do |

**Tip:** If you ever forget how to do something, open the Command Palette and type a few words. It is the most useful tool in VS Code.

---

## 4. Configuring VS Code

### Choose a theme
1. Press `Ctrl+K` then `Ctrl+T` (Mac: `Cmd+K` then `Cmd+T`).
2. Pick a color theme you like. Dark themes are easier on the eyes for many people.

### Make text easier to read
1. Open **Settings**: `Ctrl+,` (Mac: `Cmd+,`).
2. Search for **Font Size** and set it to something comfortable (16 is a good start).
3. Search for **Auto Save** and set it to **afterDelay** so you don't lose work.
4. Search for **Word Wrap** and set it to **on** so long lines don't run off the screen.

### Install helpful extensions
1. Click the **Extensions** icon in the Activity Bar (four squares), or press `Ctrl+Shift+X` (Mac: `Cmd+Shift+X`).
2. Search for each one below and click **Install**:

| Extension | Why you want it |
|---|---|
| **Python** (by Microsoft) | Run and debug Python code |
| **GitHub Copilot** | AI coding helper (see Section 8) |
| **GitHub Pull Requests** | Work with pull requests inside VS Code |
| **Markdown All in One** *(optional)* | Makes writing README files easier |

**Safety tip:** Only install extensions with lots of downloads and a trusted publisher name (like Microsoft or GitHub). Ask your teacher if you are unsure.

---

## 5. Installing Python (Optional)

If your class uses Python, you also need Python itself.

1. Go to **[python.org/downloads](https://www.python.org/downloads/)** and download the latest version.
2. **Windows:** On the first installer screen, check **"Add python.exe to PATH"** before clicking **Install Now**.
3. In VS Code, open the terminal (`` Ctrl+` ``) and test it:

```bash
python --version
```

(On some Mac/Linux computers, use `python3 --version` instead.)

4. Create a file called `hello.py`, type `print("Hello, world!")`, and click the **Run** (triangle) button at the top right.

---

## 6. Installing Git

VS Code uses **Git** behind the scenes to track changes. Check whether you already have it:

```bash
git --version
```

If you see a version number, you're set. If not:

- **Windows:** Download from **[git-scm.com/downloads](https://git-scm.com/downloads)** and accept the default options.
- **Mac:** Type `git --version` in the Terminal and follow the prompt to install developer tools.
- **Linux:** Run `sudo apt install git` (Ubuntu/Debian).

Restart VS Code afterward. Then tell Git who you are (one time only). In the VS Code terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Use the same email you used for your GitHub account. If you want to keep your email private, GitHub offers a private "noreply" email address in **Settings → Emails**.

---

## 7. Signing In to GitHub from VS Code

You need a GitHub account first. If you don't have one, make one at **[github.com](https://github.com)** and turn on two-factor authentication.

1. In VS Code, click the **Accounts** icon (a person) at the bottom of the Activity Bar.
2. Click **Sign in with GitHub** (or **Sign in to Sync Settings**).
3. Your web browser opens. Click **Authorize** and, if asked, sign in to GitHub.
4. Your browser asks to open VS Code. Click **Open**.
5. You should now see your GitHub username under the Accounts icon.

**Never share your password or tokens with anyone,** and never type them into files in your project.

---

## 8. Turning On GitHub Copilot

**GitHub Copilot** is an AI helper that suggests code as you type and can answer questions in a chat window. It is a helper, not a replacement for learning.

### Which plan will I use?

Copilot plans and limits change often, so check **[github.com/features/copilot/plans](https://github.com/features/copilot/plans)** for the latest.

- **Copilot Free:** Available to anyone with a GitHub account. It has monthly limits on code suggestions and chat messages. No payment is needed.
- **Copilot Student:** Verified students can apply through **[GitHub Education](https://education.github.com/students)** for free access to more features. Verification may require a school email or proof of enrollment, and GitHub rechecks eligibility regularly. Ask your teacher if your school can help with this.

Never enter payment details for Copilot unless a parent or guardian has agreed.

### Enable it in VS Code
1. Make sure you are **signed in to GitHub** (Section 7).
2. Open **Extensions** (`Ctrl+Shift+X`), search for **GitHub Copilot**, and click **Install**. (Newer versions of VS Code may already include Copilot. If you see a Copilot icon near the top of the window or in the Status Bar, it is already there.)
3. Click the **Copilot icon** in the Status Bar (bottom right) or the top of the window.
4. If asked, choose **Use Copilot Free** (or your Student plan, if you activated it) and sign in with GitHub.
5. Check the Status Bar. If the Copilot icon has no warning or slash through it, it's working.

### Try it out: inline suggestions
1. Create a file called `practice.py`.
2. Type a comment describing what you want:

```python
# function that returns the square of a number
```

3. Press **Enter** and wait a moment. Gray "ghost text" may appear.
4. Press **Tab** to accept it, or **Esc** to reject it.

### Try it out: Copilot Chat
1. Open Chat: `Ctrl+Alt+I` (Mac: `Ctrl+Cmd+I`), or click the Copilot icon.
2. Ask questions such as:
   - "Explain what this code does in simple words."
   - "Why am I getting this error?"
   - "Give me a hint for how to start, but don't write the whole answer."
3. Select code in your file, right-click, and choose **Copilot → Explain** to get a plain-English explanation.

---

## 9. The Core Loop in VS Code

The core loop is: **Clone → Edit → Commit → Push → Pull**. You can do all of it without typing a single Git command.

### Step 1: Clone (copy a repo to your computer)
1. Press `Ctrl+Shift+P` (Mac: `Cmd+Shift+P`) and type **Git: Clone**.
2. Choose **Clone from GitHub**. Pick one of your repos from the list, or paste a repo URL.
3. Choose a folder on your computer to store it.
4. When asked, click **Open** to open the cloned project.

*Terminal alternative:*
```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
```

### Step 2: Edit
Open a file from the Explorer and make a change. Notice that the file name turns a different color, and the **Source Control** icon (a branch symbol) shows a number badge. That number is how many files have changed.

### Step 3: Commit (save a snapshot)
1. Click the **Source Control** icon in the Activity Bar (or press `Ctrl+Shift+G`).
2. Under **Changes**, click a file to see exactly what you changed (red = removed, green = added).
3. Click the **+** next to a file to **stage** it, or the **+** next to "Changes" to stage everything.
4. Type a short, clear message in the box, such as `Add my name to README`.
   - You can also click the **sparkle icon** in the message box to have Copilot suggest a message. Always read and edit it before using it.
5. Click **Commit**.

### Step 4: Push (send your work to GitHub)
Click **Sync Changes** (or the **...** menu → **Push**). Your commit now appears on GitHub.com.

*Terminal alternative:*
```bash
git add .
git commit -m "Add my name to README"
git push
```

### Step 5: Pull (get the newest changes)
Click **Sync Changes** again, or use the **...** menu → **Pull**. Do this at the start of every work session, especially in group projects.

*Terminal alternative:*
```bash
git pull
```

### Working on a branch
1. Click the **branch name** in the bottom-left of the Status Bar.
2. Choose **Create new branch...** and give it a name like `add-intro-section`.
3. Make your changes, commit, and push. VS Code will ask you to **Publish Branch** the first time.
4. Go to GitHub.com and click **Compare & pull request** to ask for your work to be merged.

### The loop at a glance

```
   Clone ──► Edit ──► Commit ──► Push
     ▲                             │
     └───────────── Pull ◄─────────┘
```

---

## 10. Using Copilot Responsibly

Copilot is powerful, but you are the programmer.

- **Learn first, then ask.** Try to solve the problem yourself before asking Copilot. If you just paste its answer, you won't learn.
- **Read every suggestion.** Copilot can be confidently wrong. Make sure you understand each line before accepting it.
- **Follow your teacher's rules.** Some assignments allow AI help and some don't. When in doubt, ask. Being honest about when you used AI matters.
- **Ask for explanations, not just answers.** Try "Explain this like I'm new to coding" or "Give me a hint."
- **Protect private information.** Don't paste passwords, personal details, or classmates' information into chat.
- **Test your code.** Run it and check that it really does what you wanted.

---

## 11. Troubleshooting

| Problem | Try this |
|---|---|
| "git is not recognized" | Install Git (Section 6), then close and reopen VS Code |
| Can't push: "authentication failed" | Click the Accounts icon, sign out, and sign in to GitHub again |
| Copilot suggestions don't appear | Check you're signed in, look at the Copilot icon in the Status Bar, and try **Developer: Reload Window** from the Command Palette |
| Copilot says you've hit a limit | Free plans have monthly limits. Wait for the reset, or ask your teacher about the Student plan |
| "Please tell me who you are" error | Run the two `git config` commands from Section 6 |
| Python won't run | Make sure the Python extension is installed and pick an interpreter with **Python: Select Interpreter** in the Command Palette |
| Merge conflict | VS Code shows **Accept Current / Accept Incoming / Accept Both** buttons. Read both versions, choose carefully, then commit. Ask for help if you're stuck |

---

## 12. Keyboard Shortcuts Cheat Sheet

| Action | Windows / Linux | Mac |
|---|---|---|
| Command Palette | `Ctrl+Shift+P` | `Cmd+Shift+P` |
| Open Settings | `Ctrl+,` | `Cmd+,` |
| Extensions | `Ctrl+Shift+X` | `Cmd+Shift+X` |
| Source Control | `Ctrl+Shift+G` | `Ctrl+Shift+G` |
| Open Terminal | `` Ctrl+` `` | `` Ctrl+` `` |
| Save file | `Ctrl+S` | `Cmd+S` |
| Quick-open a file | `Ctrl+P` | `Cmd+P` |
| Comment / uncomment line | `Ctrl+/` | `Cmd+/` |
| Undo / Redo | `Ctrl+Z` / `Ctrl+Y` | `Cmd+Z` / `Cmd+Shift+Z` |
| Accept Copilot suggestion | `Tab` | `Tab` |
| Reject Copilot suggestion | `Esc` | `Esc` |

---

## 13. Practice Exercise

Try the whole workflow from start to finish:

1. On GitHub.com, create a new repo called `vscode-practice` with a README.
2. In VS Code, **clone** it using the Command Palette.
3. Create a file called `about_me.py` that prints your name and a fun fact. Try writing a comment first and see what Copilot suggests.
4. Ask Copilot Chat: *"Explain my code line by line."*
5. **Commit** with a clear message.
6. **Push** to GitHub and refresh the page to see your file online.
7. Create a **branch**, change your fun fact, push it, and open a **pull request**.

If you finish all seven steps, you've completed the core loop. Great work!

---

### Helpful Resources

- [VS Code Getting Started](https://code.visualstudio.com/docs/getstarted/introvideos)
- [VS Code and Git/GitHub](https://code.visualstudio.com/docs/sourcecontrol/overview)
- [GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/overview)
- [GitHub Education for Students](https://education.github.com/students)

*Happy coding!*
