# Git

Git is a very popular version control system. A Version Control System (VCS) is a software that tracks and manages changes to files over time, allowing multiple people to collaborate on projects without overwriting each other's work. It records every modification, allowing users to compare versions, review history, and revert to previous states if errors occur.

GitHub is a service that allows you to upload, host, and manage code using Git with a nice web interface.

Even though GitHub and Git sound similar, they are not the same or even created by the same company.

## Assignment

### Install Git

1. Depending on the OS you are running, follow the appropriate Git installation guide below:
   - [Linux](https://github.com/TheOdinProject/curriculum/blob/main/foundations/installations/installation_guides/git/linux.md)
   - [MacOS](https://github.com/TheOdinProject/curriculum/blob/main/foundations/installations/installation_guides/git/macos.md)
   - [ChromeOS](https://github.com/TheOdinProject/curriculum/blob/main/foundations/installations/installation_guides/git/chromeos.md)

### Configure Git and GitHub

1. Go to [GitHub.com](https://github.com/) and create an account! During the account setup, it will ask you for an email address. This needs to be a real email, and will be used by default to identify your contributions.

2. For Git to work properly, we need to let it know who we are so that it can link a local Git user (you) to GitHub. When working on a team, this allows people to see what you have committed and who committed each line of code.

   The commands below will configure Git. Be sure to enter your own information inside the quotes (but include the quotation marks!)

   ```bash
   git config --global user.name "Your.name"
   git config --global user.email yourname@example.com
   ```

   GitHub recently changed the default branch on new repositories from **master** to **main**. Change the default branch for Git using this command:

   ```bash
   git config --global init.defaultBranch main
   ```

   To verify that things are working properly, enter these commands and verify whether the output matches your name and email address.

   ```bash
   git config --get user.name
   git config --get user.email
   ```

   #### For macOS Users

   Run these commands to tell Git to ignore `.DS_Store` files, which are automatically created when you use Finder to look into a folder.

   `.DS_Store` files are invisible to the user and hold custom attributes or metadata (like thumbnails) for the folder, and if you don't configure Git to ignore them, pesky `.DS_Store` files will show up in your commits.

   ```bash
   echo .DS_Store >> ~/.gitignore_global
   git config --global copre.excludesfile ~/.gitignore_global
   ```

3. Create an SSH key, which is a cryptographically secure identifier. It's like a really long password used to identify your machine. GitHub uses SSH keys to allow you to upload to your repository without having to type in your username and password every time.

   > **Note: Multiple SSH keys**
   >
   > If you have already set up an SSH key pair with GitHub on a different machine, GitHub allows you to have multiple key pairs associated with your account. You can just follow these instructions again to set up another key pair and register it with GitHub.

   First we need to see if you have an Ed25519 algorithm SSH key already installed.

   ```bash
   ls ~/.ssh/id_ed25519.pub
   ```

   If a message appears in the console containing the text "No such file or directory", then you do not yet have an Ed25519 SSH key, and you will need to create one.

   To create a new SSH key, run the following command inside your terminal.

   ```bash
   ssh-keygen -t ed25519
   ```

   When it prompts you for a location to save the generated key, just push **Enter**.

   Next it will ask you for a passphrase. This passphrase is used to encrypt the private SSH key that is stored on your computer and you will be required to enter this passphrase every time you use SSH with these keys. If you don't use a passphrase, the private key will be readable by anyone who has access to your computer and will be able to modify all your GitHub repositories. Enter one if you wish, but it's not required. If you chose not to use a passphrase, just hit **Enter** without typing anything.

4. Now, you need to tell GitHub what your SSH key is so that you can push your code without typing in a password every time.

   First, you'll navigate to where GitHub receives our SSH key. Log into GitHub and click on your profile picture in the top right corner. Then, click on **Settings** in the drop-down menu.

   Next, on the left-hand side, click **SSH and GPG keys**. Then, click the green button in the top right corner that says **New SSH Key**. Name your key something that is descriptive enough for you to remember what device this SSH key came from, for example **linux-ubuntu**. Leave this window open while you do the next steps.

   Now you need to copy your public SSH key. To do this, we're going to use a command called `cat` to read the file to the console. (Note that the `.pub` file extension is important in this case.)

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

   Highlight and copy the entire output from the command. If you followed the instructions above, the output will likely begin with `ssh-ed25519` and end with your `username@hostname`.

   Now, go back to GitHub in your browser window and paste the key you copied into the key field. Keep the key type as **Authentication Key** and then click **Add SSH Key**. You're done! You've successfully added your SSH key!

5. Test your key by following [GitHub's directions for testing your SSH connection](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection?platform=linux). Make sure the fingerprint output in the terminal matches [one of GitHub's four public fingerprints](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints).

   You should see this response in your terminal: **Hi username! You've successfully authenticated, but GitHub does not provide shell access.** Don't let GitHub's lack of providing shell access trouble you. If you see this message, you've successfully added your SSH key and you can move on. If the output doesn't correctly match up, then try going through these steps again.