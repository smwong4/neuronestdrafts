# MATLAB Resource

## What is MATLAB?

MATLAB is both a programming language and an interactive environment well utilized by researchers for versatile reasons like running programs and analyzing data. While MATLAB has a graphical interface with point and click on icons to run commands ("MATLAB Desktop"), MATLAB primarily operates through a command line interface. 

### Applications in Research:

- Advanced statistical testing and data fitting
- Automate routine data processing tasks
- Designing and executing complex experimental tasks, including real-time data collection and behavioral tracking
- Develop computational models and apply machine learning algorithms
- Processing and analyzing neuroimaging data

This resource will focus on the basics of MATLAB to develop the skills necessary for using MATLAB in neuroimaging data analysis. 

## Navigating Workspace Overview

### Workspace Basics:

When you first open MATLAB, you will notice that it has four distinct sections: three windows and a ribbon of buttons at the top. The window on the left is the **Current Folder** (Navigation window), the central window is the **Command Window**, and the upper-right window is the **Workspace**.

- **Current Folder:** Shows a list of all the folders located within the folder you are currently in.
- **Command Window:** The main area where you can type commands directly and see their output.
- **Workspace:** Displays variables created during the session, providing an overview of the data you are working with.
- **Command History:** (not always visible by default) Logs commands entered in the Command Window.


### Navigating Directories:

MATLAB organizes folders and files using a directory tree, starting with the root directory (/). 

- **Absolute Path:** Specifies the entire path from the root directory. E.g., `ls /Users/andrewjahn`
- **Relative Path:** Specifies the path relative to the current directory. E.g., `cd Desktop`

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
