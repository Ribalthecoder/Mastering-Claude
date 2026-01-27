# A Quick Build

---

## What It Is

"A Quick Build" is an introductory hands-on exercise where you use Claude Code for the first time to create a simple project from start to finish. This tutorial demonstrates Claude Code's core capabilities by having you build a basic application (like a simple web page, calculator, or todo app) using natural language instructions, showing how Claude Code can generate code, create files, and set up project structure based on your conversational requests.

---

## Key Concepts

- **Natural Language Coding:** Describing what you want to build in plain English rather than writing code manually
- **File Generation:** Claude Code can create multiple files and folders automatically based on your project requirements
- **Iterative Development:** Refining and improving the project through back-and-forth conversation with Claude Code
- **Context Awareness:** Claude Code understands your project structure and makes coherent additions/modifications
- **Project Initialization:** Starting a new project directory and letting Claude Code scaffold the initial structure

---

## Commands & Syntax
```bash
# Navigate to where you want to create the project
cd ~/Documents/projects

# Create project directory
mkdir my-first-project
cd my-first-project

# Start Claude Code in the project directory
claude-code

# Inside Claude Code session, use natural language
"Create a simple HTML page with a button that changes color when clicked"

# Claude Code will generate files and show you what it created
# You can then ask for modifications:
"Add a counter that increments each time the button is clicked"

# Exit Claude Code when done
exit
# or press Ctrl+D
```

---

## When to Use

Use this approach when starting any new project with Claude Code - whether it's a simple script, a web application, or a complex system. The "quick build" methodology demonstrates how to leverage Claude Code's strengths: rapid prototyping, automatic file creation, and iterative development through conversation.

---

## How It Works

**Step 1:** Create a new empty directory for your project and navigate into it using terminal commands

**Step 2:** Launch Claude Code by typing `claude-code` in the project directory

**Step 3:** Describe what you want to build in natural language (e.g., "Create a simple calculator web app")

**Step 4:** Claude Code generates the necessary files (HTML, CSS, JavaScript, etc.) and explains what it created

**Step 5:** Review the generated files, test the application by opening the files in a browser or running the code

**Step 6:** Ask Claude Code for modifications or improvements (e.g., "Add a dark mode toggle")

**Step 7:** Iterate until your project meets your requirements, then exit Claude Code

---

## Common Issues

### Issue: Claude Code generates files in wrong location
**Symptoms:** Files appear outside project directory or in unexpected folders  
**Solution:** Always ensure you're in the correct directory before starting Claude Code (`pwd` to check), and specify file paths clearly in your requests

### Issue: Generated code doesn't work as expected
**Symptoms:** Application has bugs or doesn't run properly  
**Solution:** Describe the specific problem to Claude Code ("The button doesn't change color - can you fix this?"), provide error messages if any, be specific about what's not working

### Issue: Too many files created at once
**Symptoms:** Overwhelming number of files generated, hard to understand project structure  
**Solution:** Start with simpler requests ("Just create the HTML file first"), build incrementally, ask Claude Code to explain the structure before generating

---

## Important Notes

- ⚠️ **Warning:** Always create a dedicated directory for each project - Claude Code will create files in your current directory
- 💡 **Tip:** Start with very simple projects (single HTML page) before attempting complex builds to understand Claude Code's workflow
- 💡 **Tip:** Use `ls` frequently to see what files Claude Code has created and verify they're in the right place
- 📌 **Remember:** You can always ask Claude Code to explain what it just created: "Explain the structure of what you built"
- 📌 **Remember:** The first build teaches you how to communicate effectively with Claude Code - focus on learning the interaction pattern, not building something perfect

