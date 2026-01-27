# Quick Reference Guide

Essential commands and workflows for Claude Code.

---

## 🔧 Essential Slash Commands

| Command | Purpose |
|---------|---------|
| `/clear` | Clear the current session |
| `/rewind` | Rewind to a previous point |
| `/model` | Switch AI model |
| `/compact` | Compress conversation history |
| `/status` | Show current session status |
| `/permissions` | Manage file permissions |
| `/context` | View current context |
| `/stats` | Show session statistics |
| `/add-dir` | Add directory to context |
| `/handoff` | Handoff to another agent |

---

## 🖥️ Terminal Navigation Commands

| Command | Purpose |
|---------|---------|
| `pwd` | Show current directory location |
| `ls` / `dir` | List files and folders |
| `cd folder-name` | Change to specified directory |
| `cd ..` | Move up one directory level |
| `cd ~` | Go to home directory |
| `mkdir folder-name` | Create new directory |
| `clear` / `cls` | Clear terminal screen |

---

## 📁 File Operations

| Command | Purpose |
|---------|---------|
| `touch file.txt` / `echo. > file.txt` | Create new empty file |
| `cat file.txt` / `type file.txt` | Display file contents |
| `cp` / `copy` | Copy files |
| `mv` / `move` | Move or rename files |
| `rm` / `del` | Delete files |

---

## 🔀 Git Version Control

| Command | Purpose |
|---------|---------|
| `git init` | Initialize Git repository |
| `git status` | Check status of files |
| `git add .` | Stage all changes |
| `git add filename` | Stage specific file |
| `git commit -m "message"` | Commit with message |
| `git log` | View commit history |
| `git branch branch-name` | Create new branch |
| `git checkout branch-name` | Switch to branch |
| `git checkout -b name` | Create and switch branch |
| `git merge branch-name` | Merge branch into current |
| `git push origin main` | Push to remote |
| `git pull origin main` | Pull from remote |
| `git restore filename` | Discard changes in file |

---

## 🎮 Modes

| Mode | Description | When to Use |
|------|-------------|-------------|
| **Bash Mode** | Execute terminal commands | System operations, file management |
| **Planning Mode** | Create detailed plans | Complex projects, unclear requirements |
| **Interactive Mode** | Ask clarifying questions | Ambiguous tasks |

---

## 💡 Common Workflows

### Starting a New Project
```bash
# 1. Create project directory
mkdir project-name
cd project-name

# 2. Initialize Git
git init

# 3. Start Claude Code
claude-code

# 4. After Claude generates code, commit
git add .
git commit -m "Initial project setup"
```

### Managing Sessions
```bash
# Resume last session
claude-code --resume

# Fork current session
/fork

# Clean up old sessions
/cleanup
```

### Git Workflow with Claude Code
```bash
# Check what Claude Code changed
git status

# Stage and commit changes
git add .
git commit -m "Added feature X with Claude Code"

# Push to remote
git push origin main
```

---

## 🚀 Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Shift/Alt + P` | [To be documented] |
| `Tab` | Autocomplete file/folder names |
| `↑` / `↓` | Cycle through command history |
| `Ctrl+D` | Exit Claude Code session |

---

## ⚡ Quick Tips

- File/folder names with spaces need quotes: `cd "My Folder"`
- Use Tab for autocomplete to avoid typos
- `rm -r` deletes permanently - use with caution
- Git Bash provides Unix-style commands on Windows
- Commit after every successful Claude Code generation
- Use descriptive commit messages explaining WHY, not just WHAT
- Never commit sensitive info (API keys, passwords) - use .gitignore

---

**Last Updated:** January 22, 2026