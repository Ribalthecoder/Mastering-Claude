# Bash Subagent

---

## What It Is

Bash Subagent is a specialized subagent dedicated to executing terminal commands, shell scripts, and system operations, providing a focused environment for command-line tasks while keeping the main Claude Code session clean for development work. This subagent operates with Bash Mode enabled by default, allowing it to run commands, manage processes, interact with system utilities, and handle DevOps operations without cluttering your primary conversation with command outputs and system interactions.

---

## Key Concepts

- **Dedicated Command Execution:** Subagent specialized for terminal operations
- **Bash Mode Default:** Always operates with command execution enabled
- **System Operations:** File management, process control, system utilities
- **Script Execution:** Running shell scripts and automation workflows
- **DevOps Tasks:** Deployment, server management, infrastructure operations
- **Isolated Context:** Command history and outputs separate from main session

---

## Commands & Syntax
```bash
# Spawn bash subagent
/spawn-bash-subagent

# Quick spawn bash subagent with task
/bash-subagent "Deploy application to staging"

# Spawn with specific directory context
/bash-subagent --dir /path/to/project "Run build scripts"

# Execute command via bash subagent
/bash-subagent-exec "npm install && npm test"

# Get command history from bash subagent
/bash-subagent-history

# Retrieve bash subagent output
/bash-subagent-results
```

---

## When to Use

Use Bash Subagent for deployment operations that require multiple commands, running build processes while continuing development, executing maintenance scripts and system operations, managing infrastructure through CLI tools, running long command sequences without blocking main session, or any DevOps work that's distinct from code development tasks.

---

## How It Works

**Step 1:** Spawn bash subagent with `/spawn-bash-subagent` or `/bash-subagent`

**Step 2:** Subagent initializes with Bash Mode enabled and system access

**Step 3:** Assign command-line tasks to the bash subagent

**Step 4:** Subagent executes commands, scripts, and system operations

**Step 5:** Command outputs and results are captured in subagent's context

**Step 6:** Main session continues development work without command clutter

**Step 7:** Retrieve command results and outputs when needed

---

## Common Issues

### Issue: Bash subagent commands failing due to permissions
**Symptoms:** Permission denied errors on system operations  
**Solution:** Ensure subagent has necessary permissions, use sudo for privileged operations, verify file/directory ownership, check security policies

### Issue: Cannot see command output in main session
**Symptoms:** Subagent ran commands but outputs not visible  
**Solution:** This is intentional - use `/bash-subagent-results` to retrieve, outputs stay in subagent context to avoid clutter, can redirect important outputs to files for main session access

### Issue: Bash subagent stuck on interactive command
**Symptoms:** Command requires user input, subagent appears frozen  
**Solution:** Avoid interactive commands in subagents, use command flags to skip prompts (--yes, --force), provide inputs via stdin redirection

---

## Important Notes

- ⚠️ **Warning:** Bash subagent has system access - be careful with destructive commands
- ⚠️ **Warning:** Long-running commands may time out - use async pattern for very long tasks
- 💡 **Tip:** Use bash subagent to keep deployment work separate from development
- 💡 **Tip:** Bash subagent is perfect for CI/CD type operations
- 💡 **Tip:** Review command history before critical operations to verify correctness
- 💡 **Tip:** Can spawn multiple bash subagents for different environments (dev, staging, prod)
- 📌 **Remember:** Bash subagent inherits your system environment and permissions
- 📌 **Remember:** Command outputs stay in subagent context unless explicitly retrieved
