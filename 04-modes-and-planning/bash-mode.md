# Bash Mode

---

## What It Is

Bash Mode is a specialized operating mode in Claude Code that enables direct execution of terminal commands and shell operations, allowing Claude to interact with your system's file structure, run build tools, execute scripts, manage processes, and perform system-level operations autonomously. When Bash Mode is enabled, Claude can execute commands like a human developer would in the terminal, making it possible to automate complex workflows, run tests, manage dependencies, and perform operations that require actual system interaction beyond just generating code.

---

## Key Concepts

- **Direct Command Execution:** Claude runs actual bash commands on your system
- **System Interaction:** Ability to manipulate files, processes, and system state
- **Autonomous Operations:** Claude decides and executes commands based on your requests
- **Permission-Based:** Requires explicit authorization to execute potentially dangerous commands
- **Real-Time Feedback:** Claude sees actual command output and can react accordingly
- **Workflow Automation:** Chaining multiple commands to accomplish complex tasks

---

## Commands & Syntax
```bash
# Enable Bash Mode
/bash-mode on
/bash                                 # Short form

# Disable Bash Mode
/bash-mode off

# Check if Bash Mode is active
/bash-mode status

# Execute single command in Bash Mode
/bash "npm install"

# Execute with elevated permissions (if needed)
/bash --sudo "apt-get install package"

# Execute with confirmation prompt
/bash --confirm "rm -rf build/"
```

---

## When to Use

Use Bash Mode when you need Claude to install dependencies, run build processes, execute test suites, manage git operations, create and modify file structures, deploy applications, debug by running commands and examining output, or automate any development workflow that requires actual command execution rather than just code generation.

---

## How It Works

**Step 1:** Enable Bash Mode with `/bash-mode on` to grant execution permissions

**Step 2:** Describe what you want to accomplish (e.g., "install project dependencies and run tests")

**Step 3:** Claude analyzes the task and determines necessary bash commands

**Step 4:** Commands are executed on your system with real-time output captured

**Step 5:** Claude observes command results (success/failure, output, errors)

**Step 6:** Based on results, Claude may execute follow-up commands or report findings to you

---

## Common Issues

### Issue: Commands fail due to insufficient permissions
**Symptoms:** "Permission denied" errors when Claude tries to execute commands  
**Solution:** Ensure Claude has necessary permissions in `/permissions`, run commands that require sudo with `--sudo` flag, verify file/directory permissions are correct

### Issue: Dangerous command rejected
**Symptoms:** Claude refuses to execute certain commands (like `rm -rf`)  
**Solution:** This is intentional safety mechanism, use `--confirm` flag to acknowledge risk, manually execute dangerous operations if necessary, reconsider if operation is truly needed

### Issue: Command output not visible or useful
**Symptoms:** Cannot see what commands are doing or their results  
**Solution:** Use verbose mode if available to see full output, ask Claude to show command output explicitly, check if output is being redirected or suppressed

---

## Important Notes

- ⚠️ **Warning:** Bash Mode gives Claude real system access - only enable for trusted operations
- ⚠️ **Warning:** Review commands before execution, especially file deletions or system modifications
- ⚠️ **Warning:** Disable Bash Mode when not needed to prevent accidental command execution
- 💡 **Tip:** Start with read-only operations (ls, cat, git status) to verify Bash Mode is working safely
- 💡 **Tip:** Use Bash Mode for repetitive command sequences to save time
- 💡 **Tip:** Combine with Planning Mode to review command strategy before execution
- 📌 **Remember:** Commands execute in your current directory context
- 📌 **Remember:** Bash Mode persists until disabled - turn off when task is complete

