# Git Commands
* commit
* branch
* checkout
* cherry-pick
* reset
* revert
* rebase
* merge

# Git Branching

The exercises are based in the following website: [Git Branching](https://learngitbranching.js.org/)


## UNDO
```bash
git merge --abort
```
or
```bash
git rebase --abort
```
or
```bash
git reset --hard
```


## rebase (cleaner than merge)
```bash
git rebase -i HEAD~3
```


# Moving Through Git

## De-attach HEAD
```bash
git checkout <commit>
```
## Reattach HEAD
```bash
git checkout <branch>
```
# << Back and Forward >>

## Relative References
```bash
git checkout HEAD~2
```
> for moving one commit back from HEAD you can use HEAD~1
> for moving two commits back from HEAD you can use HEAD~2
> for moving one commit forward from HEAD you can use HEAD^1
> for moving two commits forward from HEAD you can use HEAD^2

## Forcing Branches

> -f is short for --force

```bash
git checkout -f <branch>
```
## Forcing Detached HEAD
```bash
git checkout -f <commit>
```

## move branch to commit
```bash
git branch -f <branch> <commit>
```

> Git Branch -f A B move the branches pointers to a commit B as Git Checkout -f A B moves the HEAD pointer to commit B.

# Reverting Commits

## Two types 

### low level
```bash
git reset --hard <commit>
```
> this will move the HEAD pointer to the commit and reset the index and working directory to match the commit (losing all changes since the commit) - Is a local operation

### high level
```bash
git revert <commit>
```
> this will create a new commit that undoes the changes in the commit (leaving the changes in the index and working directory) - maintain the history, good for sharing

# Moving Work Around (Advance 20% of the time)

## cherry-pick
```bash
git cherry-pick <commit-1> <commit-2>
```

> this will copy each selected commit and paste them on top of the current branch.

# Intercative Rebase -i

## rebase
```bash
git rebase -i HEAD~3
```
> this will open an editor with the last 3 commits, you can change the action for each commit and will star stacking from the last commit to the first one.

# Juggling Commits

## rebase
```bash
git rebase -i HEAD~3
```

## --amend
```bash
git commit --amend
```
> this will open an editor with the last commit message, you can change the message and will star stacking from the last commit to the first one.

# Git's Tags

## tag
```bash
git tag <tag-name>
```
> this will create a tag with the name <tag-name> in the current commit. Milestones, releases, etc.

* moving deatached HEAD
```bash
git checkout <tag-name>
```
> this will move the HEAD pointer to the tag

## Git Describe
```bash
git describe <tag-name>
```
> this will show the tag name and the number of commits since the tag

# 9000 Rebases

C0, C1, C2 (main)
C0, C1, C3 (bugFix)
C0, C4, C5, C6 (side)
C0, C4, C5, C7 (another)

```bash	
git rebase main bugFix
git rebase bugfix side
git rebase side another
git rebase another main
```

> this will create a linear history
> rebase another main will make the main branch to point to the last commit of the another branch

# Multiple fathers

```bash	
 git branch bugWork main^^2^
```

# Spaghetti Branches

```bash	
 git checkout one
 git cherry-pick C4 C3 C2
  git checkout two
  git cherry-pick C5 C4 C3 C2

GIT BRANCH -F THREE C2
```

# Remote Branches

```bash
git push origin <branch>
```
> this will push the branch to the remote repository

```bash
git pull origin <branch>
```
> this will pull the branch from the remote repository

```bash
git fetch origin <branch>
```
> this will fetch the branch from the remote repository

```bash
git branch -r
```
> this will show the remote branches

```bash
git branch -a
```
> this will show the remote and local branches

```bash
git branch -vv
```
> this will show the remote and local branches with the last commit

> the difference between fetch and pull is that fetch will only download the branch and pull will download the branch and merge it with the current branch.

Example:
```bash
git fetch origin master
git checkout master
git merge origin/master
```
> this will fetch the master branch from the remote repository and merge it with the current branch

## Git Clone
```bash
git clone <url>
```

# origin/main

```bash
git branch -u origin/main
```
> this will set the upstream branch to origin/main

# Git Stash

```bash
git stash
```
> this will save the current changes in a stash

# Git Fetch
  
  ```bash
  git fetch origin <branch>
  ```
  > this will fetch the branch from the remote repository
  > this will not merge or make any changes to the current branch

# Git Pull

* git cherry-pick origin/<branch>
* git rebase origin/<branch>
* git merge origin/<branch>

  
    ```bash
    git pull origin <branch>
    ```
    > this will fetch the branch from the remote repository
    > this will merge the branch with the current branch

## Git Pull  (remote > local)
  
  > fetch + merge = pull

  ```bash
  git pull origin <branch>
  ```
  > this will fetch the branch from the remote repository
  > this will merge the branch with the current branch


# Git rebase origin/<branch>

  ```bash
  git rebase origin/<branch>
  ```
  > this will fetch the branch from the remote repository
  > this will rebase the current branch with the remote branch

# Git merge origin/<branch>

  ```bash
  git merge origin/<branch>
  ```
  > this will fetch the branch from the remote repository
  > this will merge the branch with the current branch


## Solution

```bash
git clone <url>
git faketeamwork 2
git commit
git pull
```	

# Git Push (local > remote)

```bash
git push origin <branch>
```
> this will push the branch to the remote repository

## settting upstream branch

```bash
git push --set-upstream origin <branch>
```
> this will push the branch to the remote repository and set the upstream branch

# Avoiding Conflicts

## git pull --rebase

```bash
git pull --rebase origin <branch>
```
> this will fetch the branch from the remote repository
> this will rebase the current branch with the remote branch

```bash	
git fetch
git rebase origin/<branch>
git push
```
> this will fetch the branch from the remote repository
> this will rebase the current branch with the remote branch
> this will push the branch to the remote repository
> will be a clean and linear history

## merge to avoid conflicts

```bash
git fetch
git merge origin/<branch>
git push
```
> this will fetch the branch from the remote repository
> this will merge the branch with the current branch
> this will push the branch to the remote repository
> will maintain the history

### Difference between rebase and merge
> rebase will change the history of the commits, merge will not change the history of the commits

> git pull --rebase is the same as git fetch + git rebase

```bash
git pull --rebase origin <branch>
git push
```
> this will fetch the branch from the remote repository

### --rebase
```bash
git pull --rebase
git push
```
> this will fetch the branch from the remote repository
> this will rebase the current branch with the remote branch
> this will push the branch to the remote repository
> Same thing but shorter

### pull approach
```bash
git pull
git push
```
> this will fetch the branch from the remote repository
> this will merge the branch with the current branch
> this will push the branch to the remote repository
> Same thing but shorter

### Example
```bash
git clone
git fakeTeamwork
git commit
git pull --rebase
git push
```

# Remote Rejected

## Why are you rejected?
> if you try to push and making a pull request, but accidentally you are pushing to the wrong branch, you will get a rejected message.
> You be stuck in a loop, because you are trying to push to the wrong branch, but you are trying to pull from the wrong branch.

### Exercice
```bash
git reset --hard o/main
git checkout -b feature C2
git push origin feature
```

> git reset --hard o/main	# this will reset the current branch to the main branch
> git checkout -b feature C2	# this will create a new branch called feature and move the HEAD pointer to the commit C2
> git push origin feature	# this will push the branch to the remote repository

### Solution 2
```bash
git branch -f main C1
git checkout -b feature C2
git push origin feature
```

# Pushing several branches in order

```bash
git fetch
git rebase origin/main branch1
git rebase branch1 branch2
git rebase branch2 branch3
git rebase branch3 main
git push
```
> get the branches from the remote repository
> rebase the branches in order
> close the rebases with the main branch
> push the branches to the remote repository

# rebase vs merge

## rebase	

### Pros
> cleaner history
> linear history

### Cons
> modifying the history of the commits

## Pushing several branches in order (merge version)

```bash
git checkout main
git pull
git merge branch1
git merge branch2
git merge branch3
git push
```

# main & origin/main

> main is the local branch
> origin/main is the remote branch

## setting a random branch as the main branch

```bash
git checkout -b ImNotTheMainBranch origin/main
git pull
```

> this will create a new branch called ImNotTheMainBranch and move the HEAD pointer to the commit o/main

### updating a branch with the main branch

```bash
git checkout -b ImNotTheMainBranch origin/main
git pull
```

> this will create a new branch called ImNotTheMainBranch and move the HEAD pointer to the commit o/main

```bash	
git checkout -b ImNotTheMainBranch origin/main
git commit
git push
```	

> this will create a new branch called ImNotTheMainBranch and move the HEAD pointer to the commit o/main


# Alternative way to create a branch pointing to the origin/main branch

> Using git branch -u

```bash
git branch -u origin/main ImNotTheMainBranch
```
 ### If ImNotTheMainBranch is the current branch, you may omit the branch name

```bash
git branch -u origin/main
```

### Example

```bash 
git branch -u origin/main ImNotTheMainBranch
git commit
git push
```
> remote tracking branch

### Following a remote branch

```bash
git checkout -b ImNotTheMainBranch origin/main
git commit
git pull --rebase
git push
```

> this will create a new branch called ImNotTheMainBranch and move the HEAD pointer to the commit o/main


# Push Parameters

> git push origin <branch>

```bash
git push origin main
```
> it ignores the local branch and pushes the remote branch

Example

```bash
git checkout C0
git push origin main
```

## Specify different local and remote branches

```bash
git push origin <local_branch>:<remote_branch>
```

Example

```bash
git checkout C0
git push origin main:main
```
> colon refspec syntax - means push the local branch to the remote branch

'''bash
git push origin foo^:main
'''

> this will push one commit before the current branch to the main branch


