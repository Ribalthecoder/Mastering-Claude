# Quick Reference Guide

Essential commands and workflows for Claude Code.

---

## 🔧 Core Slash Commands

| Command | Purpose |
|---------|---------|
| `/clear` | Clear the current session |
| `/rewind` | Rewind to a previous point |
| `/status` | Show current session status |
| `/context` | View current context |
| `/add-dir` | Add directory to context |

---

## 🖥️ Essential Terminal Commands

| Command | Purpose |
|---------|---------|
| `pwd` | Show current directory |
| `ls` / `dir` | List files and folders |
| `cd folder-name` | Change directory |
| `cd ..` | Move up one level |
| `mkdir folder-name` | Create directory |

---

## 🔀 Git Essentials

| Command | Purpose |
|---------|---------|
| `git status` | Check file status |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Commit with message |
| `git push origin main` | Push to remote |
| `git pull origin main` | Pull from remote |

---

## 🔄 Sessions

| Command | Purpose |
|---------|---------|
| `claude-code` | Start new session |
| `claude-code --resume` | Resume last session |
| `claude-code --list-sessions` | List all sessions |

---

## 💡 Common Workflows

### New Project
```bash
mkdir project-name && cd project-name
git init
claude-code
```

### Continue Existing Project
```bash
cd project-name
claude-code --resume
```

### Save Progress
```bash
git add .
git commit -m "Description"
git push
```

---

## ⚡ Quick Tips

- Resume sessions for ongoing projects
- Commit after every Claude Code generation
- Use Tab for autocomplete
- Navigate to project directory before resuming

---

**Last Updated:** January 22, 2026