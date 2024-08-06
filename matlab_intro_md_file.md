# 1. What is MATLAB?

MATLAB is a programming language and an interactive environment utilized by researchers for versatile reasons. While MATLAB has a graphical interface with point and click on icons to run commands ("MATLAB Desktop"), MATLAB primarily operates through a command line interface. 

### Applications in Research:

- Advanced statistical testing and data fitting
- Automate routine data processing tasks
- Designing and executing complex experimental tasks, including real-time data collection and behavioral tracking
- Develop computational models and apply machine learning algorithms
- Processing and analyzing neuroimaging data

This resource will focus on the basics of MATLAB to develop the skills necessary for using MATLAB in neuroimaging data analysis. 

# 2. Workspace Basics

You can access MATLAB directly from your local computer (suggested) or from a standard web browser with MATLAB Online. To access MATLAB you must have a MathWorks Account and a MATLAB license (usually obtained through your university).

[Instructions on installing MATLAB:](https://www.mathworks.com/help/install/ug/install-products-with-internet-connection.html)

[Instructions on accessing MATLAB Online:](https://www.mathworks.com/help/matlab-online-server/ug/matlab-online.html)


### MATLAB Interface:

When you first open MATLAB, you will notice that it has several windows and a ribbon of buttons at the top. The window on the left is the **Current Folder**, the central window is the **Command Window**, and the upper-right window is the **Workspace**.

- **Current Folder:** Shows a list of all the folders located within the folder you are currently in. (This is essentially your window.)
  
- **Command Window:** The main area where you can type commands directly and see their output.
  
- **Editor Window:** Where you writing, running, and debugging MATLAB code
  
- **Workspace Window:** Displays variables created during the session, providing an overview of the data you are working with.

![image](https://github.com/user-attachments/assets/27b88c90-33be-4848-a7ee-04495f7446e0)


### Customization and Setting Preferences

MATLAB offers flexible customization options to optimize your workflow. Some ways to tailor the interface include...

- **Resize and Reposition Windows:** Adjust the size and position of MATLAB windows by clicking and dragging the window dividers or title bars to suit your preferences.
- **Save Frequently Used Commands :** The Favorites menu allows you to bookmark commonly used commands. Add a command by selecting 'New Favorite,' entering the command, and giving it a descriptive name. For quicker access, add these favorites to the Quick Access toolbar and execute them with a single click.
- **Display Variable Details:** To gain more insights into the variables you're working with, such as their types or memory usage, right-click the header bar in the Workspace window and choose the properties you wish to display.

For more advanced customizations, navigate to **Preferences** under the Home tab.
<img width="1000" alt="image" src="https://github.com/user-attachments/assets/cdc7c230-c22d-41e6-917a-ec8468bc5eeb">


### Directories:

MATLAB organizes folders and files using a directory tree, starting with the root directory (/). 

- **Absolute Path:** Specifies the entire path from the root directory. E.g., `ls /Users/your-username`
  
- **Relative Path:** Specifies the path relative to the current directory. E.g., `cd Desktop`


### Commands for Navigating Workspace

| Command          | Description                                           |
|------------------|-------------------------------------------------------|
| `pwd`            | Prints the current working directory path. |
| `cd 'folder'`    | Changes the current working directory to 'folder'. |
| `cd ~`           | Changes the current directory to the user's home directory. |
| `cd .`           | Refers to the current directory. |
| `cd ..`          | Moves up one level in the directory tree. |
| `ls`             | Lists all files and directories in the current directory. |
| `dir`            | Lists directory contents, similar to `ls`. |
| `exist 'name'`   | Checks if a variable, file, or folder 'name' exists. |
| `mkdir 'dirname'`| Creates a new directory named 'dirname'. |
| `rmdir 'dirname'`| Removes the directory named 'dirname', if it is empty. |
| `edit 'filename'`   | Opens the specified file in MATLAB's editor.           |
| `edit functionName` | Opens the function in MATLAB's editor   |
| `doc command`    | Opens the documentation for 'command'. |
| `help command`   | Displays help text for 'command' in the Command Window. |
| `clc`            | Clears all input and output from the Command Window, keeping history. |
| `quit` or  `exit`| Closes MATLAB. |



### Keyboard Shortcuts for MATLAB Command Window

Keyboard shortcuts in MATLAB's Command Window mirror the functionality often used in terminal environments. 

Note - These shortcuts will only work if you have MATLAB installed in your system. MATLAB Online provides access to MATLAB from a standard web browser. Because MATLAB Online runs in a browser, navigation using the keyboard is slightly different.



#### For Windows Users

| Shortcut          | Description                                      |
|-------------------|--------------------------------------------------|
| `Up Arrow`        | Scrolls through the history to recall previous commands, useful for repetition or modification. |
| `Down Arrow`      | Scrolls forward in the command history after using the Up Arrow. |
| `Home` or `Ctrl + A`  | Jumps to the beginning of the current line. |
| `End` or `Ctrl + E`   | Jumps to the end of the current line. |
| `Tab`             | Auto-completes commands and variable names based on partially typed text. |
| `Backspace`       | Deletes the character to the left of the cursor. |
| `Delete`          | Deletes the character right at the cursor position. |
| `Enter`           | Executes the command currently typed in the Command Window. |
| `Shift + Enter`   | Continues command entry onto the next line for multi-line commands. |
| `Ctrl + L`        | Clears the screen, keeping the history intact. |
| `Esc`             | Cancels the current command line input without executing it. |
| `Ctrl + C`        | Interrupts the execution of the current command or script. |



#### For Mac Users

| Shortcut          | Description                                      |
|-------------------|--------------------------------------------------|
| `Up Arrow`        | Scrolls through the history to recall previous commands. |
| `Down Arrow`      | Scrolls forward in the command history after using the Up Arrow. |
| `Cmd + Left Arrow` or `Ctrl + A`| Mimics the Home key, jumping to the beginning of the line. |
| `Cmd + Right Arrow` or `Ctrl + E`| Mimics the End key, jumping to the end of the line. |
| `Tab`             | Auto-completes commands and variable names based on partially typed text. |
| `Delete`          | Deletes the character to the left of the cursor. (Mac keyboards typically do not have a separate Backspace key.) |
| `Fn + Delete`     | Deletes the character right at the cursor position. |
| `Return`          | Executes the command currently typed in the Command Window. |
| `Shift + Return`  | Continues command entry onto the next line for multi-line commands. |
| `Cmd + K`         | Clears the screen, keeping the history intact. |
| `Esc`             | Cancels the current command line input without executing it. |
| `Ctrl + C`         | Interrupts the execution of the current command or script. |


### MATLAB File Types:

- **.m files**: MATLAB script and function files, each serving different purposes:
  - **Script Files**: Scripts are collections of MATLAB commands executed exactly as if they were typed into the Command Window. They operate within the current workspace, which means they can modify any existing variables or create new ones. Scripts do not accept inputs directly (though they can work with data already in the workspace) and do not return outputs. They are useful for straightforward tasks like data manipulation and plotting when you do not need to isolate code.
  - **Function Files**: Functions, on the other hand, are more versatile and encapsulate their code within a separate workspace. They can accept inputs and return outputs, making them essential for modular programming. Functions prevent potential conflicts with the main workspace by keeping variables local, except those explicitly returned. They are ideal for reusing code, enhancing code readability, and managing larger projects where data encapsulation is necessary.

- **.mlx files**: MATLAB live script files that combine code execution with narrative, formatted text, equations, images, and hyperlinks in a single, interactive document. Ideal for instructional purposes, interactive applications, and sharing results.

- **.mat files**: Binary files that store workspace variables. Useful for saving your session data and transferring variables between sessions without losing integrity.

- **.fig files**: Figure files that save MATLAB graphical outputs. They enable you to reopen and modify figures later, preserving the graphical data and properties exactly as saved.


### Importing and Exporting Files

MATLAB supports importing various data formats such as TXT, CSV, XLS, XLSX, JPG, PNG, etc. You can find additional documentation including functions and examples [here](https://www.mathworks.com/help/matlab/import_export/supported-file-formats-for-import-and-export.html).


### Commands for Handling Files
| Command                      | Description                                           |
|------------------------------|-------------------------------------------------------|
| `save 'filename'`            | Saves workspace variables to a file.                  |
| `load 'filename'`            | Loads variables from a file into the workspace.       |
| `readtable('filename')`      | Imports data from a file into a table, supporting CSV, TXT, and Excel formats. |
| `readmatrix('filename')`     | Reads numerical data from a file into a matrix, ideal for straightforward data formats. |
| `xlsread('filename')`        | Imports data from Excel files, useful for datasets in spreadsheets. |
| `csvread('filename')`        | Reads numerical data from CSV files directly into an array. |
| `fopen('filename')`          | Opens a file for reading or writing, necessary for file manipulation. |
| `fwrite(fid, data)`          | Writes binary data to the file specified by `fid`.    |
| `fprintf(fid, format, data)` | Writes formatted data to the file, allowing for customizable text outputs. |
| `fclose(fid)`                | Closes an open file to free up resources.             |
| `importdata('filename')`     | Loads mixed data from files, handling various formats automatically. |
| `exportdata('data', 'filename')` | Exports data to a file in chosen formats, useful for sharing or external use. |



### Suggested Tutorials for Workspace Basics

**[15 MIN] "The MATLAB Desktop" Module from MATLAB Desktop Tools and Troubleshooting Scripts Course (MathWorks Self-Paced Online Courses)**
This tutorial briefly reviews how to import data, customize your workspace, and set preferences.

[Tutorial Link](https://matlabacademy.mathworks.com/details/matlab-desktop-tools-and-troubleshooting-scripts/otmldts#module=2)


# 3. MATLAB Syntax

This section provides an overview of fundamental MATLAB syntax.

### Special Characters 

- **Colon `:`**
  - Used to create vectors, specify ranges, and index arrays.
  - Example: `1:5` generates a vector `[1, 2, 3, 4, 5]`.
  - Used in array slicing: `A(:, 2)` selects all rows from the second column of matrix `A`.

- **Semicolon `;`**
  - Suppresses the output of a command.
  - Example: `a = 5;` assigns 5 to `a` without displaying the output.
  - Used to separate rows in matrix definitions: `A = [1, 2; 3, 4]`.

- **Percent `%`**
  - Used for comments. Everything after `%` on that line is ignored by MATLAB.
  - Example: `x = 10; % This is a comment`.

- **Assignment Operator `=`**
  - Assigns a value to a variable.
  - Example: `a = 5`.

- **Decimal Point `.`**
  - Indicates decimal numbers.
  - Example: `3.14`.

- **Comma `,`**
  - Separates elements in arrays and function arguments.
  - Example: `[1, 2, 3]` or `plot(x, y)`.

- **Parentheses `()`**
  - Used for grouping expressions, function arguments, and array indexing.
  - Example: `a = (b + c) * d` or `y = myFunction(x)`.

- **Square Brackets `[]`**
  - Used to create arrays and matrices.
  - Example: `A = [1, 2, 3]` or `B = [1, 2; 3, 4]`.

- **Curly Braces `{}`**
  - Used for cell arrays, which can hold different types of data.
  - Example: `C = {1, 'text', [1, 2, 3]}`.

- **Single Quote `'''`**
  - Defines a string.
  - Example: `str = 'Hello, World!'`.

- **Ellipsis `...`**
  - Indicates that a statement continues on the next line.
  - Example:
    ```matlab
    a = 1 + 2 + 3 + ...
        4 + 5 + 6;
    ```
    

### Relational Operators

| Operator | Description         | Example       |
|----------|---------------------|---------------|
| `==`     | Equal to            | `a == b`      |
| `~=`     | Not equal to        | `a ~= b`      |
| `>`      | Greater than        | `a > b`       |
| `<`      | Less than           | `a < b`       |
| `>=`     | Greater than or equal to | `a >= b` |
| `<=`     | Less than or equal to    | `a <= b` |

### Logical Operators

| Operator | Description         | Example       |
|----------|---------------------|---------------|
| `&`      | Logical AND         | `a & b`       |
| `|`      | Logical OR          | `a | b`       |
| `~`      | Logical NOT         | `~a`          |
| `xor`    | Logical EXCLUSIVE OR| `xor(a, b)`   |




# 4. Working with Variables in MATLAB

This section provides an overview of how to handle variables in MATLAB, including how to create, manipulate, and delete them, as well as working with vectors and matrices.

### Creating Variables

Variables in MATLAB are created simply by assigning values to them. MATLAB does not require explicit declaration of variable types.

| Command             | Description                                           |
|---------------------|-------------------------------------------------------|
| `x = 5;`            | Creates a variable `x` and assigns it the value `5`.  |
| `name = 'MATLAB';`  | Creates a string variable `name` with the text `MATLAB`. |

#### Working with Vectors

Vectors are a fundamental data structure in MATLAB used to store lists of numbers.

| Command             | Description                                           |
|---------------------|-------------------------------------------------------|
| `v = [1, 2, 3];`    | Creates a row vector `v` with elements 1, 2, and 3.   |
| `w = [1; 2; 3];`    | Creates a column vector `w` with elements 1, 2, and 3.|
| `length(v);`        | Returns the number of elements in vector `v`.         |
| `v(2);`             | Accesses the second element of vector `v`.            |
| `v(1:2);`           | Accesses the first and second elements of vector `v`. |

#### Working with Matrices

Matrices are two-dimensional arrays of numbers. MATLAB is specifically designed to work efficiently with matrices.

| Command             | Description                                           |
|---------------------|-------------------------------------------------------|
| `A = [1, 2; 3, 4];` | Creates a 2x2 matrix `A`.                             |
| `B = zeros(3,3);`   | Creates a 3x3 matrix `B` filled with zeros.           |
| `C = ones(2,4);`    | Creates a 2x4 matrix `C` filled with ones.            |
| `D = eye(3);`       | Creates a 3x3 identity matrix `D`.                    |
| `size(A);`          | Returns the size of matrix `A`.                       |
| `A(2,1);`           | Accesses the element in the second row, first column of `A`. |
| `A(:,2);`           | Accesses all elements in the second column of `A`.    |
| `A(1,:);`           | Accesses all elements in the first row of `A`.        |

#### Manipulating Variables

Once variables are created, they can be manipulated using MATLAB's built-in functions and operators.

| Command             | Description                                           |
|---------------------|-------------------------------------------------------|
| `v = [1, 2, 3];`    | Creates a row vector `v` with elements 1, 2, and 3.   |
| `w = v + 1;`        | Adds `1` to each element of vector `v`.               |
| `u = sum(v);`       | Sums the elements of `v` and stores the result in `u`.|
| `mean(v);`          | Calculates the mean of vector `v`.                    |
| `A = A + 2;`        | Adds `2` to each element of matrix `A`.               |
| `A * 2;`            | Multiplies each element of matrix `A` by `2`.         |
| `A * B;`            | Performs matrix multiplication of `A` and `B`.        |
| `A .* B;`           | Performs element-wise multiplication of `A` and `B`.  |

#### Deleting Variables

To free up resources or clear workspace, you can delete variables that are no longer needed.

| Command             | Description                                           |
|---------------------|-------------------------------------------------------|
| `clear x;`          | Deletes the variable `x` from the workspace.          |
| `clear x y z;`      | Deletes multiple variables `x`, `y`, and `z`.         |
| `clear all;`        | Clears all variables from the workspace.              |

#### Viewing Variables

To view the variables currently stored in your workspace, you can use the Workspace window or specific commands.

| Command             | Description                                           |
|---------------------|-------------------------------------------------------|
| `who;`              | Lists all variables in the workspace.                 |
| `whos;`             | Lists all variables with detailed information including size, bytes, and class. |





## ADDITIONAL RESOURCES FOR MATLAB
MATLAB Desktop – Importing Data, Customizing the MATLAB Desktop, and Setting Preferences from MathWorks Self-Paced Online Courses: MATLAB Desktop Tools and Troubleshooting Scripts Course

[Tutorial Link](https://matlabacademy.mathworks.com/details/matlab-desktop-tools-and-troubleshooting-scripts/otmldts)
https://github.com/mikexcohen/EssentialsOfNeuroscienceWithMATLAB/blob/main/module4_FMRI/README.md 

