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

### Important Questions and Answers
1. **What are the basic data types in Python?**  
   Python’s basic data types include integers (`int`), floating-point numbers (`float`), strings (`str`), and booleans (`bool`).
2. **How does `print(f"Hello, {name}")` work?**  
   It uses an f-string to embed the value of `name` directly into the string for formatted output.
3. **Why is type conversion necessary for `input()`?**  
   `input()` returns a string, so conversion (e.g., `int()` or `float()`) is needed for numeric operations to avoid type errors.

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

### Important Questions and Answers
1. **What is the difference between `for` and `while` loops?**  
   A `for` loop iterates over a sequence (e.g., list, range), while a `while` loop runs as long as a condition is `True`.
2. **When is `elif` used?**  
   `elif` is used to check additional conditions after an `if` statement when multiple mutually exclusive conditions exist.
3. **How can you prevent an infinite loop?**  
   Ensure the `while` loop’s condition eventually becomes `False`, often by updating a counter or flag.

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

### Important Questions and Answers
1. **What is a default parameter in a function?**  
   A default parameter has a predefined value (e.g., `greeting="Hello"`) used if no argument is provided.
2. **How does `return` affect a function?**  
   `return` sends a value back to the caller and exits the function; without it, the function returns `None`.
3. **Can a function have no parameters?**  
   Yes, a function can be defined without parameters, e.g., `def say_hello(): print("Hello!")`.

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

### Important Questions and Answers
1. **What is the key difference between a list and a tuple?**  
   Lists are mutable (can be changed), while tuples are immutable (cannot be changed after creation).
2. **How does a set ensure uniqueness?**  
   Sets automatically remove duplicates by storing only unique elements, using hashing internally.
3. **How do you update a dictionary value?**  
   Assign a new value to an existing key, e.g., `student["age"] = 26`.

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

### Important Questions and Answers
1. **What is the role of `__init__` in a class?**  
   `__init__` initializes an object’s attributes when it is created, setting up its initial state.
2. **How does inheritance work in Python?**  
   A child class inherits attributes and methods from a parent class, allowing code reuse and extension (e.g., `Puppy(Dog)`).
3. **What is polymorphism, and how is it shown in the example?**  
   Polymorphism allows different classes to define methods with the same name but different behaviors; `Puppy` overrides `Dog`’s `bark()` method.

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

### Important Questions and Answers
1. **What does the `with` statement do in file handling?**  
   The `with` statement ensures the file is properly closed after operations, even if an error occurs.
2. **What is the difference between `w` and `a` modes?**  
   `w` overwrites the file if it exists, while `a` appends to the existing content.
3. **How can you read a file line by line?**  
   Use `file.readlines()` or iterate with `for line in file:` to read lines individually.

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

### Important Questions and Answers
1. **What is an exception in Python?**  
   An exception is an error that occurs during program execution, which can be caught and handled.
2. **When is the `finally` block executed?**  
   The `finally` block always executes, regardless of whether an exception occurs or not.
3. **Why is catching specific exceptions better than a general `except`?**  
   Specific exceptions (e.g., `ValueError`) allow precise error handling and avoid masking unexpected errors.

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

### Important Questions and Answers
1. **What is a module in Python?**  
   A module is a Python file containing functions, classes, or variables that can be imported and reused.
2. **How do you import a specific function from a module?**  
   Use `from module import function`, e.g., `from math import sqrt`.
3. **What is a package, and how is it structured?**  
   A package is a directory containing modules and a `__init__.py` file, organizing related code.

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

### Important Questions and Answers
1. **How does a decorator enhance a function?**  
   A decorator wraps a function to add functionality (e.g., logging, timing) before or after its execution.
2. **What is the benefit of using a generator?**  
   Generators yield values one at a time, saving memory compared to storing an entire sequence.
3. **When should you use a list comprehension?**  
   Use list comprehensions for concise creation of lists from iterables when the transformation is simple.
