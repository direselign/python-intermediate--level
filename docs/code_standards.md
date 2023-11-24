It is imperative for every piece of code to adhere to a style guide, ensuring consistent standards throughout any codebase and enhancing code readability. Poorly crafted code poses challenges in terms of scalability, optimization, and debugging. We strictly adhere to the guidelines outlined in the [PEP 8 Style Guide](https://www.python.org/dev/peps/pep-0008/), especially focusing on language-specific best practices. This section serves as a reference for the recommended practices concerning indentation, comments, quotes, and naming conventions. These practices are crucial as they can vary across different programming languages.
# Indentation
The standard is to use four spaces for indented code.
```
## Good
def example_function():
    if x > 0:
        print("x is positive")

## Bad - Using tabs
def example_function():
    if x > 0:
    	print("x is positive")
```
# Comments
Every Python course will cover how to comment, but not every course will discuss good standards for commenting. Good standards are important for consistency and accessibility for whoever is reading the code. Best standards for comments can be read about in more detail [here](https://www.python.org/dev/peps/pep-0008/#comments).
## Inline Comments
Inline comments should be used sparingly and not state the obvious. They should be separated by at least two spaces from the code and use commanding language rather than descriptive. For example, the following is preferred:
```
x = x + 1  # Compensate for border
```
## Block Comments
Block comments must be composed in full sentences, indented along with the code it describes, and positioned before the corresponding code. Placing comments after the code can be disorienting for a reader grappling with confusion. Paragraphs within comments are delineated by a lone line containing a single #, and comments spanning multiple sentences should incorporate two spaces after each sentence-ending period, except for the final sentence.
```
# This function triples a number.  It does not check for valid input.
#
# It's quite a nice function.
def triple(x):
    return 3*x
```
## Docstrings
Similar but different to comments, a docstring is a string that appears as the first statement in a module, function, class, or method definition, and is used to document what they do. Docstrings are usually used for modules, and all classes and functions exported by that module.

Docstrings ought to be enclosed within triple double quotes (""" """), and a blank line should follow any docstring that documents a class. For more detailed information on best practices for docstrings, you can refer to the standards explained [here](https://www.python.org/dev/peps/pep-0257/).

### One-Line Docstrings
One-line docstrings are for obvious cases. There should be no blank line before or after the docstring. It must be a concise phrase concluding with a period, prescribing the function or method's effect as a command, rather than providing a detailed description. For instance, the preferred format is as follows:
```
def triple(x):
    """Return the triple of a number."""
    return 3*x
```
### Multi-Line Docstrings
Multi-line docstrings initiate with a summary line, placed on the same line as the opening triple quotes. This is succeeded by a space, a more detailed description, and finally, the closing triple quotes on a line by themselves. An illustrative example is as follows:
```
def power(x, y=2, z=4):
    """Raise x to the power of y, then multiply by 4.

    Arguments:
    x -- the base number
    y -- the exponent (default 2)
    z -- the multiplier (default 4)
    """
    return x**y
```

## Quotes
Whenever quotation marks are required in code, either consistently use double quotes " " or consistently use single quotes ' ' throughout the code. However, when a string contains double quotes or single quotes, then the choice of wrapping quotation marks should be such that the use of the escape character \ is avoided.

Quotation marks for triple-quoted strings should always use double quotes.

## Names
Unfortunately there is no convention for general names. However, in this section we list the convention for common types of names. Best standards for names can be read about in more detail here.

- Modules: Use short snake_case names.
- Packages: Use short lowercase names. Only use snake_case if necessary.
- Classes: Use PascalCase.
- Functions: Use snake_case.
- Variables: Use snake_case.
- Constants: Use uppercase. Any word separation should be done with an underscore _.