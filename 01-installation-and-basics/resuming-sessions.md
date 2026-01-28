# Resuming Sessions

---

## What It Is

Resuming sessions is a Claude Code feature that allows you to continue a previous conversation and work context from where you left off, rather than starting fresh each time you launch Claude Code. When you resume a session, Claude Code reloads all the previous conversation history, remembers the files you were working on, maintains awareness of your project context, and allows you to continue building without re-explaining everything, making it essential for multi-day projects or when you need to step away and return later.

---

## Key Concepts

- **Session Persistence:** Claude Code saves your conversation history and context for later retrieval
- **Context Continuity:** Resumed sessions maintain awareness of previous decisions, code generated, and project structure
- **Session ID:** Each session has a unique identifier used to resume it later
- **Active Session:** The current conversation you're in right now
- **Session History:** A log of all your previous sessions available for resuming
- **Cold Start vs Resume:** Starting fresh loses all context; resuming preserves everything

---

## Commands & Syntax
```bash
# Resume the most recent session
claude-code --resume
claude-code -r                        # Short form

# List all available sessions
claude-code --list-sessions
claude-code -ls

# Resume a specific session by ID
claude-code --resume <session-id>
claude-code -r <session-id>

# View session details before resuming
claude-code --session-info <session-id>

# Start a new session (default behavior)
claude-code                           # Always starts fresh unless --resume used
```

---

## When to Use

Resume sessions whenever you're continuing work on an existing project where Claude Code has prior context - such as returning to a project after a break, continuing development from yesterday, picking up after closing your terminal accidentally, or when you want Claude to remember previous architectural decisions and code it generated. Always resume when working on multi-session projects to maintain continuity and avoid repeating explanations.

---

## How It Works

**Step 1:** When you finish a Claude Code session and exit, the session is automatically saved with all conversation history and context

**Step 2:** Later, when you want to continue, navigate to the same project directory in your terminal

**Step 3:** Run `claude-code --resume` to reload your most recent session in that project

**Step 4:** Claude Code restores the full conversation, remembers what files exist, and knows the project state

**Step 5:** Continue your conversation naturally - Claude remembers previous decisions and generated code

**Step 6:** You can reference earlier parts of the conversation: "Remember that login component you created earlier? Modify it to..."

---

## Common Issues

### Issue: "No session to resume" error
**Symptoms:** Claude Code says no previous session exists  
**Solution:** Ensure you're in the correct project directory where the original session occurred, verify sessions weren't cleaned up or deleted, check if you've ever run Claude Code in this directory before

### Issue: Resumed session has outdated context
**Symptoms:** Claude doesn't know about recent file changes made outside of Claude Code  
**Solution:** After resuming, update Claude on external changes: "I manually edited auth.js since our last session", use `/context` command to refresh file awareness if available

### Issue: Cannot find specific session to resume
**Symptoms:** Want to resume older session but `--resume` only loads most recent  
**Solution:** Use `claude-code --list-sessions` to see all available sessions with IDs, then use `claude-code --resume <session-id>` to load specific one

---

## Important Notes

- ⚠️ **Warning:** Resuming works best in the same project directory - changing directories can confuse context
- 💡 **Tip:** Always resume sessions for ongoing projects - it saves time explaining context and prevents inconsistencies
- 💡 **Tip:** Use descriptive first messages in new sessions so you can identify them later when browsing session history
- 📌 **Remember:** Sessions are tied to directories - navigate to the project folder before resuming
- 📌 **Remember:** If you made significant changes outside Claude Code between sessions, inform Claude after resuming
