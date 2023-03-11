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




