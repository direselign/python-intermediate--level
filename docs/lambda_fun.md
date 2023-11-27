Lambda Functions and Higher-Order Functions
-------------------------------------------
Lambda Functions:

1) Introduction to Lambda Functions:
    - Lambda functions, also known as anonymous functions, are one-liner functions defined using the lambda keyword.
    - They are often used for short, simple operations.

    ```
    add = lambda x, y: x + y
    print(add(3, 5))  # Output: 8
    ```
2) Using Lambda Functions with Higher-Order Functions:
    - Lambda functions are commonly used with higher-order functions like map, filter, and `reduce`.

    ```
    numbers = [1, 2, 3, 4, 5]

    # Using map with a lambda function
    squared = list(map(lambda x: x**2, numbers))

    # Using filter with a lambda function
    evens = list(filter(lambda x: x % 2 == 0, numbers))

    # Using reduce with a lambda function
    from functools import reduce
    product = reduce(lambda x, y: x * y, numbers)
    ```

# Higher-Order Functions:

1) Higher-Order Functions:

    - Higher-order functions are functions that take other functions as arguments or return functions as results.
    - They enable functional programming paradigms.
    ```
    def apply_operation(x, y, operation):
        return operation(x, y)

    def add(x, y):
        return x + y

    def multiply(x, y):
        return x * y

    result1 = apply_operation(3, 4, add)       # Output: 7
    result2 = apply_operation(3, 4, multiply)  # Output: 12
    ```
2) Built-in Higher-Order Functions:

    - Python provides built-in higher-order functions like map, filter, and reduce for common operations.

    ```
    numbers = [1, 2, 3, 4, 5]

    # Using map to square each element
    squared = list(map(lambda x: x**2, numbers))

    # Using filter to get even numbers
    evens = list(filter(lambda x: x % 2 == 0, numbers))

    # Using reduce to find the product
    from functools import reduce
    product = reduce(lambda x, y: x * y, numbers)
    ```
Exercises:

```
# 1. Create a lambda function that reverses a given string.
Higher-Order Function for List Transformation:

# 2. Implement a higher-order function that applies a given transformation function to each element of a list.

# 3. Use the filter function and a lambda function to filter out negative numbers from a list.

# 4. Use the map function and a lambda function to convert a list of temperatures from Celsius to Fahrenheit.

# 5. Use the reduce function and a lambda function to find the maximum value in a list.```