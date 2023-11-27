Decorators and Generators
-------------------------
Introduction to Decorators

Decorators are functions that modify or extend the behavior of other functions or methods.
They use the @decorator syntax in Python.

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

Chaining Decorators: Multiple decorators can be applied to a single function, and they are applied from the innermost to the outermost.

```
def decorator1(func):
    def wrapper():
        print("Decorator 1")
        func()
    return wrapper

def decorator2(func):
    def wrapper():
        print("Decorator 2")
        func()
    return wrapper

@decorator1
@decorator2
def my_function():
    print("Original function")

my_function()
```
Decorator with Arguments: Decorators can take arguments to make them more flexible.

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
1) Generators

    - Introduction to Generators
        - Generators allow you to create iterators in a concise and memory-efficient way using a function with the yield keyword.
        - They are useful for working with large datasets or infinite sequences.

        ```
        def count_up_to(n):
            i = 1
            while i <= n:
                yield i
                i += 1

        for number in count_up_to(5):
            print(number)
        ```
    - Generator Expressions
        - Generator expressions are a concise way to create generators using a syntax similar to list comprehensions.
        ```
        squares = (x**2 for x in range(5))
        for square in squares:
            print(square)
        ```
    - Infinite Generators:
        - Generators can be used to represent infinite sequences.
        ```
        def infinite_count():
            i = 1
            while True:
                yield i
                i += 1

        for number in infinite_count():
            print(number)

        ```
    - Pipelining Generators
        - Generators can be chained together to create a pipeline of data processing.
        ```
        def numbers():
            for i in range(5):
                yield i

        def square(nums):
            for num in nums:
                yield num**2

        result = square(numbers())
        for value in result:
            print(value)
        ```
Exercises:
```
# 1. Create a decorator that logs the input arguments and return value of a function.
# 2. Implement a decorator that measures the execution time of a function and prints it.
# 3. Write a generator that generates the Fibonacci sequence up to a specified limit.
# 4. Implement a generator that produces an infinite sequence of prime numbers.
# 5. Create a generator that tokenizes a sentence into words.
```