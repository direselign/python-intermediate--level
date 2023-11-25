Introduction to Object-Oriented Programming (OOP)
-------------------------------------------------
Object-Oriented Programming (OOP) is a paradigm that organizes code into reusable and structured components called objects. In Python, everything is an object, and understanding OOP principles can significantly enhance code organization and maintainability.

1) Classes and Objects:
    - A class is a blueprint for creating objects. Objects are instances of a class.
    - Classes encapsulate data (attributes) and behavior (methods).
    ```
    # Example of a simple class
    class Dog:
        def __init__(self, name, age):
            self.name = name
            self.age = age

        def bark(self):
            print(f"{self.name} says Woof!")

    # Creating an object
    my_dog = Dog("Buddy", 3)

    # Accessing attributes and calling methods
    print(my_dog.name)
    my_dog.bark()
    ```
2) Encapsulation:
    - Encapsulation is the bundling of data and methods that operate on the data within a single unit (class).
    - It helps hide the internal implementation details and exposes only what's necessary.
    ```
    class BankAccount:
        def __init__(self, balance):
            self._balance = balance  # _ indicates a protected attribute

        def deposit(self, amount):
            self._balance += amount

        def withdraw(self, amount):
            if amount <= self._balance:
                self._balance -= amount
            else:
                print("Insufficient funds.")
    ```
3) Inheritance:
    - Inheritance allows a class (subclass) to inherit the attributes and methods of another class (base class).
    - It promotes code reuse and establishes an "is-a" relationship between classes.
    ```
    class Animal:
        def __init__(self, name):
            self.name = name

        def make_sound(self):
            pass

    class Dog(Animal):
        def make_sound(self):
            print("Woof!")

    class Cat(Animal):
        def make_sound(self):
            print("Meow!")
    ```
4) Polymorphism:
    - Polymorphism allows objects of different classes to be treated as objects of a common base class.
    - It enables a single interface for different types of objects.
    ```
    def animal_sound(animal):
        animal.make_sound()

    my_dog = Dog("Buddy")
    my_cat = Cat("Whiskers")

    animal_sound(my_dog)  # Output: Woof!
    animal_sound(my_cat)  # Output: Meow!
    ```

Exercises:
```
# 1. Create a class hierarchy for different shapes (circle, rectangle, etc.). Include methods to calculate area and perimeter. Demonstrate inheritance.
# 2. Design a simple library system with classes for books, authors, and library users. Implement methods for checking out and returning books.
# 3. Extend the bank account example to include different account types (e.g., savings account). Use inheritance to share common functionalities.
# 4. Create a class hierarchy for vehicles, including cars, bikes, and trucks. Implement methods to calculate fuel efficiency and demonstrate polymorphism.
# 5. Model a company's employee structure with classes for employees, managers, and executives. Implement methods for calculating salaries and demonstrate encapsulation.
```

OOP is a powerful paradigm that promotes code organization, reusability, and flexibility. These exercises will help you practice designing and implementing class hierarchies, understanding the principles of encapsulation, inheritance, and polymorphism.