# Hierarchical CLAUDE.md Files

---

## What It Is

Hierarchical CLAUDE.md Files is a system where multiple CLAUDE.md files exist at different directory levels within a project, with each file providing configurations specific to its directory scope while inheriting and potentially overriding settings from parent directories. This allows for organization-wide defaults at the root, project-specific rules in project folders, and component-specific conventions in subdirectories, creating a cascading configuration system that balances consistency with flexibility for different parts of large codebases.

---

## Key Concepts

- **Configuration Hierarchy:** Parent directory rules apply to child directories
- **Inheritance:** Child CLAUDE.md files inherit from parent configurations
- **Override Capability:** Child configurations can override parent settings
- **Scope Specificity:** More specific (deeper) rules take precedence
- **Modular Configuration:** Distribute rules across relevant directories
- **Reduced Duplication:** Common rules defined once at appropriate level

---

## Commands & Syntax
```bash
# View configuration hierarchy for current directory
/show-claude-hierarchy

# Create CLAUDE.md at current level
/init --local

# Show effective configuration (merged from all levels)
/show-effective-config

# Validate entire hierarchy for conflicts
/validate-hierarchy

# Example directory structure:
# /project/
#   CLAUDE.md                    (Project-wide rules)
#   /frontend/
#     CLAUDE.md                  (Frontend-specific rules)
#     /components/
#       CLAUDE.md                (Component-specific rules)
#   /backend/
#     CLAUDE.md                  (Backend-specific rules)
```

---

## When to Use

Use hierarchical CLAUDE.md when managing monorepos with multiple projects, large projects with distinct subsystems (frontend, backend, mobile), codebases with different language or framework conventions in different areas, teams with different ownership of various directories, or when you need both organization-wide standards and project-specific flexibility.

---

## How It Works

**Step 1:** Create root CLAUDE.md with organization or project-wide conventions

**Step 2:** Navigate to subdirectory with specific needs (e.g., /frontend)

**Step 3:** Create local CLAUDE.md with directory-specific rules using `/init --local`

**Step 4:** Local CLAUDE.md inherits all parent rules automatically

**Step 5:** Local rules can override parent rules by redefining them

**Step 6:** Claude Code merges configurations from root down to current directory

**Step 7:** Most specific (deepest) rules take precedence in case of conflicts

---

## Common Issues

### Issue: Conflicting rules across hierarchy levels
**Symptoms:** Unclear which rule applies when parent and child conflict  
**Solution:** Use `/validate-hierarchy` to identify conflicts, document override strategy clearly, be explicit about which rules can be overridden vs absolute

### Issue: Cannot determine where rule is coming from
**Symptoms:** Unexpected behavior, unclear which CLAUDE.md is responsible  
**Solution:** Use `/show-claude-hierarchy` to see all active configs, check `/show-effective-config` for merged result, add comments noting source of critical rules

### Issue: Changes to parent CLAUDE.md not reflecting in child directories
**Symptoms:** Updated root config but subdirectories don't see changes  
**Solution:** Ensure child configs aren't overriding inherited rules, use `/reload-claude-md` in affected directories, verify no caching issues

---

## Important Notes

- 💡 **Tip:** Keep root CLAUDE.md for universal rules, use child configs for exceptions
- 💡 **Tip:** Document hierarchy strategy in root CLAUDE.md for team clarity
- 💡 **Tip:** Use hierarchical configs in monorepos to handle multiple tech stacks
- 💡 **Tip:** Review hierarchy regularly to prevent configuration sprawl
- 💡 **Tip:** Child configs should be concise - only what's different from parent
- 📌 **Remember:** More CLAUDE.md files = more token usage across hierarchy
- 📌 **Remember:** Deeper (more specific) rules always win over parent rules
- 📌 **Remember:** All CLAUDE.md files in hierarchy should be version controlled

