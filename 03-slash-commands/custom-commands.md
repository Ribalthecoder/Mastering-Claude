# Custom Slash Commands

---

## What It Is

Custom Slash Commands allow you to create your own personalized commands that execute predefined actions, run specific workflows, or trigger complex sequences of operations with simple shortcuts. Instead of typing repetitive instructions or long prompts, you can define custom commands that encapsulate common tasks, project-specific operations, or team workflows, making your Claude Code usage more efficient and consistent by turning frequent multi-step processes into single-command shortcuts.

---

## Key Concepts

- **Command Creation:** Defining your own slash commands with custom behavior
- **Workflow Automation:** Encapsulating repetitive tasks into reusable commands
- **Team Standards:** Creating shared commands for consistent team workflows
- **Command Aliases:** Shortcuts for frequently used operations
- **Parameterized Commands:** Custom commands that accept arguments
- **Command Library:** Collection of custom commands for your projects

---

## Commands & Syntax
```bash
# Create a new custom command
/create-command name "description" "action"

# Example: Create command for running tests
/create-command test "Run all tests" "npm test && echo 'Tests completed'"

# Create command with parameters
/create-command deploy "Deploy to environment" "npm run deploy --env={env}"

# List all custom commands
/list-custom-commands

# Edit existing custom command
/edit-command test

# Delete custom command
/delete-command name

# Execute custom command
/test                                 # Runs your custom test command
/deploy production                    # Runs deploy with parameter

# Export custom commands for sharing
/export-commands commands.json

# Import custom commands
/import-commands commands.json
```

---

## When to Use

Create custom commands for repetitive development workflows (build, test, deploy sequences), project-specific operations that require multiple steps, team-standard processes everyone should follow consistently, complex git operations you frequently perform, environment setup tasks for new developers, or any multi-step process you find yourself doing repeatedly throughout development.

---

## How It Works

**Step 1:** Identify a repetitive task or workflow you perform frequently

**Step 2:** Break down the steps into a sequence of actions or a template prompt

**Step 3:** Use `/create-command` to define the custom command with name and behavior

**Step 4:** Test the command to ensure it works as expected

**Step 5:** Use your custom command throughout development by typing `/<command-name>`

**Step 6:** Share commands with team by exporting and having them import

---

## Common Issues

### Issue: Custom command not working as expected
**Symptoms:** Command runs but doesn't perform intended actions  
**Solution:** Review command definition with `/list-custom-commands`, test individual steps separately to identify which fails, revise command with `/edit-command`, ensure proper syntax and escaping of special characters

### Issue: Command name conflicts with built-in commands
**Symptoms:** Custom command doesn't execute or built-in version runs instead  
**Solution:** Choose unique names that don't overlap with standard slash commands, use prefixes like `/my-` or `/custom-` for your commands, check `/list-custom-commands` and built-in list before naming

### Issue: Parameters not passing correctly
**Symptoms:** Parameterized command doesn't use provided values  
**Solution:** Verify parameter syntax in command definition (usually `{param-name}`), check if command definition properly references parameters, test with simple parameters first before complex ones

---

## Important Notes

- 💡 **Tip:** Start with simple custom commands before creating complex multi-step workflows
- 💡 **Tip:** Document your custom commands with clear descriptions for team members
- 💡 **Tip:** Export and version control your commands.json file with project for team sharing
- 💡 **Tip:** Use descriptive names that clearly indicate what the command does
- 💡 **Tip:** Create project-specific command libraries for different codebases
- 📌 **Remember:** Custom commands are session/project-specific unless explicitly shared
- 📌 **Remember:** Commands can execute bash operations, so be cautious with destructive actions

