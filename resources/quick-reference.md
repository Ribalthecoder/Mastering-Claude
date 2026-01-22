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
# 1. Initialize Claude Code in project
claude-code /init

# 2. Add project directories
/add-dir src/

# 3. Start planning
/planning-mode
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

---

## 🚀 Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Shift/Alt + P` | [To be documented] |

---

## 📚 File Structure
```
project/
├── CLAUDE.md           # Main configuration
├── .claude/            # Claude Code data
│   ├── rules/         # Project-specific rules
│   └── skills/        # Custom skills
```

---

*This reference will be expanded with examples and detailed explanations as the course progresses.*

**Last Updated:** January 22, 2026