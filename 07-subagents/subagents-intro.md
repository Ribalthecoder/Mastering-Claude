# Subagents Introduction

---

## What It Is

Subagents are independent AI instances that Claude Code can spawn to handle specific subtasks in parallel, allowing for distributed problem-solving where multiple AI agents work simultaneously on different aspects of a project. Each subagent operates with its own context, focus area, and objectives while the main Claude Code session orchestrates their work, collects results, and integrates outputs. This enables tackling complex projects more efficiently by dividing work among specialized agents rather than handling everything sequentially in a single conversation thread.

---

## Key Concepts

- **Parallel Processing:** Multiple AI agents working simultaneously on different tasks
- **Task Delegation:** Main agent assigns specific subtasks to subagents
- **Independent Context:** Each subagent has its own conversation and context window
- **Specialization:** Subagents can be configured for specific domains or task types
- **Result Aggregation:** Main agent collects and synthesizes subagent outputs
- **Orchestration:** Coordinating multiple subagents toward unified goal

---

## Commands & Syntax
```bash
# Spawn a new subagent
/spawn-subagent task-description

# Spawn subagent with specific name
/spawn-subagent --name "frontend-dev" "Build React components"

# List active subagents
/list-subagents

# Check subagent status
/subagent-status subagent-name

# Get results from subagent
/subagent-results subagent-name

# Terminate subagent
/terminate-subagent subagent-name

# Spawn multiple subagents at once
/spawn-subagents 3 "Task 1" "Task 2" "Task 3"
```

---

## When to Use

Use subagents for large projects with independent components that can be developed in parallel, tasks with clear separation of concerns (frontend/backend, different microservices), when you need different specialized expertise for different parts, projects where multiple approaches should be explored simultaneously, or any situation where parallel execution would significantly reduce total development time compared to sequential work.

---

## How It Works

**Step 1:** Identify a complex task that can be broken into independent subtasks

**Step 2:** Use `/spawn-subagent` to create agents for each subtask with clear objectives

**Step 3:** Each subagent starts its own conversation thread and begins working

**Step 4:** Subagents work independently and in parallel on their assigned tasks

**Step 5:** Main agent monitors progress with `/subagent-status`

**Step 6:** Retrieve completed work with `/subagent-results`

**Step 7:** Main agent integrates subagent outputs into cohesive final solution

---

## Common Issues

### Issue: Subagents producing inconsistent or conflicting code
**Symptoms:** Different subagents make incompatible architectural decisions  
**Solution:** Provide clear shared context in CLAUDE.md before spawning, explicitly define interfaces/contracts between components, review and align subagent outputs before integration

### Issue: Too many subagents consuming excessive resources
**Symptoms:** System slowdown, high token usage, complex coordination  
**Solution:** Limit number of concurrent subagents (3-5 typically optimal), terminate completed subagents promptly, ensure tasks are truly parallelizable

### Issue: Subagent waiting on another's output
**Symptoms:** Blocked subagent cannot proceed due to dependency  
**Solution:** Identify and sequence dependencies before spawning, use async patterns where possible, have main agent pass intermediate results between dependent subagents

---

## Important Notes

- ⚠️ **Warning:** Each subagent consumes tokens independently - costs multiply
- ⚠️ **Warning:** More subagents doesn't always mean faster - coordination overhead exists
- 💡 **Tip:** Use subagents for truly independent tasks, not artificially split work
- 💡 **Tip:** Provide each subagent with focused, clear objectives
- 💡 **Tip:** Monitor subagent progress regularly to catch issues early
- 💡 **Tip:** Start with 2-3 subagents before scaling up
- 📌 **Remember:** Subagents don't communicate with each other - only through main agent
- 📌 **Remember:** Integration of subagent work requires main agent effort

