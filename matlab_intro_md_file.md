# MATLAB Resource for Psychology and Neuroscience Graduate Students

## What is Matlab?

MATLAB (Matrix Laboratory) is both a programming language and an interactive environment developed by MathWorks. It is designed for high-performance numerical computation, visualization, and programming. MATLAB is particularly powerful for matrix manipulations, making it ideal for a wide range of applications in engineering, physics, finance, biology, and neuroscience. It enables users to perform tasks quickly and efficiently by combining interactive tools and MATLAB commands, streamlining workflows, and...

### Key Features:

- **Programming Language:** MATLAB is centered around matrices, which allows for efficient computation and data manipulation.
- **Interactive Environment:** Users can leverage a graphical interface to point and click on icons to run commands, although MATLAB primarily operates through a command line interface. This command-line approach, while initially appearing tedious, provides greater speed, flexibility, and efficiency in running programs and analyzing data.
- **Advantages for Researchers:** Fluency in MATLAB programming saves time, minimizes errors, and enhances versatility as a scientist. It facilitates data analysis, statistical testing, signal processing, computational modeling, machine learning, and automation.

## How can you use Matlab in your research?

### Applications in Research:

- **Data Analysis:** MATLAB excels in handling large datasets, enabling complex data analysis and visualization.
- **Statistical Analysis:** Researchers can conduct statistical tests, data fitting, and hypothesis testing.
- **Signal Processing:** Essential for analyzing and visualizing EEG, fMRI, and other brain imaging data.
- **Modeling:** Development of computational models to simulate neural processes and other scientific phenomena.
- **Machine Learning:** Implementation of machine learning algorithms for predictive modeling, classification, and clustering.
- **Automation:** Automate repetitive tasks, streamline workflows, and ensure consistency in data processing and analysis.

## Navigating Workspace Overview

### Workspace Basics:

When you first open MATLAB, you will notice that it has four distinct sections: three windows and a ribbon of buttons at the top, similar to the layout of Microsoft Word. The window on the left is the **Current Folder** (Navigation window), the central window is the **Command Window**, and the upper-right window is the **Workspace**.

- **Current Folder:** Shows a list of all the folders located within the folder you are currently in.
- **Command Window:** The main area where you can type commands directly and see their output.
- **Workspace:** Displays variables created during the session, providing an overview of the data you are working with.
- **Command History:** (not always visible by default) Logs commands entered in the Command Window.

MATLAB organizes folders and files using a directory tree, starting with the root directory (/). The directory tree resembles an upside-down tree where root is the base and all other folders extend from it like branches.

### Navigating Directories:

- **Absolute Path:** Specifies the entire path from the root directory. E.g., `ls /Users/andrewjahn`
- **Relative Path:** Specifies the path relative to the current directory. E.g., `cd Desktop`

### Key Commands:

- **`pwd` (Print Working Directory):** Displays the current directory.
- **`cd` (Change Directory):** Changes the current directory.
- **`ls` (List):** Lists the contents of the current directory.

### Special Directories:

- **Home Directory:** Represented by `~`. E.g., `cd ~/Desktop`
- **Current Directory:** Represented by `.` 
- **Parent Directory:** Represented by `..`

## Command Cheat Sheet for Navigating Workspace

| Command       | Description                         |
|---------------|-------------------------------------|
| `clc`         | Clear the Command Window            |
| `clear`       | Remove variables from the Workspace |
| `clear all`   | Remove all variables from the Workspace |
| `whos`        | List current variables and their details |
| `who`         | List current variables              |
| `pwd`         | Show current directory              |
| `cd 'folder'` | Change directory                    |
| `ls`          | List files in the current directory |
| `save 'filename'` | Save workspace variables to a file |
| `load 'filename'` | Load variables from a file into workspace |

## File Handling – Matlab Files and Importable Files

### File Types:

- **.m files:** MATLAB script and function files.
- **.mat files:** Binary files that store workspace variables.
- **.fig files:** Figure files for saving graphical figures.
- **Importable Files:** MATLAB supports importing various data formats such as TXT, CSV, XLS, XLSX, JPG, PNG, etc.

### Importing Data:

- `readtable`: Read data from a file into a table.
- `readmatrix`: Read matrix data from a file.
- `xlsread`: Read data from an Excel file.
- `csvread`: Read data from a CSV file.

## Command Cheat Sheet for File Handling

| Command                    | Description                               |
|----------------------------|-------------------------------------------|
| `save 'filename'`          | Save workspace variables to a file        |
| `load 'filename'`          | Load variables from a file into workspace |
| `readtable('filename')`    | Read a table from a file                  |
| `readmatrix('filename')`   | Read matrix data from a file              |
| `xlsread('filename')`      | Read data from an Excel file              |
| `csvread('filename')`      | Read data from a CSV file                 |
| `fopen('filename')`        | Open a file for reading or writing        |
