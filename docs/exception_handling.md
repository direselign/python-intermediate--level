Exception Handling
------------------
Exception handling is a crucial aspect of robust programming. It allows you to anticipate and gracefully handle errors, preventing your program from crashing unexpectedly. In this section, we'll explore various aspects of exception handling in Python.

1) Try-Except Blocks:

    - `try` block contains the code that might raise an exception.
    - `except` block handles the exception if one occurs.
    ```
    try:
        # Code that might raise an exception
        result = 10 / 0
    except ZeroDivisionError:
        # Handle the specific exception
        print("Cannot divide by zero.")
    ```
2) Multiple Except Blocks:
    - Handle different types of exceptions with multiple `except` blocks.
    ```
    try:
        num = int(input("Enter a number: "))
        result = 10 / num
    except ValueError:
        print("Invalid input. Please enter a number.")
    except ZeroDivisionError:
        print("Cannot divide by zero.")
    ```

3) Generic Except Block:
    - Use a generic `except` block to catch unexpected exceptions.
    ```
    try:
        # Code that might raise an exception
    except Exception as e:
        # Handle any exception
        print(f"An error occurred: {e}")
    ```

Exercises:
```
# 1. Create a simple calculator program that takes two numbers and an operation (+, -, *, /) from the user. Use exception handling to handle errors such as invalid input and division by zero.
# 2. Modify the file reading exercise from the previous section to include exception handling. Handle FileNotFoundError and any other potential errors.
# 3. Write a program that checks if a user-entered password is strong. A strong password has at least eight characters, contains both uppercase and lowercase characters, and includes at least one digit. Use exception handling to provide meaningful error messages for each condition.
# 4. Simulate a network connection function that may occasionally fail. Implement a function that connects to a network and handle potential network-related exceptions.
# 5. Simulate a database query function that may raise database-related exceptions. Create a program that queries a database and handles exceptions gracefully.
```

Exception handling is essential for writing reliable and user-friendly programs. These exercises will help you practice handling different types of exceptions and provide a better understanding of how to make your programs more resilient to errors.