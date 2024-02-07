# Git Basics

## Git Workflow

### Create
Create a new file or change an existing file.

### Stage Files
Tracks a file to be saved in Git.

    git add . will track all untracked files
    git add <filename or folder> will track specific file and folders 

### Commit
Saves the changes locally in git.

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

### Status
Show what files are modified and tracked

    git status

### Add Origin
Add a reference to the remote repository on github

    git remote add origin <ssh-code>

### List Repositories
Shows any remote repositories you've connected to this repo

    git remote -v

### Set Upstream
Say where you want to push to by default

    git push -u <origin master or other location>

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

## Creating a new branch and switching to it.

Use the following command:

    git checkout -b new-branch-name

This will let you work on the website files without affecting the main branch.

## Pushing the new branch to the remote repository
    git push origin new-branch-name

