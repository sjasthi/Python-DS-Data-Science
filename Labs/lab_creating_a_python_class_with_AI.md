# Lab: Build a Car Class with AI

In this lab you will use an AI assistant (GitHub Copilot https://github.com/copilot  or Claude Code Claude.ai) to help you design, build, test, and explain **one Python class: `Car`**. The goal is not just to get working code, but to understand every line of it well enough to explain it to someone else.

Before starting, review the prompts in [Advanced Exploration of Objects and Classes through AI](exploring_objects_and_classes_advanced.md).

## Learning Objectives

By the end of this lab you will be able to:

- Define a class with attributes and methods
- Use `__init__` to set up an object's starting state
- Write methods that change an object's state, and methods that only check it
- Validate input and handle edge cases
- Use `__str__` to give your objects a readable description
- Create multiple objects from the same class and see that each has its own state

## Step 1: The `Car` Class

| Attribute | Description |
|---|---|
| `make`, `model` | Strings describing the car |
| `mpg` | Miles per gallon |
| `tank_capacity` | Maximum gallons the tank can hold |
| `fuel_level` | Gallons currently in the tank |
| `odometer` | Total miles driven |

| Method | What it should do |
|---|---|
| `fill_gas(gallons)` | Adds fuel to the tank. The tank cannot hold more than `tank_capacity`. |
| `drive(miles)` | Uses fuel based on `mpg` and increases `odometer`. Refuses if there is not enough fuel. |
| `can_drive(miles)` | Returns `True` or `False`. Does **not** change the car. |
| `range_remaining()` | Returns how many more miles the car can go on the current fuel. |
| `__str__()` | Returns a readable summary, e.g. `2020 Honda Civic: 8.5 gal, 12430 mi` |

> Notice the pattern: an **action** method (`drive`), a **check** method (`can_drive`), and a method that **changes state with rules** (`fill_gas`).

## Step 2: Build It with AI

Use the AI to help you write the class. Here are some prompts to get started:

- "Help me create a `Car` class in Python with these attributes: make, model, mpg, tank_capacity, fuel_level, odometer. Explain each line."
- "Now add a `drive` method that uses fuel based on mpg. Explain how it uses `self`."
- "What should happen if someone tries to overfill the tank or drive farther than the fuel allows? Show me how to handle that."
- "Why do we need `self` in every method? Show me what breaks if I leave it out."
- "What is the difference between `__init__` and `__str__`?"
- "Write a short test script that creates two cars and shows they keep separate values."

**Tips**

- Do not just copy and paste. Read the code, run it, then change something and predict what will happen.
- Ask follow-up questions whenever something is unclear, such as "Can you explain that a different way?"
- Run the code after every new method, not just at the end.

## Step 3: Requirements

Your final program must include:

1. A `Car` class with an `__init__` method that sets all attributes
2. At least **5 methods**, including `__str__`, `fill_gas`, `drive`, and `can_drive`
3. **Input validation** that handles at least **2 edge cases** (for example: overfilling the tank, driving farther than the fuel allows, negative miles or gallons)
4. A **test section** at the bottom (using `if __name__ == "__main__":` or a notebook cell) that:
   - Creates at least **2 cars** with different values
   - Calls **every method** at least once
   - Triggers **each edge case** you handled, and shows the result
5. Comments or docstrings explaining what each method does

## Step 4: Reflection

Answer these briefly in a `README.md` or in markdown cells at the end of your notebook. Use your own words.

1. **Class vs. object:** What is the difference between a class and an object? Use `Car` as the example.
2. **A bug you hit:** Describe one error or unexpected result you ran into, what caused it, and how you fixed it.
3. **Your own change:** Describe one change you made to the AI's code on your own, and why.
4. **Prompt log:** List the 5 or more prompts you used, including at least 2 follow-up questions.

## Step 5: What to Submit

Submit through a GitHub repo link or the course upload:

- Your Jupyter notebook (`.ipynb`)
- Your reflection (`README.md` or markdown cells)
- A screenshot or pasted output showing your test section running

Make sure your code runs from top to bottom without errors before you submit.

## Grading Rubric (10 points)

| Criteria | Points |
|---|---|
| Class is correctly defined with `__init__`, attributes, and `__str__` | 2 |
| At least 5 working methods, including `fill_gas`, `drive`, and a non-mutating `can_drive` | 3 |
| Input validation handles at least 2 edge cases correctly | 2 |
| Test section creates 2+ cars, calls every method, and shows edge cases | 1 |
| Reflection is complete, accurate, and in your own words (class vs. object, a real bug, your own change, prompt log) | 2 |
| **Total** | **10** |

## Be Ready to Explain

Your instructor may ask you to run your code and explain what a specific method does, or to make a small change on the spot. If something in your submission is not clear to you, go back and ask the AI to explain it before you turn it in.
