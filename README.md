# Python Programming Notes

## 1. Basics
### Explanation
Variables store data and are created upon assignment. Python is dynamically typed, so no type declaration is needed. Data types include integers, floats, strings, and booleans. Input/output functions (`input()`, `print()`) handle user interaction. Operators perform arithmetic, comparison, and logical operations.

### Example Code
```python
# Variables and Data Types
name = "Alice"  # String
age = 25       # Integer
height = 5.6   # Float
is_student = True  # Boolean

# Input/Output
user_name = input("Enter your name: ")
print(f"Hello, {user_name}!")

# Operators
total = age + 10
is_adult = age >= 18
print(f"Age in 10 years: {total}, Adult: {is_adult}")
```

### Output
```
Enter your name: Bob
Hello, Bob!
Age in 10 years: 35, Adult: True
```

### Tips/Pitfalls
- **Tip**: Use descriptive variable names (e.g., `user_age` instead of `x`).
- **Pitfall**: `input()` returns a string; convert to `int` or `float` for numeric operations (e.g., `int(input("Enter age: "))`).

### Quiz
1. What is the data type of `3.14`?
2. What will `print(5 + "3")` cause?
3. How do you convert a user’s input string to an integer?

## 2. Control Flow
### Explanation
Control flow directs program execution using conditionals (`if`, `elif`, `else`) and loops (`for`, `while`) to handle decisions and repetition.

### Example Code
```python
# If-Else
score = 85
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
else:
    grade = "C"
print(f"Grade: {grade}")

# For Loop
for i in range(3):
    print(f"Iteration {i}")

# While Loop
count = 0
while count < 3:
    print(f"Count: {count}")
    count += 1
```

### Output
```
Grade: B
Iteration 0
Iteration 1
Iteration 2
Count: 0
Count: 1
Count: 2
```

### Visual (ASCII)
```
If-Else Flow:
  score >= 90? --> [Yes: A]
         |
         v
  score >= 80? --> [Yes: B]
         |
         v
       [Else: C]
```

### Tips/Pitfalls
- **Tip**: Use `break` to exit loops early, `continue` to skip iterations.
- **Pitfall**: Infinite `while` loops occur if the condition never becomes `False`.

### Quiz
1. What does `elif` stand for?
2. How many times will `for i in range(5):` loop?
3. What happens if a `while` loop’s condition is always `True`?

## 3. Functions
### Explanation
Functions are reusable code blocks that perform specific tasks, defined with `def`. They can take parameters and return values.

### Example Code
```python
# Function Definition
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

# Function Calls
print(greet("Alice"))         # Default greeting
print(greet("Bob", "Hi"))    # Custom greeting

# Function with Multiple Parameters
def add(a, b):
    return a + b
print(add(3, 4))
```

### Output
```
Hello, Alice!
Hi, Bob!
7
```

### Tips/Pitfalls
- **Tip**: Use default parameters for optional arguments.
- **Pitfall**: Forgetting `return` results in `None` as the function’s output.

### Quiz
1. What is the purpose of the `return` statement?
2. What is the output of `greet("Eve", "Hey")` in the example?
3. Can a function have multiple `return` statements?

## 4. Data Structures
### Explanation
Python’s built-in data structures include:
- **Lists**: Ordered, mutable collections.
- **Tuples**: Ordered, immutable collections.
- **Sets**: Unordered, unique elements.
- **Dictionaries**: Key-value pairs.

### Example Code
```python
# List
fruits = ["apple", "banana", "cherry"]
fruits.append("orange")
print(fruits[1])  # Access second item

# Tuple
coords = (10, 20)
print(coords[0])  # Access first item

# Set
unique_nums = {1, 2, 2, 3}
print(unique_nums)  # Duplicates removed

# Dictionary
student = {"name": "Alice", "age": 25}
print(student["name"])  # Access value by key
```

### Output
```
banana
10
{1, 2, 3}
Alice
```

### Visual (ASCII)
```
List: [apple|banana|cherry|orange]
Tuple: (10|20)
Set: {1, 2, 3}
Dict: {name:Alice, age:25}
```

### Tips/Pitfalls
- **Tip**: Use `list.copy()` to avoid modifying the original list when copying.
- **Pitfall**: Tuples are immutable; attempting to change them raises an error.

### Quiz
1. How do you add an item to a list?
2. What makes a set different from a list?
3. How do you access a dictionary value using a key?

## 5. Object-Oriented Programming (OOP)
### Explanation
OOP organizes code into classes and objects. A **class** is a blueprint for objects, which are instances of the class. Key concepts:
- **Attributes**: Data stored in objects.
- **Methods**: Functions defined in a class.
- **Inheritance**: A class can inherit attributes/methods from another.
- **Encapsulation**: Restricting access to certain attributes/methods.
- **Polymorphism**: Different classes can share method names with unique behaviors.

