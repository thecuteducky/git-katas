
````markdown
# Git Katas  
Beginner exercises for Git and personal practice

---

## 1. Basic Commits

### Commands
```bash
New-Item
git status
git add .
git commit -m "message"
git log --oneline --graph
````

### Errors encountered

Issues while using file commands in PowerShell:

```bash
Get-ChildItem
Remove-Item "..\??" -Force
```

### Notes / Evidence

* Problem screenshot:

  <img width="901" height="137" alt="image" src="https://github.com/user-attachments/assets/37f7fa53-5e21-4559-98e5-8a241c7963e9" />

* Fix attempt:

  <img width="856" height="44" alt="image" src="https://github.com/user-attachments/assets/f17f7fa3-b2ba-4c52-9137-06ba94f33885" />

---

## 2. Basic Staging

### File commands

```bash
Set-Content
Get-Content
Add-Content
```

### Git staging commands

```bash
git add <file>
git restore --staged <file>   # unstage
git restore file.txt          # restore working directory file
git diff                      # unstaged changes
git diff --cached             # staged changes
```

### Key concept

If you do not run `git add`, changes stay in the working directory:

* Not staged
* Not included in commit
* Not tracked for next commit

Only after:

```bash
git add file.txt
```

The file moves to the staging area.

---

### Git states

| Area              | Meaning          |
| ----------------- | ---------------- |
| Working Directory | Current changes  |
| Staging Area      | Ready for commit |
| Repository        | Commit history   |

---

## 3. Basic Branching

### Commands

```bash
git branch
git switch <branch>
```

### Concept

* Each branch is a pointer to a different commit history
* Allows parallel development

---

## 4. Basic Revert

### Command

```bash
git revert <commit>
```

### Concept

* Creates a new commit that undoes changes
* Does not delete history

### Note

Even after revert:

* Changes are removed from working directory
* Commit still exists in history

### Vim command

```bash
:wq
```

* w = write (save)
* q = quit

---

## 5. Basic Cleaning

### Commands

```bash
ls -R
git clean -n        # preview
git clean -f -d     # delete files and directories
```

### Safe workflow

```bash
git clean -n -d
git add .
git clean -f -d
```

---

## 6. Basic Stashing

### Diff commands

```bash
git diff
git diff --cached
```

### Stash concept

A file can have:

* staged changes (index)
* unstaged changes (working directory)

### Commands

```bash
git stash
git stash apply
git stash apply --index
```

### Behavior

| Command                 | Result                 |
| ----------------------- | ---------------------- |
| git stash apply         | restores files only    |
| git stash apply --index | restores staging state |

### Recovery flow

```bash
git reset --hard HEAD
git stash apply --index
```

---

## 7. Basic Cherry-Picking

### Command

```bash
git cherry-pick <commit>
```

### Concept

* Copies a commit into current branch
* Does not merge branches
* Creates a new commit

### Undo cherry-pick

```bash
git reset --hard HEAD^
```

### Effect

* Removes cherry-picked commit
* Restores previous state

---

## Summary

This repository covers:

* Basic commits workflow
* Staging area concept
* Branching fundamentals
* Revert vs reset behavior
* Cleaning working directory
* Stashing workflow
* Cherry-picking behavior

```
```
