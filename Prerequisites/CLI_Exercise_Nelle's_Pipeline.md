# Exercise 

To practice using the CLI commands, we're going to follow an exercise provided in the Unix Shell course designed by the Software Carpentry Foundation.

The resources we'll be using have been unzipped and added to the project folder at: 

```bash
OdinProjectFoundations/shell-lesson-data
```

---

## Nelle’s Pipeline: A Typical Problem

Nelle Nemo, a marine biologist, has just returned from a six-month survey of the North Pacific Gyre, where she has been sampling gelatinous marine life in the Great Pacific Garbage Patch.

She has **1520 samples** that she’s run through an assay machine to measure the relative abundance of **300 proteins**.

She needs to run these 1520 files through an imaginary program called:

```bash
goostats.sh
```

In addition to this huge task, she has to write up results by the end of the month so her paper can appear in a special issue of *Aquatic Goo Letters*.

If Nelle chooses to run `goostats.sh` by hand using a GUI, she’ll have to select and open a file **1520 times**.

If `goostats.sh` takes **30 seconds** to run each file, the whole process will take more than **12 hours** of Nelle’s attention.

With the shell, Nelle can instead assign her computer this mundane task while she focuses her attention on writing her paper.

The next few lessons will explore the ways Nelle can achieve this.

More specifically, the lessons explain how she can use a command shell to run the `goostats.sh` program, using loops to automate the repetitive steps of entering file names, so that her computer can work while she writes her paper.

As a bonus, once she has put a processing pipeline together, she will be able to use it again whenever she collects more data.

---

## In order to achieve her task, Nelle needs to know how to:

- navigate to a file/directory
- create a file/directory
- check the length of a file
- chain commands together
- retrieve a set of files
- iterate over files
- run a shell script containing her pipeline

---

# Nelle's Pipeline: Organising Files

Knowing this much about files and directories, Nelle is ready to organise the files that the protein assay machine will create.

She creates a directory called:

```bash
north-pacific-gyre
```

This directory will contain:
- the data files from the assay machine
- her data processing scripts

Each of her physical samples is labelled according to her lab’s convention with a unique ten-character ID, such as:

```text
NENE01729A
```

This ID is what she used in her collection log to record the location, time, depth, and other characteristics of the sample, so she decides to use it within the filename of each data file.

Since the output of the assay machine is plain text, she will call her files:

```text
NENE01729A.txt
NENE01812A.txt
```

and so on.

All 1520 files will go into the same directory.

---

## Listing Files

Now in her current directory:

```bash
shell-lesson-data
```

Nelle can see what files she has using the command:

```bash
ls north-pacific-gyre/
```

---

# Tab Completion

This command is a lot to type, but she can let the shell do most of the work through what is called **tab completion**.

If she types:

```bash
ls nor
```

and then presses `Tab` on her keyboard, the shell automatically completes the directory name for her:

```bash
ls north-pacific-gyre/
```

Pressing `Tab` again does nothing since there are multiple possibilities.

Pressing `Tab` twice brings up a list of all matching files.

---

## More Tab Completion

If Nelle then presses `G` and then presses `Tab` again, the shell will append:

```text
goo
```

since all files that start with `g` share the first three characters `goo`.

```bash
ls north-pacific-gyre/goo
```

To see all of those files, she can press `Tab` twice more.

```bash
ls north-pacific-gyre/goo

goodiff.sh
goostats.sh
```

This is called **tab completion**, and we will see it in many other tools as we go on.
