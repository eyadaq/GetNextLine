# 📄 get_next_line

## 📌 Table of Contents
- [Introduction](#introduction)
- [Project Objectives](#project-objectives)
- [Function Prototype](#function-prototype)
- [How It Works](#how-it-works)
- [Constraints](#constraints)
- [Compilation](#compilation)
- [Usage](#usage)
- [Implementation Overview](#implementation-overview)
- [Resources](#resources)

---

## 🧩 Introduction

**get_next_line** is a project at 42 school that teaches you how to read a file or input line by line. You must return a new line from a file descriptor every time the function is called, keeping track of the buffer between calls.

---

## 🎯 Project Objectives

- Learn how to manage static variables and memory.
- Handle partial reads and buffer management.
- Understand how file descriptors behave.
- Write clean, modular code that handles edge cases and errors.

---

## 🧪 Function Prototype

```c
char *get_next_line(int fd);
````

* Reads from file descriptor `fd`.
* Returns the next line (including the newline character).
* Returns `NULL` on EOF or error.

---

## ⚙️ How It Works

1. Reads from `fd` into a buffer.
2. Saves leftover characters after newline using a static variable.
3. Allocates and returns a line up to and including `\n`.
4. Frees memory appropriately on error or EOF.

---

## ❗ Constraints

* You must use a buffer of size `BUFFER_SIZE`, defined at compilation.
* Only one static variable is allowed per file descriptor.
* You are not allowed to use global variables.
* The function should work for multiple file descriptors at once.

---

## 🛠 Compilation

To compile `get_next_line.c` with your main:

```bash
gcc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c main.c
```

Change `BUFFER_SIZE` to any value to test behavior.

---

## 🚀 Usage

Example usage in `main.c`:

```c
#include <fcntl.h>
#include <stdio.h>

int main(void)
{
    int fd = open("file.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }
    close(fd);
    return 0;
}
```

---

## 🧠 Implementation Overview

* `get_next_line.c`:

  * Handles reading, extracting lines, and storing leftovers.
* `get_next_line_utils.c`:

  * Custom versions of `strlen`, `strchr`, `strjoin`, `strdup`, etc.
* Key functions:

  * `read()` to fill buffer.
  * `strchr()` to find newline.
  * `strjoin()` to concatenate strings.
  * `strdup()` to copy results.

---

## 📚 Resources

* `man 2 read`, `man open`, `man close`, `man malloc`, `man free`
* 42 Community GitHub and forums
* [https://harm-smits.github.io/42docs/projects/get\_next\_line](https://harm-smits.github.io/42docs/projects/get_next_line)

---

> 🛠 Project developed as part of the 42 Network to master file I/O and memory handling in C.

```
