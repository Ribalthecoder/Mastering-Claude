# Continuing Plans in New Context Window

---

## What It Is

Continuing Plans in New Context Window is a feature that allows you to split long-running plan implementations across multiple Claude Code sessions by preserving the plan structure and execution state, enabling you to pause work, close your session, and later resume from where you left off without losing track of progress or requiring re-planning. This is essential for large projects where a single plan might take days or weeks to complete, requiring you to work in multiple sessions while maintaining continuity and avoiding the confusion of starting fresh each time.

---

## Key Concepts

- **Plan Persistence:** Saving plan state for later continuation
- **Progress Tracking:** Marking completed vs pending steps
- **Context Restoration:** Reloading plan and project understanding in new session
- **Multi-Session Workflows:** Breaking large implementations across multiple work periods
- **State Checkpoints:** Saving progress at key milestones
- **Plan Resumption:** Continuing from specific step rather than starting over

---

## Commands & Syntax
```bash
# Save current plan with progress
/save-plan plan-name

# List all saved plans
/list-plans

# Load and continue existing plan
/continue-plan plan-name

# Load plan at specific step
/continue-plan plan-name --from-step 5

# Show plan progress
/plan-progress

# Mark current step as complete and move to next
/complete-step

# Skip step (with reason)
/skip-step "Already implemented manually"

# Export plan for documentation
/export-plan plan-name --format markdown
```

---

## When to Use

Use plan continuation when implementing large features that span multiple work sessions, you need to pause development and return later without losing context, working on projects with multiple team members who need to pick up where others left off, handling interruptions or context switches between different tasks, maintaining long-term project roadmaps with phased implementation, or any situation where single-session completion is unrealistic.

---

## How It Works

**Step 1:** Create comprehensive plan during initial session using Planning or Improved Plan Mode

**Step 2:** Begin implementation and work through several steps

**Step 3:** Before ending session, save plan with `/save-plan project-feature-name`

**Step 4:** Later, when ready to continue, start new Claude Code session

**Step 5:** Use `/continue-plan project-feature-name` to restore plan and progress

**Step 6:** Review `/plan-progress` to see what's completed and what's next

**Step 7:** Continue implementation from where you left off

---

## Common Issues

### Issue: Loaded plan doesn't reflect recent code changes
**Symptoms:** Plan seems outdated after resuming  
**Solution:** Manually update Claude on changes made since last session, use `/add-dir` to ensure Claude sees current code state, consider re-syncing plan with actual implementation status

### Issue: Lost track of which steps were actually completed
**Symptoms:** Unsure if step was done or just marked complete  
**Solution:** Use Git commits to track actual progress alongside plan, add completion notes when marking steps done, review actual code to verify completion before moving forward

### Issue: Cannot find saved plan
**Symptoms:** `/list-plans` doesn't show expected plan  
**Solution:** Verify you're in correct project directory, check if plan was saved under different name, ensure plan wasn't accidentally deleted during cleanup

---

## Important Notes

- ⚠️ **Warning:** Plans saved in one project directory may not be accessible from another
- 💡 **Tip:** Use descriptive plan names that include project and feature (e.g., "ecommerce-checkout-flow")
- 💡 **Tip:** Commit code after completing each major plan step for safety
- 💡 **Tip:** Add notes to steps as you complete them for context when resuming
- 💡 **Tip:** Export plans periodically as backup and documentation
- 📌 **Remember:** Plan continuation works best when original plan was detailed and clear
- 📌 **Remember:** Update plan if you deviate from original approach during implementation

