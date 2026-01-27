# Installing Claude Code on Windows

---

## What It Is

Claude Code is a command-line interface (CLI) tool created by Anthropic that allows developers to use Claude AI directly from their terminal for coding tasks. Installing it on Windows enables you to interact with Claude through terminal commands to build software, automate tasks, and get AI assistance without using a web browser.

---

## Key Concepts

- **CLI Tool:** A terminal-based application that you control with text commands rather than a graphical interface
- **Global Installation:** Installing Claude Code system-wide so it can be accessed from any directory on your computer
- **Node.js Dependency:** Claude Code requires Node.js (JavaScript runtime) to be installed first as it's built on this platform
- **Initialization:** First-time setup that configures Claude Code with your API credentials and preferences

---

## Commands & Syntax
```bash
# Check if Node.js is installed (prerequisite)
node --version

# Install Claude Code globally via npm
npm install -g @anthropic-ai/claude-code

# Verify installation was successful
claude-code --version

# Initialize Claude Code (first-time setup)
claude-code init

# Get help and see available commands
claude-code --help
```

---

## When to Use

Install Claude Code when you want to integrate AI assistance directly into your development workflow through the terminal, enabling you to code faster, automate repetitive tasks, and access Claude's capabilities without switching between applications.

---

## How It Works

**Step 1:** Ensure Node.js 18 or higher is installed on your Windows system (download from nodejs.org if needed)  

**Step 2:** Open terminal (PowerShell, Command Prompt, or Git Bash) with Administrator privileges  

**Step 3:** Run the global npm installation command to download and install Claude Code  

**Step 4:** Verify the installation by checking the version number  

**Step 5:** Run the initialization command to set up your API credentials and configuration  

**Step 6:** Restart your terminal to ensure all environment variables are loaded properly

---

## Common Issues

### Issue: "npm is not recognized as a command"
**Symptoms:** Error message when trying to install Claude Code  
**Solution:** Node.js is not installed or not in PATH. Install Node.js from nodejs.org and restart terminal

### Issue: Permission denied during installation
**Symptoms:** EACCES or permission error during npm install  
**Solution:** Run terminal as Administrator (right-click → Run as Administrator) or use `npm install -g @anthropic-ai/claude-code --force`

### Issue: Claude Code command not found after installation
**Symptoms:** "claude-code is not recognized" after installing  
**Solution:** Restart terminal completely, check if npm global directory is in system PATH, or reinstall

---

## Important Notes

- ⚠️ **Warning:** Must have Node.js version 18 or higher installed first - Claude Code will not work with older versions
- 💡 **Tip:** Use Git Bash on Windows for better compatibility with Unix-style commands that Claude Code uses
- 💡 **Tip:** Run terminal as Administrator during installation to avoid permission issues
- 📌 **Remember:** After installation, always restart your terminal before using Claude Code for the first time

