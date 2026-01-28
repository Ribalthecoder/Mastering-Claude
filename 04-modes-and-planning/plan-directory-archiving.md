# Plan Directory & Archiving Plans

---

## What It Is

Plan Directory & Archiving Plans is the organizational system within Claude Code that manages storage, categorization, archival, and retrieval of all your project plans, providing a centralized location where plans are saved, indexed, and maintained for future reference. This system allows you to organize plans by project, archive completed plans to keep active workspace clean, search through historical plans, export plans for documentation, and maintain a knowledge base of architectural decisions and implementation strategies that can inform future work.

---

## Key Concepts

- **Centralized Storage:** Single location for all plan files
- **Plan Organization:** Categorizing plans by project, status, or type
- **Active vs Archived:** Separating ongoing plans from completed work
- **Plan Versioning:** Tracking iterations and updates to plans
- **Search and Retrieval:** Finding relevant plans from historical archives
- **Knowledge Base:** Using past plans to inform future decisions

---

## Commands & Syntax
```bash
# View plan directory structure
/plan-directory

# List all plans (active and archived)
/list-plans --all

# List only active plans
/list-plans --active

# List only archived plans
/list-plans --archived

# Archive a completed plan
/archive-plan plan-name

# Unarchive a plan (restore to active)
/unarchive-plan plan-name

# Delete plan permanently
/delete-plan plan-name

# Search plans by keyword
/search-plans "authentication"

# Show plan directory location
/plan-directory --path

# Export all plans for backup
/export-plans --all --output plans-backup.zip

# Clean up old archived plans
/cleanup-plans --older-than 90days
```

---

## When to Use

Use plan directory management when you have accumulated many plans and need organization, completed projects and want to archive plans while keeping them accessible, searching for how you solved similar problems in past projects, backing up architectural decisions and implementation strategies, cleaning up storage by removing obsolete plans, or maintaining project documentation that includes planning artifacts.

---

## How It Works

**Step 1:** Claude Code automatically saves plans to designated plan directory

**Step 2:** Plans remain in "active" state while you're working on them

**Step 3:** When project is complete, use `/archive-plan` to move plan to archive

**Step 4:** Archived plans are preserved but don't clutter active plan list

**Step 5:** Use `/search-plans` to find relevant plans when needed

**Step 6:** Export plans periodically for backup or to share with team

**Step 7:** Clean up very old plans that are no longer relevant

---

## Common Issues

### Issue: Plan directory taking up too much disk space
**Symptoms:** Large amount of storage consumed by saved plans  
**Solution:** Archive old plans to compress them, use `/cleanup-plans` to remove ancient plans, export and delete plans for long-completed projects

### Issue: Cannot find specific plan in large directory
**Symptoms:** Too many plans to browse effectively  
**Solution:** Use `/search-plans` with keywords instead of browsing, implement better naming conventions (project-feature-date), regularly archive completed plans to reduce active list

### Issue: Accidentally deleted important plan
**Symptoms:** Plan no longer available and wasn't backed up  
**Solution:** Check if plan was archived rather than deleted, restore from exports if you maintain backups, recreate from Git history if implementation was committed

---

## Important Notes

- ⚠️ **Warning:** Deleted plans are permanent - archive instead if you might need reference later
- ⚠️ **Warning:** Plan directory may grow large over time - implement regular cleanup routine
- 💡 **Tip:** Archive plans immediately after project completion while memory is fresh
- 💡 **Tip:** Use consistent naming: "projectname-feature-YYYYMMDD" for easy sorting
- 💡 **Tip:** Export plans monthly as backup - they're valuable documentation
- 💡 **Tip:** Search archived plans when starting similar projects for reference
- 📌 **Remember:** Archived plans are still accessible - archiving doesn't delete
- 📌 **Remember:** Plan directory is project-specific unless using global configuration

