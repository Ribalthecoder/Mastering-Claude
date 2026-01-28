# /handoff Command

---

## What It Is

The `/handoff` command transfers the current session and all its context to another AI agent, model, or specialized tool, enabling seamless collaboration between different AI systems or routing complex tasks to the most appropriate handler. This command facilitates workflows where different parts of a problem are better suited to different AI capabilities, allowing you to leverage specialized agents for specific domains (like code review, testing, documentation) while maintaining continuity of context and conversation history throughout the handoff process.

---

## Key Concepts

- **Agent Transfer:** Moving session control from one AI to another
- **Context Preservation:** Maintaining conversation history during handoff
- **Specialized Routing:** Directing tasks to agents optimized for specific work
- **Collaborative Workflows:** Multiple AI agents working on same project
- **Domain Expertise:** Leveraging agents with specialized knowledge
- **Seamless Transition:** Handoff occurs without losing project understanding

---

## Commands & Syntax
```bash
# Handoff to another agent or model
/handoff agent-name

# Handoff with specific instructions
/handoff code-review "Focus on security issues"

# List available handoff targets
/handoff --list

# Handoff with context summary
/handoff testing --summarize

# Return from handoff to original agent
/handoff --return

# Handoff specific task while maintaining primary agent
/handoff --task "Generate tests" --to testing-agent
```

---

## When to Use

Use `/handoff` when encountering a task outside current agent's specialty (e.g., design work, database optimization, security audit), you need expert-level assistance in specific domain, current model is not optimal for the next phase of work, you want specialized review from domain-specific agent, or implementing multi-agent workflows where different AI systems handle different project aspects.

---

## How It Works

**Step 1:** Identify that current task would benefit from specialized agent or different model

**Step 2:** Use `/handoff --list` to see available agents and their capabilities

**Step 3:** Execute handoff command with target agent name and optional instructions

**Step 4:** Current session context is transferred to the receiving agent

**Step 5:** New agent takes control and responds with its specialized expertise

**Step 6:** You can return with `/handoff --return` or continue with new agent

---

## Common Issues

### Issue: Context lost during handoff
**Symptoms:** New agent doesn't understand project or previous decisions  
**Solution:** Use `/handoff --summarize` to provide condensed context, manually brief new agent on critical background if needed, ensure handoff includes relevant files in context

### Issue: Handoff target not available
**Symptoms:** Specified agent doesn't exist or isn't accessible  
**Solution:** Check `/handoff --list` for available options, verify spelling of agent name, ensure you have access to premium/specialized agents if required

### Issue: Unclear which agent to handoff to
**Symptoms:** Multiple agents might be suitable for task  
**Solution:** Read agent descriptions in `/handoff --list` carefully, start with general-purpose agent and handoff further if needed, ask current agent for recommendation before handing off

---

## Important Notes

- 💡 **Tip:** Use handoff strategically - don't switch agents unnecessarily as it can break flow
- 💡 **Tip:** Provide clear instructions during handoff to help receiving agent understand expectations
- 💡 **Tip:** Keep track of which agent you're working with, especially in long sessions
- 💡 **Tip:** Some specialized agents may have limited capabilities outside their domain
- 📌 **Remember:** Handoff maintains session continuity - you don't start from scratch
- 📌 **Remember:** Not all Claude Code installations have multiple agents - feature availability varies

