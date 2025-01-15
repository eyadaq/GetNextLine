# Get Next Line

## Project Description

**Get Next Line** is a project from the 42 curriculum that focuses on creating a function that reads a line from a file descriptor, handling cases where the line is longer than the buffer size or contains multiple lines. This project aims to improve your understanding of file I/O, memory management, and string manipulation in C.

### Objective

The objective of the project is to implement the function `get_next_line`, which reads a line from a given file descriptor and returns it. The function should handle the following scenarios:

- **End of file (EOF)**: The function should return NULL when there is no more data to read.
- **Multiple lines**: The function should read multiple lines, returning one line at a time.
- **Memory management**: Proper memory allocation and deallocation are essential. You need to manage buffer sizes dynamically.

### Key Requirements

- The function must handle multiple calls to read a file descriptor and return one line at a time.
- The file descriptor can be a regular file or stdin.
- It must be able to read lines of any size, handling the case where lines are larger than the buffer.
- Memory management must be efficient, and you must avoid memory leaks.

### Function Prototypes

```c
char *get_next_line(int fd);
