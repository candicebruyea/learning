# Git Basics

## Git Workflow

### Create
Create a new file or change an existing file.
      
      git init will initialize new git project.
      touch filename.txt will create a new empty file.

### Stage Files
Tracks a file to be saved in Git.

    git add . will track all untracked files
    git add <filename or folder> will track specific file and folders 

### Commit
Saves the changes locally in git. Write in present tense, be brief.

    git commit -m "What and why you're committing" -m "some description"

### Push
Committed changes are pushed to the remote directory.  
origin = location of our git repository  
main - branch we want to commit to.

    git push origin main


![local-git-workflow.png](images/local-git-workflow.png)


## Terminal Commands

### Change directory  

    cd <directory-name>

### List 
List all files in directory

    ls 

### Initialize a new Git project
      git init

### Status
Show what files are modified and tracked

    git status

* Untracked files = git sees the file but has not started tracking changes yet.
* Changes to be committed = files have been added to the staging area.

### Add Origin
Add a reference to the remote repository on github

    git remote add origin <ssh-code>

### List Repositories
Shows any remote repositories you've connected to this repo

    git remote -v

### List Commits

      git log

* 40 character code (SHA) identifies the commit, written in orange.
* Author, date, time and commit message are displayed.

### Set Upstream
Say where you want to push to by default

    git push -u <origin master or other location>

### Check the differences between the working directory and staging area

      git diff <filename>

* changes are marked with a *+ and indicated in green.


### Unstage Files
Unstage files set to be committed.

    git restore --staged <file>...

### Check how many branches
Star beside = branch you're currently on
   
    git branch

### Switch between branches

    git checkout

### Make new branch

    git checkout -b <feature-name>

### Check Git Version

    git --version


# Github Clone

## Cloning a website from a Github Repository

1. Get the Repository Code
    * Navigate to the repository's main page on GitHub and copy the SSH code.
2. Clone the Repository to your Local Machine
    * In your terminal, use the 'git clone' command + the repository's URL.


      git clone <ssh key>

## Creating a new branch and switching to it.

Use the following command:

    git checkout -b new-branch-name

This will let you work on the website files without affecting the main branch.

## Pushing the new branch to the remote repository
    git push origin new-branch-name

## Merging changes from a feature branch to the main branch

1. Create a pull request so others working on the project can review.
   * In Github repository, select Pull Requests in menu and click New pull request button.
   * Select the feature branch. All changes should be displayed.
   * Click Create pull request button. Leave a description saying how to test. "To Test: description how to test"
   * Add Reviewers, Edit Labels and Project if needed.
   * Click Create pull request button.

# Using the Nano Editor

### Open an existing file
    nano <filename.extension>

### Create a new file
    nano new_<filename.extension>

# Checking for an existing SSH Key

Open Terminal.

Enter ls -al ~/.ssh to see if existing SSH keys are present.

    ls -al ~/.ssh
Lists the files in your .ssh directory, if they exist

Check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following.

    id_rsa.pub

    id_ecdsa.pub

    id_ed25519.pub

If you receive an error that ~/.ssh doesn't exist, you do not have an existing SSH key pair in the default location. You can create a new SSH key pair in the next step.

# Generating a new SSH Key

In the terminal, paste the text below, replacing the email used in the example with your GitHub email address.

    ssh-keygen -t ed25519 -C "your_email@example.com"

This creates a new SSH key, using the provided email as a label.

When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location. 

At the prompt, type a secure passphrase. 

# Adding your SSH key to the ssh-agent

Start the ssh-agent in the background.

    eval "$(ssh-agent -s)"

If you're using macOS Sierra 10.12.2 or later, you will need to modify your ~/.ssh/config file to automatically load keys into the ssh-agent and store passphrases in your keychain.

First, check to see if your ~/.ssh/config file exists in the default location.

    open ~/.ssh/config

If the file doesn't exist, create the file.

    touch ~/.ssh/config

Open your ~/.ssh/config file, then modify the file to contain the following lines. If your SSH key file has a different name or path than the example code, modify the filename or path to match your current setup.

    Host github.com
    AddKeysToAgent yes
    UseKeychain yes
    IdentityFile ~/.ssh/id_ed25519

Note: If you chose not to add a passphrase to your key, you should omit the UseKeychain line.
If you see a Bad configuration option: usekeychain error, add an additional line to the configuration's' Host *.github.com section.Text

    Host github.com
    IgnoreUnknown UseKeychain



Open the ssh directory.

    open ~/.ssh/

Open the id_ed25519.pub file and copy the SSH Key there.

Add your SSH private key to the ssh-agent and store your passphrase in the keychain.

    ssh-add --apple-use-keychain ~/.ssh/id_ed25519