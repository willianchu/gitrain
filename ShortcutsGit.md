# -am (Automatic git add.)
```bash
git commit -am "commit message"
```

# alias (shorten commands)
```bash
git config --global alias.ac "commit -am"

git ac "commit message"
```

# --amend (change the last commit message)
```bash
git commit --amend -m "new commit message"
```

# --force (overwrite history on remote)
```bash
git push origin master --force
```
> if you have some commits on the remote that you don't have locally, you lost them forever.

# revert (undo a commit with a new commit)
```bash
git revert name-of-commit
```

# . (you can use to access vscode web editor)
> just go to your github an press the dot (.) to access the web editor.

> to run you need to set cloudspaces as default editor.

# Stash (save changes without commiting)
```bash
git stash
```

# stash pop (apply the last stash)
```bash
git stash pop
```
# to rename a MASTER branch to MAIN
```bash
git branch -m master main
```

# Log (show the history of commits)
> it's hard to read, so we can use some flags to make it easier to read.
```bash
git log --oneline --graph --decorate --all
```
# bisect (find the commit that broke something)
```bash
git bisect start
git bisect bad
git bisect good name-of-commit
```
# squash (combine multiple commits into one)
```bash
git rebase -i name-of-commit
```
# cherry-pick (apply a commit from another branch)
```bash
git cherry-pick name-of-commit
```
# reset (undo a commit)
```bash
git reset --hard name-of-commit
```

# hooks (run scripts before or after certain git commands)

# git checkout - (go back to the previous branch)
```bash
git checkout -
```





