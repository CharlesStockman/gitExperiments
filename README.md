# Git Cookbook 

## Create a new repository and push to a Global Repository

### Remote Directory
Using Github to create the remote direcotry<br>
	&emsp;&emsp; Do not include a description or when the local repository is pushed to the global repository there will be a conflict.

### Local Repository 

#### Transform a directory into a Git Repository

|Command|Description|
|-------|-----------|
| git init | Create a working directory from a normal directory by adding a .git directory |

#### Put a File Under Version Control

|Command|Description|
|-------|-----------|
| git add . | Move the files to the staging area                |
| git commit -m "Original Source Code" | Move the files to the local repository.  They are now under version control.  |

#### Associate the Remote with the Local Repository

|Command|Description|
|-------|-----------|
| git remote add https://github.com/CharlesStockman/notesFromCourses.git  | Saves a named connection to a remote repository in your local .git/config<br>Associates origin with the url. |    
| git push -u origin main | The -u flag sets the "upstream" tracking relationship between your local branch and the remote branch.<br> After running this once, git remembers the connection so future pushes/pulls can just be git push or git pull without specifying origin main every time.

## Git Amend

### Change the comment of the last commit 
Prerquesite: Create a file text call amend1.txt

|Command|Description|
|-------|-----------|
|git add amend1.txt<br>git commit -m "Wrong comment"<br>git push<br>|Push a file to the global repository|
|git amend commit -m "The correct comment" |
|git status | Can skip this command, but showing why git pull must be done<br> Output of git status<br> On branch main<br><br>Your branch and 'origin/main' have <b>diverged</b><br>and have 1 and 1 different commits each, respectively.<br>(use "git pull" to merge the remote branch into yours)|git pull | 
|git push||
|git log -oneline|Should resemble the folllwing lines<br>e6f2390 Correct Comment<br>37be54b Wrong command