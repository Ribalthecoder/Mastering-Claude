# Session Management

---

## What It Is

Session Management is the comprehensive system within Claude Code that controls how conversations are created, stored, organized, tracked, and maintained over time. It encompasses all the functionality for managing multiple concurrent sessions, viewing session history, understanding session metadata (like creation time, file count, message count), organizing sessions by project, and performing maintenance tasks like cleaning up old sessions to free storage space and keep your workspace organized.

---

## Key Concepts

- **Session Lifecycle:** Creation → Active use → Pause/Exit → Storage → Resume or Delete
- **Session Metadata:** Information about each session (ID, creation date, last modified, project path, message count)
- **Concurrent Sessions:** Running multiple Claude Code sessions simultaneously in different projects
- **Session Storage:** Where and how Claude Code saves session data on your system
- **Session Organization:** Grouping and finding sessions by project, date, or other criteria
- **Session Cleanup:** Removing old or unnecessary sessions to maintain system performance

---

## Commands & Syntax
```bash
# View all sessions with details
claude-code --list-sessions
claude-code -ls

# Get detailed information about a session
claude-code --session-info <session-id>

# Delete a specific session
claude-code --delete-session <session-id>

# Clean up old sessions (interactive)
claude-code --cleanup-sessions

# Export session for backup or sharing
claude-code --export-session <session-id> --output session.json

# Import a previously exported session
claude-code --import-session session.json

# View current session information (while in session)
/session-info                         # Shows current session details
/session                              # Alternative command

# Rename current session
/rename-session "New descriptive name"
```

---

## When to Use

Use session management commands when you need to organize multiple projects, find and resume older sessions from weeks or months ago, clean up storage space by removing outdated sessions, share sessions with teammates (export/import), track how much work you've done across different projects, or troubleshoot issues with corrupted or problematic sessions.

---

## How It Works

**Step 1:** Claude Code automatically creates and tracks sessions as you work - no manual setup required

**Step 2:** Each session is assigned a unique ID and stored with metadata (timestamps, project path, message count)

**Step 3:** Use `--list-sessions` to view all your sessions with basic info (ID, date, project name)

**Step 4:** Select a session of interest and use `--session-info <id>` to see detailed information

**Step 5:** Resume sessions with `--resume <id>`, delete unwanted ones with `--delete-session <id>`, or export important ones for backup

**Step 6:** Periodically run `--cleanup-sessions` to review and remove old sessions, keeping only relevant work

---

## Common Issues

### Issue: Too many sessions cluttering the list
**Symptoms:** `--list-sessions` shows dozens or hundreds of old sessions  
**Solution:** Run `claude-code --cleanup-sessions` and interactively delete old/unused sessions, set up a regular cleanup schedule (weekly or monthly), delete sessions from abandoned projects

### Issue: Cannot find a specific old session
**Symptoms:** Need to resume work from weeks ago but can't identify which session  
**Solution:** Use `--session-info` on likely candidates to check project paths and dates, name sessions descriptively during work using `/rename-session`, keep better notes about which projects you worked on

### Issue: Session corruption or errors
**Symptoms:** Session won't resume or shows errors when loading  
**Solution:** Try resuming a different recent session from same project, start fresh session and manually reference old code, export working sessions regularly as backup, delete corrupted session if unrecoverable

---

## Important Notes

- ⚠️ **Warning:** Deleted sessions cannot be recovered - export important sessions before deleting for backup
- ⚠️ **Warning:** Sessions take up disk space - clean up regularly if storage is limited
- 💡 **Tip:** Name your sessions descriptively at the start: `/rename-session "E-commerce checkout feature"` for easy identification later
- 💡 **Tip:** Export milestone sessions before major refactors - if something breaks, you can return to exported state
- 💡 **Tip:** Review session list monthly and archive/delete completed project sessions
- 📌 **Remember:** Each project directory can have multiple sessions - they're not limited to one per project
- 📌 **Remember:** Session IDs are unique and persistent - save important IDs in project documentation for reference

