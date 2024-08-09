# Core Python Programming

This section provides a foundational understanding of Python programming, covering essential topics like coding style, debugging, testing, and control flow. Whether you're a beginner or looking to solidify your programming practices, the resources here will guide you through the core aspects of writing effective Python code.

## 1. Python Coding Style

Adhering to a consistent coding style is crucial for writing readable and maintainable code. Python’s official style guide, [PEP 8](https://peps.python.org/pep-0008/), provides comprehensive guidelines on how to format your code. Following PEP 8 ensures that your code is clean, organized, and consistent with the wider Python community.

- **Indentation**: Use 4 spaces per indentation level.
- **Line Length**: Limit all lines to a maximum of 79 characters.
- **Imports**: Imports should be on separate lines, and grouped in the order of standard library imports, related third-party imports, and local application/library-specific imports.

For additional tools to enforce style conventions and check for common errors, consider using [flake8](https://pypi.org/project/flake8-pytest-style/).

## 2. Debugging and Testing

Writing robust code involves rigorous debugging and testing. Python offers several built-in and third-party tools to help ensure your code runs correctly.

- **Debugging**: Use the built-in `pdb` module to step through your code and inspect variables in real-time. The [Python documentation](https://docs.python.org/3/tutorial/errors.html) offers a detailed guide on using `pdb`.
  
- **Testing**: The `unittest` module is Python’s built-in testing framework, while [pytest](https://docs.pytest.org/en/stable/) is a popular third-party tool that simplifies writing and running tests.

## 3. Control Flow

Understanding control flow is fundamental to writing effective programs. Control flow structures allow you to dictate the execution of statements based on conditions.

- **Conditional Statements**: The `if`, `elif`, and `else` statements allow you to execute blocks of code based on Boolean conditions. [Learn more](https://docs.python.org/3/tutorial/controlflow.html#more-on-defining-functions).
  
- **Loops**: Python supports `for` and `while` loops, which enable you to iterate over sequences or repeat actions until a condition is met. For more details, refer to the [Python tutorial](https://docs.python.org/3/tutorial/controlflow.html).

## 4. Functions and Modules

Functions are reusable blocks of code that perform specific tasks, while modules are files containing Python definitions and statements. Organizing your code into functions and modules enhances readability and reusability.

- **Defining Functions**: Use the `def` keyword to create functions. Functions can take arguments and return values. Explore more about function definitions in the [Python documentation](https://docs.python.org/3/tutorial/controlflow.html#more-on-defining-functions).

- **Using Modules**: Modules allow you to organize your code by grouping related functions, classes, and variables. Learn how to import and use modules in the [official Python tutorial](https://docs.python.org/3/tutorial/modules.html).

## 5. Interactive Mode and Scripting

Python can be used interactively or to write scripts. 

- **Interactive Mode**: Useful for quick tests and explorations. Type `python` in your command line to enter the interactive mode. Read more about it [here](https://docs.python.org/3/tutorial/appendix.html#interactive-mode).

- **Scripting**: Write your code in `.py` files and execute them in the terminal. Scripting is ideal for larger, reusable programs.

## 6. Python Resources and Tutorials

To further your understanding, explore these resources:

### Suggested Tutorials:
- [Python Language Overview - Neuroimaging Data Science](https://neuroimaging-data-science.org/content/003-programming/001-python-language.html)
- [Introduction to Python - CS50 Harvard](https://cs50.harvard.edu/python/2022/)

### Supplemental Materials:
- [PEP 8 - Python's Style Guide](https://peps.python.org/pep-0008/)
- [Python Modules Documentation](https://docs.python.org/3/tutorial/modules.html)
- [Control Flow - Python Docs](https://docs.python.org/3/tutorial/controlflow.html)
