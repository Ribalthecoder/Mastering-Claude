# /context Command

---

## What It Is

The `/context` command displays what files, directories, and information Claude Code currently has awareness of in your session, showing you exactly what Claude can "see" and reference when responding to your requests. This command reveals the working context including loaded files, directory structures, project metadata, and environmental information that Claude uses to understand your codebase, helping you verify Claude has access to necessary files, troubleshoot why Claude doesn't know about certain code, and manage what information is included in the conversation to optimize token usage.

---

## Key Concepts

- **Context Window:** The total information Claude can reference in current session
- **File Awareness:** Which files Claude has read and can reference
- **Directory Structure:** Folder organization Claude understands
- **Active Context:** Currently loaded vs available but not loaded files
- **Context Size:** Token count consumed by loaded context
- **Selective Loading:** Adding only necessary files to save tokens

---

## Commands & Syntax
```bash
# View all files and directories in context
/context

# Show detailed context with file sizes
/context --verbose

# Show only files (exclude directories)
/context --files

# Show only directories
/context --dirs

# Show context token usage
/context --tokens

# Refresh context to detect new/changed files
/context --refresh

# Show specific file content in context
/context show file.js
```

---

## When to Use

Use `/context` when Claude doesn't seem to know about a file you're discussing, to verify which files are loaded before asking Claude to reference multiple files, when optimizing token usage by checking what's unnecessarily loaded, troubleshooting why Claude gives generic responses (might lack project context), before adding new directories to ensure you're not duplicating context, or to understand why responses are slow (too much context loaded).

---

## How It Works

**Step 1:** Claude Code maintains awareness of files and directories you've explicitly added or referenced

**Step 2:** Type `/context` to query what's currently in Claude's working memory

**Step 3:** Claude Code returns a list of all files, directories, and metadata it has access to

**Step 4:** Review the output to ensure necessary files are present

**Step 5:** Add missing files with `/add-dir` or remove unnecessary ones to optimize

**Step 6:** Use context information to craft better prompts referencing available files

---

## Common Issues

### Issue: File exists but not showing in context
**Symptoms:** File is in project directory but `/context` doesn't list it  
**Solution:** Use `/add-dir` to explicitly add the directory containing the file, refresh context with `/context --refresh`, ensure file isn't in .gitignore or excluded by Claude Code filters

### Issue: Context is huge and slowing down responses
**Symptoms:** Many files in context, slow performance  
**Solution:** Remove unnecessary directories from context, be selective about what you add with `/add-dir`, use more specific directory paths instead of adding entire project root

### Issue: Context seems outdated
**Symptoms:** Claude references old file content or doesn't know about recent changes  
**Solution:** Use `/context --refresh` to reload file states, save files in your editor before expecting Claude to see changes, restart session if context is severely stale

---

## Important Notes

- 💡 **Tip:** Check `/context` before asking Claude to modify multiple files - ensure all are loaded
- 💡 **Tip:** Use `/context --tokens` to see how much of your token budget is consumed by files
- 💡 **Tip:** Add specific subdirectories instead of entire project to keep context manageable
- 💡 **Tip:** Refresh context after making manual file changes outside Claude Code
- 📌 **Remember:** Context includes file content, not just filenames - large files consume many tokens
- 📌 **Remember:** Claude only knows what's explicitly in context - it doesn't auto-discover your entire project

