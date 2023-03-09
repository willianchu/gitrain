# Git Commands
* commit
* branch
* checkout
* cherry-pick
* reset
* revert
* rebase
* merge

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

# Moving Work Around

## cherry-pick
```bash
git cherry-pick <commit-1> <commit-2>
```

> this will copy each selected commit and paste them on top of the current branch.





