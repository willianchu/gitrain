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



