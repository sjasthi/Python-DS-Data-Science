# Assignment: Build Your Portfolio with GitHub, VS Code, and GitHub Copilot

**Program:** Learn and Help — Python for Data Science  
**Points:** 25  
**Due date:** As announced by the instructor  
**Work type:** Individual

## Your Mission

Build and publish your own profile/portfolio website at **https://YOUR-USERNAME.github.io/**. Use **Visual Studio Code (VS Code)** to create and edit your files, **GitHub** to track and share your work, and **GitHub Copilot (GHCP)** to help you build, understand, and improve your website.

Your portfolio is a practical application: it introduces you, showcases what you are learning, and gives visitors a way to explore your projects. You can keep improving it throughout the course.

## Learning Objectives

By completing this assignment, you will be able to:

- Explain the different roles of Git, GitHub, VS Code, GitHub Copilot, and GitHub Pages.
- Create a repository and practice **clone → edit → commit → push → pull**.
- Use Copilot to ask focused questions, generate or improve code, and explain suggestions.
- Build a personalized website using HTML and CSS.
- Publish a working website with GitHub Pages and test it.
- Showcase a Python or data science project and reflect on your learning.

## References and Inspiration

Read these class guides before starting:

1. [Introduction to GitHub](../Presentations/introduction_to_github.md)
2. [Introduction to VS Code](../Presentations/introduction_to_vscode.md)

Explore these example portfolios:

