# Fundamentals of Git

Git is like a **super save button** for your files and directories. Officially, Git is a version control system.

A save in a text editor records all of the words in a document as a single file. You are only ever given one record of the file, such as an **essay.doc&**, unless you make a duplicate of the copies (which is difficult to remember to do and keep track of):

    **essay1.doc**, **essay2.doc**, **essay3.doc** 

However, a save in a Git records differences in the files and folders AND keeps a **historical record of each save**. This feature is a game changer. As an individual developer, Git enables you to review how your project grows and to easily look at or restore file states from the past. Once connected to a network, Git allows you to push your project to GitHub or other alternatives such as: Bitbucket, Beanstalk, or GitLab for sharing and collaborating with other developers.

---

## About Version Control

What is a "version control", and why should you care?

Version control is a system that records changes to a file or set of files over time sot that you can recall specific versions later. 

If you are a graphic or web designer and want to keep every version of an image or layout (which you would most certainly want to), a Version Control System (VCS) is a very wise thing to use. It allows you to revert selected files back to previous state, revert the entire project back to a previous state, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more. Using a VCS also generally means that if you screw things up or lose files, you can easily recover. In addition, you get all this for very little overhead.

---

### Local Version Control System

Many people's version-control method of choice is to copy files into another directory (perhaps a time-stamped directory). This approach is very common because it is simple, but it is also incredibly error-prone. It is easy to forget which directory you're in and accidentally write to the wrong file or copy over files you don't mean to.

To deal with this issue, programmers long ago developed a local VCSs that had a simple database that kept all the changes to files under revision control.

<p align="center">
    <img src="/Prerequisites/assets/localVCS.png" alt="Local VCS">
    <p>Figure 1. Local version control diagram</p>
 </p>

One of the most popular VCS tools was a system called RCS, which is still distributed with many computers today. RCS works by keeping patch sets (that is, the differences between files) in a special format on disk; it can then re-create what any file looked like at any point in time by adding up all the patches.

---

### Centralised Version Control Systems

The next major issue that people encounter is that they need to collaborate with developers on other systems. To deal with this problem, Centralised Version Control System (CVCS) were developed. These systems (such as CVS, Subversion, and Perforce) have a single server that contains all the versioned files, and a number of clients that check out files from that central place. For many years, this has been the standard for version control.

<p align="center">
    <img src="/Prerequisites/assets/centralisedVCS.png" alt="Centralised VCS">
    <p>Figure 2. Centralised version control system</p>
 </p>

 This setup offers many advantages, especially over local VCSs. For example, everyone knows to a certain degree what everyone else on the project is doing. Admins have fine-grained control over who can do what, and it's far easier to administer a CVCS than it is to deal with local databases on every client.

 However, this setup also has some serious downsides. The most obvious is the single point of failure that the centralised server represents. If that server goes down for an hour, then during that hour nobody can collaborate at all or save versioned changes to anything they're working on. If the hard disk the central database is on becomes corrupted, and proper backups haven't been kept, you lose absolutely everything - the entire history of the project except whatever single snapshots people happen to have on their local machine. Local VCSs suffer from this same problem - whenever you have the entire history of the project in a single place, you risk losing everything.

---

 ### Distributed Version Control Systems

 This is where Distributed Version Control System (DVCSs) step in. In a DVCS (such as Git, Mercurial or Darcs), clients don't just check out the latest snapshot of the files; rather, they fully mirror the repository, including its full history. Thus, if any server dies, and these systems were collaborating via that server, any of the client repositories can be copied back up to the server to restore it. Every clone is really a full backup of all the data.

 <p align="center">
    <img src="/Prerequisites/assets/distributedVCS.png" alt="Distributed VCS">
    <p>Figure 3. Distributed version control system</p>
 </p>


Furthermore, many of these systems deal pretty well with having several remote repositories they can work with, so you can collaborate with different groups of people in different ways simultaneously within the same project. This allows you to set up several types of workflows that aren't possible in centralised system, such as hierarchical models.

