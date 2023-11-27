Decorators and Descriptors
---------------------------
Decorators and descriptors are advanced features in Python that provide powerful mechanisms for modifying or extending the behavior of functions and classes, respectively. Understanding these concepts can greatly enhance your ability to write clean, modular, and reusable code.
1) Decorators
    - A decorator is a function that takes another function as an argument and extends or modifies its behavior.
    - Common use cases include logging, timing, authentication, and memoization.
        ```
        def my_decorator(func):
            def wrapper():
                print("Something is happening before the function is called.")
                func()
                print("Something is happening after the function is called.")

            return wrapper

        @my_decorator
        def say_hello():
            print("Hello!")

        say_hello()
        ```
    - Decorator with Arguments:Decorators can take arguments to make them more flexible.
        ```
        def repeat(n):
            def decorator(func):
                def wrapper(*args, **kwargs):
                    for _ in range(n):
                        func(*args, **kwargs)

                return wrapper

            return decorator

        @repeat(3)
        def greet(name):
            print(f"Hello, {name}!")

        greet("Alice")
        ```
    - Built-in Decorators: Python provides built-in decorators such as @property, @staticmethod, and @classmethod for common use cases
        ```
        class MyClass:
            def __init__(self, value):
                self._value = value

            @property
            def value(self):
                return self._value

            @value.setter
            def value(self, new_value):
                self._value = new_value
        ```
2) Descriptors:
    - A descriptor is a class that defines how attributes are accessed and modified in another class.
    - Common descriptors include property, classproperty, and staticmethod.
        ```
        class Square:
            def __init__(self, side):
                self._side = side

            @property
            def side(self):
                return self._side

            @side.setter
            def side(self, value):
                if value < 0:
                    raise ValueError("Side length must be non-negative")
                self._side = value

            @property
            def area(self):
                return self._side ** 2

        ```
    - Custom Descriptors: You can create custom descriptors by implementing the __get__ and __set__ methods.
        ```
        class Celsius:
            def __init__(self, temperature=0):
                self._temperature = temperature

            def to_fahrenheit(self):
                return (self._temperature * 9/5) + 32

            def __get__(self, instance, owner):
                return self._temperature

            def __set__(self, instance, value):
                if value < -273.15:
                    raise ValueError("Temperature below -273.15 is not possible")
                self._temperature = value

        class Temperature:
            celsius = Celsius()

        temp = Temperature()
        temp.celsius = 25
        print(temp.celsius)  # Output: 25
        print(temp.celsius.to_fahrenheit())  # Output: 77.0
        ```
3) Metaclasses:

    Metaclasses are a powerful and advanced concept in Python that allow you to control the behavior of class creation. A metaclass is essentially a class for classes, providing a way to customize how classes themselves are created and behave.

    - Class as an Instance of a Metaclass
        - In Python, classes are instances of metaclasses.
        - The default metaclass is type, and when you define a class, it is an instance of this metaclass.
        ```
        class MyClass:
            pass

        print(type(MyClass))  # Output: <class 'type'>
        ```
    - Defining a Metaclass
        - You can create your own metaclasses by inheriting from the type class.
        - Metaclasses typically override the __new__ and/or __init__ methods.
        ```
        class MyMeta(type):
            def __new__(cls, name, bases, dct):
                # Customize class creation here
                return super().__new__(cls, name, bases, dct)

        class MyClass(metaclass=MyMeta):
            pass
        ```
    - Use Cases for Metaclasses
        - Metaclasses can be used for various advanced scenarios, such as code injection, validation, and aspect-oriented programming.
        - A common use case is modifying the behavior of class attributes during class creation.  
        ```
        class MyMeta(type):
            def __init__(cls, name, bases, dct):
                # Modify attributes or perform other actions during class creation
                for key, value in dct.items():
                    if isinstance(value, str):
                        dct[key] = value.upper()

                super().__init__(name, bases, dct)

        class MyClass(metaclass=MyMeta):
            name = "example"
        ``` 
4) Class Methods and Static Methods

    Class methods and static methods are special types of methods in Python classes that have different behavior from regular instance methods. They are used for tasks that don't require access to the instance or its attributes.
    - Defining Class Methods
        - Class methods are defined using the @classmethod decorator.
        - The first parameter is conventionally named cls and refers to the class itself.
        ```
        class MyClass:
            class_variable = "I am a class variable"

            def __init__(self, instance_variable):
                self.instance_variable = instance_variable

            @classmethod
            def class_method(cls):
                print(f"Accessing class variable: {cls.class_variable}")

        # Calling a class method
        MyClass.class_method()
        ```
    - Use Cases for Class Methods
        - Class methods are often used for tasks related to the class itself, such as creating instances or accessing class-level variables.
        ```
        class Dog:
            total_dogs = 0

            def __init__(self, name):
                self.name = name
                Dog.total_dogs += 1

            @classmethod
            def get_total_dogs(cls):
                return cls.total_dogs
        ```
    - Defining Static Methods
        - Static methods are defined using the @staticmethod decorator.
        - They don't have access to the instance or class, and they behave like regular functions.
        ```
        class MathOperations:
            @staticmethod
            def add(x, y):
                return x + y

            @staticmethod
            def multiply(x, y):
                return x * y
        ```
    - Use Cases for Static Methods
        - Static methods are suitable for utility functions that don't depend on instance or class-specific data.
        ```
        class StringFormatter:
            @staticmethod
            def capitalize_first_letter(string):
                return string.capitalize()
        ```
Exercises:
```
# 1. Create a decorator that logs the input arguments and return value of a function.
# 2. Implement a decorator that measures the execution time of a function and prints it.
# 3. Design a decorator that memoizes the results of a function, caching previously computed results to improve performance.
# 4. Develop a descriptor that makes an attribute read-only once it is set.
# 5. Create a descriptor that triggers a callback function when an attribute is set.
```

Singleton Metaclass:

Create a metaclass that ensures a class can only have one instance, similar to a singleton pattern.
Validation Metaclass:

Develop a metaclass that validates the attributes of a class during creation, raising an error if certain conditions are not met.
Logging Metaclass:

Design a metaclass that logs the creation of classes, showing the class name, base classes, and attributes.
Code Injection Metaclass:

Implement a metaclass that injects additional code into methods of a class during class creation.
Aspect-Oriented Metaclass:

Create a metaclass that allows attaching aspects (cross-cutting concerns) to methods of a class.

Class Method Counter:

Create a class that keeps track of the number of instances created using a class method.
Static Method Date Validation:

Implement a class with a static method that validates whether a given string represents a valid date.
Class Method Factory:

Develop a class that acts as a factory for creating instances with different configurations using a class method.
Static Method Geometry:

Create a class with static methods for calculating the area and perimeter of common geometric shapes (circle, rectangle, triangle).
Class Method Configuration:

Build a class that manages configuration settings. Implement a class method to load configurations from a file.