# Inheritance in Python

## 1. What Is Inheritance?

Inheritance is a fundamental concept in Object-Oriented Programming (OOP) that allows a new class to **reuse** the attributes and methods of an existing class. Think of it like a family tree — a child inherits traits from a parent but can also develop their own unique traits.

| Term              | Also Called       | Meaning                                      |
|-------------------|-------------------|----------------------------------------------|
| **Parent class**  | Base class, Superclass | The class being inherited **from**        |
| **Child class**   | Derived class, Subclass | The class that **inherits**              |

> **Key takeaway:** Inheritance promotes **code reuse** — you write common functionality once in a parent class and share it across multiple child classes.

---

## 2. Why Use Inheritance?

Imagine you're building a school management system. You have `Student`, `Teacher`, and `Staff` — they all share common attributes like `name`, `age`, and `email`. Without inheritance, you'd copy-paste the same code in all three classes. With inheritance, you write it once in a `Person` class and let the others inherit.

**Benefits of Inheritance:**

- **Code Reuse** — Write once, use in many classes
- **Organization** — Group related classes in a logical hierarchy
- **Extensibility** — Add new features in child classes without changing the parent
- **Maintainability** — Fix a bug in one place (parent) and all children benefit

---

## 3. Basic Inheritance Syntax

```python
class Parent:
    # parent attributes and methods
    pass

class Child(Parent):
    # child inherits everything from Parent
    # and can add its own attributes and methods
    pass
```

> **Notice:** The child class includes the parent class name in **parentheses** — `Child(Parent)`. This is how Python knows to inherit.

---

## 4. Your First Inheritance Example — Animals

```python
class Animal:
    def __init__(self, name, sound):
        self.name = name
        self.sound = sound

    def speak(self):
        return f"{self.name} says {self.sound}!"

    def __str__(self):
        return f"Animal: {self.name}"


class Dog(Animal):
    def fetch(self, item):
        return f"{self.name} fetches the {item}!"


class Cat(Animal):
    def purr(self):
        return f"{self.name} is purring..."
```

### Using the classes:

```python
dog = Dog("Buddy", "Woof")
cat = Cat("Whiskers", "Meow")

print(dog.speak())       # Buddy says Woof!
print(dog.fetch("ball")) # Buddy fetches the ball!

print(cat.speak())       # Whiskers says Meow!
print(cat.purr())        # Whiskers is purring...
```

> **What happened?** `Dog` and `Cat` never defined `__init__` or `speak()`, but they **inherited** both from `Animal`. Each child also added its own unique method (`fetch` and `purr`).

---

## 5. The `super()` Function

When a child class needs its **own** `__init__` (to add new attributes), use `super()` to call the parent's `__init__` first — so you don't lose the parent's setup.

```python
class Animal:
    def __init__(self, name, sound):
        self.name = name
        self.sound = sound

    def speak(self):
        return f"{self.name} says {self.sound}!"


class Dog(Animal):
    def __init__(self, name, sound, breed):
        super().__init__(name, sound)   # ← call parent's __init__
        self.breed = breed              # ← add new attribute

    def info(self):
        return f"{self.name} is a {self.breed}"
```

### Using it:

```python
dog = Dog("Buddy", "Woof", "Golden Retriever")

print(dog.speak())   # Buddy says Woof!        ← inherited from Animal
print(dog.info())    # Buddy is a Golden Retriever  ← defined in Dog
print(dog.breed)     # Golden Retriever         ← new attribute
```

> ⚠️ **Common mistake:** Forgetting to call `super().__init__()` inside the child's `__init__`. If you skip it, the parent's attributes (`name`, `sound`) won't be set, and you'll get an `AttributeError`.

---

## 6. Method Overriding

A child class can **replace** (override) a parent's method by defining a method with the **same name**. Python will use the child's version instead of the parent's.

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        return f"{self.name} makes a sound"


class Dog(Animal):
    def speak(self):                        # ← overrides Animal.speak()
        return f"{self.name} says Woof!"


class Cat(Animal):
    def speak(self):                        # ← overrides Animal.speak()
        return f"{self.name} says Meow!"
```

### Using it:

```python
animal = Animal("Generic Animal")
dog = Dog("Buddy")
cat = Cat("Whiskers")

print(animal.speak())   # Generic Animal makes a sound
print(dog.speak())      # Buddy says Woof!
print(cat.speak())      # Whiskers says Meow!
```

> **Key takeaway:** The child's `speak()` **overrides** the parent's `speak()`. Each class can customize its own behavior while sharing the same method name.

---

## 7. The `isinstance()` and `issubclass()` Functions

Python provides two built-in functions to check inheritance relationships:

### `isinstance(object, class)` — Is this object an instance of this class?

```python
dog = Dog("Buddy")

print(isinstance(dog, Dog))      # True  — dog IS a Dog
print(isinstance(dog, Animal))   # True  — dog IS ALSO an Animal (inherited)
print(isinstance(dog, Cat))      # False — dog is NOT a Cat
```

### `issubclass(ChildClass, ParentClass)` — Is this class a child of that class?

```python
print(issubclass(Dog, Animal))   # True  — Dog inherits from Animal
print(issubclass(Cat, Animal))   # True  — Cat inherits from Animal
print(issubclass(Dog, Cat))      # False — Dog does NOT inherit from Cat
print(issubclass(Animal, object))# True  — Every class inherits from object
```

> **Fun fact:** In Python, **every class** inherits from the built-in `object` class — even if you don't write `class Animal(object)`. It's automatic!

---

## 8. Inheritance Chain — Grandparent → Parent → Child

Inheritance can go multiple levels deep:

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def breathe(self):
        return f"{self.name} is breathing"


class Dog(Animal):
    def bark(self):
        return f"{self.name} says Woof!"


class Puppy(Dog):
    def play(self):
        return f"{self.name} is playing!"
```