- [Anushka's website](https://anushka05012.github.io/)
- [Esha's website](https://eshaandhavala.github.io/)

Notice how portfolios introduce their owners, organize information, and showcase projects. Use these sites for inspiration; write your own content and create a design that represents you.

Additional help:

- [GitHub Pages quickstart](https://docs.github.com/en/pages/quickstart)
- [Set up GitHub Copilot in VS Code](https://code.visualstudio.com/docs/setup/copilot)

## Before You Start

- Install VS Code and Git, and sign in to GitHub from VS Code using the class guides.
- Enable GitHub Copilot in VS Code using an available eligible plan. A paid subscription is not required for this assignment. If access or usage limits block you, contact the instructor for an alternative before submitting.
- GitHub requires users to meet its minimum age requirement, including being at least 13. If you are not eligible, speak with the instructor and a parent/guardian about an approved alternative; do not create an account with a false age.
- Your website and its public repository are visible to everyone. Use only information you and your parent/guardian are comfortable sharing. A first name or appropriate display name is enough. A personal photograph and public email address are optional.
- Never publish passwords, tokens, home addresses, phone numbers, exact daily schedules, or private information about yourself or others. Use GitHub's noreply email for commits if you want to keep your email private.

## Part 1: Set Up Your Repository and VS Code (5 points)

1. Create a **public** GitHub repository named exactly **YOUR-USERNAME.github.io**, replacing `YOUR-USERNAME` with your actual GitHub username.
   - Example: username `studentcoder` → repository `studentcoder.github.io`.
   - If you already have this repository, improve your existing portfolio for this assignment.
2. Initialize it with a `README.md`.
3. In VS Code, open the Command Palette and choose **Git: Clone**. Paste your repository URL, choose a local folder, and open the cloned folder.
4. Create these files in the repository's top-level folder:

| File | Purpose |
|---|---|
| `index.html` | The home page and portfolio content |
| `style.css` | Colors, spacing, typography, and layout |
| `README.md` | Project description, website URL, and local preview instructions |
| `learning_log.md` | Copilot use, testing notes, and reflection |

5. Use VS Code's Source Control panel or integrated terminal to stage, commit, and push your work.
6. Make **at least three meaningful commits during this assignment**, showing actual progress. Examples: `Create portfolio structure`, `Add project showcase and styling`, and `Fix navigation and improve mobile layout`.
7. Practice **Pull** from VS Code at the start of a later work session. Pull downloads remote changes; push uploads your local commits.

**Evidence:** A screenshot showing your project open in VS Code and a link to your repository's commit history. Review screenshots for private information before submitting.

## Part 2: Build Your Personal Portfolio (10 points)

Create a complete, personalized portfolio. A single page with clearly labeled sections is enough.

### Required Content

| Section | What to include |
|---|---|
| **Welcome / Introduction** | Your first name or display name, a short headline, and a welcoming introduction |
| **About Me** | A short paragraph about your interests, hobbies, or learning goals |
| **Skills / What I Am Learning** | At least four skills or tools, such as Python, pandas, data visualization, GitHub, or VS Code; describe your experience honestly |
| **Projects** | At least two project entries, including at least one Python or data science project |
| **Learning / Community Goals** | A short statement about what you want to learn next or how you hope to use technology to help others |

For **each project entry**, include:

- A project title and a description of the problem or purpose.
- The tools or technologies used.
- What you learned or contributed.
- At least one working link to its code, notebook, demo, or other project artifact that the instructor can access.

You may use class exercises or projects you have already completed. Your portfolio itself may count as the second project. If a linked repository is private, arrange instructor access.

### Required Design and Usability

- Include navigation links that jump to your page's sections.
- Link `style.css` from `index.html` and use it to personalize your design.
- Make the page readable on both a computer and a narrow/mobile screen.
- Use clear headings, readable font sizes, sufficient text contrast, and meaningful link labels.
- If you use images, provide descriptive alternative text and use images you own or have permission to use.
- Remove placeholder text and check spelling.
- Include a working link to your GitHub profile.

**Scope:** Plain HTML and CSS are sufficient. JavaScript is optional. You do not need a custom domain, paid hosting, a database, or a contact form. GitHub Pages hosts static files; it does not run a Python server. Link to your Python notebooks or repositories rather than expecting Python code to execute on the website.

## Part 3: Use GitHub Copilot and Document Your Learning (5 points)

Use **GitHub Copilot inside VS Code** for at least **three purposeful interactions** while building your portfolio. Include:

1. **Build:** Ask for help creating or improving a small part of the website.
2. **Understand:** Ask Copilot to explain a piece of HTML or CSS.
3. **Improve or troubleshoot:** Ask for help fixing an issue, improving readability, or making the layout work on mobile.

Example prompts you can adapt:

> Help me create a beginner-friendly HTML structure for a student portfolio with About Me, Skills, and Projects sections. Explain the purpose of each section. Use placeholders instead of inventing facts about me.

> Explain how the navigation links connect to section IDs in my HTML.

> My project cards overflow on a narrow screen. Help me identify the CSS causing this and explain a simple fix.

In `learning_log.md`, document each interaction:

| Prompt or question | What Copilot suggested | What I accepted, changed, or rejected | How I checked it |
|---|---|---|---|
| Your actual prompt | Brief summary | Your decision and reason | Test or observation |

Then write a **150–250 word reflection** answering:

- How do GitHub, VS Code, Copilot, and GitHub Pages each help you build an application?
- What was one challenge, and how did you solve it?
- What is one piece of code you can now explain in your own words?
- What would you improve next?

**AI expectations:** Copilot assistance is encouraged. Read its suggestions, personalize the result, and test every change. Be ready to explain your own files and demonstrate a small edit. Do not submit an unchanged AI-generated site or copy another student's portfolio. Credit any templates, tutorials, or borrowed assets in your README.

## Part 4: Publish, Test, and Submit (5 points)

### Publish with GitHub Pages

1. Push your website files to the `main` branch. Confirm `index.html` is in the top-level folder.
2. On GitHub, open your portfolio repository's **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Choose **main** and **/ (root)**, then save.
5. Wait for deployment, then open **https://YOUR-USERNAME.github.io/**. Publishing can take several minutes.
6. After the first deployment, make one improvement in VS Code, commit and push it, and confirm that the live site updates. This can be one of your three required commits.

### Test Your Website

Record brief results in `learning_log.md`:

- [ ] The live URL opens in a private/incognito browser window without signing in.
- [ ] All required sections are present and contain your own content.
- [ ] Navigation, GitHub profile, and project links work.
- [ ] The page is readable on a desktop and at a narrow/mobile width.
- [ ] Images, if used, load correctly and have alternative text.
- [ ] Your latest change appears on the published site.
- [ ] The public website, repository, and screenshots contain no private information.

If you get a 404, check the repository name, Pages branch/folder settings, and the spelling and location of `index.html`. Check the repository's **Actions** tab for deployment failures. For missing images or styles, check relative paths and capitalization.

### What to Submit

Submit the following through the instructor's designated assignment submission channel:

1. **Live portfolio URL:** `https://YOUR-USERNAME.github.io/`
2. **Source repository URL:** `https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io`
3. **Commit history URL:** Open your repository's commit history and copy its link.
4. **Learning log link:** Link to `learning_log.md` in your repository.
5. **Two screenshots:** Your project open in VS Code, and your published website in a browser.

Your README must include a short project description, live website link, local preview instructions (for example, open `index.html` in a browser), and credits if applicable. If you already had a portfolio, also summarize your new improvements in the learning log and identify the assignment commits.

## Grading Rubric — 25 Points

| Category | Criteria | Points |
|---|---|---:|
| **GitHub and VS Code workflow** | Correct repository and required files (2); at least three meaningful assignment commits made through the VS Code workflow, pull practice, and VS Code evidence (3) | **5** |
| **Portfolio content** | All five required sections with personalized content (3); two project entries with required details and working artifact links, including a Python/data science project (3) | **6** |
| **Design and usability** | Working section navigation and GitHub profile link (1); personalized external CSS (1); readable desktop/mobile layout (1); clear headings, contrast, meaningful links, and image alt text where applicable (1) | **4** |
| **Copilot and reflection** | Three documented purposeful Copilot interactions covering build, understand, and improve/troubleshoot (3); thoughtful 150–250 word reflection demonstrating understanding (2) | **5** |
| **Publishing, testing, and submission** | Working public GitHub Pages site and verified update after publishing (2); completed testing notes (1); complete submission evidence and README (2) | **5** |
| **Total** | | **25** |

Partial credit is available for completed work in each category. Visual complexity is not required: a simple, readable portfolio that you understand and can maintain can earn full credit.

## Optional Extensions — No Additional Points

- Add a light/dark theme toggle.
- Add a small data visualization from one of your projects.
- Create a project filter or another useful JavaScript interaction.
- Feature a project that addresses a school or community need.

**Build something that represents you—and that you can keep growing as you learn!**
