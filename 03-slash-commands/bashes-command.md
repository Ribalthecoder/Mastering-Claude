# /bashes Command

---

## What It Is

The `/bashes` command displays a history of all bash/terminal commands that were executed during your current Claude Code session, providing a chronological log of shell operations performed either by Claude Code directly or through your manual terminal inputs. This command serves as an audit trail for system operations, helping you track what commands were run, troubleshoot issues by reviewing executed commands, reproduce successful operations, or understand the sequence of terminal actions that led to the current project state.

---

## Key Concepts

- **Command History:** Record of all bash commands executed in session
- **Execution Log:** Chronological list showing when and what was run
- **Audit Trail:** Track system operations for debugging and documentation
- **Command Reproducibility:** Reference past commands to repeat successful operations
- **Session-Specific:** Only shows commands from current session, not global terminal history
- **Both Manual and AI:** Includes commands you typed AND commands Claude Code executed

---

## Commands & Syntax
```bash
# Display all bash commands from current session
/bashes

# Show commands with timestamps
/bashes --timestamps

# Show last N commands only
/bashes --last 10

# Show commands with execution results/output
/bashes --verbose

# Filter commands by keyword
/bashes --filter "git"                # Show only git commands

# Export bash history to file
/bashes --export bash-history.txt
```

---

## When to Use

Use `/bashes` when you need to remember what commands were run earlier in the session, troubleshooting failed operations by reviewing command sequence, documenting your development process for team members or documentation, recreating a successful build/deployment sequence, verifying that dangerous commands (like deletions) were or weren't executed, or creating scripts by collecting the working commands from your session.

---

## How It Works

**Step 1:** Throughout your Claude Code session, all bash commands are logged automatically

**Step 2:** This includes commands Claude Code ran on your behalf and commands you manually entered

**Step 3:** Type `/bashes` to retrieve the complete command log for current session

**Step 4:** Review the output showing commands in order of execution

**Step 5:** Use the information to troubleshoot, document, or reproduce operations

**Step 6:** Optionally export the history to a file for permanent record or script creation

---

## Common Issues

### Issue: Command history is empty or incomplete
**Symptoms:** `/bashes` shows nothing or missing commands  
**Solution:** History only captures commands from current session - won't show pre-session commands, verify bash mode was enabled when commands were run, some Claude Code versions may not log all operations

### Issue: Too many commands to review effectively
**Symptoms:** Hundreds of commands making it hard to find relevant ones  
**Solution:** Use `/bashes --last 20` to see recent commands only, use `/bashes --filter "keyword"` to narrow down to specific command types, export to file and search with text editor

### Issue: Cannot tell which commands succeeded vs failed
**Symptoms:** List shows commands but not their outcomes  
**Solution:** Use `/bashes --verbose` to see execution results if available, manually test suspicious commands to verify they worked, check actual file system state to confirm command effects

---

## Important Notes

- 💡 **Tip:** Review `/bashes` before exiting session to document what was done
- 💡 **Tip:** Use command history to create deployment scripts from successful dev sessions
- 💡 **Tip:** Export bash history for complex setups to avoid repeating manual command sequences
- 💡 **Tip:** Filter by keywords (npm, git, docker) to audit specific tool usage
- 📌 **Remember:** History is session-specific - clears when you exit Claude Code
- 📌 **Remember:** Shows commands executed, not necessarily their results or success status
