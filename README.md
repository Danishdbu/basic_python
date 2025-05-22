
# Python Programming Notes: Beginner to Advanced

---

## 1. Basics

### Variables
Variables store data values.
```python
x = 5
name = "Alice"
```
**Explanation**: `x` is an integer variable, `name` is a string.

### Data Types
- int: Integer numbers
- float: Decimal numbers
- str: Text
- bool: True or False
```python
age = 25
pi = 3.14
is_active = True
```

### Input / Output
```python
name = input("Enter your name: ")
print("Hello", name)
```
**Output**: Based on user input.

### Operators
- Arithmetic: +, -, *, /, //, %, **
- Comparison: ==, !=, >, <, >=, <=
- Logical: and, or, not
```python
print(5 + 2)      # 7
print(3 > 1 and 4 < 2)  # False
```

### ASCII Chart (Operator Precedence)
```
Highest Priority
----------------
()      Parentheses
**      Exponent
*, /    Multiply/Divide
+,-     Add/Subtract
==,!=   Comparison
and, or Logical
```

### Quiz Questions
1. What is the output of `print(2 ** 3)`?
2. Which data type does `input()` return?
3. What operator is used for integer division?

---

## 2. Control Flow

### If-Else Statements
```python
x = 10
if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

### Loops
#### For Loop
```python
for i in range(3):
    print(i)
```
#### While Loop
```python
count = 0
while count < 3:
    print(count)
    count += 1
```

### Tip:
- Avoid infinite loops: ensure `while` condition eventually becomes false.

### Quiz Questions
1. What is the range of `range(3)`?
2. How do you exit a loop early?
3. What keyword starts a conditional block?

---

## 3. Functions

### Defining and Calling
```python
def greet(name):
    return "Hello " + name

print(greet("Bob"))
```

### Parameters & Return Values
```python
def add(x, y):
    return x + y
```

### Default Arguments
```python
def power(base, exp=2):
    return base ** exp
```

### Quiz Questions
1. What keyword is used to define a function?
2. Can a function return multiple values?
3. What is a default argument?

---

## 4. Data Structures

### Lists
```python
fruits = ["apple", "banana"]
fruits.append("orange")
print(fruits[0])
```

### Tuples
```python
coords = (4, 5)
print(coords[1])
```

### Sets
```python
nums = {1, 2, 3, 3}
print(nums)  # {1, 2, 3}
```

### Dictionaries
```python
person = {"name": "Alice", "age": 25}
print(person["name"])
```

### ASCII Table: Data Structure Properties
```
+-------------+---------+-------------+
| Structure   | Ordered | Mutable     |
+-------------+---------+-------------+
| List        | Yes     | Yes         |
| Tuple       | Yes     | No          |
| Set         | No      | Yes         |
| Dictionary  | Yes     | Yes         |
+-------------+---------+-------------+
```

### Quiz Questions
1. Are sets ordered?
2. How do you access a dictionary value?
3. Can a tuple be changed after creation?

---

## 5. Object-Oriented Programming (OOP)

### Classes and Objects
```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(self.name + " says woof!")

my_dog = Dog("Buddy")
my_dog.bark()
```

### Inheritance
```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Cat(Animal):
    def speak(self):
        print("Meow")
```

### Quiz Questions
1. What method initializes a class?
2. What is inheritance in OOP?
3. What does `self` refer to?

---

## 6. File Handling

### Reading Files
```python
with open("file.txt", "r") as f:
    print(f.read())
```

### Writing Files
```python
with open("file.txt", "w") as f:
    f.write("Hello")
```

### Quiz Questions
1. What does `"r"` mean in file mode?
2. What is the benefit of `with` in file handling?

---

## 7. Error Handling

### Try-Except
```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Can't divide by zero")
```

### Finally Block
```python
finally:
    print("Always runs")
```

### Quiz Questions
1. What block runs regardless of errors?
2. What error is raised for undefined variables?

---

## 8. Modules & Packages

### Importing Modules
```python
import math
print(math.sqrt(16))
```

### Creating a Module
- Save functions in `mymodule.py`
```python
import mymodule
```

### Quiz Questions
1. What keyword is used to include a module?
2. What file extension is used for a module?

---

## 9. Advanced Topics

### Lambda Functions
```python
square = lambda x: x * x
print(square(4))
```

### List Comprehension
```python
squares = [x * x for x in range(5)]
```

### Generators
```python
def count_up(n):
    for i in range(n):
        yield i
```

### Decorators
```python
def decorator(func):
    def wrapper():
        print("Before")
        func()
        print("After")
    return wrapper

@decorator
def greet():
    print("Hello")
```

### Quiz Questions
1. What is the syntax for a lambda function?
2. What does `yield` do?
3. What is a use case for decorators?

---


