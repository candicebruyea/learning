# Git Ignore Cheat Sheet

This is a cheat sheet listing files/folders commonly excluded from Git repositories.

### Why must files be excluded?
Git sees every file in your working copy as either: 
1. Tracked - has been previously staged/committed
2. Untracked - hasn't been staged or committed
3. Ignored - Git has been explicitly told to ignore

Git may see hidden machine generated files and add them to your repository. To prevent this, the files can be added to a .gitignore file, which you edit and commit by hand whenever there are new files you wish to ignore.


### Typically Excluded Files and Folders
* Build output directories such as /bin, /out, or /target
* Files generated at runtime, such as .log, .lock, or .tmp
* Hidden system files, such as .DS_Store or Thumbs.db
* Personal IDE config files, such as .idea/workspace.xml
* Dependency caches, such as the contents of /node_modules or /packages
* Compiled code, such as .o, .pyc

### Files I've found and added to .gitignore
* .DS_Store - stores custom attributes of Mac folders, like icon positions etc.
* .idea/ - created by JetBrains IDEs to store project-specific settings and configs.

### Creating a .gitignore File
1. In terminal, navigate to the root directory of your Git repository.
2. Create a .gitignore file:


    touch .gitignore

This will create a .gitignore file in the current directory.
3. Edit the .gitignore file to specify the files and folders you want Git to ignore. 

    
    # Ignore build output
    /build/
    # Ignore log files
    *.log

4. If the file you are adding is already checked in, you will first need to untrack the file by using the command:

    
    git rm --cached FILENAME

### Sources
"Learn Git - Git ignore" *Atlassian*  
https://www.atlassian.com/git/tutorials/saving-changes/gitignore  

"Getting Started With Git - Ignoring Files" *Github Docs*  
https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files