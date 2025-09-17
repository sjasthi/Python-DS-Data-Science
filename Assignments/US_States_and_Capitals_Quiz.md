## Assignment: Python Lists and Dictionaries
## U.S. States and Capitals Quiz Program

**Total Points:** 25  

---

## 🎯 Learning Objectives

By completing this assignment, you will demonstrate your ability to:
- Create and manipulate Python dictionaries effectively
- Use the `random` module for data selection
- Implement user input validation and interaction
- Apply string methods for text processing
- Write clean, well-commented Python code with proper control structures

---

## 📋 Assignment Overview

You will create an interactive quiz program that tests users' knowledge of U.S. state capitals. The program will use dictionaries to store state-capital pairs, randomly select questions, track user performance, and provide feedback on quiz results.

---

## 📚 Part 1: Data Structure Setup (8 points)

### Step 1: Create the States Dictionary (5 points)

Create a dictionary called `states_capitals` containing all 50 U.S. states as keys and their capitals as values. 

**Reference:** [Britannica - U.S. State Capitals](https://www.britannica.com/topic/list-of-state-capitals-in-the-United-States-2119210)

Your dictionary should follow this format:
```python
states_capitals = {
    "Alabama": "Montgomery",
    "Alaska": "Juneau",
    "Arizona": "Phoenix",
    # ... continue for all 50 states
}
```

### Step 2: Data Validation (3 points)

Write code to:
- Print the total number of states in your dictionary
- Print the first 5 states and capitals (alphabetically) to verify your data
- Check that you have exactly 50 state-capital pairs

---

## 🎮 Part 2: Quiz Implementation (12 points)

### Step 1: Random Question Selection (4 points)
- Import the `random` module
- Create a function or code block that randomly selects 5 states from your dictionary
- Ensure no state is repeated in a single quiz session

### Step 2: User Interaction Loop (5 points)
Create a quiz loop that:
- Displays each question in the format: "What is the capital of [State Name]?"
- Accepts user input for each answer
- Handles case-insensitive matching (e.g., "austin" should match "Austin")
- Provides immediate feedback after each question ("Correct!" or "Incorrect. The correct answer is [Capital]")

### Step 3: Score Tracking (3 points)
- Keep track of correct and incorrect responses
- Display the running question number (e.g., "[1]", "[2]", etc.)
- Calculate and display the final score in the format: "Your score is X out of 5"

---

## ✨ Part 3: Program Enhancement (5 points)

### Step 1: Input Validation (2 points)
- Handle empty responses (prompt user to enter an answer)
- Strip whitespace from user inputs
- Handle basic spelling variations where reasonable

### Step 2: Enhanced User Experience (3 points)
- Display a welcome message explaining the quiz
- Show progress during the quiz (question X of 5)
- Provide encouraging feedback based on final score:
  - **5/5:** "Perfect! Excellent knowledge of U.S. geography!"
  - **4/5:** "Great job! You know your state capitals well!"
  - **3/5:** "Good work! You got more than half correct!"
  - **1-2/5:** "Keep studying! You'll improve with practice!"
  - **0/5:** "Don't give up! Review the state capitals and try again!"

---

## 🔧 Implementation Strategy

Follow this recommended approach:

1. **Create the complete dictionary** with all 50 states and capitals
2. **Test your data structure** by printing a few entries
3. **Implement random selection** of 5 states for the quiz
4. **Build the quiz loop** with user input and scoring
5. **Add input validation** and user experience enhancements
6. **Test thoroughly** with different inputs and edge cases

---

## 💻 Sample Program Output

```
================================
Welcome to the U.S. States and Capitals Quiz!
You will be asked about 5 randomly selected states.
================================

[1] What is the capital of Minnesota?
Your answer: St. Paul
Correct!

[2] What is the capital of Texas?
Your answer: Dallas
Incorrect. The correct answer is Austin.

[3] What is the capital of Florida?
Your answer: Disneyland
Incorrect. The correct answer is Tallahassee.

[4] What is the capital of California?
Your answer: San Francisco
Incorrect. The correct answer is Sacramento.

[5] What is the capital of Massachusetts?
Your answer: Boston
Correct!

================================
Quiz Complete!
Your score is 2 out of 5.
Keep studying! You'll improve with practice!
================================
```

---

## 📤 Submission Requirements

### 📁 File Submissions
1. **Python Notebook:** Submit the completed `python_ds_assignment_2.ipynb` file
2. **Output Capture:** Create a text file containing the output from **TWO** complete program runs
   - Run the program twice with different random questions
   - Copy and paste the complete output (including your inputs) into a text file
   - Name the file: `lastname_firstname_quiz_outputs.txt`

### 💻 Code Requirements
1. **File Header:** Include your name, course, date, and assignment description
2. **Comments:** Add clear comments explaining your logic and approach
3. **Variable Names:** Use descriptive variable names
4. **Code Organization:** Structure your code with clear sections for each part
5. **Error Handling:** Include basic input validation

### 📓 Google Colab Notebook Structure
Organize your notebook with these sections:
1. **Introduction Cell** (Markdown) - Explain the assignment
2. **Data Setup** - Dictionary creation and validation
3. **Quiz Implementation** - Main program logic
4. **Testing** - Example runs and verification
5. **Conclusion** (Markdown) - Reflection on the assignment

---

## 📊 Grading Rubric (25 points total)

| Component | Points | Criteria |
|-----------|--------|----------|
| **Dictionary Creation** | 8 | Complete 50-state dictionary, proper format, validation |
| **Quiz Logic** | 7 | Random selection, user interaction, correct flow |
| **Score Tracking** | 5 | Accurate counting, proper display, final results |
| **Code Quality** | 3 | Comments, organization, variable naming |
| **User Experience** | 2 | Input handling, feedback messages, formatting |

### 🎯 Grade Scale
- **23-25 points:** Excellent (A) - All requirements met with high quality
- **20-22 points:** Good (B) - Most requirements met with minor issues
- **17-19 points:** Satisfactory (C) - Basic requirements met
- **Below 17 points:** Needs Improvement (D/F) - Major requirements missing

---

## 💡 Tips for Success

### 🐍 Programming Tips
1. **Start with a small dictionary** (5-10 states) for initial testing
2. **Test random selection** multiple times to ensure it works correctly
3. **Handle case sensitivity** using `.lower()` or `.upper()` methods
4. **Use `random.choice()` or `random.sample()`** for selecting states
5. **Print intermediate values** while debugging your logic

### ⚠️ Common Pitfalls to Avoid
- Forgetting to import the `random` module
- Not handling case sensitivity in user inputs
- Allowing duplicate questions in the same quiz
- Incorrect final score calculation
- Missing input validation for empty responses

### 📓 Jupyter Notebook Tips
- Use markdown cells to document your approach
- Test your code in small chunks before combining
- Include sample outputs in your notebook
- Make sure all cells run successfully from top to bottom

---

## 🚀 Extension Ideas (Optional)

If you finish early, consider these enhancements:
- Add a difficulty level system (easy/medium/hard based on population or region)
- Include multiple choice options instead of free-text input
- Add a timer for each question
- Create a leaderboard system
- Allow users to choose the number of questions

---

## 📞 Getting Help

If you encounter issues:
1. Review the implementation strategy section
2. Check the common pitfalls list
3. Test your code incrementally
4. Use print statements to debug logic
5. Ask questions during office hours

---

**Good luck with your U.S. States and Capitals Quiz Program!** 🇺🇸

---

*Last updated: [Date]*
