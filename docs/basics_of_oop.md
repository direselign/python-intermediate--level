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
5) Special Methods (Dunder Methods)
    In Python, special methods, also known as "dunder" (double underscore) methods or magic methods, are used to define how objects of a class behave in various scenarios. They provide a way to customize the behavior of your objects and enable certain language features. These methods are identified by their double underscores at the beginning and end of their names (e.g., __init__, __str__).
    1) `__init__(self, ...)`: the constructor method initializes an object's attributes when it is created.
        ```
        class Person:
            def __init__(self, name, age):
                self.name = name
                self.age = age
        ```
    2) `_str__(self)`: The `__str__` method returns a string representation of an object and is called by the str() function.
        ```
        class Person:
            def __init__(self, name, age):
                self.name = name
                self.age = age

            def __str__(self):
                return f"{self.name}, {self.age} years old"

        ```
    3) `__len__(self)`: The `__len__` method returns the length of an object and is called by the len() function.
        ```
        class Playlist:
            def __init__(self, songs):
                self.songs = songs

            def __len__(self):
                return len(self.songs)
        ```
    4) `__getitem__(self, key)`: The `__getitem__` method allows objects to be accessed using square bracket notation.
        ```
        class Playlist:
            def __init__(self, songs):
                self.songs = songs

            def __getitem__(self, index):
                return self.songs[index]
        ```
    5) `__add__(self, other)`: The `__add__` method defines the behavior of the + operator.
        ```
        class Point:
            def __init__(self, x, y):
                self.x = x
                self.y = y

            def __add__(self, other):
                return Point(self.x + other.x, self.y + other.y)
        ```

Exercises:
```
# 1. Create a class hierarchy for different shapes (circle, rectangle, etc.). Include methods to calculate area and perimeter. Demonstrate inheritance.
# 2. Design a simple library system with classes for books, authors, and library users. Implement methods for checking out and returning books.
# 3. Extend the bank account example to include different account types (e.g., savings account). Use inheritance to share common functionalities.
# 4. Create a class hierarchy for vehicles, including cars, bikes, and trucks. Implement methods to calculate fuel efficiency and demonstrate polymorphism.
# 5. Model a company's employee structure with classes for employees, managers, and executives. Implement methods for calculating salaries and demonstrate encapsulation.
# 6. Create a class representing a 3D vector with x, y, and z components. Implement the __add__ method to allow vector addition.
# 7. Design a class that behaves like a container. Implement __len__ and __getitem__ methods to allow checking the length and accessing elements.
# 8. Create a class that represents a string. Implement a method to reverse the string using the __add__ method.
# 9. Design a class for a 2x2 matrix. Implement the __mul__ method to allow matrix multiplication.
# 10. Build a class that acts as a custom iterator. Implement __iter__ and __next__ methods to iterate over a sequence of elements.
```

OOP is a powerful paradigm that promotes code organization, reusability, and flexibility. These exercises will help you practice designing and implementing class hierarchies, understanding the principles of encapsulation, inheritance, and polymorphism.