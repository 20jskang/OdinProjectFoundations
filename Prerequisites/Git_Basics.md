# Git Basics

Here we'll cover common Git commands used to manage your projects and to upload your work onto GitHub. We refer to these commands as the **basic Git workflow**. When you're using Git, these are the commands that you'll use 70-80% of the time. 

---

**Before you start**

    - GitHub recently updated the way it names the default branch. This means you need to make sure you are using a recent version of git (2.28 or later). You can check your version by running: ```git --version```
    - If you haven't already, set your local default Git branch to **main**. You can do so by running: ```git config --global init.defaultBranch main```
    - For more information on the change from **master** to **main** see [GitHub's Renaming Repository](https://github.com/github/renaming)

---

**Git Commands**

| Commands | Description |
| -------- | ----------- |
| git clone {Repository copy link SSH/HTTPS} {Destination folder} | Clones the GitHub repository to local **Destination folder**. |
| cd git_test (Followed by) git remote -v | Used to test if repository has successfully been connected to the local machine. Output should look similar to <br> ```origin git@github.com:USER-NAME/git_test.git (fetch)``` <br> ``` origin git@github.com:USER-NAME/git_test.git (push)``` |
| git status | Displays the state of current working directory and the staging area. |
| git add {file name} | Adds the {file} to the staging area in Git. The staging area is part of the two-step process for making a commit in Git. Think of the staging area as a "waiting room" for your changes until you commit them. |
| git commit -m "#Message Content" | Commits all staged files with commit message |
| git log | Shows log of all the commits on the repository |
| git push / git push origin main | Pushes all commits to GitHub |

---

## Cheat sheet

This is reference list of the most commonly used Git commands. Try to familiarize yourself with the commands so that you can eventually remember them all:

    Commandsrelated to a remote repository:
        - git clone git@github.com:USER-NAME/REPOSITORY-NAME.git
        - git push or git push origin main

    Commands related to the workflow:
        - git add.
        - git commit -m "A message describing what you have done to make this snapshot different"
    
    Commands related to checking status or log history
        - git status
        - git log

