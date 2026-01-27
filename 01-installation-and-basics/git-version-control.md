# Using Git for Version Control

---

## What It Is

Git is a version control system that tracks changes to your code over time, allowing you to save snapshots (commits) of your project, revert to previous versions, collaborate with others, and manage different versions of your code simultaneously. When using Claude Code, Git integration is essential because it lets you safely experiment with AI-generated code, track what changes Claude Code makes, roll back mistakes, and maintain a history of your project's evolution.

---

## Key Concepts

- **Repository (Repo):** A project folder tracked by Git that stores all files and their complete history
- **Commit:** A snapshot of your project at a specific point in time with a descriptive message
- **Staging:** Selecting which changes you want to include in your next commit
- **Branch:** A parallel version of your code where you can experiment without affecting the main codebase
- **Remote:** A version of your repository hosted online (like GitHub) for backup and collaboration
- **Working Directory:** The current state of files in your project folder (may have uncommitted changes)

---

## Commands & Syntax
```bash
# Initialize Git in a project
git init                              # Creates .git folder, starts tracking

# Check status of your files
git status                            # Shows modified, staged, and untracked files

# Stage files for commit
git add filename.txt                  # Stage specific file
git add .                             # Stage all changes in current directory

# Commit staged changes
git commit -m "Description of changes"   # Save snapshot with message

# View commit history
git log                               # Shows all commits
git log --oneline                     # Compact view of commits

# Create and switch branches
git branch branch-name                # Create new branch
git checkout branch-name              # Switch to branch
git checkout -b branch-name           # Create and switch in one command

# Merge branches
git merge branch-name                 # Merge specified branch into current branch

# Connect to remote repository (like GitHub)
git remote add origin https://github.com/username/repo.git

# Push changes to remote
git push origin main                  # Upload commits to remote repository

# Pull changes from remote
git pull origin main                  # Download and merge remote changes

# Undo changes
git restore filename.txt              # Discard changes in working directory
git reset HEAD~1                      # Undo last commit (keep changes)
git reset --hard HEAD~1               # Undo last commit (delete changes)
```

---

## When to Use

Use Git throughout your entire Claude Code workflow - initialize Git before starting any project, commit after each significant change or after Claude Code generates new code, create branches when experimenting with major features, and push to remote repositories for backup and collaboration. Git is especially critical with AI-generated code because you can easily revert if Claude Code creates something problematic.

---

## How It Works

**Step 1:** Initialize Git in your project directory with `git init` (do this once per project)

**Step 2:** After Claude Code generates or modifies files, check what changed using `git status`

**Step 3:** Stage the changes you want to save using `git add .` (stages everything) or `git add filename` (stages specific files)

**Step 4:** Commit the staged changes with a descriptive message: `git commit -m "Added user authentication"`

**Step 5:** If using remote repository (GitHub), push your commits: `git push origin main`

**Step 6:** Repeat steps 2-5 after each significant change - commit early and often, especially after Claude Code makes modifications

---

## Common Issues

### Issue: "Not a git repository" error
**Symptoms:** Git commands fail with this error message  
**Solution:** You haven't initialized Git in this directory - run `git init` first, or navigate to the correct project directory that has Git initialized

### Issue: Merge conflicts
**Symptoms:** Git says there are conflicts when merging or pulling  
**Solution:** Open conflicted files, look for `<<<<<<` markers, manually choose which version to keep, remove conflict markers, then `git add` and `git commit` the resolved files

### Issue: Accidentally committed sensitive information
**Symptoms:** API keys or passwords committed to Git history  
**Solution:** Use `git reset --hard HEAD~1` to undo immediately (if not pushed), or use tools like `git-filter-repo` to remove from history - never commit secrets, use .gitignore and environment variables

### Issue: Push rejected - remote has changes
**Symptoms:** Cannot push because remote repository has commits you don't have locally  
**Solution:** First `git pull origin main` to get remote changes, resolve any conflicts, then `git push origin main`

---

## Important Notes

- ⚠️ **Warning:** `git reset --hard` permanently deletes changes - use with extreme caution and only when you're certain
- ⚠️ **Warning:** Never commit sensitive information (API keys, passwords) - use .gitignore file to exclude sensitive files
- 💡 **Tip:** Commit after every successful Claude Code generation - if the next change breaks something, you can easily revert
- 💡 **Tip:** Use descriptive commit messages that explain WHY you made changes, not just WHAT changed
- 💡 **Tip:** Create a .gitignore file to exclude unnecessary files (node_modules, .env, build folders)
- 📌 **Remember:** Git is local - your commits are only on your computer until you `git push` to a remote repository
- 📌 **Remember:** Branches let you experiment safely - create a branch before trying risky Claude Code modifications
