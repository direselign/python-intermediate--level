File Handling
-------------
File handling is a crucial aspect of programming, enabling you to read and write data from and to external files. In Python, file operations are straightforward and versatile. This section covers the fundamentals of file handling, including reading, writing, and manipulation of files.

File Handling Basics:
--------------------
1) Opening and Closing Files:
    - open() function is used to open a file, and close() method is used to close it.
    - Always close files explicitly to free up system resources.
    ```
    # Opening a file for reading
    file = open("example.txt", "r")

    # Reading content
    content = file.read()
    print(content)

    # Closing the file
    file.close()
    ```

2) Reading from Files:
    - Use various methods (read(), readline(), readlines()) to read content from files.
    ```
    # Reading the entire content
    with open("example.txt", "r") as file:
        content = file.read()

    # Reading line by line
    with open("example.txt", "r") as file:
        line = file.readline()
    ```
3) Writing to Files:
    - Open a file in write mode ("w"). Be cautious, as this will overwrite existing content.
    - Use "a" mode to append content to an existing file.
    ```
    # Writing to a file
    with open("example.txt", "w") as file:
        file.write("Hello, this is a sample text.")

    # Appending to a file
    with open("example.txt", "a") as file:
        file.write("\nAppended text.")
    ```
4) Handling Exceptions:
    - Use try-except blocks to handle file-related exceptions, such as FileNotFoundError.
    ```
    try:
        with open("nonexistent_file.txt", "r") as file:
            content = file.read()
    except FileNotFoundError:
        print("File not found.")
    ```

Exercises
```
# 1. Create a program that reads a text file and counts the number of words.
# 2. Write a program that copies the content of one file into another.
# 3. Given a CSV file with columns like "Name," "Age," and "Country," write a program to read the file and convert it into a list of dictionaries.
# 4. Create a program that takes a text file and encrypts its content using a simple encryption algorithm. Save the encrypted content to a new file.
# 5. Given a log file with timestamps and messages, write a program to analyze the log and extract information such as the number of occurrences of each type of message.
```