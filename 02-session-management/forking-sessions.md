# Forking Sessions

---

## What It Is

Forking sessions is a feature that allows you to create a copy or branch of your current Claude Code conversation at a specific point in time, enabling you to explore different approaches or solutions without affecting your main session. Similar to Git branches for code, forking creates a divergent path where you can experiment with alternative implementations, test risky changes, or explore multiple solutions to the same problem simultaneously, while keeping your original session intact and accessible.

---

## Key Concepts

- **Session Fork:** A duplicate of your conversation at a specific moment, creating two independent paths
- **Parent Session:** The original session from which the fork was created
- **Child Session:** The new forked session that branches off from the parent
- **Divergence Point:** The exact moment in the conversation where the fork occurred
- **Parallel Experimentation:** Running multiple solution approaches simultaneously without mixing contexts
- **Safe Exploration:** Testing ideas without risk of corrupting your working session

---

## Commands & Syntax
```bash
# Fork the current session (creates new branch)
/fork

# Fork with a descriptive name
/fork "Trying React instead of Vue"

# Fork at a specific point in conversation (if supported)
/fork --at-message <message-id>

# View fork tree (see parent and child relationships)
/fork-tree

# Switch between forked sessions
claude-code --resume <forked-session-id>

# Merge insights from fork back to parent (manual process)
# Copy useful code/decisions from forked session to parent session
```

---

## When to Use

Fork sessions when you want to try a completely different architectural approach without losing your current progress, experiment with risky refactorings that might break things, explore multiple UI design options simultaneously, test alternative libraries or frameworks for the same feature, or when a stakeholder asks "what if we did it this other way" and you want to preserve both options.

---

## How It Works

**Step 1:** While in an active Claude Code session, decide you want to try an alternative approach

**Step 2:** Use `/fork` command with an optional descriptive name for the experiment

**Step 3:** Claude Code creates a copy of your session up to this point and starts a new independent session

**Step 4:** Continue working in the forked session - all changes happen only in this fork, not the parent

**Step 5:** Exit the fork and use `--list-sessions` to see both your original and forked sessions

**Step 6:** Resume either session independently - compare results, merge best parts manually, or abandon unsuccessful fork

---

## Common Issues

### Issue: Lost track of which session is the fork vs original
**Symptoms:** Multiple similar sessions, unsure which contains which approach  
**Solution:** Always name forks descriptively when creating them (`/fork "Material UI version"`), use `--session-info` to check session creation times and metadata, keep notes outside Claude Code about which session is which

### Issue: Want to merge forked changes back to parent
**Symptoms:** Fork has good code, need it in main session  
**Solution:** Claude Code doesn't auto-merge - manually copy code from fork to parent, resume parent session and describe what to add from fork, use Git to manage actual code merging outside Claude Code sessions

### Issue: Too many forks creating confusion
**Symptoms:** Dozens of experimental forks cluttering session list  
**Solution:** Delete unsuccessful forks promptly with `--delete-session`, name forks clearly so you know which to keep, commit good code to Git then delete the fork session

---

## Important Notes

- ⚠️ **Warning:** Forks are independent - changes in one don't affect the other, manual merging required
- 💡 **Tip:** Fork before major refactorings - if the refactor fails, you haven't lost your working version
- 💡 **Tip:** Use forks to compare frameworks: fork once for React implementation, another for Vue, then choose best
- 💡 **Tip:** Name forks descriptively immediately - "API refactor" is better than "Fork 1"
- 📌 **Remember:** Forks share history up to divergence point - they start identical then diverge
- 📌 **Remember:** Commit your main session to Git before forking - provides additional safety net

