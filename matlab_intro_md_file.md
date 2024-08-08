# 1. What is MATLAB?

MATLAB is a programming language and an interactive environment utilized by researchers for versatile reasons. While MATLAB has a graphical interface with point and click on icons to run commands ("MATLAB Desktop"), MATLAB primarily operates through a command line interface. 

### 1a. Applications in Research:

- Advanced statistical testing and data fitting
- Automate routine data processing tasks
- Designing and executing complex experimental tasks, including real-time data collection and behavioral tracking
- Develop computational models and apply machine learning algorithms
- Processing and analyzing neuroimaging data

This resource will focus on the basics of MATLAB to develop the skills necessary for using MATLAB in neuroimaging data analysis. 

### 1b. Supplemental Resources

[MATLAB in Neuroimaging Oveview](https://www.youtube.com/watch?v=0cft-tyRj4o)

# 2. Workspace Basics

You can access MATLAB directly from your local computer (suggested) or from a standard web browser with MATLAB Online. To access MATLAB you must have a MathWorks Account and a MATLAB license (usually obtained through your university).

[Instructions on installing MATLAB:](https://www.mathworks.com/help/install/ug/install-products-with-internet-connection.html)

[Instructions on accessing MATLAB Online:](https://www.mathworks.com/help/matlab-online-server/ug/matlab-online.html)


### 2a. MATLAB Interface:

When you first open MATLAB, you will notice that it has several windows and a ribbon of buttons at the top. The window on the left is the **Current Folder**, the central window is the **Command Window**, and the upper-right window is the **Workspace**.

- **Current Folder:** Shows a list of all the folders located within the folder you are currently in. (This is essentially your window.)
  
- **Command Window:** The main area where you can type commands directly and see their output.
  
- **Editor Window:** Where you writing, running, and debugging MATLAB code
  
- **Workspace Window:** Displays variables created during the session, providing an overview of the data you are working with.

![image](https://github.com/user-attachments/assets/27b88c90-33be-4848-a7ee-04495f7446e0)


### 2b. Customization and Setting Preferences

MATLAB offers flexible customization options to optimize your workflow. Some ways to tailor the interface include...

- **Resize and Reposition Windows:** Adjust the size and position of MATLAB windows by clicking and dragging the window dividers or title bars to suit your preferences.
- **Save Frequently Used Commands :** The Favorites menu allows you to bookmark commonly used commands. Add a command by selecting 'New Favorite,' entering the command, and giving it a descriptive name. For quicker access, add these favorites to the Quick Access toolbar and execute them with a single click.
- **Display Variable Details:** To gain more insights into the variables you're working with, such as their types or memory usage, right-click the header bar in the Workspace window and choose the properties you wish to display.

For more advanced customizations, navigate to **Preferences** under the Home tab.
<img width="1000" alt="image" src="https://github.com/user-attachments/assets/cdc7c230-c22d-41e6-917a-ec8468bc5eeb">
 

### 2c. Search Path and Directories:

A **directory** is a location in the file system that can contain files and other directories (subdirectories). It's essentially a folder where files and other folders are organized.

MATLAB organizes folders and files using a directory tree, starting with the root directory (`/`).

A **path** is a string that specifies the location of a file or directory in the file system. It can be an absolute path (starting from the root of the file system) or a relative path (relative to the current directory)

- **Absolute Path:** Specifies the entire path from the root directory. E.g., `/home/user/Documents/file.txt`
- **Relative Path:** Specifies the path relative to the current directory. E.g., `Documents/file.txt` if the current directory is /home/user.

The **search path** is a subset of all the folders in the file system that MATLAB uses to locate files efficiently. The order of folders on the search path is significant: MATLAB uses the file in the folder nearest to the top when multiple files with the same name exist. For more information, see [What Is the MATLAB Search Path?](https://www.mathworks.com/help/matlab/matlab_env/what-is-the-matlab-search-path.html).


### 2d. Command Cheat Sheet


| Commands          | Description                                           |
|------------------|-------------------------------------------------------|
| **Directories and Paths**              |                               
| `pwd`            | Prints the current working directory path. |
| `cd 'folder'`    | Changes the current working directory to 'folder'. |
| `cd ~`           | Changes the current directory to the user's home directory. |
| `cd .`           | Refers to the current directory. |
| `cd ..`          | Moves up one level in the directory tree. |
| `ls`             | Lists all files and directories in the current directory. |
| `dir`            | Lists directory contents, similar to `ls`. |
| `what`           | Lists all MATLAB specific files in the current directory. |
| `mkdir 'dirname'`| Creates a new directory named 'dirname'. |
| `rmdir 'dirname'`| Removes the directory named 'dirname', if it is empty. |
| `path`           | Displays the current MATLAB search path. |
| `addpath 'folder'`| Adds the specified folder to the MATLAB search path. |
| `rmpath 'folder'`| Removes the specified folder from the MATLAB search path. |
| `savepath`       | Saves the current MATLAB search path for future sessions. |
| **Files**              |       
| `exist 'name'`   | Checks if a variable, file, or folder 'name' exists. |
| `load 'filename'`| Loads variables from a file into the workspace. |
| `save 'filename'`| Saves workspace variables to a file. |
| `type 'filename'`| Displays the contents of the specified file. |
| `which 'filename'`   | Returns the full path if the file is on the search path.           |
| `edit 'filename'`   | Opens the specified file in MATLAB's editor.           |
| **Command Help**              |       
| `doc command`    | Opens the documentation for 'command'. |
| `help command`   | Displays help text for 'command' in the Command Window. |
| `clc`            | Clears all input and output from the Command Window, keeping history. |
| `quit` or  `exit`| Closes MATLAB. |
| **Managing Workspace**              |       
| `clc`            | Clears all input and output from the Command Window, keeping history. |
| `clear`            | Clears all input and output from the Command Window, keeping history. |
| `quit` or  `exit`| Closes MATLAB. |


### 2e. Keyboard Shortcuts for MATLAB Command Window

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


### 2f. Suggested Tutorials

**[15 MIN] "The MATLAB Desktop" Module from MATLAB Desktop Tools and Troubleshooting Scripts Course (MathWorks Self-Paced Online Courses)**
This tutorial briefly reviews how to import data, customize your workspace, and set preferences.

[Tutorial Link](https://matlabacademy.mathworks.com/details/matlab-desktop-tools-and-troubleshooting-scripts/otmldts#module=2)

### 2g. Supplemental Resources 

[Documentation: Set Command Window Preferences](https://www.mathworks.com/help/matlab/matlab_env/command-window-preferences.html)

[Video: Using and Customizing the MATLAB Environment](https://www.youtube.com/watch?v=LEaT9Jp7MdQ&list=PLn0OLiymPak2HkkG-NToKdP7ye7NlpC8D&index=3)

[Documentation: Search Path](https://www.mathworks.com/help/matlab/search-path.html?s_tid=CRUX_lftnav)


# 3. MATLAB Elements and Syntax

### 3a. Basic Elements

**Comment:** A comment in MATLAB is a piece of text in a script or function that is not executed. Comments are used to explain code and are created using the percent sign. For example, `x = 10 % This is a comment` assigns 10 to x and includes a comment. You can also write a block of comments using the block comment operators % { and % }.

**Variable:** A variable in MATLAB is a storage location identified by a name that can hold different types of data such as numbers, arrays, or strings. Variables are created by assignment statements, for example, `x = 5` creates a variable x with a value of 5. 

**String:** A string is a series of characters, sometimes called a character vector or character array. Strings are created using single quotes, e.g., `str = 'hello'` creates a string variable `str` with the text `hello`.

**Array:** An array is a data structure in that can store values of the same type. Arrays are created using square brackets and can be one-dimensional (e.g., vectors) or multi-dimensional (e.g., matrices). 
- **Vector:** A vector is a one-dimensional array that can hold a sequence of variables Vectors can be either row vectors or column vectors.
  - A row vector is created by enclosing the elements in square brackets, separated by spaces or commas, e.g., 'rowVec = [1, 2, 3]' creates a 1x3 row vector.
  - A column vector is created by enclosing the elements in square brackets, separated by semicolons, e.g., 'colVec = [1; 2; 3]' creates a 3x1 column vector.
- **Matrix:** A matrix is a two-dimensional array of numbers arranged in rows and columns. Matrices are created using square brackets with rows separated by semicolons, e.g., `A = [1, 2, 3; 4, 5, 6]` creates a 2x3 matrix. 
- **String Array:**: A string array is a one-dimensional or multidimensional array that holds strings. For example, `strArray = ["Hello", "World"]` creates a 1x2 string array.

**Cell:** A cell (sometimes referred to as cell array) is a data structure in MATLAB that can hold different types of data in an array format. Each element of a cell array is called a cell, and can contain different types or sizes of data. Cell arrays are created using curly braces, e.g., `C = {1, 'text', [1, 2, 3]}` creates a 

**Structures:**
**Function:**

**Tables:**

To help you identify elements, some entries appear in different colors in the Command Window and Editor. By default:

- Keywords are blue.
- Character vectors and strings are purple.
- Unterminated character vectors are maroon.
- Comments are green.

<img width="295" alt="image" src="https://github.com/user-attachments/assets/be066590-ca88-4ac0-8d40-7ee8c90022ee">


### 3b. Special Characters 

Below are some of the key special characters you should be familiar with, including delimiters which are what the lists of variables are enclosed by when creating arrays and cells. For detailed information about other special characters, see [MATLAB Operators and Special Characters](https://www.mathworks.com/help/matlab/matlab_prog/matlab-operators-and-special-characters.html). 

**Square Brackets `[]`:** 
- A delimiter used to create arrays and matrices
  - Example: `A = [1, 2, 3])`.

**Curly Braces `{}`:**
- A delimiter used to create cells
  - Example: `C = {1, 'text', [1, 2, 3]})`.
- Indexing cells
  - Example: `cellArray{index} = newValue`.

**Parentheses `()`:**
- Group expressions
  - Examples: `a = (b + c) * d)`.
- Function arguments
  -  Example: `result = myFunction(arg1, arg2)`.
- Indexing arrays
  - Example: `element = A(row, column)`.

**Comma `,`**
- Separates elements in arrays and function arguments.
  - Example: `[1, 2, 3]` or `plot(x, y)`.
    
**Colon `:`**
- Creates vectors and specify ranges, and index arrays.
  - Example: `1:5` generates a vector `[1, 2, 3, 4, 5]`.
- The colon alone, without start or end values, specifies all of the elements in that dimension. 
  - Example: `A(:, 2)` selects all rows from the second column of matrix `A`.

**Semicolon `;`**
- Suppresses the output of a command.
  - Example: `a = 5;` assigns 5 to `a` without displaying the output.
- Separates rows in matrix definitions.
  - Example: `A = [1, 2; 3, 4]`.

**Ellipsis `...`**
- Indicates that a statement continues on the next line.
  - Example:
    ```matlab
    a = 1 + 2 + 3 + ...
        4 + 5 + 6;
    ```
**Double Percent Signs `%%`**
- Starts a code section and is typically followed by the section title
  - Example: `%% first code section` starts a section titled `first code section` without displaying the output.

### 3c. Accessing and Manipulating Elements

**Indicies**: Indices are used to specify the position of the element(s) so that you can retrieve them without processing the entire dataset. This capability enables you to easily update or modify specific elements within data structures or extract relevant portions of data for analysis or visualization.

For one-dimensional arrays or cells, you specify the element's position using a single index, which corresponds to the element's position in that dimension. For example:
  
```matlab
rowVector = [10, 20, 30, 40, 50];
thirdElement = rowVector(3);  % The 3 is an index for third element in the row, which is 30

colVector = [10; 20; 30; 40; 50];
fourthElement =colVector(4);  %  The 4 is an index for fourth element in the column, which is 40
  ```

For multi-dimensional arrays or cells, you specify the element's position using a pair of indices (or more for higher dimensions), which correspond to the element's row and column positions. For example:

```matlab
matrix = [1, 2, 3; 4, 5, 6; 7, 8, 9];
element = matrix(2, 3);  % These indicies are specifying the element in the second row and third column, which is 6
  ```

**Accessing Elements**: Access element(s) with the appropriate indicies and delimiter (e.g., parantheses or cell braces).To access a subset of elements, you must specify the range using the colon `:` operator. For example:

  ```matlab

% Vectors
v = [10, 20, 30, 40, 50];
v(2);          % Accesses the second element, result is 20
v(2:4);               % Accesses elements from the second to the fourth, result is [20, 30, 40]

% Matrices
A = [1, 2, 3; 4, 5, 6; 7, 8, 9];
A(2,1);              % Accesses the element in the second row, first column, result is 4
A(1:2, 2:3);          % Accesses a submatrix from rows 1 to 2 and columns 2 to 3, result is [2, 3; 5, 6]

% One-dimensional String Arrays
strArray = ["Hello", "World", "MATLAB"];
strArray(1);    % Accesses the first element, result is "Hello"
strArray(1:2);        % Accesses the first two elements, result is ["Hello", "World"]

% Multi-dimensional String Arrays
multiStrArray = ["Hello", "World"; "MATLAB", "Programming"];
multiStrArray(1, 2); % Accesses the element in the first row, second column, result is "World"
multiStrArray(1:2, 1); % Accesses the first column, result is ["Hello"; "MATLAB"]

% One-dimensional Cell Arrays
cellArray = {1, 'MATLAB', [2, 3, 4]};
cellArray{1};   % Accesses the first element, result is 1
cellArray{2:3};       % Accesses elements from the second to the third, result is {'MATLAB', [2, 3, 4]}

% Multi-dimensional Cell Arrays
multiCellArray = {1, 'text'; 2, 'more text'; 3, 'even more text'};
cellArray{2, 1};   % Accesses the element in the second row, first column, result is 2
multiCellArray{2:3, 2}; % Accesses elements from rows 2 to 3 in column 2, result is {'more text', 'even more text'}
  ```

**Modifying Elements**: Change element(s) by using the `=` to assign a new value to the corresponding index. 

  ```matlab
% Vectors
v = [10, 20, 30, 40, 50];
v(2) = 25;                % Modifies the second element, result is [10, 25, 30, 40, 50]
v(2:4) = [21, 31, 41];    % Modifies elements from the second to the fourth, result is [10, 21, 31, 41, 50]

% Matrices
A = [1, 2, 3; 4, 5, 6; 7, 8, 9];
A(2,1) = 40;              % Modifies the element in the second row, first column, result is [1, 2, 3; 40, 5, 6; 7, 8, 9]
A(1:2, 2:3) = [20, 30; 50, 60];  % Modifies a submatrix from rows 1 to 2 and columns 2 to 3, result is [1, 20, 30; 40, 50, 60; 7, 8, 9]

% One-dimensional String Arrays
strArray = ["Hello", "World", "MATLAB"];
strArray(1) = "Hi";       % Modifies the first element, result is ["Hi", "World", "MATLAB"]
strArray(1:2) = ["Hey", "There"];  % Modifies the first two elements, result is ["Hey", "There", "MATLAB"]

% Multi-dimensional String Arrays
multiStrArray = ["Hello", "World"; "MATLAB", "Programming"];
multiStrArray(1, 2) = "Everyone";  % Modifies the element in the first row, second column, result is ["Hello", "Everyone"; "MATLAB", "Programming"]
multiStrArray(1:2, 1) = ["Hi"; "Hello"];  % Modifies the first column, result is ["Hi", "Everyone"; "Hello", "Programming"]

% One-dimensional Cell Arrays
cellArray = {1, 'MATLAB', [2, 3, 4]};
cellArray{1} = 10;       % Modifies the first element, result is {10, 'MATLAB', [2, 3, 4]}
cellArray{2:3} = {'Hi', [5, 6, 7]}; % Modifies elements from the second to the third, result is {10, 'Hi', [5, 6, 7]}

% Multi-dimensional Cell Arrays
multiCellArray = {1, 'text'; 2, 'more text'; 3, 'even more text'};
multiCellArray{2, 1} = 20;   % Modifies the element in the second row, first column, result is {1, 'text'; 20, 'more text'; 3, 'even more text'}
multiCellArray{2:3, 2} = {'new text', 'latest text'}; % Modifies elements from rows 2 to 3 in column 2, result is {1, 'text'; 20, 'new text'; 3, 'latest text'}
  ```

### 3d. Case and Space Sensitivity

MATLAB is **case-sensitive**, meaning that variable and function names like `VariableName` and `variablename` are considered different.

Additionally, MATLAB is *somewhat* **space-sensitive**, meaning spaces around operators, assignments, and in-function calls are mostly optional and do not affect code execution. While spaces are generally not significant in MATLAB syntax, improper placement can sometimes cause errors or affect readability. For Example:

```matlab
     % These are all equivalent
     y = sin(x);
     y=sin(x);
     y = sin( x );

     % Both create the same vector    
     A = [1 2 3];
     A = [1, 2, 3];


     % These are also equivalent
     result = max( a, b );
     result=max(a,b);


     % Each would work with or without spaces    
     a=1; % No spaces
     b = 2; % With spaces
     c = 3 + 4; % With spaces around the operator
     d=3+4; % No spaces around the operator
```

However, spaces within strings and in the definition of matrices and arrays must be used correctly. For example:

 ```matlab
     str1 = 'Hello';
     str2 = 'Hello ';
     isEqual = strcmp(str1, str2); % This will be false because of the trailing space in str2


     rowVec = [1 2, 3, 4 5];  % MATLAB might not interpret this correctly due to mixed delimiters
     rowVec = [1 2   3,4, 5];  % Might still run but is hard to read and maintain

     A = [1 2 3 4 5];  % Consistent use of spaces
     B = [1, 2, 3, 4, 5];  % Consistent use of commas
  ```    

For more information, see [Case and Space Sensitivity](https://www.mathworks.com/help/matlab/matlab_prog/case-and-space-sensitivity.html)

**Code Style**: 

Note that while MATLAB allows for flexible spacing, consistent use of spaces enhances code readability and maintainability. This is especially important in collaborative environments or when sharing code with others. 

Adopting a consistent coding style, including the use of spaces, helps in maintaining clean and understandable code. MATLAB's [code analyzer](https://www.mathworks.com/help/matlab/matlab_prog/use-the-matlab-code-analyzer.html) provides guidelines and warnings to improve code quality, including spacing issues. 

### 3e. Code Suggestions and Completions
MATLAB offers real-time syntax checking and code suggestions. As you type in the Command Window or Editor, MATLAB will suggest function names, variable names, and other elements. MATLAB also indicates matched and mismatched delimiters (e.g., parentheses and brackets) and paired language keywords (e.g., for, if, while, else, and end statements). For more information, see [Check Syntax as You Type](https://www.mathworks.com/help/matlab/matlab_env/check-syntax-as-you-type.html).

### 3f. Scripts vs Functions 

**Scripts**: Scripts are collections of MATLAB commands executed exactly as if they were typed into the Command Window. They operate within the current workspace, which means they can modify any existing variables or create new ones. Scripts do not accept inputs directly (though they can work with data already in the workspace) and do not return outputs. Scripts are useful for automating a series of MATLAB commands and for writing code that does not need to be modular or reusable, like data manipulation and plotting. 

**Functions**: Functions, on the other hand, are more versatile and encapsulate their code within a separate workspace. They can accept inputs and return outputs, making them essential for modular programming. Functions prevent potential conflicts with the main workspace by keeping variables local, except those explicitly returned. They are ideal for reusing code, enhancing code readability, and managing larger projects where data encapsulation is necessary.


### 3g. Command Cheat Sheet

| Command                             | Description                                           |
|-------------------------------------|-------------------------------------------------------|
| **Viewing Elements**               |                                                       |
| `who`                               | Lists the names of all elements currently in the workspace. Does not display values.
                 |
| `whos`                              | Lists all elements in the workspace along with detailed information about each variable, such as size, bytes, class (data type), and attributes. Does not display values.        |
| `disp(element)`                    | Displays the value of the specified element.         |
| **Deleting Elements**               |     
| `clear element`                | Deletes the specified element from the workspace.    |
| `clear all`                         | Deletes all elements from the workspace.             |
| `clearvars varName1 varName2`       | Deletes specific element from the workspace.        |
| `clearvars -except varName1 var2`   | Deletes all elements from the workspace except the specified ones.      |
| **Inspecting Elements**            |                                  
| `size(element)`                | Returns the dimensions of an array.                     |
| `length(element)`              | Returns the length of the largest array dimension.    |
| `class(element)`               | Returns the class of the element.               |

### 3h. Suggested Tutorials

[Tutorial: Creating and Manipulating Arrays](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=3)

[Tutorial: Accessing Data in Arrays](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=4)


### 3i. Supplemental Materials 

[Cheat Sheet: Example of Code Syntax and Formatting](https://learnxinyminutes.com/docs/matlab/)

[Live Demo: Basic Syntax](https://www.tutorialspoint.com/matlab/matlab_syntax.htm)

[Live Demo: Variables Overview](https://www.tutorialspoint.com/matlab/matlab_variables.htm)

[Live Demo: Colon Notation](https://www.tutorialspoint.com/matlab/matlab_colon_notation.htm)

[Live Demo: Matrices](https://www.tutorialspoint.com/matlab/matlab_matrics.htm)

[Live Demo: Scripts](https://www.tutorialspoint.com/matlab/matlab_m_files.htm)

[Documentation: Matrices and Arrays](https://www.mathworks.com/help/matlab/matrices-and-arrays.html?s_tid=CRUX_lftnav)

[Documentation: Create and Run Sections in Code](https://www.mathworks.com/help/matlab/matlab_prog/create-and-run-sections.html)

[Documentation: Creating Scripts](https://www.mathworks.com/help/matlab/matlab_prog/create-scripts.html)

[Documentation: Scripts](https://www.mathworks.com/help/matlab/scripts.html?s_tid=CRUX_lftnav)

[Video: Variables for Numbers, Indexing](https://www.youtube.com/watch?v=sGb_xNsVELw&list=PLn0OLiymPak2HkkG-NToKdP7ye7NlpC8D&index=5)

[Andy's Brain Book: Navigation and Matrices](https://andysbrainbook.readthedocs.io/en/latest/Matlab/Matlab_01_Navigation.html)

# 4. Data

### 4a. Data Types

Data types (also referred to as classes) define the kind of data a variable can hold and the operations that can be performed on it. 

- **Numeric Types**
   - **double**: This is the default numeric data type in MATLAB. Suitable for general-purpose numerical computations where precision and range are important.
   - **Integer Types**: Whole numbers only, which require less memory but have less precision and limitations on certain mathematical operations compared to double.

- **Character and String Types**
   - **char**: Character arrays for storing text created using single quotes.
   - **string**: String arrays, which are more flexible than character arrays and can be created using double quotes.

- **Logical Type**
   - **logical**: Represents true or false values.


### 4b. Sets and Operators

| Operator | Description         | Example       |
|----------|---------------------|---------------|
| **Arithmetic**      |
| `+`      | Addition                 | `a + b`          |
| `-`      | Subtraction              | `a - b`          |
| `*`      | Matrix multiplication    | `a * b`          |
| `.*`     | Element-wise multiplication | `a .* b`      |
| `/`      | Matrix right division    | `a / b`          |
| `./`     | Element-wise right division | `a ./ b`      |
| `\`      | Matrix left division     | `a \ b`          |
| `.\`     | Element-wise left division | `a .\ b`      |
| `^`      | Matrix power             | `a ^ b`          |
| `.^`     | Element-wise power       | `a .^ b`         |
| `.'`     | Transpose                | `a.'`            |
| **Relational**      |
| `==`     | Equal to            | `a == b`      |
| `~=`     | Not equal to        | `a ~= b`      |
| `>`      | Greater than        | `a > b`       |
| `<`      | Less than           | `a < b`       |
| `>=`     | Greater than or equal to | `a >= b` |
| `<=`     | Less than or equal to    | `a <= b` |
| **Logical**      |
| `&`      | Logical AND         | `a & b`       |
| `|`      | Logical OR          | `a | b`       |
| `~`      | Logical NOT         | `~a`          |
| `xor`    | Logical EXCLUSIVE OR| `xor(a, b)`   |
| **Sets**      |
| `union`  | Union of two sets        | `union(a, b)`    |
| `intersect` | Intersection of two sets | `intersect(a, b)`|
| `setdiff` | Difference of two sets  | `setdiff(a, b)`  |
| `setxor`  | Symmetric difference of two sets | `setxor(a, b)`|
| `ismember` | Determine if elements are members of a set | `ismember(a, b)`|
| `unique` | Unique elements in an array | `unique(a)`      |

### 4c. Suggested Tutorials

[Tutorial: Mathematical and Statistical Operations with Arrays](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=5)

[Tutorial: Conditional Data Selection](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=7)

[Tutorial: Tables of Data](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=9)

[Tutorial: Organizing Tabular Data](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=10)

[Course: A tour of MATLAB Data Types](https://matlabacademy.mathworks.com/details/a-tour-of-matlab-data-types/otmlmdt) 

[Course: Calculations with Vectors and Matrices](https://matlabacademy.mathworks.com/details/calculations-with-vectors-and-matrices/otmlcvm)

[Course: Tables](https://matlabacademy.mathworks.com/details/tables/otmltab)

[Course: Find and Extract Subsets of Data](https://matlabacademy.mathworks.com/details/find-and-extract-subsets-of-data/otmlesd)

[Course: Clean and Prepare Data for Analyses](https://matlabacademy.mathworks.com/details/clean-and-prepare-data-for-analysis/otmlpda)

[Course: Calculations on Grouped Data](https://matlabacademy.mathworks.com/details/calculations-on-grouped-data/otmlcgd)



### 4d. Supplemental Materials 

[Video: Introducing MATLAB Fundamental Classes](https://www.mathworks.com/videos/introducing-matlab-fundamental-classes-data-types-101503.html)

[Live Demo: Data Types](https://www.tutorialspoint.com/matlab/matlab_data_types.htm)

[Live Demo: Numbers](https://www.tutorialspoint.com/matlab/matlab_numbers.htm)

[Live Demo: Strings](https://www.tutorialspoint.com/matlab/matlab_strings.htm)


[Documentation: Fundamental MATLAB Classes](https://www.mathworks.com/help/matlab/matlab_prog/fundamental-matlab-classes.html)

[Documentation: Data Types](https://www.mathworks.com/help/matlab/data-types.html)

[Documentation: Operators and Elementary Operations](https://www.mathworks.com/help/matlab/operators-and-elementary-operations.html)

[Andy's Brain Book: Variables and Structures](https://andysbrainbook.readthedocs.io/en/latest/Matlab/Matlab_02_VariablesStructures.html)


# 5. Handling Files

### 5a. MATLAB File Types:

- **.m files**: MATLAB script and function files.

- **.mlx files**: MATLAB live script files that combine code execution with narrative, formatted text, equations, images, and hyperlinks in a single, interactive document. Ideal for instructional purposes, interactive applications, and sharing results.

- **.mat files**: Binary files that store workspace variables. Useful for saving your session data and transferring variables between sessions without losing integrity.

- **.fig files**: Figure files that save MATLAB graphical outputs. They enable you to reopen and modify figures later, preserving the graphical data and properties exactly as saved.


### 5b. Importing and Exporting Files

MATLAB supports importing and exporting various data formats such as TXT, CSV, XLS, XLSX, JPG, PNG, etc. You can find additional documentation including functions and examples [here](https://www.mathworks.com/help/matlab/import_export/supported-file-formats-for-import-and-export.html).


### 5c. Commands for Handling Files
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

### 5d. Suggested Tutorials

[Lesson: Gettting Data Into MATLAB](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=2)

[Tutorial: M Files](https://www.tutorialspoint.com/matlab_m_files/index.htm)

### 5e. Supplemental Materials 

[Live Demo: Data Import](https://www.tutorialspoint.com/matlab/matlab_data_import.htm)

[Live Demo: Data Output] (https://www.tutorialspoint.com/matlab/matlab_data_import.htm)

[Quick Guide: M Files](https://tutorialspoint.com/matlab_m_files/matlab_m_files_quick_guide.htm )

[Documentation: Supported File Formats](https://www.mathworks.com/help/matlab/import_export/supported-file-formats-for-import-and-export.html)

[Documentation: Spreadsheets](https://www.mathworks.com/help/matlab/spreadsheets.html?)s_tid=CRUX_lftnav

[Documentation: Data Import and Export](https://www.mathworks.com/help/matlab/data-import-and-export.html)

[Documentation: File Operations](https://www.mathworks.com/help/matlab/file-operations.html)


[Documentation: Cloud File Storage](https://www.mathworks.com/help/matlab/cloud-file-storage.html)


# 6. Functions

### 6a. Structuring Code

Structuring your MATLAB code efficiently is crucial for readability, maintainability, and scalability. Here are some best practices:

1. **Clear Organization**: Break your code into sections using comments and the `%%` operator. This allows you to run sections independently in the MATLAB editor.
   
2. **Modular Design**: Write modular code by separating different functionalities into functions. This makes your code reusable and easier to debug.

3. **Consistent Naming Conventions**: Use meaningful and consistent naming conventions for variables, functions, and scripts. This improves code readability and helps others understand your code.

4. **Documentation**: Comment your code generously. Explain the purpose of complex sections, and use comments to describe inputs, outputs, and important variables.

5. **Avoid Magic Numbers**: Use named constants instead of hard-coding numbers in your code. This improves readability and makes your code easier to update.


### 6b. Functions

Functions allow you to encapsulate code into reusable blocks, improving code organization and reducing redundancy. In MATLAB, functions can be defined within a script or in a separate function file.

- **Defining a Function**: A function starts with the `function` keyword, followed by the output variables, the function name, and the input variables. When defining functions at the within a script file, each function must be terminated with 'end'. The use of 'end' is optional if the function is the only function in that file.


```matlab
function output = myFunction(input1, input2)
    % Function code goes here
    output = input1 + input2;
end
```

- **Calling a Function**: You can call a function by using its name and passing the required arguments.

```matlab
result = myFunction(5, 3);
```

- **Multiple Outputs**: Functions can return multiple outputs.
  
```matlab
function [out1, out2] = myFunction(input1, input2)
    out1 = input1 + input2;
    out2 = input1 * input2;
end
```

### 6c. Loops and Conditional Statements

Loops and conditional statements are fundamental constructs in programming that control the flow of execution based on conditions. You can use loops and conditional statements in scripts, command windows, or within functions. The the 'end' keyword to mark the conclusion of the loop or conditional statement.

- **For Loop**: Repeats a group of statements a fixed, predetermined number of times.

 ```matlab
  for i = 1:10
    disp(i);
end
```

- **While Loop**: Repeats a group of statements an indefinite number of times under control of a logical condition.

```matlab
i = 1;
while i <= 10
    disp(i);
    i = i + 1;
end
```

- **If-Else Statement**: Executes statements conditionally.

 ```matlab
  x = 5;
if x > 0
    disp('x is positive');
elseif x < 0
    disp('x is negative');
else
    disp('x is zero');
end
```
- **Switch-Case Statement**: Executes one set of statements from several choices.
  
 ```matlab
  switch variable
    case 1
        disp('First case');
    case 2
        disp('Second case');
    otherwise
        disp('Otherwise case');
end
```

### 6d. Troubleshooting and Debugging

Identifying and resolving errors quickly can save a significant amount of time and ensure your code runs smoothly. Here are some tips and tools for troubleshooting and debugging in MATLAB:

#### Common Errors

1. **Syntax Errors**: These occur when the MATLAB interpreter encounters code that does not conform to the syntax rules of the language. These are often caught immediately when the code is run.
  - Example: Missing end statement in loops or conditional blocks.
   
3. **Runtime Errors**: These occur during the execution of the program and are typically due to invalid operations or data.
   - Example: Division by zero, accessing an element out of array bounds.
     
4. **Logical Errors**: These occur when the code runs without any syntax or runtime errors, but the output is not as expected. These require careful inspection of the code logic.
  - Example: Incorrect implementation of an algorithm.


#### Debugging Tools and Techniques

**MATLAB Debugger**

MATLAB provides a built-in debugger to help you find and fix errors in your code. You can use the debugger to set breakpoints, step through code, inspect variables, and evaluate expressions.

- **Setting Breakpoints**: Set breakpoints at lines where you want execution to pause so you can inspect the state of your program.

- **Stepping Through Code**: Use the step commands to execute your code one line at a time.

- **Inspecting Variables**: Check the values of variables at different points in your code to ensure they contain the expected values.

- **Continuing Execution**: Continue running your code until the next breakpoint or end of the script.

- **Quitting Debug Mode**: Exit debug mode when you are finished debugging.

```matlab
% Example: MATLAB Debugger Usage

% Set a breakpoint at line 10 in myFunction
dbstop in myFunction at 10

% Step to the next line of code
dbstep

% Display the value of a variable
disp(myVar)

% Continue execution until the next breakpoint
dbcont

% Exit debug mode
dbquit
```

**Error Handling**

**Try-Catch Blocks**: Use `try-catch` blocks to catch and handle errors.

```matlab
try
    % Code that might cause an error
catch ME
    % Code to handle the error
    disp(ME.message);
end
```

**Diagnostic Functions**

- **disp() and fprintf()**: Use these functions to print variable values and messages to the Command Window for tracking the flow of your program.

- **assert()**: Use assertions to check for conditions that must be true at certain points in your program.

```matlab
disp('Debugging message');
fprintf('The value of x is: %d\n', x);
assert(x > 0, 'x must be positive');
```

#### Best Practices

1. **Incremental Development**: Develop your code in small, testable increments. Test each increment thoroughly before adding more functionality.
2. **Unit Testing**: Write unit tests for your functions to automatically verify their correctness.
3. **Code Review**: Have your code reviewed by peers to catch errors you might have missed.

### 6e. Command Cheat Sheet

| Command        | Description                                             |
|----------------|---------------------------------------------------------|
| **Loops and Conditionals**      |
| `for`          | Starts a for loop                                       |
| `while`        | Starts a while loop                                     |
| `if`           | Starts an if statement                                  |
| `elseif`       | Adds an else-if branch to an if statement               |
| `else`         | Adds an else branch to an if statement                  |
| `switch`       | Starts a switch statement                               |
| `case`         | Defines a case within a switch statement                |
| `otherwise`    | Defines the default case within a switch statement      |
| `break`        | Exits a for or while loop prematurely                   |
| `continue`     | Skips the remaining code in a loop iteration            |
| **Functions**      |
| `function`     | Defines a new function                                  |
| `end`          | Ends a function or control flow statement               |
| `nargin`       | Returns the number of function input arguments          |
| `nargout`      | Returns the number of function output arguments         |
| `varargin`     | Allows a variable number of input arguments             |
| `varargout`    | Allows a variable number of output arguments            |
| `inputname`    | Returns the name of an input argument as a string       |
| `return`       | Exits a function                                        |
| **Troubleshooting**      |
| `dbstop`       | Sets a breakpoint                                       |
| `dbclear`      | Clears breakpoints                                      |
| `dbstep`       | Executes the next line or steps into a function         |
| `dbcont`       | Continues execution until the next breakpoint           |
| `dbquit`       | Exits debug mode                                        |
| `disp`         | Displays the value of a variable                        |
| `fprintf`      | Prints formatted data to the Command Window             |
| `assert`       | Throws an error if a condition is not met               |
| `try...catch`  | Executes code and catches errors                        |
| `error`        | Throws an error and displays a message                  |
| `warning`      | Displays a warning message                              |
| `lastwarn`     | Retrieves the last warning message                      |
| `lasterr`      | Retrieves the last error message                        |
| `which`        | Identifies the path of a function or file               |

### 6f. Suggested Tutorials

[Lesson: Creating Informative Scripts](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=2)

[Tutorial: Storytelling with Scripts](https://matlabacademy.mathworks.com/details/matlab-desktop-tools-and-troubleshooting-scripts/otmldts#module=3)

[Tutorial: Structuring Code](https://www.mathworks.com/matlabcentral/fileexchange/115905-programming-structuring-code)

[Tutorial: Programming Constructs](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=14)

[Tutorial: Increasing Automation with Functions](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=15)

[Tutorial: Troubleshooting Code A](https://matlabacademy.mathworks.com/details/matlab-desktop-tools-and-troubleshooting-scripts/otmldts#module=4)

[Tutorial: Troubleshooting Code B](https://matlabacademy.mathworks.com/details/matlab-fundamentals/mlbe#module=16)

[Course: Debugging and Error Handling](https://matlabacademy.mathworks.com/details/debugging-and-error-handling/otmldeh)

[Course: The Why and How of Writing Functions](https://matlabacademy.mathworks.com/details/the-how-and-why-of-writing-functions/otmlhwf)

[Course: Make Your Functions User Friendly](https://matlabacademy.mathworks.com/details/make-your-functions-user-friendly/otmlfuf)

### 6g. Supplemental Materials

[Video: What are Functions in Matlab](https://www.mathworks.com/support/search.html/videos/managing-code-in-matlab-functions-97215.html?fq%5B%5D=asset_type_name:video&fq%5B%5D=category:matlab/programming-and-data-types&page=1)

[Video: Creating Functions in MATLAB](https://www.youtube.com/watch?v=YTQI5hIl_r4&list=PLn0OLiymPak2HkkG-NToKdP7ye7NlpC8D&index=6)

[Video: Creating For Loops](https://www.youtube.com/watch?v=Abgbu32XOh4&list=PLn0OLiymPak2HkkG-NToKdP7ye7NlpC8D&index=7) 

[Video: Stepping Into Functions](https://www.youtube.com/watch?v=aYfB4bI-9i8&list=PLn0OLiymPak2HkkG-NToKdP7ye7NlpC8D&index=9)

[Video: Common Programming Errors and their Solution](https://www.youtube.com/watch?v=_AnsdD5QNPE&list=PLn0OLiymPak2HkkG-NToKdP7ye7NlpC8D&index=10)

[Live Demo: Loops](https://tutorialspoint.com/matlab/matlab_loops.htm)

[Live Demo: Decision Making](https://www.tutorialspoint.com/matlab/matlab_decisions.htm)

[Documentation: Scripts](https://www.mathworks.com/help/matlab/scripts.html)

[Documentation: Functions](https://www.mathworks.com/help/matlab/functions.html?s_tid=CRUX_lftnav)

[Documentation: Loops and Conditional Statements](https://www.mathworks.com/help/matlab/control-flow.html)

[Documentation: Exception Handling](https://www.mathworks.com/help/matlab/exception-handling.html)

[Documentation: Live Scripts and Functions](https://www.mathworks.com/help/matlab/live-scripts-and-functions.html)

[Documentation: Error Handling](https://www.mathworks.com/help/matlab/error-handling.html?s_tid=CRUX_lftnav)

[Andy's Brain Book: Paths and Functions](https://andysbrainbook.readthedocs.io/en/latest/Matlab/Matlab_03_FunctionsPaths.html#functions)

[Andy's Brain Book: Control Structures](https://andysbrainbook.readthedocs.io/en/latest/Matlab/Matlab_04_ControlStructures.html)

