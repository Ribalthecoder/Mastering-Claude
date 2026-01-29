# Async Tasks & Subagents

---

## What It Is

Async Tasks & Subagents is a workflow pattern where subagents are spawned to work on long-running or background tasks asynchronously while the main Claude Code session remains available for other work, enabling true multitasking where you can continue interactive development while subagents handle time-consuming operations like running extensive test suites, performing large refactors, generating comprehensive documentation, or processing large datasets in the background.

---

## Key Concepts

- **Asynchronous Execution:** Subagents work independently while main session continues
- **Non-Blocking Operations:** Main agent doesn't wait for subagent completion
- **Background Processing:** Long-running tasks execute without freezing session
- **Status Polling:** Checking subagent progress without blocking
- **Result Retrieval:** Collecting outputs when ready
- **Concurrent Workflows:** Multiple parallel workstreams in single project

---

## Commands & Syntax
```bash
# Spawn subagent for async task
/spawn-async "Run full test suite"

# Spawn with callback notification
/spawn-async "Generate API documentation" --notify-on-complete

# Check async task status without blocking
/async-status

# Poll specific subagent
/async-status subagent-name

# Retrieve results when ready
/async-results subagent-name

# Wait for async task to complete
/async-wait subagent-name

# Cancel async task
/async-cancel subagent-name

# List all async tasks
/async-list
```

---

## When to Use

Use async subagents for running comprehensive test suites that take minutes, performing large-scale refactoring across many files, generating extensive documentation or reports, processing or analyzing large datasets, deploying applications with lengthy build times, or any task where waiting would waste your time and you have other productive work to do meanwhile.

---

## How It Works

**Step 1:** Identify task that will take significant time and doesn't require immediate interaction

**Step 2:** Spawn async subagent with `/spawn-async` specifying the task

**Step 3:** Subagent begins work in background while main session returns control to you

**Step 4:** Continue other work in main session - write code, review files, plan next steps

**Step 5:** Periodically check `/async-status` to monitor background task progress

**Step 6:** When subagent completes, retrieve results with `/async-results`

**Step 7:** Integrate async work into main session or spawn follow-up tasks

---

## Common Issues

### Issue: Forgot about async task and lost results
**Symptoms:** Subagent completed but results weren't retrieved  
**Solution:** Use `--notify-on-complete` flag for important tasks, regularly check `/async-list` for status, set reminders to check back on long-running tasks

### Issue: Async task consuming too many resources
**Symptoms:** System slowdown while async subagent runs  
**Solution:** Limit concurrent async tasks, configure resource limits if available, schedule heavy tasks for off-hours, consider if task truly needs async or can wait

### Issue: Cannot determine if async task failed or still running
**Symptoms:** Status unclear, no progress updates  
**Solution:** Use `/async-status --verbose` for detailed information, check subagent logs if available, implement heartbeat or progress reporting in task

---

## Important Notes

- ⚠️ **Warning:** Async subagents continue consuming resources even when you're not actively using them
- ⚠️ **Warning:** Too many concurrent async tasks can overwhelm system
- 💡 **Tip:** Use async for tasks taking >2 minutes where you have other work
- 💡 **Tip:** Set notifications for critical async tasks so you don't forget
- 💡 **Tip:** Review async task results promptly - they may expire or be cleaned up
- 💡 **Tip:** Cancel async tasks you no longer need to free resources
- 📌 **Remember:** Async doesn't mean faster - just non-blocking
- 📌 **Remember:** Main session can exit while async tasks continue (depending on implementation)

