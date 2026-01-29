# Project & User Rules

---

## What It Is

Project & User Rules is a dual-configuration system where project-level rules (shared by all team members via CLAUDE.md in version control) coexist with user-level rules (personal preferences stored locally and not committed to Git), allowing teams to enforce consistent standards while individual developers maintain their own workflow preferences and customizations. This separation ensures team alignment on critical conventions while respecting individual working styles, creating a balance between collaboration consistency and personal productivity optimization.

---

## Key Concepts

- **Project Rules:** Team-wide standards committed to version control
- **User Rules:** Personal preferences stored locally, not shared
- **Rule Precedence:** Defining which takes priority when rules conflict
- **Configuration Separation:** Different files for shared vs personal settings
- **Team Consistency:** Ensuring critical standards apply to everyone
- **Personal Flexibility:** Allowing individual workflow customization

---

## Commands & Syntax
```bash
# View project rules (from CLAUDE.md)
/show-project-rules

# View user rules (from local config)
/show-user-rules

# Edit user rules
/edit-user-rules

# Set user preference
/user-rule set output-style verbose
/user-rule set default-model sonnet

# Remove user rule
/user-rule remove output-style

# Check rule precedence for specific setting
/check-rule code-style

# User rules are typically stored in:
# ~/.claude-code/user-rules.md
# or
# ~/.config/claude-code/preferences.md
```

---

## When to Use

Use project rules for coding standards, architectural patterns, testing requirements, commit message formats, security policies, and any conventions critical for team consistency. Use user rules for personal output verbosity preferences, default model selection, favorite keyboard shortcuts, custom aliases for common commands, notification preferences, or any setting that affects your experience but not code quality or team collaboration.

---

## How It Works

**Step 1:** Team defines project rules in CLAUDE.md (version controlled, shared)

**Step 2:** Individual developers set personal preferences using `/edit-user-rules`

**Step 3:** User rules are stored locally (typically in home directory, not in project)

**Step 4:** When Claude Code starts, it loads both project and user rules

**Step 5:** If rules conflict, precedence determines which applies (typically project rules win for code-related, user rules win for UI/preference)

**Step 6:** Team standards enforced via project rules, personal workflow via user rules

---

## Common Issues

### Issue: User rules overriding critical project standards
**Symptoms:** Individual code doesn't match team conventions  
**Solution:** Define project rules with explicit precedence markers, educate team on which rules shouldn't be overridden, review code in PRs to catch deviations

### Issue: Cannot find user rules file
**Symptoms:** User preferences not persisting across sessions  
**Solution:** Use `/show-user-rules` to see current file location, create user rules file manually if missing, check Claude Code documentation for proper path

### Issue: Confusion about which rule applies
**Symptoms:** Unexpected behavior, unclear if project or user rule is active  
**Solution:** Use `/check-rule <setting>` to see which rule is in effect, document precedence policy clearly in project CLAUDE.md, use `/show-effective-config` to see merged result

---

## Important Notes

- ⚠️ **Warning:** User rules should never override critical team standards
- ⚠️ **Warning:** User rules are not backed up with project - document important ones
- 💡 **Tip:** Use project rules for "what code looks like", user rules for "how I work"
- 💡 **Tip:** Document acceptable user rule overrides in project CLAUDE.md
- 💡 **Tip:** Periodically review user rules to remove outdated preferences
- 💡 **Tip:** Export/backup user rules when setting up new development machine
- 📌 **Remember:** Project rules are in Git, user rules are local only
- 📌 **Remember:** New team members get project rules automatically, must set user rules themselves
- 📌 **Remember:** Project rule changes affect everyone, user rule changes affect only you
