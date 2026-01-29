# --agent Flag

---

## What It Is

The `--agent` flag is a command-line parameter used when starting Claude Code that specifies which subagent or agent configuration to use from the beginning, allowing you to launch directly into a specialized agent role rather than starting with the default general-purpose agent. This is particularly useful for dedicated workflows where you know in advance what type of work you'll be doing, enabling you to skip manual agent spawning and configuration by starting with the right agent profile from the command line.

---

## Key Concepts

- **Direct Agent Launch:** Starting Claude Code with specific agent configuration
- **Agent Profiles:** Predefined configurations for different roles or tasks
- **Command-Line Configuration:** Setting agent type before session begins
- **Workflow Optimization:** Skipping manual setup for known use cases
- **Role Specialization:** Launching into specific expertise from the start
- **Configuration Persistence:** Agent settings apply for entire session

---

## Commands & Syntax
```bash
# Start Claude Code with specific agent
claude-code --agent testing
claude-code --agent documentation
claude-code --agent code-review

# Use agent with specific model
claude-code --agent refactoring --model opus

# Combine with other flags
claude-code --agent security-audit --verbose

# Start with custom agent configuration
claude-code --agent-config ./configs/custom-agent.json

# List available agent profiles
claude-code --list-agents

# Start with agent and specific directory
claude-code --agent frontend-dev --dir ./src/components
```

---

## When to Use

Use `--agent` flag when starting dedicated sessions for specific tasks (testing day, documentation sprint, code review session), you know the exact type of work before launching Claude Code, working within established workflows with defined agent roles, team members specializing in different areas using appropriate agents, or when you want consistent behavior across multiple sessions for the same task type.

---

## How It Works

**Step 1:** Identify the agent profile that matches your intended work

**Step 2:** Launch Claude Code with `--agent profile-name` from terminal

**Step 3:** Claude Code loads specified agent configuration on startup

**Step 4:** Session begins with agent-specific context, rules, and behavior

**Step 5:** All work in session follows agent's specialized configuration

**Step 6:** No need to manually spawn or configure agent after launch

**Step 7:** Exit and restart with different agent for different task types

---

## Common Issues

### Issue: Agent profile doesn't exist
**Symptoms:** Error message about unknown agent when launching  
**Solution:** Use `--list-agents` to see available profiles, check spelling of agent name, verify agent configurations are installed, create custom agent if needed

### Issue: Agent configuration conflicts with project CLAUDE.md
**Symptoms:** Unexpected behavior due to conflicting rules  
**Solution:** Agent settings typically override CLAUDE.md - document this, review agent config to understand precedence, adjust CLAUDE.md or agent config to align

### Issue: Want to switch agent mid-session
**Symptoms:** Started with wrong agent but already in session  
**Solution:** Cannot change agent mid-session - must exit and restart, spawn subagent with different profile instead, plan agent choice more carefully before launching

---

## Important Notes

- 💡 **Tip:** Create agent profiles for frequently performed tasks
- 💡 **Tip:** Use descriptive agent names that clearly indicate purpose
- 💡 **Tip:** Document available agents and when to use each for team
- 💡 **Tip:** Combine `--agent` with `--resume` to continue specialized sessions
- 📌 **Remember:** Agent choice affects entire session - choose at launch
- 📌 **Remember:** Can still spawn additional subagents even when using `--agent`
- 📌 **Remember:** Agent profiles are reusable configurations, not one-time settings

