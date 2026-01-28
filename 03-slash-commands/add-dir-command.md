# /add-dir Command

---

## What It Is

The `/add-dir` command explicitly adds a directory and its contents to Claude Code's context, making all files within that directory visible and accessible to Claude for reading, referencing, and modification. This command is essential for expanding Claude's awareness beyond the current working directory, allowing you to selectively load specific folders into context so Claude can understand your project structure, reference multiple files across directories, and perform operations that span different parts of your codebase without manually mentioning each file.

---

## Key Concepts

- **Context Expansion:** Adding more files to Claude's working knowledge
- **Directory Loading:** Bringing entire folder structures into awareness
- **Selective Context:** Choosing which directories to include vs exclude
- **Recursive Loading:** Including subdirectories and their contents
- **Token Impact:** Each added directory consumes tokens based on file sizes
- **Project Scope:** Defining boundaries of what Claude can see and modify

---

## Commands & Syntax
```bash
# Add a directory to context
/add-dir path/to/directory

# Add directory with all subdirectories (recursive)
/add-dir path/to/directory --recursive

# Add directory but exclude certain file types
/add-dir src/ --exclude "*.test.js"

# Add multiple directories at once
/add-dir src/ components/ utils/

# Add directory with file size limit
/add-dir docs/ --max-file-size 100kb

# Preview what would be added without actually adding
/add-dir src/ --preview

# Remove previously added directory
/remove-dir path/to/directory
```

---

## When to Use

Use `/add-dir` when Claude needs to reference files outside the current directory, you're asking Claude to modify multiple files across different folders, Claude doesn't know about a specific directory you're discussing, you want Claude to understand the full project structure, you're setting up a new session and need to establish project context, or when working on features that span multiple directories (e.g., frontend + backend).

---

## How It Works

**Step 1:** Identify which directory contains files Claude needs to access

**Step 2:** Use `/add-dir path/to/directory` to load that directory into context

**Step 3:** Claude Code scans the directory and loads file contents into its working memory

**Step 4:** All files in that directory become available for Claude to reference and modify

**Step 5:** Check with `/context` to verify the directory was added successfully

**Step 6:** Claude can now respond to requests involving those files without you manually specifying each one

---

## Common Issues

### Issue: Added directory but Claude still doesn't know about files
**Symptoms:** Files from added directory not showing up in `/context`  
**Solution:** Verify correct path was used (check spelling, case-sensitivity), use absolute path instead of relative if issues persist, ensure directory isn't empty or contains only excluded file types

### Issue: Adding directory causes context to become too large
**Symptoms:** Slow responses or token limit warnings after adding directory  
**Solution:** Be more selective - add specific subdirectories instead of entire tree, use `--exclude` to filter out unnecessary files (node_modules, build folders), remove directory with `/remove-dir` if not needed

### Issue: Cannot add directory due to permission errors
**Symptoms:** Error message about insufficient permissions  
**Solution:** Check file system permissions on the directory, run Claude Code with appropriate privileges if needed, verify path is accessible and not protected by OS

---

## Important Notes

- ⚠️ **Warning:** Adding large directories (like node_modules) can consume massive tokens - be selective
- ⚠️ **Warning:** Each added directory increases context size - can slow performance and hit limits
- 💡 **Tip:** Use `--preview` first to see what would be added before committing
- 💡 **Tip:** Add specific feature directories instead of entire project root
- 💡 **Tip:** Exclude test files, build artifacts, and dependencies unless specifically needed
- 📌 **Remember:** Added directories persist for session - they stay in context until removed or session ends
- 📌 **Remember:** Use `/context` after adding to verify what was loaded

