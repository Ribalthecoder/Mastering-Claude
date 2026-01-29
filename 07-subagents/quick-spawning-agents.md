# Quick Spawning Subagents

---

## What It Is

Quick Spawning Subagents is a streamlined workflow for rapidly creating multiple subagents with minimal configuration, using templates, presets, and shortcuts to reduce the overhead of spawning agents for common tasks. Instead of manually configuring each subagent with detailed instructions, quick spawning allows you to launch agents using predefined roles, task templates, or simple descriptions, making it practical to leverage parallel processing even for smaller tasks where setup time would otherwise negate the benefits.

---

## Key Concepts

- **Rapid Deployment:** Creating subagents in seconds rather than minutes
- **Template-Based:** Using predefined configurations for common roles
- **Preset Roles:** Standard agent types (tester, documenter, refactorer)
- **Minimal Configuration:** Spawning with just task description
- **Batch Creation:** Spawning multiple agents simultaneously
- **Default Context:** Agents inherit sensible defaults automatically

---

## Commands & Syntax
```bash
# Quick spawn with role template
/quick-spawn tester
/quick-spawn documenter
/quick-spawn refactorer

# Quick spawn with simple description
/qspawn "Write unit tests"

# Batch spawn from list
/qspawn-batch "Build API" "Write tests" "Create docs"

# Quick spawn with file context
/qspawn "Review this file" --file auth.js

# Use preset configurations
/qspawn --preset code-review
/qspawn --preset security-audit

# Quick spawn inheriting main context
/qspawn "Optimize performance" --inherit-context
```

---

## When to Use

Use quick spawning when you need parallel work but don't have time for detailed setup, tasks follow common patterns that fit preset roles, experimenting with multi-agent workflows before committing to complex orchestration, handling straightforward parallelizable work (multiple files to process, multiple components to build), or when the cost of setup would outweigh parallelization benefits with traditional spawning.

---

## How It Works

**Step 1:** Identify tasks that fit common patterns or can be described simply

**Step 2:** Use `/qspawn` with role name or brief task description

**Step 3:** System automatically configures subagent with appropriate defaults

**Step 4:** Subagent inherits relevant context from main session

**Step 5:** Agent begins work immediately without additional setup

**Step 6:** Retrieve results same as traditional subagents

**Step 7:** Terminate when done or let system auto-cleanup completed agents

---

## Common Issues

### Issue: Quick-spawned agent lacks necessary context
**Symptoms:** Subagent doesn't understand project specifics  
**Solution:** Use `--inherit-context` flag to pass main context, explicitly mention files with `--file` flag, add brief context in task description

### Issue: Preset role doesn't match actual need
**Symptoms:** Agent behavior doesn't align with expectations  
**Solution:** Use custom description instead of preset, combine preset with additional instructions, create custom presets for frequently used patterns

### Issue: Too quick - spawned agents without clear objectives
**Symptoms:** Subagent produces vague or incorrect results  
**Solution:** Be more specific in task description even when quick spawning, review and refine objectives before spawning, use traditional spawn for complex tasks

---

## Important Notes

- 💡 **Tip:** Quick spawn is perfect for "parallel grunt work" (process multiple files, test multiple functions)
- 💡 **Tip:** Use presets for standard tasks, custom descriptions for unique needs
- 💡 **Tip:** Quick spawning sacrifices some control for speed - acceptable tradeoff for simple tasks
- 💡 **Tip:** Combine quick spawn with traditional spawn - use each where appropriate
- 📌 **Remember:** Quick spawn doesn't mean less capable - just faster setup
- 📌 **Remember:** Can always provide additional instructions to quick-spawned agents
- 📌 **Remember:** Speed benefit only matters if you're actually spawning multiple agents
