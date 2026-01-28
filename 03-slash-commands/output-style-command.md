# /output-style Command

---

## What It Is

The `/output-style` command allows you to customize how Claude Code formats and presents its responses, controlling aspects like verbosity level, code formatting preferences, explanation detail, output structure, and presentation style. This command enables you to tailor Claude's communication to match your preferences, workflow, and experience level, whether you want concise answers for quick tasks, detailed explanations for learning, specific code formatting standards, or structured outputs for documentation purposes.

---

## Key Concepts

- **Response Formatting:** How Claude structures and presents information
- **Verbosity Control:** Adjusting detail level from brief to comprehensive
- **Code Style:** Formatting preferences for generated code (indentation, naming, etc.)
- **Explanation Depth:** Amount of context and reasoning provided
- **Output Templates:** Predefined formats for specific use cases
- **Customization Persistence:** Style preferences maintained throughout session

---

## Commands & Syntax
```bash
# View current output style settings
/output-style

# Set verbosity level
/output-style verbose                 # Detailed explanations
/output-style concise                 # Brief, to-the-point responses
/output-style minimal                 # Only essential information

# Set code formatting style
/output-style code-format standard
/output-style code-format compact

# Set explanation style
/output-style explain detailed        # Include reasoning and context
/output-style explain brief           # Just the facts
/output-style explain none            # Code only, no explanations

# Combine multiple preferences
/output-style verbose --code-format standard --explain detailed

# Reset to default style
/output-style reset
```

---

## When to Use

Use `/output-style` when responses are too verbose and you want quicker answers, you're learning and need more detailed explanations, working on specific coding standards that require particular formatting, generating documentation and need structured outputs, switching between quick prototyping (concise) and careful implementation (verbose), or when Claude's default style doesn't match your workflow preferences.

---

## How It Works

**Step 1:** Recognize that Claude's default response style doesn't match your current needs

**Step 2:** Use `/output-style` to view available options and current settings

**Step 3:** Select appropriate style based on your task (concise for quick edits, verbose for learning)

**Step 4:** Apply the style with corresponding command

**Step 5:** Claude Code adjusts its responses according to new style preferences

**Step 6:** Style persists for remainder of session unless changed again

---

## Common Issues

### Issue: Style changes don't seem to affect responses
**Symptoms:** Responses look the same after changing output style  
**Solution:** Some style changes are subtle - try extreme settings (minimal vs verbose) to see difference, restart session if settings seem stuck, verify command syntax was correct

### Issue: Too concise and missing important information
**Symptoms:** Brief responses omit details needed to understand or implement  
**Solution:** Switch to verbose or detailed style for complex tasks, ask follow-up questions to get more information, use concise only for simple, well-understood operations

### Issue: Cannot find right balance
**Symptoms:** Verbose is too much, concise is too little  
**Solution:** Try "standard" or default style as middle ground, adjust style per task rather than setting once for entire session, provide explicit instructions in prompts about desired detail level

---

## Important Notes

- 💡 **Tip:** Use concise style for repetitive tasks where you know what you're doing
- 💡 **Tip:** Use verbose style when learning new concepts or debugging complex issues
- 💡 **Tip:** Switch styles throughout session based on current task complexity
- 💡 **Tip:** Combine with model selection - Haiku + concise for speed, Opus + verbose for learning
- 📌 **Remember:** Style is session-specific - resets when you start new session
- 📌 **Remember:** You can always ask "explain more" if concise response is insufficient

