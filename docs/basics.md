Review of Basics
----------------
Before diving into advanced Python concepts, let's ensure a strong foundation by reviewing key basics. This includes variables, control flow, functions, and data structures. A solid grasp of these fundamentals is essential for building more complex programs.

Example:
```
# Variables and Data Types
name = "Alice"
age = 25
is_student = False

# Control Flow
if is_student:
    print(f"Hello, {name}! You are a student.")
else:
    print(f"Hello, {name}! You are not a student.")

# Functions
def greet_person(person_name, is_student):
    if is_student:
        return f"Hello, {person_name}! You are a student."
    else:
        return f"Hello, {person_name}! You are not a student."

print(greet_person("Bob", True))

# Lists and Loops
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print(f"I like {fruit}s.")

# Exercise:
# 1. Create a function to calculate the area of a rectangle given its length and width.
# 2. Use a loop to print the squares of numbers from 1 to 5.
# 3. Create a dictionary representing a person with keys for name, age, and profession.
```