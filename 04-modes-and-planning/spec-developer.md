# Spec Developer

---

## What It Is

Spec Developer is a specialized mode that transforms Claude Code into a requirements analyst and specification writer, helping you create comprehensive technical specifications, product requirement documents (PRDs), API documentation, and detailed design documents before any implementation begins. Instead of building features, Spec Developer mode focuses on thoroughly documenting what should be built, creating professional specifications that can guide development, facilitate team alignment, serve as contracts for external developers, and provide clear acceptance criteria for testing.

---

## Key Concepts

- **Specification Writing:** Creating formal technical documentation
- **Requirement Analysis:** Breaking down needs into detailed specifications
- **Documentation Standards:** Following industry formats (PRD, API spec, design doc)
- **Acceptance Criteria:** Defining measurable success conditions
- **Stakeholder Alignment:** Creating documents for team review and approval
- **Implementation Blueprint:** Detailed guide for developers to follow

---

## Commands & Syntax
```bash
# Enable Spec Developer mode
/spec-developer
/spec                                 # Short form

# Generate specification for feature
/spec create "User authentication system"

# Create specific document type
/spec create-prd "Mobile app redesign"
/spec create-api-doc "REST API endpoints"
/spec create-design-doc "Database schema"

# Add section to existing spec
/spec add-section acceptance-criteria

# Review and improve specification
/spec review

# Export specification
/spec export --format markdown
/spec export --format pdf

# Generate implementation checklist from spec
/spec to-checklist
```

---

## When to Use

Use Spec Developer mode when planning major features that need formal documentation, working with distributed teams that need clear specifications, outsourcing development and need detailed contracts, seeking stakeholder approval before implementation, creating API documentation for external developers, establishing acceptance criteria for QA testing, or when you need professional documentation for compliance or auditing purposes.

---

## How It Works

**Step 1:** Enable Spec Developer mode with `/spec-developer`

**Step 2:** Describe the feature or system you need specified

**Step 3:** Claude generates comprehensive specification document with standard sections

**Step 4:** Review specification for completeness and accuracy

**Step 5:** Request additions or modifications to specific sections

**Step 6:** Use `/spec review` to get Claude's assessment of spec quality

**Step 7:** Export final specification for team review or as implementation guide

---

## Common Issues

### Issue: Specification is too technical or too vague
**Symptoms:** Document doesn't match audience needs  
**Solution:** Specify target audience when creating spec (developers, stakeholders, QA), request technical depth adjustment, provide examples of desired level of detail

### Issue: Missing important sections
**Symptoms:** Specification doesn't cover all necessary aspects  
**Solution:** Use `/spec add-section` to include missing parts, reference standard templates (PRD, design doc) for section ideas, ask Claude what sections are typically included

### Issue: Specification doesn't match actual requirements
**Symptoms:** Document describes something different from what's needed  
**Solution:** Review and provide corrections iteratively, enable Interactive Questions mode alongside Spec Developer, break down into smaller specifications for complex projects

---

## Important Notes

- 💡 **Tip:** Use Spec Developer before Planning Mode - spec informs better plans
- 💡 **Tip:** Create specifications for major features even in solo projects - clarifies thinking
- 💡 **Tip:** Share specs with stakeholders for approval before implementation begins
- 💡 **Tip:** Convert approved specs to implementation checklists for tracking
- 💡 **Tip:** Maintain specs as living documents - update when requirements change
- 📌 **Remember:** Good specification saves implementation time by reducing ambiguity
- 📌 **Remember:** Specifications serve as contracts - be precise and complete
- 📌 **Remember:** Export and version control specifications alongside code