---

## A Short History of Git

As with many great things in life, Git began with a bit of creative destruction and fiery controversy.

The Linux kernel is an open source software project of fairly large scope. During the early years of the Linux kernel maintenance (1991-2002), changes to the software were passed around as patches and archived files. In 2002, the Linux kernel project began using a proprietary DVCS called BitKeeper.

In 2005, the relationship between the community that developed the Linux kernel and the commercial company that developed BitKeeper broke down, and the tool's free-of-charge status was revoked. This prompted the Linux development community (and in particular Linus Torvalds, the creator of Linux) to develop their own tool based on some of the lessons they learned while using BitKeeper. Some of the goals of the new system were as follows:

    - Speed
    - Simple design
    - Strong support for non-linear development (thousands of parallel branches)
    - Fully distributed
    Able to handle large projects like the Linux kernel efficiently (speed and data size)

Since its birth in 2005, Git has evolved and matured to be easy to use and yet retain these initial qualities. It's amazingly fast, it's very efficient with large project, and it has an incredible branching system for non-linear development (more about [Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell#ch03-git-branching))

---

## What is Git?

So, what is Git in a nutshell? This is an important section to absorb, because if you understand what Git is and the fundamentals of how it works, then using Git effectively will probably be much easier for you.

**Snapshots, Not Differences**
The major difference between Git and any other VCS is the way Git thinks about its data. Conceptually, most other systems store information as a list of file-based changes. These other systems think of information they store as a set of files and the changes made to each file over time (commonly described as delta-based version control).


 <p align="center">
    <img src="/Prerequisites/assets/checkinsOverTime1.png" alt="Checkins Over Time 1">
    <p>Figure 4. Storing data as changes to a base version of each filem</p>
 </p>

 Git doesn't think of or store its data this way. Instead, Git thinks of its data more like a series of snapshots of a miniature file system. With Git, everytime you commit, or save the state of your project, Git basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot. To be efficient, if files have not changes, Git doesn't store the file again, just to link to the previous identical file it has already stored. Git thinks about its data more like a **stream of snapshots**.

 <p align="center">
    <img src="/Prerequisites/assets/checkinsOverTime2.png" alt="Checkins Over Time 2">
    <p>Figure 5. Storing data as snapshots of the project over time</p>
 </p>

 This is an important distinction between Git and nearly all other VCSs. It makes Git reconsider almost every aspect of version control that most other systems copied from the previous generation. This makes Git more like a mini filesystem with some incredibly powerful tools built on top of it, rather than simply a VCS. 

 **Nearly Every Operation Is Local**

Most operation in Git need only local files and resources to operate - generally no information is needed from another computer on your network. If you're used to a CVCS where most operations have that network latency overhead, this aspect of Git will make you think that the gods of speed have blessed Git with unworldly powers. Because you have the entire history of the project right there on your local disk, most operations seem almost instantaneous.

For example, to browse the history of a project, Git doesn't need to go out to the server to get the history and display it for you - it simply reads it directly from your local database. This means you see the project history almost instantly. If you want to see the changes introduced between the current version of a file and the file a month ago, Git can look up the file a month ago and do a local difference calculation, instead of having to either ask a remote server to do it or pull an older version of the file from the remote server to do it locally.

This also means that there is very little you can't do if you're offline or off VPN. If you get on an airplane or a train and want to do a little work, you can commit happily (to your local copy) until you get to a network connection to upload. If you go home and can't get your VPN client working properly, you can still work. In many other systems, doing so is either impossible or painful.

**Git Has Integrity**

Everything in Git is checksummed before it is stored and is then referred to by that checksum. This means it's impossible to change the contents of any file or directory without Git knowing about it. This functionality is built into Git at the lowest levels and is integral to its philosophy. You can't lose information in transit or get file corruption without Git being able to detect it.

The mechanism that Git uses for the checksumming is called a SHA-1 hash. This is a 40-character string composed of hexadecimal characters (0-9 and a-f) and calculated based on the contents of a file or directory structure in Git.

You will see these hash values all over the place in Git because it uses them so much. In fact, Git stores everything in its database not by file name but by the has value of its contents.

**Git Genrally Only Adds Data**

When you do actions in Git, nearly all of them only add data to the Git database. It is hard to get the system to do anything that is not undoable or to make it erase data in any ways. As with any VCS, you can lose or mess up changes you haven't committed yet, but after you commit a snapshot into Git, it is very difficult to lose, especially if you regularly push your database to another repository.

**The Three States**

Pay attention! Now, here is the main thing to remember about Git if you want the rest of the learning process to go smoothly. Git has three main states that your files can reside in: modified, staged, and committed:

    - Modified means that you have changed the file but have not committed it to your database yet.
    - Staged means that you have marked a modified file in its current version to go into your commit snapshot.
    - Committed means that the data is safely stored in your local database.

This leads us to the three main sections of a Git project: the working tree, the staging area, and the Git directory

 <p align="center">
    <img src="/Prerequisites/assets/workingTree.png" alt="Git Working Tree">
    <p>Figure 6. Working tree, staging area, and Git directory</p>
 </p>

 The working tree is a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on a disk for you to use or modify.

 The staging area is a file, generally contained in your Git directory, that stores information about what will go into your next commit. Its technical name in Git parlance is the "index", but the phrase "staging area" works just as well.

 The Git directory is where Git stores the metadata and object database for your project. This is the most important part of Git, and it is what is copied when you clone a repository from another computer.

 The basic Git workflow goes:

    1. You modify files in your working tree.
    2. You selectively stage just those changes you want to be part of your next commit, which adds only those changes to the staging area.
    3. You do a commit, which takes the files as they are in the staging area and stores that snapshot permanetly to your Git repository.

If a particular version of a file is in the Git directory, it's considered committed. If it has been modified and was added to the staging area, it is staged. And if it was changed since it was checked out but has not been staged, it is modified.

---

## About GitHub

GitHub is a cloud-based platform where you can store, share, and work together with others to write code.

Storing your code in a "repository" on GitHub allows you to:

    - Showcase or share your work
    - Track and manage changes to your code over time
    - Let others review your code, and make suggestions to improve it
    - Collaborate on a shared project, without worrying that your changes will impact the work of your collaborators before you're ready to integrate them

Collaborative working, one of GitHub's fundamentals features, is made possible by the open-source software, Git, upon which GitHub is built.

---

## About Git

Git is a version control system that intelligently tracks changes in files. Git is particularly useful when you and a group of people are all making changes to the same files at the same time.

Typically, do this in a Git-based workflow, you would:

    - Create a branch off from the main copy of files that you (and your collaborators) are working on
    - Make edits to the files independetly and safely on your own personal branch
    - Let Git intelligently merge your specific changes back into the main copy of files, so that your changes don't impact other people's updates
    - Let Git keep track of your and other people's changes, so you al lstay working on the most up-to-date version of the project


---

## How does GitHub and Git work together

When you upload files to GitHub, you'll store them in a "Git repository". This means that when you make changes ("commits") to your files in GitHub, Git will automatically start to track and mange your changes. 

There are plenty of Git-related actions that you can complete on GitHub directly in your browser, such as creating a Git repository, creating branches, and uploading editing files.

However, most people work on their files locally (on their own computer), then continually sync these local changes - and all the related Git data - with the central "remote" repository on GitHub.
There are plenty of tools that you can use to do this, such as GitHub Desktop.

Once you start to collaborate with others and all need to work on the same repository at the same time, you'll continually:

    - Pull all the latest changes made by your collaborators from the remote repository on GitHub
    - Pull back your own changes to the same remote repository on GitHub

Git figures out how to intelligently merge this flow of changes, and GitHub helps your manage the flow throughout features such as "pull request".