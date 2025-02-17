# What is Git?

Git is a version control system that helps you track changes in your code. It lets you:  
- Save different versions of your code.
- Collaborate with others without messing things up.
- Roll back to previous versions if needed.

## Basic Git commands

### Initialize Git

```
git init
```

This command inilializes a new git repo in your project folder

##### What happens when you run this command?

- It creates a hidden ```.git``` folder inside your project
- This folder stores all Git history, commits and settings
- Your folder is now Git-tracked repository, ready for version control
- Run this command inside your project folder once to start tracking changes

#### How to check if its initialized?

After running following command:

```
ls -a
```

If you see a ```.git``` folder, Git is active.

## Track the status 

```git status``` is used to check the current status of your repo. 

It shows:
- Untracked files (new files not added to Git yet)
- Changes not staged for commit (modified files)
- Changes staged for commit (ready to be committed)
- Which branch you're on & if it's ahead/behind the remote

### Command:

```
git status
```

## Git staging

Staging is like putting files in a bagpack before submitting them.

- You make some changes to your project files.
- Before saving those changes in Git, you first stage them.
- Staging means telling Git which changes you're ready to save.

### Command:

```
git add filename.txt
git add .
```

- ```git add file.txt``` adds a single file
- ```git add .``` adds all changed files

## Unstaging the files without losing changes

Unstaging refers to the process of taking out files out after you've added them with ```git add``` command but haven't commited yet.

### Command:

```
git restore --staged filename.txt
```

After executing this command, ```filename.txt``` is no longer staged, but your edits are still there. 
You can either re-stage or leave it as is. Basically, this command just stops the files from being part of next commit.

## Git Commiting

Commiting is like **saving your progress in a game**, it takes a snapshot of your staged changes so you can always go back to them.

### Command:

```
git commit -m "commit message"
```

#### What is ```-m```?

```-m``` represents the **message** that you want to write while commiting the files.

## Viewing commit history

```git log``` command is used to view the history of the commits in your Git repository. It shows a detailed list of all commits, including the commit ID, author, date and commit message. This is helpful for reviewing the changes made over time, identifying specific commits or debugging issues.

### Command:

```
git log
```

### Common options:
- ```git log --oneline```: Shows a simplified, one-line view of each commit
- ```git log author="name"```: Filters commits by specific author
- ```git log since="2 weeks ago"```: Shows commits from the last 2 weeks.
- ```git log --oneline --graph```: Displays graph of commit history

## Rewinding changes your changes and history

```git reset``` is used to rewind the Git history, allowing you to move the **head pointer** to previous commit and adjust the staging area and working directory accordingly. 

### Command:

```
git reset <commit-id>
```

Here: ```<commit-id>``` is the ID when you use ```git log``` command

#### Example:

Assume after executing ```git log``` command, following is your output:

```
commit 72c799d35c94140742fb9b68aa833477aa75b0bd
Author: Unknown Guy <unknownGuyk@gmail.com>
Date:   Mon March 17 12:07:15 2023 +0530

    main.txt added
```

Here, ```<commit-id>``` is ```72c799d35c94140742fb9b68aa833477aa75b0bd```
