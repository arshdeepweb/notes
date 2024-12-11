# Git Commands Reference

This README provides a quick reference for commonly used Git commands. Git is a free and open-source distributed version control system that helps manage code and collaborate effectively.

---

## Setup
### Configuring User Information
```bash
git config --global user.name "[firstname lastname]"
git config --global user.email "[valid-email]"
git config --global color.ui auto
```

---

## Repository Setup & Initialization
### Initialize a New Repository
```bash
git init
```

### Clone an Existing Repository
```bash
git clone [url]
```

---

## Stage & Snapshot
### Checking Status
```bash
git status
```

### Staging Files
```bash
git add [file]
```

### Unstaging Files
```bash
git reset [file]
```

### Viewing Changes
```bash
git diff          # Changes not staged
git diff --staged # Changes staged but not committed
```

### Commit Changes
```bash
git commit -m "[descriptive message]"
```

---

## Branching & Merging
### Branch Operations
```bash
git branch                # List branches
git branch [branch-name]  # Create a new branch
```

### Switch Branch
```bash
git checkout [branch-name]
```

### Merge Branch
```bash
git merge [branch]
```

### Viewing Commit Log
```bash
git log
```

---

## Sharing & Updating
### Adding Remote Repository
```bash
git remote add [alias] [url]
```

### Fetch Updates
```bash
git fetch [alias]
```

### Merge Remote Changes
```bash
git merge [alias]/[branch]
```

### Push Changes
```bash
git push [alias] [branch]
```

### Pull Changes
```bash
git pull
```

---

## Tracking Path Changes
### Remove Files
```bash
git rm [file]
```

### Move/Rename Files
```bash
git mv [existing-path] [new-path]
```

### View Commit Logs with File Movements
```bash
git log --stat -M
```

---

## Temporary Commits
### Stash Changes
```bash
git stash
```

### List Stashes
```bash
git stash list
```

### Apply Stash
```bash
git stash pop
```

### Discard Stash
```bash
git stash drop
```

---

## Rewriting History
### Rebase
```bash
git rebase [branch]
```

### Reset to Specific Commit
```bash
git reset --hard [commit]
```

---

## Inspect & Compare
### Viewing Logs
```bash
git log                      # Full commit history
git log branchB..branchA     # Commits in branchA not in branchB
git log --follow [file]      # Changes to a file across renames
```

### Viewing Differences
```bash
git diff branchB...branchA   # Diff of branchA not in branchB
```

### Viewing Specific Object
```bash
git show [SHA]
```

---

## Ignoring Patterns
### Configure Ignore File
Create a `.gitignore` file and add patterns to exclude files, such as:
```
logs/
*.notes
pattern*/
```

For system-wide ignore patterns:
```bash
git config --global core.excludesfile [file]
```

---

## Additional Resources
- [Git Official Documentation](https://git-scm.com/docs)
- [GitHub Education](https://education.github.com)

---

This cheat sheet provides quick command references for working with Git. For more detailed explanations, refer to the official Git documentation.

