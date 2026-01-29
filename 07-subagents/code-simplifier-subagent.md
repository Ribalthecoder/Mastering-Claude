# Code Simplifier Subagent

---

## What It Is

Code Simplifier Subagent is a specialized subagent focused on refactoring and simplifying complex code, identifying overly complicated implementations, removing unnecessary abstractions, reducing code duplication, and making codebases more maintainable and readable. This subagent applies simplification principles systematically across files or modules, suggesting and implementing refactorings that preserve functionality while improving code quality, making it easier for teams to maintain and extend their systems.

---

## Key Concepts

- **Complexity Reduction:** Identifying and simplifying overly complex code
- **Refactoring Focus:** Improving code structure without changing behavior
- **Pattern Recognition:** Finding common simplification opportunities
- **Maintainability Improvement:** Making code easier to understand and modify
- **Technical Debt Reduction:** Addressing accumulated complexity over time
- **Best Practices Application:** Applying language-specific simplification patterns

---

## Commands & Syntax
```bash
# Spawn code simplifier subagent
/spawn-simplifier

# Simplify specific file
/simplifier "Simplify auth.js"

# Simplify directory
/simplifier --dir src/components/

# Focus on specific simplification types
/simplifier --focus duplication
/simplifier --focus complexity
/simplifier --focus abstraction

# Set aggressiveness level
/simplifier --level conservative      # Safe, obvious improvements
/simplifier --level moderate          # Balanced approach
/simplifier --level aggressive        # Significant restructuring

# Generate simplification report without changes
/simplifier --analyze-only
```

---

## When to Use

Use Code Simplifier Subagent when codebase has grown complex and hard to maintain, onboarding new team members struggle with code complexity, preparing codebase for major feature additions, technical debt has accumulated and needs addressing, after multiple developers have worked on same code creating inconsistencies, or as regular maintenance to prevent complexity accumulation.

---

## How It Works

**Step 1:** Spawn simplifier subagent targeting specific files, directories, or entire codebase

**Step 2:** Subagent analyzes code identifying complexity hotspots and simplification opportunities

**Step 3:** Generates simplification plan with specific refactorings categorized by type and impact

**Step 4:** Implements refactorings while ensuring functional equivalence through tests

**Step 5:** Produces simplified code with explanations of changes made

**Step 6:** Main session reviews changes and integrates simplified code

**Step 7:** Subagent can iterate on feedback for further refinement

---

## Common Issues

### Issue: Simplification breaks functionality
**Symptoms:** Tests fail or behavior changes after simplification  
**Solution:** Use conservative level initially, ensure comprehensive test coverage before simplifying, review changes carefully before accepting, test edge cases after refactoring

### Issue: Simplifier removes necessary complexity
**Symptoms:** Abstraction that served purpose is removed  
**Solution:** Provide context about why complexity exists, use `--analyze-only` to review before applying, keep business logic complexity vs accidental complexity distinction clear

### Issue: Too aggressive simplification hard to review
**Symptoms:** Massive changes difficult to understand and validate  
**Solution:** Simplify incrementally - one file or module at a time, use moderate level instead of aggressive, commit after each successful simplification

---

## Important Notes

- ⚠️ **Warning:** Always have comprehensive tests before simplifying - refactoring without tests is risky
- ⚠️ **Warning:** Simplification can introduce subtle bugs - thorough review essential
- 💡 **Tip:** Start with high-complexity, low-risk files to build confidence
- 💡 **Tip:** Commit after each successful simplification for easy rollback
- 💡 **Tip:** Use `--analyze-only` first to understand scope before applying changes
- 💡 **Tip:** Simplifier works best on well-tested code - write tests first if needed
- 📌 **Remember:** Simpler isn't always better - some problems require complex solutions
- 📌 **Remember:** Simplification is iterative - multiple passes often needed
- 📌 **Remember:** Team consensus on "simple" varies - discuss major refactorings

