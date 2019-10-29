# git cheatsheets

### REMOTE
```
git remote add origin [url]
git remote -v
```

### MAKE CHANGES
```
$ git status
$ git add [file]
$ git reset [file]
$ git diff
$ git diff --staged
$ git commit -m "[descriptive message]"
```

### CREATE REPOSITORIES
```
git init [project-name]
git clone [url]
```

### GROUP CHANGES
```
$ git branch
$ git branch [branch-name]
$ git checkout [branch-name]
$ git merge [branch]
$ git branch -d [branch-name]
```

### REFACTOR FILENAMES
```
$ git rm [file]
$ git rm --cached [file]
$ git mv [file-original] [file-renamed]
```

### REVIEW HISTORY
```
$ git log
$ git log --follow [file]
$ git diff [first-branch]...[second-branch]
$ git show [commit]
```

### REDO COMMITS
```
$ git reset [commit]
$ git reset --hard [commit]
```

### SAVE FRAGMENTS
```
$ git stash
$ git stash list
$ git stash pop
$ git stash drop
```

### SYNCHRONIZE CHANGES
```
$ git fetch [bookmark]
$ git merge [bookmark]/[branch]
$ git push [alias] [branch]
$ git pull
```

## Credit
https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf