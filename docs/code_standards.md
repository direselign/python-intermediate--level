All written code should follow a style guide to ensure that standards are kept consistent across any codebase and make code easier to read. Badly written code is difficult to scale, optimise, and debug.
We follow the standards in the PEP 8 Style Guide. In particular, this section will act as a reference for language-specific best practices for indentation, comments, quotes, and names, since these can vary across different programming languages.
# Indentation
The standard is to use four spaces for indented code.
`
## Good
def example_function():
    if x > 0:
        print("x is positive")

## Bad - Using tabs
def example_function():
    if x > 0:
    	print("x is positive")
`