# **FileIO & Exceptions**

- Files on most modern file systems are composed of three main parts:

1. *Header: metadata about the contents of the file (file name, size, type, and so on)*
2. *Data: contents of the file as written by the creator or editor*
3. *End of file (EOF): special character that indicates the end of the file*

**File Paths**:

-   - *Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)*

-   - *File Name: the actual name of the file*

-   - *Extension: the end of the file path pre-pended with a period (.) used to indicate the file type*

## **Opening and Closing a File in Python:-**

1. *open file in python  `file = open('file.txt')`*

2. *'r' Open for reading (default)*

3. *'w' Open for writing, truncating (overwriting) the file first*

4. *'rb' or 'wb' Open in binary mode (read/write using byte data)*

### **file objects categories:**

1. *Text files*

2. *Buffered binary files*

3. *Raw binary files*

*The `__file__`attribute is a special attribute of modules, similar to `__name__`.*

## **Python Exceptions**

- *Exceptions versus Syntax Errors*
*Syntax errors occur when the parser detects an incorrect statement.*

- *exception error This type of error occurs whenever syntactically correct Python code results in an error.* 

## **Raising an Exception**

*We can use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.*

## **The AssertionError Exception**

*Instead of waiting for a program to crash midway, we  can also start by making an assertion in Python.*

**then** :

- **raise** *to throw an exception at any time*.

- **assert** *to verify if a certain condition - is met and throw an exception if it isn’t*.

- **try**  *all statements are executed until an exception is encountered*.

- **except** *to catch and handle the exception(s) that are encountered in the try clause*.

- **else** *that should run only when no exceptions are encountered in the try clause*.