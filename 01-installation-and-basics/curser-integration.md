# Using Cursor + Claude Code

---

## What It Is

Cursor is an AI-powered code editor (a fork of VS Code) that integrates AI assistance directly into the coding interface, and it can work alongside Claude Code to create a powerful development workflow. By combining Cursor's inline AI code suggestions and editing capabilities with Claude Code's terminal-based project generation and file management, developers can leverage both tools simultaneously - using Cursor for detailed code editing and refactoring while using Claude Code for broader architectural decisions, file creation, and terminal operations.

---

## Key Concepts

- **Dual-Tool Workflow:** Using both Cursor (for editing) and Claude Code (for generation/architecture) in the same project
- **Cursor IDE:** An intelligent code editor with built-in AI chat, inline completions, and code understanding
- **Complementary Strengths:** Cursor excels at precise editing within files; Claude Code excels at project-level operations and terminal work
- **Synchronized Context:** Both tools can work on the same files - changes made in one are immediately visible in the other
- **Integrated Terminal:** Cursor has a built-in terminal where you can run Claude Code directly

---

## Commands & Syntax
```bash
# Open project in Cursor
cursor .                              # Opens current directory in Cursor
cursor /path/to/project               # Opens specific project

# Inside Cursor, use the integrated terminal (Ctrl+`)
# Then run Claude Code as normal
claude-code                           # Start Claude Code session

# No special commands needed - both tools work on the same files
# Edit in Cursor → Changes appear immediately
# Generate with Claude Code → Files open automatically in Cursor
```

---

## When to Use

Use Cursor + Claude Code together when building complex projects where you need both high-level architecture and detailed code refinement. Use Claude Code for initial project setup, creating multiple files, and structural changes, then switch to Cursor for precise editing, debugging, and working with specific code sections. This combination is ideal for professional development workflows where you want AI assistance at both the macro (project) and micro (code) levels.

---

## How It Works

**Step 1:** Open your project directory in Cursor using `cursor .` or by launching Cursor and opening the folder

**Step 2:** Open Cursor's integrated terminal using Ctrl+` (backtick) or View → Terminal

**Step 3:** In the terminal, navigate to your project directory if needed and run `claude-code`

**Step 4:** Use Claude Code to generate project structure, create files, or make architectural changes

**Step 5:** Switch to Cursor's editor pane to view and refine the generated code using Cursor's AI features

**Step 6:** Use Cursor for detailed editing, debugging, and working within specific files

**Step 7:** Return to Claude Code terminal for broader changes or creating new files

**Step 8:** Iterate between both tools as needed throughout development

---

## Common Issues

### Issue: Changes not syncing between tools
**Symptoms:** Edits in Cursor don't appear in Claude Code context or vice versa  
**Solution:** Save files in Cursor (Ctrl+S) before asking Claude Code to modify them, if using Git commit changes between tool switches, reload Cursor workspace if files seem out of sync

### Issue: Claude Code overwrites Cursor edits
**Symptoms:** Manually edited code in Cursor gets replaced by Claude Code  
**Solution:** Commit your Cursor edits with Git before using Claude Code for major changes, be specific with Claude Code about which parts to modify, use branches for experimental Claude Code changes

### Issue: Terminal conflicts in Cursor
**Symptoms:** Cannot run both Cursor's AI and Claude Code simultaneously  
**Solution:** They operate independently - use Cursor AI for editing files and Claude Code terminal for generation, no conflict should occur as they serve different purposes

---

## Important Notes

- ⚠️ **Warning:** Always save files in Cursor before asking Claude Code to modify them - unsaved changes won't be visible to Claude Code
- 💡 **Tip:** Use Cursor for fine-tuning and debugging; use Claude Code for generating new files and major structural changes
- 💡 **Tip:** Keep Cursor's file explorer open to see when Claude Code creates new files - they'll appear immediately
- 💡 **Tip:** Use Git commits between tool switches to ensure you can revert if either tool makes unwanted changes
- 📌 **Remember:** Cursor and Claude Code are complementary, not competitive - each has strengths in different areas
- 📌 **Remember:** You can run Claude Code directly in Cursor's terminal - no need to switch windows

