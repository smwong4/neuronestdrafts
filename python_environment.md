# Python Environment and Setup

Python can be accessed directly from your local computer or through cloud-based environments like Google Colab or Jupyter Notebook. To get started, you must install Python and set up an integrated development environment (IDE) or text editor.

## Python Installation

This section will guide you through the process of installing Python on your system. Python can be installed via several methods:

- **Anaconda**: A popular distribution that includes Python and a variety of packages tailored for data science. Anaconda also provides a user-friendly interface for managing environments and packages.
- **Miniconda**: A lightweight alternative to Anaconda that installs Python and the conda package manager, allowing you to install only the packages you need.
- **Python.org**: You can directly download the official Python installer from [Python.org](https://www.python.org/downloads/). This method provides a more minimal setup but requires manual package management via pip.

## Python File Types

Python uses various file types to handle different types of tasks:

- **.py**: The standard Python script file containing executable code.
- **.ipynb**: Jupyter Notebook files, which contain both code and rich text elements such as images and equations. These files are especially useful for data analysis and scientific research.
- **.json**: A format commonly used for storing and exchanging data. JSON files are easy to read and write in Python, making them ideal for configuration files, data storage, and API responses.

## Importing and Exporting Files

Python provides powerful tools for importing and exporting data in various formats:

- **CSV Files**: Python's `csv` module or `pandas` library makes it easy to read from and write to CSV files.
- **Excel Files**: The `pandas` library allows for seamless import and export of Excel files using its `read_excel` and `to_excel` functions.
- **JSON Files**: Python’s `json` module enables reading and writing JSON files, a common format for structured data interchange.

## Working with Python Environments

### Virtual Environments
Using virtual environments allows you to manage dependencies for your projects without affecting other projects.

### Package Management
To install and manage packages, you can use pip, which is the standard package installer for Python.

## Interacting with Python

- **IDEs and Editors**: There are various integrated development environments (IDEs) and text editors for writing Python code. Popular choices include:
  - **Jupyter Notebook**: Ideal for interactive data analysis and sharing.
  - **Spyder**: A scientific IDE with advanced editing, debugging, and introspection features.
  - **VS Code**: A lightweight yet powerful editor with extensive extensions for Python development.

- **Command Line Interface**: Basic Python commands can be executed directly in the terminal or command prompt, allowing for quick script execution and environment management.

- **Version Control**: Version control is crucial for managing changes in your code over time. Git, combined with GitHub, is a widely-used system for tracking changes, collaborating on code, and sharing projects.

## Command Cheat Sheet

| Command                          | Description                                           |
|----------------------------------|-------------------------------------------------------|
| `python --version`               | Check Python version                                  |
| `pip install package_name`       | Install a package                                     |
| `pip list`                       | List installed packages                               |
| `virtualenv env_name`            | Create a virtual environment                          |
| `source env_name/bin/activate`   | Activate virtual environment                          |
| `deactivate`                     | Deactivate virtual environment                        |

## References

- [Neuroimaging Data Science - Python Language Overview](https://neuroimaging-data-science.org/content/003-programming/001-python-language.html)
- [Introduction to Python for Scientific Programming - Installing Python](https://github.com/rthorst/Introduction-to-Python-for-Scientific-Programming/blob/master/Programming%20Basics%201%20Installing%20Python/Programming%20Basics%201%20Introduction%20to%20Python.ipynb)
