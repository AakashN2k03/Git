# Git Command Cheat Sheet 📌
---

## Repository Management

### 1. Initialize a Repository
```bash
git init
```
Creates a new Git repository in the current folder.

### 12. Clone a Repository
```bash
git clone "repo_url"
```
Copies a remote repository to your local machine.

---

## Working with Changes

### 2. Check Status
```bash
git status
```
Shows the state of the working directory and staging area.

### 3. Stage Changes
```bash
git add .                    # Stage all changes
git add <filename>           # Stage specific file
git add *.js                 # Stage all JavaScript files
```
Prepares changes for the next commit.

### 4. Commit Changes
```bash
git commit -m "commit message"
```
Saves the staged changes to the repository with a descriptive message.

---

## Remote Operations

### 5. Pull Updates from Remote
```bash
git pull
```
Fetches and merges changes from the remote repository into your current branch.

### 6. Push Changes to Remote
```bash
git push                     # Push to default remote branch
git push origin main         # Push to specific remote branch
git push origin main --force # Force push (use with caution)
```
Uploads local branch commits to the remote repository.

### 13. View and Add Remotes
```bash
git remote -v                                           # View current remotes
git remote add origin https://github.com/user/repo.git # Add new remote
```
Manage remote repository connections.

---

## Viewing Information

### 7. View Differences
```bash
git diff                     # Changes between working directory and staging area
git diff --cached            # Changes between staging area and last commit
git diff HEAD                # All changes since last commit
```
Shows file changes in various contexts.

### 8. View Commit History
```bash
git log                      # Full commit details
git log --oneline            # Compact one-line summary per commit
git log --graph              # Visual representation of branch history
```
- `git log` → Full commit details with author, date, and message
- `git log --oneline` → Compact one-line summary per commit
- `git log --graph` → Shows branching structure visually

---

## Branch Operations

### 10. Checkout Branch or Commit
```bash
git checkout <branch_name>        # Switch to existing branch
git checkout -b <new_branch>      # Create and switch to new branch
git checkout <commit_hash>        # Switch to specific commit (detached HEAD)
```

**Detached HEAD Example:**

Before:
```
main → C1 → C2 → C3 (HEAD)
```

After `git checkout C1`:
```
HEAD → C1
main → C3
```

Returning to current branch:
```bash
git checkout main
# HEAD → main → C3
```

### 11. Switch Branch (Modern Alternative)
```bash
git switch <branch_name>     # Switch to existing branch
git switch -c <new_branch>   # Create and switch to new branch
```
Modern alternative to `git checkout` for branch operations.

---

## Advanced Operations

### 9. Reset to an Older Commit
```bash
git reset --hard <commit_hash>
```
⚠️ **Warning:** This permanently deletes commits after `<commit_hash>` in both local and remote.

**Example:**

Before:
```
main → C1 → C2 → C3 (HEAD)
```

After:
```bash
git reset --hard C1
git push origin main --force
# Result: main → C1 (HEAD)
```

### 14. Cherry-pick
```bash
git cherry-pick <commit_hash>
```
Applies the changes from a specific commit to your current branch without merging the entire branch. Useful for selectively applying fixes or features.

### 15. Merge
```bash
git merge <branch_name>
```
Combines all commits from the specified branch into the current branch, preserving the complete history of both branches.

### 16. Rebase
```bash
git rebase <branch_name>
```
Moves/replays your commits on top of another branch for a cleaner, linear history. Creates a more streamlined project timeline.

## ⚠ Note:

- Use git reset --hard + git push --force with caution — it permanently deletes commits.
- Use rebase only on local/private branches, not on branches others are working on.

---

## Need Help?
- `git help <command>` - Get detailed help for any Git command
- `git --version` - Check your Git version
