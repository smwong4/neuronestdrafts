## 2. Python Environment Setup

Python can be accessed directly from your local computer or through cloud-based environments like Google Colab or Jupyter Notebook. To get started, you must install Python and set up an integrated development environment (IDE) or text editor.

### 2a. Installing Python and IDEs

- **Python Installation:** You can download and install Python from [python.org](https://www.python.org/downloads/).
- **IDEs and Text Editors:** Popular choices include VSCode, PyCharm, and Jupyter Notebook. 

### 2b. Working with Python Environments

- **Virtual Environments:** Use virtual environments to manage dependencies for your projects.
    ```bash
    python -m venv myenv
    source myenv/bin/activate  # On Windows use `myenv\Scripts\activate`
    ```
- **Package Management:** Use pip to install and manage packages.
    ```bash
    pip install numpy pandas
    ```

### 2c. Command Cheat Sheet

| Command                          | Description                                           |
|----------------------------------|-------------------------------------------------------|
| `python --version`               | Check Python version                                  |
| `pip install package_name`       | Install a package                                     |
| `pip list`                       | List installed packages                               |
| `virtualenv env_name`            | Create a virtual environment                          |
| `source env_name/bin/activate`   | Activate virtual environment                          |
| `deactivate`                     | Deactivate virtual environment                        |


