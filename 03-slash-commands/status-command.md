# /status Command

---

## What It Is

The `/status` command provides a real-time overview of your current Claude Code session, displaying critical information such as the active model being used, token usage and remaining capacity, files currently in context, session duration, number of messages exchanged, and other session metadata. This command acts as your session dashboard, helping you monitor resource usage, understand context limitations, troubleshoot issues, and make informed decisions about when to compact, clear, or optimize your session.

---

## Key Concepts

- **Session Dashboard:** Central view of all session metrics and information
- **Token Monitoring:** Track how much context capacity you're using vs available
- **Context Awareness:** See which files and directories Claude currently knows about
- **Model Information:** Confirm which AI model is handling your requests
- **Session Metrics:** Message count, duration, and other statistical data
- **Resource Management:** Data needed to optimize session performance

---

## Commands & Syntax
```bash
# Display full session status
/status

# Show detailed status with all metrics
/status --verbose

# Show only token usage information
/status --tokens

# Show only files in context
/status --files

# Show only model information
/status --model

# Compact view for quick check
/status --brief
```

---

## When to Use

Use `/status` when Claude Code responses seem slow or degraded to check token usage, before deciding whether to compact or clear session, when you want to verify which files Claude is aware of, to confirm model switch was successful after using `/model`, troubleshooting unexpected behavior by checking session state, or periodically during long development sessions to monitor resource consumption and prevent hitting limits.

---

## How It Works

**Step 1:** Type `/status` in your active Claude Code session

**Step 2:** Claude Code queries internal session state and gathers metrics

**Step 3:** Information is displayed in organized format showing key metrics

**Step 4:** Review the output to understand current session state

**Step 5:** Use the information to make decisions (compact if token usage high, add files if missing from context, etc.)

**Step 6:** Continue working with awareness of session resource status

---

## Common Issues

### Issue: Status shows files not actually in project
**Symptoms:** `/status --files` lists files that don't exist or are outdated  
**Solution:** Claude's context may be stale - manually update context with current file list, use `/context` or `/add-dir` to refresh, consider clearing and restarting session if severely out of sync

### Issue: Token usage approaching 100% but conversation feels short
**Symptoms:** High token count despite few visible messages  
**Solution:** Large files in context consume many tokens even with few messages, check `/status --files` to see what's loaded, remove unnecessary files from context, compact conversation to free space

### Issue: Status command not available
**Symptoms:** `/status` returns error or is not recognized  
**Solution:** Verify correct command syntax for your Claude Code version (might be `/session-info` or `/stats`), check if status functionality exists in your version, update Claude Code if using outdated version

---

## Important Notes

- 💡 **Tip:** Check `/status` regularly during long sessions to avoid hitting token limits unexpectedly
- 💡 **Tip:** If token usage exceeds 80%, consider compacting to free space for continued work
- 💡 **Tip:** Use `/status --files` to verify Claude has context on all files you're discussing
- 💡 **Tip:** Status is non-destructive - checking it doesn't change anything, safe to use anytime
- 📌 **Remember:** Token usage includes conversation history + files in context + current message
- 📌 **Remember:** Different models have different token limits - Opus typically highest, Haiku lowest

