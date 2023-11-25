Advanced Data Structures:
-------------------------
In this section, we'll explore advanced data structures beyond the basics of lists and dictionaries. These structures, including sets, tuples, and namedtuples, offer specialized functionalities that can enhance your ability to organize and manipulate data.

Advanced Data Structures:
1) Sets:
    - Sets are unordered collections of unique elements.
    - Useful for operations like union, intersection, and difference.
```
unique_colors = {"red", "blue", "green"}
new_colors = {"blue", "yellow"}

# Union of sets
all_colors = unique_colors.union(new_colors)
print(all_colors)
```
2) Tuples
    - Tuples are immutable sequences. Once created, their elements cannot be changed.
    - Ideal for representing fixed collections of values.
    ```
    coordinates = (10, 20)
    x, y = coordinates  # Unpacking values

    # Immutable, can't be modified
    # coordinates[0] = 5  # This will raise an error
    ```
3) Namedtuples
    - Namedtuples are tuples with named fields, providing more readable and self-documenting code.
    - They are immutable like regular tuples.
    ```
    from collections import namedtuple

    # Define a named tuple
    Point = namedtuple("Point", ["x", "y"])

    # Create an instance
    p = Point(x=5, y=10)

    print(f"X-coordinate: {p.x}, Y-coordinate: {p.y}")

    # Excercises
    # 1. Create two sets, one representing even numbers up to 10 and the other representing multiples of 3 up to 10. Perform the union, intersection, and difference operations between them.
    # 2. Create a tuple representing the temperature in degrees Celsius for each day of the week. Write a program that finds the average temperature.
    # 3. Define a named tuple called Student with fields for name, age, and grade. Create instances for three students and print their information.
    # 4. Modify the Student named tuple to include a new field for subject. Update the instances accordingly.
    # 5. Given a list, convert it into a set and then back into a list. Ensure that the final list has only unique elements.

    ```