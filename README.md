# gitrain

## Super basic stuff for beginners
```bash
git --version

git init

git status

git log

git branch -d branch_name

git remote add origin https://abc.com/abc.git

```
* git log - view the history of commits
* git branch -d branch_name - delete a branch
* git remote add origin https://abc.com/abc.git - add a remote repository


## This is the name you want to show up on your commits
```bash
git config user.name "Johnny test"
```	

## Stage all new, modified, and deleted files. Use the shorthand command
```bash
git add -A
```

## Check the compact version of the status for repository
```bash
git status -s
git status --short
```

## Commit the updated files directly, skipping the staging environment:
```bash
git commit -a -m "Commit message"
```
> But only works for files that are already tracked by Git. New files must be added first.

## Show all git possible commands in command line:
```bash
git help --all
git status --help
```

## Create a new branch called hello-world-images
```bash
git branch hello-world-images
```
## List the existing branches
```bash
git branch
```

## Create and switch to a new branch called hello-world-images
```bash
git checkout -b hello-world-images
```

```bash	
git merge --abort
```

## remove the hello-you branch from the local repository
```bash
git branch -d hello-you
```

## Add a remote repository as an origin
```bash
git remote add origin https://abc.com/abc.git
```

> pull = fetch + merge

## Pull the latest changes from the remote repository
```bash
git pull origin master
```

## Get all the change history of the origin for this branch
```bash
git fetch origin
```
## Merge the current branch with the branch master, on origin
```bash	
git merge origin/master
```
or simpler
```bash
git pull origin master
```

## Update the current branch from its origin using a single command:
```bash
git pull origin
```

## push the current branch to its default remote origin
```bash
git push origin
```

## List all local and remote branches of the current Git.
```bash
git branch -a
```
## List only remote branches of the current Git.
```bash
git branch -r
```
## Rename the origin remote to upstream
```bash
git remote rename origin upstream
```
> this will rename the origin remote to upstream

## show the name of the origin remote
```bash
git remote show origin
```

# Git ignore

## In .gitignore add a line to ignore all .temp files
```bash
*.temp
```
## In .gitignore add a line to ignore all files in any directory named temp:
```bash
temp/*
```
## In .gitignore, ignore all .log files, except main.log
```bash
*.log
!main.log
```
## Add a new remote named ssh-origin connecting to x/y.git on abc.com using SSH
```bash
git remote add ssh-origin git@abc.com:x/y.git
```
## Replace the remote URL for origin with x/y.git on abc.com using SSH
```bash
git remote set-url origin git@abc.com:x/y.git
```

## Show the log of the repository, showing just 1 line per commit
```bash
git log --oneline
```

## revert the latest commit
```bash
git revert HEAD
```
## revert the latest commit, skipping the commit message editor
```bash
git revert HEAD --no-edit
```

## revert the two last commits
```bash
git revert HEAD~1 HEAD
```
## revert the THREE last commits
```bash
git revert HEAD~2 HEAD~1 HEAD
```
## reset to the commit with the hash abc1234
```bash
git reset abc1234
```
## Amend the previous commit to with the message "Updated index"
```bash
git commit --amend -m "Updated index"
```
> amend is used to change the last commit message