### Example Code
```python
# Class Definition
class Dog:
    # Constructor (Initializer)
    def __init__(self, name, age):
        self.name = name  # Instance attribute
        self.age = age
        self._energy = 100  # Protected attribute

    # Instance Method
    def bark(self):
        return f"{self.name} says Woof!"

    # Method with Encapsulation
    def get_energy(self):
        return self._energy

    def play(self):
        if self._energy >= 10:
            self._energy -= 10
            return f"{self.name} is playing!"
        return f"{self.name} is too tired."

# Inheritance
class Puppy(Dog):
    def bark(self):  # Polymorphism (override)
        return f"{self.name} says Yip!"

# Creating Objects
dog1 = Dog("Max", 5)
puppy1 = Puppy("Buddy", 1)

# Using Objects
print(dog1.bark())
print(puppy1.bark())
print(dog1.play())
print(f"Energy: {dog1.get_energy()}")
```

### Output
```
Max says Woof!
Buddy says Yip!
Max is playing!
Energy: 90
```

### Visual (ASCII)
```
Class Hierarchy:
  Dog
  ├── __init__(name, age)
  ├── bark()
  ├── get_energy()
  └── play()
      |
Puppy (inherits Dog)
  └── bark() [overridden]
```

### Tips/Pitfalls
- **Tip**: Use `_` prefix for protected attributes to signal they shouldn’t be accessed directly.
- **Pitfall**: Overriding a method without calling the parent’s method (use `super()`) can break inheritance logic.
- **Detail**: `__init__` is not a constructor but an initializer; the object is created before `__init__` is called.

### Quiz
1. What is the difference between a class and an object?
2. How does `Puppy` inherit from `Dog` in the example?
3. What is encapsulation, and how is it shown in the `Dog` class?

## 6. File Handling
### Explanation
File handling involves reading from and writing to files using `open()` with modes (`r`, `w`, `a`, etc.).

### Example Code
```python
# Writing to a File
with open("example.txt", "w") as file:
    file.write("Hello, Python!\n")

# Reading from a File
with open("example.txt", "r") as file:
    content = file.read()
print(content)
```

### Output
```
Hello, Python!
```

### Tips/Pitfalls
- **Tip**: Use `with` to automatically close files.
- **Pitfall**: Forgetting to specify the file mode defaults to read (`r`), which fails if the file doesn’t exist.

### Quiz
1. What does the `with` statement do in file handling?
2. What mode is used to append to a file?
3. What happens if you try to read a non-existent file in `r` mode?

## 7. Error Handling
### Explanation
Error handling uses `try`, `except`, `else`, and `finally` to manage exceptions and prevent crashes.

### Example Code
```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ValueError:
    print("Please enter a valid number.")
except ZeroDivisionError:
    print("Cannot divide by zero.")
else:
    print(f"Result: {result}")
finally:
    print("Execution complete.")
```

### Output (if input is `0`)
```
Cannot divide by zero.
Execution complete.
```

### Tips/Pitfalls
- **Tip**: Catch specific exceptions instead of a general `except`.
- **Pitfall**: Overusing `try-except` can hide bugs; use it only for expected errors.

### Quiz
1. What is the purpose of the `finally` block?
2. What exception is raised when dividing by zero?
3. When is the `else` block executed in a `try-except` structure?

## 8. Modules & Packages
### Explanation
Modules are Python files containing reusable code. Packages are directories of modules. Use `import` to access them.

### Example Code
```python
# Importing Built-in Module
import math
print(math.sqrt(16))

# Custom Module (save as mymodule.py)
"""
# mymodule.py
def greet(name):
    return f"Hello, {name}!"
"""
# Importing Custom Module
import mymodule
print(mymodule.greet("Alice"))
```

### Output
```
4.0
Hello, Alice!
```

### Tips/Pitfalls
- **Tip**: Use `import as` for shorter names (e.g., `import numpy as np`).
- **Pitfall**: Circular imports (two modules importing each other) cause errors.

### Quiz
1. How do you import a specific function from a module?
2. What is a package in Python?
3. What happens if you import a non-existent module?

## 9. Advanced Topics
### Explanation
Advanced topics include:
- **Decorators**: Functions that modify other functions.
- **Generators**: Functions that yield values one at a time.
- **Lambda Functions**: Anonymous, single-line functions.
- **Comprehensions**: Concise ways to create lists, sets, or dictionaries.

### Example Code
```python
# Decorator
def my_decorator(func):
    def wrapper():
        print("Before function")
        func()
        print("After function")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()

# Generator
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b
print(list(fibonacci(5)))

# Lambda
square = lambda x: x * x
print(square(4))

# List Comprehension
squares = [x**2 for x in range(5)]
print(squares)
```

### Output
```
Before function
Hello!
After function
[0, 1, 1, 2, 3]
16
[0, 1, 4, 9, 16]
```

### Tips/Pitfalls
- **Tip**: Use generators for memory-efficient iteration over large datasets.
- **Pitfall**: Lambda functions are limited to single expressions; avoid complex logic.

### Quiz
1. What does a decorator do to a function?
2. What keyword is used in a generator to produce values?
3. Write a list comprehension to create a list of even numbers from 1 to 10.
