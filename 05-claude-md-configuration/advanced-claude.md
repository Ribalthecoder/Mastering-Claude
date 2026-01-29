# Advanced CLAUDE.md

---

## What It Is

Advanced CLAUDE.md refers to sophisticated configuration techniques that go beyond basic project settings, including conditional rules based on file types or directories, templated responses for common tasks, custom workflows and macros, integration with external tools, environment-specific configurations, and dynamic content that adapts based on context. These advanced features transform CLAUDE.md from a simple instruction file into a powerful automation and customization system that can dramatically enhance Claude Code's effectiveness for complex projects.

---

## Key Concepts

- **Conditional Rules:** Different behavior based on file type, directory, or context
- **Templated Responses:** Predefined formats for common outputs (commit messages, docs)
- **Workflow Automation:** Multi-step processes triggered by keywords
- **Tool Integration:** Connecting Claude Code with linters, formatters, test runners
- **Environment Awareness:** Different rules for dev, staging, production
- **Dynamic Content:** Variables and logic in configuration

---

## Commands & Syntax
```markdown
<!-- Inside CLAUDE.md file -->

# Advanced CLAUDE.md Examples

## Conditional Rules by File Type
```
When working on *.test.js files:
- Always include comprehensive test cases
- Use Jest assertions
- Follow AAA pattern (Arrange, Act, Assert)

When working on *.css files:
- Use BEM naming convention
- Include mobile-first media queries
- Ensure accessibility contrast ratios
```

## Templated Commit Messages
```
Commit message template:
type(scope): brief description

[detailed explanation]

[breaking changes if any]
```

## Custom Workflows
```
Workflow: new-feature
1. Create feature branch
2. Generate component boilerplate
3. Create test file
4. Update documentation
```

## Tool Integration
```
Before committing:
- Run: npm run lint
- Run: npm test
- Run: npm run type-check
```

## Environment-Specific Rules
```
In production mode:
- Never use console.log
- Always include error boundaries
- Require security review for auth changes
```
```

---

## When to Use

Use Advanced CLAUDE.md when managing large projects with complex conventions, working with teams that need strict consistency enforcement, projects with multiple environments requiring different behavior, automating repetitive workflows to save time, integrating Claude Code deeply into your development pipeline, or when basic CLAUDE.md doesn't provide enough control over Claude's behavior.

---

## How It Works

**Step 1:** Start with basic CLAUDE.md created via `/init`

**Step 2:** Identify patterns in your interactions - repeated instructions, conditional needs

**Step 3:** Add advanced sections to CLAUDE.md using structured syntax

**Step 4:** Define conditional rules, templates, or workflows as needed

**Step 5:** Test that advanced features work by triggering relevant scenarios

**Step 6:** Refine and expand advanced configurations based on team feedback

**Step 7:** Document advanced features so team understands available automations

---

## Common Issues

### Issue: Conditional rules not triggering correctly
**Symptoms:** Rules defined for specific file types don't apply  
**Solution:** Verify file pattern syntax is correct (*.js vs .js), ensure conditions are mutually exclusive and clear, test with explicit file references to debug

### Issue: Templates producing inconsistent output
**Symptoms:** Templated responses vary unexpectedly  
**Solution:** Make templates more specific and detailed, include examples in template definition, test templates across different scenarios

### Issue: Advanced CLAUDE.md is too complex to maintain
**Symptoms:** Team members confused by elaborate configurations  
**Solution:** Document each advanced feature with comments, keep configurations as simple as possible, regular review and cleanup of unused features

---

## Important Notes

- ⚠️ **Warning:** Complex CLAUDE.md files consume more context tokens
- ⚠️ **Warning:** Over-specification can make Claude Code less flexible for edge cases
- 💡 **Tip:** Start simple and add advanced features only when clear need emerges
- 💡 **Tip:** Use comments liberally to explain advanced configurations
- 💡 **Tip:** Version control CLAUDE.md changes to track what works
- 💡 **Tip:** Share advanced patterns with community for others to learn from
- 📌 **Remember:** Advanced features should save time, not add complexity
- 📌 **Remember:** Test advanced configurations thoroughly before team adoption
