# Command Lines

---

# What is a Shell?

Humans and computers commonly interact in many different ways, such as through:
- a keyboard and mouse
- touch screen interfaces
- speech recognition systems

The most widely used way to interact with personal computers is called a **graphical user interface (GUI)**.

With a GUI, we give instructions by:
- clicking a mouse
- using menu-driven interactions

While the visual aid of a GUI makes it intuitive to learn, this way of interacting scales very poorly with some tasks.

A **command-line interface (CLI)** allows users to interact with a computer by reading and writing text.

It excels at making repetitive tasks automatic and fast.

A **shell** is a particular program that lets you type commands.

We'll be using **Bash**, which is the most popular Unix Shell, to learn CLI commands.

Bash is often the default shell on Unix and in Unix-like tools for Windows.

---

## Why use the shell?

The shell can be used for:
- simple tasks like creating an empty folder
- launching complex programs with a single command

In fact, some tools and resources such as cloud computing systems usually require users to be familiar with the shell.

Shell commands can be:
- combined together
- saved into reproducible scripts
- used to automate repetitive tasks

Using the shell will take some effort and time to learn.

While a GUI presents you with choices to select, CLI choices are not automatically presented to you.

It can feel daunting at first, but once you become familiar with this style of interaction, you will be able to efficiently accomplish a huge variety of tasks.

---

# Let's get started

When the shell is first opened, you are presented with a **prompt**, indicating that the shell is waiting for input.

The shell typically uses:

```bash
$
```

as the prompt, but it may use a different symbol.

Some prompts may look slightly different.

Most popular shell environments display:
- your username
- the host name
- followed by the `$`

---

# Basic Command Lines Table

| CLI Command | Action |
| ----------- | ------ |
| `ls` | Lists the contents of the current directory |
| `ls -F` | `-F` option tells `ls` to classify output by adding markers to file and directory names:<br><br>- `/` indicates a directory<br>- `@` indicates a link<br>- `*` indicates an executable |
| `ls -a` | Shows all files including hidden ones |
| `ls -s` | Displays the size of files and directories alongside their names |
| `ls -S` | Sorts files and directories by size |
| `pwd` | Stands for **print working directory**. Shows the current working directory |
| `clear` | Clears the terminal |
| `clear -x` | Clears the terminal while still allowing access to previous commands using the arrow keys |
| `cd {directory}` | Stands for **change directory**. Changes the shell's current working directory. If used without an argument, it changes to the home directory |
| `cd ..` | Moves back one directory level |
| `mkdir {name}` | Creates a directory in the current working directory |
| `mkdir -p` | `-p` option allows `mkdir` to create nested subdirectories in a single operation |
| `nano {name}.txt` | `nano` is a text editor. It works only with plain character data, not tables, images, or other media |
| `mv {directory}/{name}.txt {directory}/{name}.txt` | `mv` moves files from one location to another. It can also rename files. Be careful: it silently overwrites existing files with the same name |
| `cp` | Copies files instead of moving them |
| `cp -r` | `-r` or `--recursive` applies `cp` to directories and all their contents |
| `rm {file}` | Removes a file |
| `rm -r {directory}` | Removes a directory recursively |
| `touch {file}` | Creates or updates files |

---

# File System Structure

<p align="center">
  <img src="assets/fileSystemExample.png" alt="fileSystem Example">
</p>

The filesystem looks like an upside-down tree.

The topmost directory is called the **root directory**, which contains everything else.

We refer to it using:

```bash
/
```

This slash is also the leading slash in paths such as:

```bash
/Users/JohnDoe
```

Inside the root directory are several other directories:

- `bin` → built-in programs
- `data` → miscellaneous data files
- `Users` → user personal directories
- `tmp` → temporary files

and many more.

We know that our current working directory:

```bash
/Users/JohnDoe
```

is stored inside:

```bash
/Users
```

because `/Users` is the first part of the path.

Similarly, we know that:

```bash
/Users
```

is stored inside the root directory:

```bash
/
```

because the path begins with `/`.