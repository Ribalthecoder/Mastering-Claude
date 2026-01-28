# /clear Command

---

## What It Is

The `/clear` command in Claude Code immediately removes all conversation history and context from the current session, effectively resetting it to a blank state as if you just started Claude Code for the first time. This command wipes Claude's memory of previous messages, generated code, file awareness, and project understanding, giving you a fresh start while remaining in the same session - useful when you want to start over without exiting and creating a new session.

---

## Key Concepts

- **Context Reset:** Removes all conversation history and Claude's awareness of what happened previously
- **In-Session Reset:** Clears without exiting - you stay in the same session but with blank slate
- **Memory Wipe:** Claude forgets all previous code, decisions, and file modifications discussed
- **Clean Start:** Equivalent to starting a new session but keeps the same session ID
- **Irreversible Action:** Once cleared, previous conversation cannot be recovered in that session
- **File Persistence:** Files on disk remain unchanged - only Claude's memory is cleared

---

## Commands & Syntax
```bash
# Clear all conversation history immediately
/clear

# Clear with confirmation prompt (if available)
/clear --confirm

# Alternative syntax (some versions)
/reset
```

---

## When to Use

Use `/clear` when the conversation has gone off track and you want to restart with a different approach, the context has become too cluttered with failed attempts or irrelevant information, you're switching to a completely different task in the same project, you want to test if Claude can solve a problem without prior context, or when the session is confused and giving inconsistent responses due to accumulated context.

---

## How It Works

**Step 1:** Recognize that current conversation context is problematic or no longer useful

**Step 2:** Type `/clear` in the Claude Code session

**Step 3:** Claude Code immediately erases all conversation history from memory

**Step 4:** Your session continues but Claude has no memory of anything discussed before the clear

**Step 5:** Start fresh as if you just launched Claude Code - re-explain project context if needed

**Step 6:** Continue working with clean context - previous mistakes and wrong paths are forgotten

---

## Common Issues

### Issue: Accidentally cleared important conversation
**Symptoms:** Hit `/clear` by mistake, lost valuable context or code snippets  
**Solution:** Check if session was auto-saved before clear (some versions save snapshots), review actual files on disk - code Claude generated is still there, manually document important decisions before clearing in future

### Issue: Claude still seems to remember things after clear
**Symptoms:** Claude references information from before the `/clear` command  
**Solution:** Verify `/clear` command completed successfully, exit and restart session if behavior persists, ensure you're using correct clear syntax for your Claude Code version

### Issue: Needed to partially clear, not full reset
**Symptoms:** Wanted to remove recent context but keep earlier valuable conversation  
**Solution:** Use `/rewind` instead to go back to specific point, fork session before clearing if you might want to return, `/clear` is all-or-nothing - consider if it's the right tool

---

## Important Notes

- ⚠️ **Warning:** `/clear` is permanent - cannot undo or recover cleared conversation in that session
- ⚠️ **Warning:** Files on disk are NOT affected - only Claude's memory is cleared, not your actual code
- 💡 **Tip:** Before clearing, copy any important code snippets or decisions Claude mentioned to a file
- 💡 **Tip:** Consider `/rewind` if you only need to undo recent mistakes, not clear everything
- 💡 **Tip:** Use `/clear` when starting a completely different component/feature in the same project
- 📌 **Remember:** Your files remain unchanged - `/clear` only affects what Claude remembers
- 📌 **Remember:** After clearing, you'll need to re-explain project context for Claude to understand it again

