# Troubleshooting Guide

Common issues and their solutions when working with Claude Code.

---

## 🔴 Installation Issues 

# Problem: Claude Code not found after installation
**Symptoms:** `command not found: claude-code`

* Solutions:
- Check if installation completed successfully
- Verify PATH environment variable
- Restart terminal
- Try reinstalling

---

## 🟡 Session Issues

# Problem: Session won't resume
**Symptoms:** Cannot resume previous session

* Solutions:
- Check session ID
- Verify session still exists
- Try starting new session

# Problem: Context too large
**Symptoms:** "Context limit exceeded" error

* Solutions:
- Use `/compact` to compress history
- Use `/clear` to start fresh
- Remove unnecessary files from context

---

## 🟢 Performance Issues

# Problem: Slow responses
**Possible Causes:**
- Large context window
- Many files in context
- Network issues

* Solutions:
- Compact context regularly
- Add only necessary directories
- Check internet connection

---

## 📝 Configuration Issues

# Problem: CLAUDE.md not being recognized
* Solutions:
- Check file location (should be in project root)
- Verify file syntax
- Run `/init` to regenerate

---


**Last Updated:** January 22, 2026