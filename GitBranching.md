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

## Relative References
```bash
git checkout HEAD~2
```

