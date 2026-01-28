# Session Cleanup

---

## What It Is

Session Cleanup is the process of reviewing, organizing, and deleting old or unnecessary Claude Code sessions to maintain system performance, free up disk storage space, and keep your session list manageable and navigable. Over time, as you work on multiple projects and create numerous sessions, your system accumulates session data that can slow down Claude Code operations, make finding relevant sessions difficult, and consume significant storage - regular cleanup ensures your development environment remains efficient and organized.

---

## Key Concepts

- **Session Accumulation:** Natural buildup of sessions over weeks and months of development work
- **Storage Impact:** Each session stores conversation history, file snapshots, and metadata consuming disk space
- **Performance Degradation:** Too many sessions can slow down session listing and loading operations
- **Cleanup Strategy:** Systematic approach to deciding which sessions to keep vs delete
- **Session Archival:** Exporting important sessions before deletion as backup
- **Maintenance Schedule:** Regular intervals for cleanup (weekly, monthly, or project-based)

---

## Commands & Syntax
```bash
# Interactive cleanup - reviews sessions one by one
claude-code --cleanup-sessions

# List sessions sorted by age (oldest first)
claude-code --list-sessions --sort-by-date

# Delete specific session by ID
claude-code --delete-session <session-id>

# Delete all sessions older than X days
claude-code --delete-sessions-older-than 90

# Delete all sessions from specific project path
claude-code --delete-sessions-in /path/to/old-project

# Export session before deleting (backup)
claude-code --export-session <session-id> --output backup.json

# Check total storage used by sessions
claude-code --session-storage-info
```

---

## When to Use

Perform session cleanup when your session list becomes difficult to navigate (dozens of entries), you receive low disk space warnings, Claude Code operations feel slower than usual, you've completed and archived a project, you're doing quarterly or monthly maintenance, or before starting a major new project to ensure a clean working environment.

---

## How It Works

**Step 1:** Run `claude-code --list-sessions` to review all existing sessions and identify candidates for deletion

**Step 2:** For each old session, check project status - if project is complete/archived, session can likely be deleted

**Step 3:** Export any sessions containing important architectural decisions or complex code before deleting

**Step 4:** Use `--cleanup-sessions` for interactive review, or `--delete-session <id>` for specific deletions

**Step 5:** Delete sessions from abandoned projects, failed experiments, or duplicates immediately

**Step 6:** Keep only active project sessions and important reference sessions for completed projects

---

## Common Issues

### Issue: Accidentally deleted important session
**Symptoms:** Realized after deletion that session contained needed information  
**Solution:** Check if you have exported backup of the session, review Git history if code was committed, recreate work from memory or documentation - prevention is key, always export before deleting important sessions

### Issue: Unsure which sessions are safe to delete
**Symptoms:** Large list of sessions, afraid to delete anything important  
**Solution:** Only delete sessions from projects you've completely abandoned, export questionable sessions as backup before deleting, keep sessions from last 30 days by default, delete anything older only if project is done

### Issue: Cleanup doesn't free much space
**Symptoms:** Deleted many sessions but disk usage barely changed  
**Solution:** Session storage might not be your issue - check other large files/folders, ensure sessions were fully deleted not just archived, restart Claude Code to clear caches

---

## Important Notes

- ⚠️ **Warning:** Deleted sessions are permanent - no undo or recovery without exported backup
- ⚠️ **Warning:** Do not delete active project sessions - only cleanup completed or abandoned work
- 💡 **Tip:** Export sessions before deletion for important projects - storage is cheap, lost work is expensive
- 💡 **Tip:** Set up monthly cleanup reminders - prevents overwhelming accumulation
- 💡 **Tip:** Delete experimental/fork sessions immediately after deciding which approach to use
- 📌 **Remember:** Cleanup is maintenance, not required - do it when list becomes unmanageable or storage is limited
- 📌 **Remember:** If project code is in Git, session deletion is low-risk - you can always start fresh with existing code

