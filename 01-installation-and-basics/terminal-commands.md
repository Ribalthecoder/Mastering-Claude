# Terminal Commands for Beginners

---

## What It Is

Terminal commands are text-based instructions you type into a command-line interface to interact with your computer's operating system. For Claude Code users, understanding basic terminal commands is essential because Claude Code operates entirely through the command line, and you'll need these foundational commands to navigate directories, manage files, and execute Claude Code operations.

---

## Key Concepts

- **Terminal/Command Line:** A text-based interface where you type commands instead of clicking icons
- **Directory Navigation:** Moving between folders using commands instead of File Explorer
- **File Operations:** Creating, deleting, moving, and viewing files through text commands
- **Path:** The location of a file or folder on your computer (e.g., C:\Users\Documents\project)
- **Working Directory:** The current folder location where your terminal is operating

---

## Commands & Syntax
```bash
# Show current directory location
pwd                          # Print Working Directory

# List files and folders in current directory
ls                           # List (Mac/Linux/Git Bash)
dir                          # List (Windows CMD/PowerShell)

# Change directory
cd folder-name               # Move into a folder
cd ..                        # Move up one level (parent folder)
cd ~                         # Go to home directory
cd /                         # Go to root directory

# Create new directory
mkdir folder-name            # Make directory

# Create new file
touch filename.txt           # Create empty file (Mac/Linux/Git Bash)
echo. > filename.txt         # Create empty file (Windows)

# View file contents
cat filename.txt             # Display file contents (Mac/Linux/Git Bash)
type filename.txt            # Display file contents (Windows)

# Copy files
cp source.txt destination.txt      # Copy file (Mac/Linux/Git Bash)
copy source.txt destination.txt    # Copy file (Windows)

# Move or rename files
mv oldname.txt newname.txt         # Move/rename (Mac/Linux/Git Bash)
move oldname.txt newname.txt       # Move/rename (Windows)

# Delete files
rm filename.txt              # Remove file (Mac/Linux/Git Bash)
del filename.txt             # Delete file (Windows)

# Delete directories
rm -r folder-name            # Remove directory and contents (Mac/Linux/Git Bash)
rmdir /s folder-name         # Remove directory (Windows)

# Clear terminal screen
clear                        # Clear screen (Mac/Linux/Git Bash)
cls                          # Clear screen (Windows)
```

---

## When to Use

You'll use terminal commands constantly when working with Claude Code - navigating to project directories, creating folders for new projects, viewing file contents, and managing your development environment all require basic terminal proficiency.

---

## How It Works

**Step 1:** Open your terminal (PowerShell, Git Bash, or Command Prompt on Windows)

**Step 2:** Check your current location using `pwd` to see where you are in the file system

**Step 3:** Use `ls` or `dir` to see what files and folders are in your current location

**Step 4:** Navigate to desired location using `cd` commands (e.g., `cd Documents/projects`)

**Step 5:** Perform operations like creating folders (`mkdir`), files (`touch`), or running Claude Code commands

**Step 6:** Use `cd ..` to move back up or `cd ~` to return to home directory when done

---

## Common Issues

### Issue: "No such file or directory"
**Symptoms:** Error when trying to navigate or access a file  
**Solution:** Check spelling of folder/file name (case-sensitive on Mac/Linux), use `ls` to see available options, ensure you're in the correct parent directory

### Issue: "Permission denied"
**Symptoms:** Cannot create, delete, or modify files  
**Solution:** Run terminal as Administrator (Windows) or use `sudo` before command (Mac/Linux), check if file is locked or in use

### Issue: Commands not working after switching between terminals
**Symptoms:** Commands work in one terminal but not another  
**Solution:** Git Bash uses Unix commands (ls, rm), while CMD uses Windows commands (dir, del) - use appropriate syntax for your terminal

---

## Important Notes

- ⚠️ **Warning:** Be extremely careful with `rm -r` or `del` commands - deleted files often cannot be recovered from terminal
- 💡 **Tip:** Use Tab key to autocomplete folder and file names - saves time and prevents typos
- 💡 **Tip:** Use up/down arrow keys to cycle through previously entered commands
- 📌 **Remember:** File and folder names with spaces need quotes: `cd "My Documents"` not `cd My Documents`
- 📌 **Remember:** Git Bash on Windows provides Unix-style commands which match most online tutorials better than CMD

---

**Status:** ✅ Completed  
**Add to Quick Reference:** Yes (basic navigation commands)