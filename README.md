
<div align="center">
  <h2>my libft</h2>
  <img src="./bin/my_libft.png"  />
  <br>
</div>

![Language](https://img.shields.io/badge/language-C-blue)
![Status](https://img.shields.io/badge/status-maintained-brightgreen)
![42](https://img.shields.io/badge/origin-42-black)
![License](https://img.shields.io/badge/license-MIT-yellow)

> A **custom C standard library**, based on **42 school projects** (`libft`, `ft_printf`, `get_next_line`)  
> and extended with additional utility functions.  
> This repository is maintained and evolves to serve as a **personal C toolbox**.

---

## 📖 Table of Contents
- [Description](#-description)
- [Features](#-features)
- [Installation](#%EF%B8%8F-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Examples](#-examples)
- [Roadmap](#-roadmap)
- [Credits](#-credits)
- [License](#-license)

---

## 📝 Description
`my-libft` is a **C library** regrouping several projects from the 42 curriculum and beyond:  

- **libft** → reimplementation of essential libc functions (`strlen`, `strdup`, `atoi`, …)  
- **ft_printf** → custom implementation of `printf`  
- **get_next_line** → function that reads a line from a file descriptor  
- **extras** → additional helpers and utilities (string manipulation, memory management, etc.)  

It provides a strong foundation for building larger C projects while keeping code **clean, reusable, and modular**.

---

## ✨ Features
List of functions:

### 🔤 Character checks & conversions
- `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`
- `ft_tolower`, `ft_toupper`, `**ft_strrstr**`

### 🧵 String functions
- `ft_strlen`, `ft_strlcpy`, `ft_strlcat`
- `ft_strncmp`, `ft_strchr`, `ft_strrchr`, `ft_strnstr`
- `ft_strdup`, `ft_strjoin`, `ft_strtrim`, `ft_split`
- `ft_substr`, `**ft_strjoin_free**`

### 💾 Memory functions
- `ft_memset`, `ft_memcpy`, `ft_memmove`
- `ft_memchr`, `ft_memcmp`
- `ft_bzero`, `ft_calloc`

### 🔢 Conversions
- `ft_atoi`, `ft_itoa`, `**ft_atod**`

### 🖊 File descriptors
- `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`

### 🔗 Linked list utilities
- `ft_lstnew`, `ft_lstadd_front`, `ft_lstadd_back`
- `ft_lstsize`, `ft_lstlast`
- `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`

### 🖨 **ft_printf**  
  - Handles `%c`, `%s`, `%p`, `%d`, `%i`, `%u`, `%x`, `%X`, `%%`  

### 📜 **get_next_line** (4 versions see more in Usage) 
  - Reads from file descriptor line by line  
  - Handles multiple file descriptors 
---

## ⚙️ Installation
Requirements:  
- OS: Linux or macOS  
- C compiler (gcc, clang)  
- `make`

```bash
git clone https://github.com/LogUmi/my-libft.git
cd my-libft
make
```
This will generate a `libft.a` file.

---

## 🖥 Usage
To use `my-libft` in your own project, compile it and link it:

```bash
gcc main.c -L. -lft -o my_program
```
or
```bash
gcc main.c libft.a -o my_program
```
> ⚠️ If you need the `ft_atod` function, don't forget to add the `-lm` flag (linking math.h) to your `gcc` or `clang` command line.

In your source files, include the header:

```c
#include "libft.h"
```
> ⚠️ **About `get_next_line`**  
> This repository maintains **4 versions**:  
> - **Static allocation**  
>   - `get_next_lines` → single file descriptor  
>   - `get_next_linesm` → multiple file descriptors  
>   *(check in the `.h` that `BUFFER_SIZE` and `STATIC_SIZE` are relevant; no `free` is needed on the returned string)*  
> - **Dynamic allocation**  
>   - `get_next_lined` → single file descriptor  
>   - `get_next_linedm` → multiple file descriptors  
>   *(you must `free` the returned string after use)*  

---

## 📂 Project Structure

```
.
├── img/                # Content for README
├── includes/           # Header files (.h)
├── srcs/               # Source code (.c)
├── Makefile
└── README.md
```

---

## 🔎 Examples

```c
#include <stdio.h>
#include "libft.h"

int	main(int argc, char *argv[])
{
	int	i;
	
	i = argc - 1;
	if (argc <= 1)
		return (0);
	while (i > 0)
	{
		printf("%s has %lu characters\n", argv[i], ft_strlen(argv[i]));
		i--;
	}
	return (0);
}
```
then compile & run:
```bash
gcc main.c libft.a -o my_program
./my_program string1 "string2" anotherstring
```
Example output:
```
anotherstring has 13 characters
string2 has 7 characters
string1 has 7 characters
```

---

## 🚀 Roadmap
This project is the original version that was evaluated at 42 and will remain in this state.  
A maintained implementation of this project continues to live on through **my libft**.

---

## 👤 Credits
Project developed by **Loïc Gérard** – 📧 Contact: lgerard@studend.42perpignan.fr - [École 42 Perpignan](https://42perpignan.fr).

---

## 📜 License
This project is licensed under the MIT License. You are free to use, modify, and distribute it.

> ⚠️ **Note for students**  
> If you are a student at 42 (or elsewhere), it is strongly recommended **not to copy/paste** this code.  
> Instead, try to **write your own solution** — it’s the only way to really learn and succeed.
