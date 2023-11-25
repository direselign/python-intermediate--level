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

4) Advanced Dictionary Techniques
Dictionaries are versatile data structures in Python, and beyond their basic key-value pairs, there are advanced techniques and methods that can enhance their functionality. This section delves into some of these advanced dictionary techniques.
1) Dictionary Comprehensions:
    - Similar to list comprehensions but for dictionaries.
    - A concise way to create dictionaries using a single line of code.
    ```
        squares = {x: x**2 for x in range(1, 6)}
    ```
2) Merging Dictionaries:Using the update() method or dictionary unpacking (**) to merge two dictionaries.
    ```
    dict1 = {'a': 1, 'b': 2}
    dict2 = {'b': 3, 'c': 4}

    # Using update()
    dict1.update(dict2)

    # Using dictionary unpacking
    merged_dict = {**dict1, **dict2}
    ```
3) Default Values with setdefault() and defaultdict:
    - setdefault(key, default) sets the default value for a key if it doesn't exist.
    - defaultdict from the collections module provides a default value for any nonexistent 
    ```
    # Using setdefault()
    my_dict = {}
    my_dict.setdefault('a', []).append(1)

    # Using defaultdict
    from collections import defaultdict
    num_dict = defaultdict(int)
    num_dict['one'] += 1
    ```
4) Dictionary Views:

    - keys(), values(), and items() return dynamic views on the dictionary.
    - Changes in the dictionary are reflected in the views.
    ```
    my_dict = {'a': 1, 'b': 2, 'c': 3}

    # Keys view
    keys_view = my_dict.keys()

    # Values view
    values_view = my_dict.values()

    # Items view
    items_view = my_dict.items()
    ```
5) Dictionary Filtering:
    - Use dictionary comprehensions to filter elements based on certain conditions.
    ```
    original_dict = {'a': 1, 'b': 2, 'c': 3}

    # Filter elements with values greater than 1
    filtered_dict = {k: v for k, v in original_dict.items() if v > 1}
    ```

Exercises:

```
# 1. Given a text, create a dictionary that counts the frequency of each word.
# 2. Create two dictionaries and merge them using both update() and dictionary unpacking. Ensure that the values of common keys are updated.
# 3. Create a nested dictionary using comprehension to represent a multiplication table. For example, for a 3x3 table, the result should be {'1': {'1': 1, '2': 2, '3': 3}, '2': {...}, '3': {...}}.
# 4. Use setdefault() to create a dictionary with lists as values. Append elements to these lists for different keys.
# 5. Given a dictionary, filter out elements where the value is less than 3.
```