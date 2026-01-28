# /stats Command

---

## What It Is

The `/stats` command provides comprehensive statistical information about your current Claude Code session, including message counts, token usage metrics, session duration, API calls made, cost estimates (if applicable), performance data, and other quantitative measures of your interaction. This command serves as an analytics dashboard for your development session, helping you understand resource consumption, track productivity metrics, monitor costs, optimize usage patterns, and make data-driven decisions about session management.

---

## Key Concepts

- **Session Analytics:** Quantitative data about your Claude Code usage
- **Token Metrics:** Input tokens, output tokens, and total consumption
- **Message Statistics:** Count of user messages vs AI responses
- **Duration Tracking:** How long the session has been active
- **Cost Estimation:** Approximate API costs based on token usage (if using paid tier)
- **Performance Indicators:** Response times and throughput metrics

---

## Commands & Syntax
```bash
# Display all session statistics
/stats

# Show detailed statistics
/stats --verbose

# Show only token usage stats
/stats --tokens

# Show only cost estimates
/stats --cost

# Show performance metrics
/stats --performance

# Compare with previous sessions
/stats --compare

# Export statistics to file
/stats --export stats.json
```

---

## When to Use

Use `/stats` when monitoring token consumption to avoid hitting limits, estimating costs before making large requests on paid tiers, analyzing which types of tasks consume most tokens, troubleshooting slow responses by checking performance metrics, documenting session productivity for time tracking or reporting, or comparing efficiency across different development approaches to optimize workflow.

---

## How It Works

**Step 1:** Throughout your session, Claude Code tracks various metrics in the background

**Step 2:** Data is collected on messages sent/received, tokens consumed, time elapsed, etc.

**Step 3:** Type `/stats` to query the accumulated statistics

**Step 4:** Claude Code compiles and formats the data into readable report

**Step 5:** Review metrics to understand session characteristics

**Step 6:** Use insights to optimize token usage, manage costs, or improve workflow

---

## Common Issues

### Issue: Stats show unexpectedly high token usage
**Symptoms:** Token count much higher than expected for conversation length  
**Solution:** Check context size with `/context --tokens` - large files consume many tokens, review if unnecessary files are loaded, consider compacting conversation with `/compact`

### Issue: Cannot see cost estimates
**Symptoms:** `/stats --cost` shows no data or zeros  
**Solution:** Cost tracking may only work on paid API tiers, free tier might not display costs, verify you're using version that supports cost tracking

### Issue: Stats seem inaccurate
**Symptoms:** Numbers don't match perceived usage  
**Solution:** Stats accumulate throughout session - they're cumulative not per-message, restart session and track from zero if you want fresh metrics, export and analyze data file for discrepancies

---

## Important Notes

- 💡 **Tip:** Check `/stats --tokens` periodically during long sessions to monitor consumption rate
- 💡 **Tip:** Use stats to identify token-heavy operations and optimize by reducing context
- 💡 **Tip:** Export stats at session end to track productivity patterns over time
- 💡 **Tip:** Compare token usage across different models to find cost-effective approach
- 📌 **Remember:** Token usage includes input (your prompts + context) and output (Claude's responses)
- 📌 **Remember:** Stats reset when you start new session - they're not persistent across sessions
