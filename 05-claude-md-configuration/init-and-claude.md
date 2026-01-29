# /init & Claude.md

---

## What It Is

The `/init` command creates a CLAUDE.md file in your project directory, which serves as a persistent configuration and instruction file that Claude Code automatically reads at session start to understand project-specific context, coding standards, architectural decisions, and workflow preferences. This file acts as a "project memory" that ensures Claude Code consistently behaves according to your project's needs across all sessions without requiring you to repeat instructions, making it essential for maintaining consistent AI assistance throughout a project's lifecycle.

---

## Key Concepts

- **Project Configuration:** Persistent settings stored in file rather than session
- **Automatic Loading:** Claude reads CLAUDE.md on session start without prompting
- **Coding Standards:** Define project-specific style, patterns, and conventions
- **Context Preservation:** Important project information available in every session
- **Team Consistency:** All team members' Claude Code instances follow same rules
- **Version Controlled:** CLAUDE.md is committed to Git like any other project file

---

## Commands & Syntax
```bash
# Initialize CLAUDE.md in current directory
/init

# Initialize with template
/init --template web-app
/init --template api-service

# Initialize in specific directory
/init path/to/project/

# View current CLAUDE.md contents
/show-claude-md

# Edit CLAUDE.md
/edit-claude-md

# Reload CLAUDE.md after manual edits
/reload-claude-md

# Validate CLAUDE.md syntax
/validate-claude-md
```

---

## When to Use

Use `/init` at the beginning of every new project to establish consistent Claude Code behavior, when starting to use Claude Code on existing projects, to document project-specific conventions that Claude should follow, when team members join and need their Claude Code instances configured identically, or to ensure architectural decisions and patterns are consistently applied throughout development.

---

## How It Works

**Step 1:** Navigate to your project root directory in terminal

**Step 2:** Run `/init` to create initial CLAUDE.md file

**Step 3:** Claude Code generates template with common sections (project overview, tech stack, conventions)

**Step 4:** Edit CLAUDE.md to add project-specific information, standards, and preferences

**Step 5:** Commit CLAUDE.md to version control so team members have access

**Step 6:** Every time Claude Code starts in this directory, it reads CLAUDE.md automatically

**Step 7:** Claude applies rules and context from CLAUDE.md to all responses

---

## Common Issues

### Issue: Claude not following CLAUDE.md instructions
**Symptoms:** Rules in CLAUDE.md seem to be ignored  
**Solution:** Use `/reload-claude-md` to ensure it's loaded, verify syntax with `/validate-claude-md`, make instructions more explicit and specific, check if instructions conflict with each other

### Issue: CLAUDE.md is too verbose and wasting tokens
**Symptoms:** Large CLAUDE.md file consuming significant context  
**Solution:** Keep CLAUDE.md concise - only essential information, use hierarchical CLAUDE.md files to distribute content, remove outdated or redundant sections

### Issue: Team members have conflicting CLAUDE.md versions
**Symptoms:** Different behaviors across team members' sessions  
**Solution:** Ensure CLAUDE.md is committed to Git and everyone pulls latest, establish process for updating CLAUDE.md through PRs, review CLAUDE.md changes during code review

---

## Important Notes

- 💡 **Tip:** Keep CLAUDE.md concise - it's loaded into every session and consumes tokens
- 💡 **Tip:** Include tech stack, coding conventions, and architectural principles
- 💡 **Tip:** Update CLAUDE.md when making architectural decisions during development
- 💡 **Tip:** Use comments in CLAUDE.md to explain why certain rules exist
- 📌 **Remember:** CLAUDE.md should be version controlled like any project file
- 📌 **Remember:** Every team member should have same CLAUDE.md for consistency
- 📌 **Remember:** Reload after editing CLAUDE.md manually outside Claude Code

