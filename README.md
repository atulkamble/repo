
# Git Commands Guide for Beginners

A simple guide to learning Git commands, understanding version control, and managing projects using Git and GitHub.

## 1. What Is Git?

Git is a version control system used to track changes in files and manage source code.

## 2. What Is GitHub?

GitHub is an online platform used to store Git repositories, share code, and collaborate with other developers.

## 3. Install Git

Download Git from:

https://git-scm.com/downloads

Check whether Git is installed:

```bash
git --version
```

## 4. Configure Git

Set your username:

```bash
git config --global user.name "Your Name"
```

Set your email:

```bash
git config --global user.email "your-email@example.com"
```

View configuration:

```bash
git config --list
```

## 5. Create a Repository

Create a project folder:

```bash
mkdir git-practice
cd git-practice
```

Initialize Git:

```bash
git init
```

This creates a local Git repository.

## 6. Check Repository Status

```bash
git status
```

Shows untracked files, modified files, and staged changes.

## 7. Add Files to Staging

Add one file:

```bash
git add README.md
```

Add all changes in the current directory:

```bash
git add .
```

Staging selects which changes will be included in the next commit.

## 8. Commit Changes

```bash
git commit -m "Initial commit"
```

A commit saves staged changes in the local repository's history.

## 9. View Commit History

Show commit history:

```bash
git log
```

Show a short history:

```bash
git log --oneline
```

Show commits with file changes:

```bash
git log --stat
```

## 10. Check File Differences

Show unstaged changes:

```bash
git diff
```

Show staged changes:

```bash
git diff --staged
```

Compare two commits:

```bash
git diff commit1 commit2
```

Replace `commit1` and `commit2` with actual commit IDs.

## 11. Connect Git to GitHub

Create an empty repository on GitHub.

Add the remote repository:

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

Check remote details:

```bash
git remote -v
```

Rename the current branch to main:

```bash
git branch -M main
```

Upload the branch:

```bash
git push -u origin main
```

Replace `USERNAME` and `REPOSITORY` with the correct values.

## 12. Push and Pull Changes

Upload committed changes:

```bash
git push
```

Download and integrate remote changes:

```bash
git pull
```

Download remote changes without merging them:

```bash
git fetch
```

## 13. Clone a Repository

Download an existing repository:

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```

Enter the downloaded folder:

```bash
cd REPOSITORY
```

## 14. Branch Commands

List local branches:

```bash
git branch
```

Create a branch:

```bash
git branch feature
```

Switch to a branch:

```bash
git switch feature
```

Create and switch to a new branch:

```bash
git switch -c feature
```

Merge a branch into the current branch:

```bash
git merge feature
```

Delete a merged local branch:

```bash
git branch -d feature
```

## 15. Rename and Delete Files

Rename a tracked file:

```bash
git mv old.txt new.txt
```

Remove a tracked file:

```bash
git rm file.txt
```

Commit the changes afterward.

## 16. Undo and Restore Changes

Discard unstaged changes in a file:

```bash
git restore file.txt
```

Unstage a file without deleting its changes:

```bash
git restore --staged file.txt
```

Undo the latest commit by creating a new commit:

```bash
git revert HEAD
```

Modify the latest commit:

```bash
git commit --amend
```

Be careful: restoring files discards changes, and amending a commit that has already been pushed can cause collaboration problems.

## 17. Temporarily Save Changes

Save uncommitted changes:

```bash
git stash
```

List saved stashes:

```bash
git stash list
```

Restore the latest stash and remove it from the stash list:

```bash
git stash pop
```

Apply the latest stash without removing it:

```bash
git stash apply
```

## 18. Work with Remote Branches

List remote branches:

```bash
git branch -r
```

List local and remote branches:

```bash
git branch -a
```

Remove outdated remote-tracking references:

```bash
git fetch --prune
```

Change the remote repository URL:

```bash
git remote set-url origin NEW_REPOSITORY_URL
```

## 19. Delete and Reset Operations

Delete a local branch that has been merged:

```bash
git branch -d feature
```

Force-delete a local branch:

```bash
git branch -D feature
```

Move the current branch back one commit while keeping changes staged:

```bash
git reset --soft HEAD~1
```

Move the current branch back one commit and unstage the changes while keeping them in the working directory:

```bash
git reset --mixed HEAD~1
```

**Warning:** `git reset --hard` can permanently discard uncommitted changes. Avoid it until you understand its effects.

## 20. Create a .gitignore File

A `.gitignore` file tells Git which untracked files to ignore.

Example:

```gitignore
.env
node_modules/
__pycache__/
*.log
.terraform/
```

Do not commit passwords, AWS access keys, tokens, or other secrets. Ignoring a file does not remove it from Git if it is already tracked.

## 21. Useful Information Commands

Show the current branch:

```bash
git branch --show-current
```

Show repository details:

```bash
git remote show origin
```

Show tracked files:

```bash
git ls-files
```

Show help:

```bash
git help
```

Get help for a specific command:

```bash
git help commit
```

## 22. Common Git Workflow

Follow these commands whenever you make changes to a project:

```bash
git status
git add .
git commit -m "Describe your changes"
git push
```

### What happens?

1. `git status` checks the current changes.
2. `git add .` stages the changes.
3. `git commit` saves the changes locally.
4. `git push` uploads committed changes to GitHub.

## 23. Common Git Errors

### Error: Not a Git Repository

**Reason:** You are not inside a Git repository.

**Solution:**

```bash
cd project-folder
git status
```

### Error: Remote Origin Already Exists

**Reason:** A remote named `origin` is already configured.

**Solution:**

```bash
git remote -v
git remote set-url origin NEW_REPOSITORY_URL
```

### Error: Push Rejected

**Reason:** The remote repository may contain commits that your local branch does not have.

**Solution:** Review the remote changes and integrate them before pushing:

```bash
git fetch origin
git pull --rebase origin main
git push
```

Resolve any conflicts before continuing.

## 24. Important Git Terms

| Term | Meaning |
|---|---|
| Repository | A project tracked by Git |
| Working directory | Files you are currently editing |
| Staging area | Changes selected for the next commit |
| Commit | A saved checkpoint |
| Branch | An independent line of development |
| Merge | Combining changes from branches |
| Remote | A linked repository, usually on GitHub |
| Clone | Copying a repository to your computer |
| Push | Uploading commits to a remote repository |
| Pull | Fetching and integrating remote changes |
| Conflict | Changes that Git cannot automatically combine |

## 25. Recommended Learning Order

1. Install and configure Git.
2. Practise `git init`, `git status`, and `git add`.
3. Learn `git commit` and `git log`.
4. Connect a project to GitHub.
5. Practise `git push`, `git pull`, and `git clone`.
6. Learn branches and merging.
7. Practise restore, revert, stash, and conflict resolution.

## Conclusion

Git helps developers track changes, maintain project history, collaborate with teams, and manage source code safely.

Practise these commands in a test repository before using destructive commands on important projects.
