# Command Lines

---

## What is a Shell?

Humans and computers commonly interact in many different ways, such as through a keyboard and mouse, touch screen interfaces, or using speech recognition systems. The most widely used way to interact with personal computers is called a graphical user interface (GUI). With GUI, we give instructions by clicking a mouse and using menu-driven interactions.

While the visual aid of a GUI makes it intuitive to learn, this way of interacting scales very poorly with some tasks.

A **command-line interface (CLI)** allows users to interact with a computer by reading and writing text. It excels at making repetitive tasks automatic and fast.

A **shell** is a particular program that lets you type commands. We'll be using "Bash" which is the most popular Unix Shell to learn the CLI commands. Bash is often the default shell on Unix and in Unix-like tools for Windows.

### Why use the shell?

The shell can be used for simple tasks like creating an empty folder and for launching (even complex) programs with a single command. In fact, some tools are resources such as cloud computing systems usually require users to be familiar with the shell. Shell commands can be combined and saved into reproducible scripts that automate repetitive tasks.

Using the shell will take some effort and some time to learn. While a GUI presents you with choices to select, CLI choices are not automatically presented to you. It can be daunting at first, but once you've come familiar with this different style of interacting, you will be able to efficiently accomplish a huge variety of tasks.

---

## Let's get started

When the shell is first opened, you are represented with a **prompt**, indicating that shell is waiting for input.

The shell typically uses **$** as the prompt, but may use a different symbol. 

Note that some prompt might look a little different. In particular, most popular shell environment by default put your username and the host name before the $. 

Basic command lines table:

| CLI Command | Action |
| ----------- | ------ |
| ls | This command will list the contents of the current directory |
| ls -F | **-F option** tells **ls** to classify the output by adding a marker to file and directory names to indicate what they are. a) a trailing **/** indicates that this is a directory b) **@** indicates a link c) **\*** indicates an executable |
| ls -a | Shows all files including hidden ones |
| ls -s | Display the size of files and directories alongside the names |
| ls -S | Sort the files and directories by size |
| pwd | Stands for '**print working directory**'. Shows current working directory |
| clear | Clears the terminal. |
| clear -x | Clears the terminal and still allows access to previous commands by using the up and down arrow key |
| cd {directory} | Stands for 'change directory', it changes the shell's current working directory. If just inputted without any argument following the command, it sets the home directory as the working directory |
| cd .. | Move's back a directory by one level |
| mkdir {name} | Makes directory in the current working directory |
| mkdir -p | **-p** option allows **mkdir** to create a directory with nested subdirectories in a single operation |
| nano {name}.txt | **nano** is a text editor. It can only work with plain character data, not tables, images, or any other human-friendly media. |
| mv {directory}/{name}.txt {directory}{name}.txt | **mv** argument allows us to move the first argument **dir/example.txt** to move to the another location **dir2/example2.txt**. In this process it allows us to rename the file name as well. If we were to keep it in the same directory but save it as a new txt name, it will work as the same as to renaming the file. It will silently overwrite any existing file with the same name, which could lead to data loss. So use with caution! |
| cp | **cp** command works very much like mv, except it copies a file instead of moving it |
| cp -r | **-r** or **--recursive** option for cp applies the command not just to the specified directory but to all of it's content |
| rm {file} | Removes the file from the directory |
| rm -r {directory} | **-r** to remove a directory |
| touch {file} | Used to create or update files |


---

## File System Structure

<p align="center">
  <img src="assets/fileSystemExample.png" alt="fileSystem Example">
</p>

The filesystem looks like an upside down tree. The topmost directory is the **root directory** that holds everything else. We refer to it using a slash character, **/**, on its own; this character is the leading slash in **/Users/JohnDoe**.

Inside that directory are several other directories: **bin** (which is where some built in programs are stored), **data** (for miscellaneous data files), **Users** (where users' personal directories are located), **tmp** (for temporary files that don't need to be stored long-term), and so on.

We know that our current working directory **/Users/JohnDoe** is stored inside **/Users** because **/Users** is the first part of its name. Similarly, we know that **/Users** is stored inside the root directory **/** because the name begins with **/**. 