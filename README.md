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


## Connecting local folder to a GitHub repository

To connect a local project folder to a GitHub repository, you need to link your local Git repository with the remote GitHub repo. This allows you to push your changes and keep your project synchronized. You achieve this by adding the remote URL using ```git remote add origin <repo-url>``` ensuring your local work can be tracked and shared on GitHub.

### Command:

```
git remote add origin <repo-url>
```

Here:
- ```remote``` means that you're working with URLs.
- ```origin``` is the name of the URL you're going to add.

## Viewing Remote Repsoitory Details

The ```git remote -v``` command displays the remote repositories linked to your local Git project. It shows both the **fetch** and **push** URLs, helping you verify the remote connections.

### Commands:

```
git remote -v
```

### Example Output:

```
origin  https://github.com/user/repo.git (fetch)
origin  https://github.com/user/repo.git (push)
```

Above output confirms that ```origin``` is linked to your GitHub repository for both fetching updates and pushing changes.

## Uploading Changes To The Remote repository

The command ```git push origin master``` is used to push your local changes to the remote repository on the **master** branch.

### Command:

```
git push origin master
```

Here:
- ```git push```: Pushes your commits to the repository.
- ```origin```: The default name for the repository.
- ```master```: The branch where the changes will be pushed.

### Note:

Many repos use ```main``` instead of ```master```, so you need to write:

```
git push origin main
```

## Branches in GitHub

A **branch** in GitHub is like a seperate version of your project where you can make changes **without affecting the main code.** It allows multiple people to work on different features or fixes at the same time.

### Key Points:

- The ```main``` or ```master``` **branch** is the default and usually constains the stable code.
- You can create a **new branch** to work on a feature or fix a bug.
- Once done, you can merge the branch back into ```main```.

### Commands:

- To create a branch:

    ```
    git branch new-feature
    ```

- Swtich to another branch:

    ```
    git checkout new-feature
    ```

- Create & swtich in one command:

    ```
    git checkout -b new-feature
    ```

- Push a branch into GitHub

    ```
    git push origin new-feature
    ```

Using branches keeps your project **organized, clean and safe** from breaking changes.

## Copying a Remote Respository Locally

The ```git clone``` command is used to **create a local copy** of a remote Git repository. This allows you to download the entire project, including its commit history, and work it on locally.

### Command:

```
git clone <repo-url>
```

This command will create a folder named ```repo``` inn your local system and copy all the repository files into it.

### Key Points:
- It **copies** entire repo, including branch and history.
- You can start working locally immediately.
- It **automatically sets up** ```origin``` as the remote repository.

This command is essential for contributing in **open source projects** or working with repositories hosted on GitHub.