### Using it:

```python
pup = Puppy("Max")

print(pup.play())      # Max is playing!     ← from Puppy
print(pup.bark())      # Max says Woof!      ← from Dog
print(pup.breathe())   # Max is breathing    ← from Animal
```

> **How it works:** `Puppy` inherits from `Dog`, which inherits from `Animal`. So `Puppy` has access to methods from **all** levels of the chain.

---

## 9. Real-World Example — School System

```python
class Person:
    def __init__(self, name, age, email):
        self.name = name
        self.age = age
        self.email = email

    def introduce(self):
        return f"Hi, I'm {self.name}, age {self.age}"


class Student(Person):
    def __init__(self, name, age, email, student_id, major):
        super().__init__(name, age, email)
        self.student_id = student_id
        self.major = major

    def introduce(self):
        return f"Hi, I'm {self.name}, a {self.major} major (ID: {self.student_id})"


class Teacher(Person):
    def __init__(self, name, age, email, department, years_exp):
        super().__init__(name, age, email)
        self.department = department
        self.years_exp = years_exp

    def introduce(self):
        return f"Hi, I'm {self.name}, {self.department} dept ({self.years_exp} years)"
```

### Using it:

```python
s = Student("Alice", 20, "alice@metro.edu", "S1001", "Computer Science")
t = Teacher("Dr. Smith", 45, "smith@metro.edu", "Math", 15)

print(s.introduce())  # Hi, I'm Alice, a Computer Science major (ID: S1001)
print(t.introduce())  # Hi, I'm Dr. Smith, Math dept (15 years)

# Both still have the shared attributes from Person
print(s.email)        # alice@metro.edu
print(t.email)        # smith@metro.edu
```

---

## 10. What Does a Child Class Inherit?

| Inherited from Parent            | NOT Inherited            |
|----------------------------------|--------------------------|
| Instance methods                 | Private attributes/methods (name-mangled with `__`) |
| Class methods                    | — |
| Static methods                   | — |
| Instance attributes (via `super().__init__()`) | — |
| Class attributes                 | — |

> **Note for Python 101:** All attributes and methods are technically accessible in Python. The `__` (double underscore) prefix triggers *name mangling*, which makes it harder (but not impossible) to access from a child class. We'll keep things simple and focus on standard inheritance.

---

## 11. Common Mistakes to Avoid

### Mistake 1 — Forgetting `super().__init__()`

```python
class Dog(Animal):
    def __init__(self, name, sound, breed):
        # ❌ Forgot super().__init__(name, sound)
        self.breed = breed

dog = Dog("Buddy", "Woof", "Golden Retriever")
print(dog.name)   # AttributeError: 'Dog' object has no attribute 'name'
```

### Mistake 2 — Forgetting the parent class in parentheses

```python
class Dog:                   # ❌ No (Animal) — this is NOT inheritance!
    pass

dog = Dog()
print(isinstance(dog, Animal))   # False — Dog is independent
```

### Mistake 3 — Calling `super()` without parentheses on `__init__`

```python
class Dog(Animal):
    def __init__(self, name, sound, breed):
        super().__init__       # ❌ Missing () — doesn't actually call it!
        self.breed = breed
```

> **Fix:** Always write `super().__init__(args)` — with parentheses on both `super()` and `__init__()`.

---

## 12. Visualizing the Hierarchy

```
        ┌──────────────┐
        │    Animal     │    ← Parent / Base / Superclass
        │  - name       │
        │  - sound      │
        │  + speak()    │
        └──────┬───────┘
               │ inherits
       ┌───────┴────────┐
       │                 │
┌──────┴──────┐   ┌──────┴──────┐
│     Dog     │   │     Cat     │   ← Children / Derived / Subclasses
│  - breed    │   │  + purr()   │
│  + fetch()  │   └─────────────┘
│  + info()   │
└──────┬──────┘
       │ inherits
┌──────┴──────┐
│    Puppy    │   ← Grandchild
│  + play()   │
└─────────────┘
```

---

## 13. Quick Reference — Inheritance Syntax

| Task                          | Syntax                                      |
|-------------------------------|---------------------------------------------|
| Create a child class          | `class Child(Parent):`                      |
| Call parent's `__init__`      | `super().__init__(args)`                    |
| Override a method             | Define same method name in child            |
| Check instance                | `isinstance(obj, ClassName)`                |
| Check subclass                | `issubclass(ChildClass, ParentClass)`       |

---

## 14. Summary

1. **Inheritance** lets a child class reuse attributes and methods from a parent class
2. Use **parentheses** in the class definition to inherit: `class Dog(Animal):`
3. Use **`super().__init__()`** to call the parent's constructor from the child
4. **Method overriding** lets a child replace a parent's method with its own version
5. **`isinstance()`** checks if an object belongs to a class (or its ancestors)
6. **`issubclass()`** checks if one class inherits from another
7. Inheritance can chain multiple levels: Grandparent → Parent → Child
8. Every Python class ultimately inherits from the built-in `object` class

---

*Python 101 | Learn and Help Program | Metropolitan State University*
