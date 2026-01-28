# Planning Mode

---

## What It Is

Planning Mode is a specialized operating mode where Claude Code creates comprehensive, step-by-step plans for complex tasks before executing any actual implementation, allowing you to review, approve, and refine the approach before committing to code generation. Instead of immediately writing code, Claude breaks down your request into logical phases, identifies dependencies, considers edge cases, outlines the architecture, and presents a structured plan that you can discuss and modify, ensuring alignment on approach before investing time in implementation.

---

## Key Concepts

- **Pre-Implementation Planning:** Design before coding
- **Structured Breakdown:** Complex tasks divided into manageable steps
- **Dependency Mapping:** Identifying what needs to happen before what
- **Architecture Preview:** High-level design decisions made explicit
- **Iterative Refinement:** Plan can be discussed and revised before execution
- **Risk Identification:** Potential issues surfaced during planning phase

---

## Commands & Syntax
```bash
# Enable Planning Mode
/planning-mode
/plan                                 # Short form

# Disable Planning Mode (return to normal execution)
/planning-mode off

# Generate plan for specific task
/plan "Build user authentication system"

# Review current plan
/show-plan

# Approve plan and begin implementation
/approve-plan
/execute-plan

# Modify specific step in plan
/modify-plan step-3 "Use JWT instead of sessions"

# Request plan revision
/revise-plan "Add password reset functionality"
```

---

## When to Use

Use Planning Mode for complex features with multiple components, unfamiliar technologies or frameworks where you need to think through approach, projects with unclear requirements that need structured thinking, when you want to review architecture before committing to implementation, collaborative work where team needs to approve approach, or any situation where "measure twice, cut once" philosophy applies to avoid costly rewrites.

---

## How It Works

**Step 1:** Enable Planning Mode with `/planning-mode` before describing your task

**Step 2:** Describe what you want to build or accomplish

**Step 3:** Claude generates detailed plan with numbered steps, dependencies, and considerations

**Step 4:** Review the plan - assess if approach makes sense, identify missing steps or issues

**Step 5:** Discuss and refine the plan with Claude until you're satisfied

**Step 6:** Approve with `/approve-plan` and Claude begins implementation following the plan

---

## Common Issues

### Issue: Plan is too high-level or vague
**Symptoms:** Steps lack detail needed to implement  
**Solution:** Ask Claude to elaborate on specific steps, request more technical detail, use `/revise-plan` to add specificity

### Issue: Plan doesn't account for edge cases
**Symptoms:** Implementation following plan encounters unforeseen issues  
**Solution:** During planning phase, explicitly ask "what edge cases should we consider?", request error handling steps in plan, revise plan to be more comprehensive

### Issue: Plan is too detailed and overwhelming
**Symptoms:** Dozens of micro-steps making it hard to see big picture  
**Solution:** Ask for higher-level plan first, request plan focuses on major phases not individual functions, use hierarchical planning (high-level → detailed per phase)

---

## Important Notes

- 💡 **Tip:** Always use Planning Mode for features you're implementing for the first time
- 💡 **Tip:** Share plans with team members before implementation for feedback
- 💡 **Tip:** Save approved plans as documentation for future reference
- 💡 **Tip:** Planning Mode works especially well with Opus model for complex reasoning
- 📌 **Remember:** Time spent planning saves time debugging and refactoring later
- 📌 **Remember:** Plans are flexible - you can deviate during implementation if needed
- 📌 **Remember:** Good plan includes not just "what" but "why" for decisions

