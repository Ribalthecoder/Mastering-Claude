# /compact Command

---

## What It Is

The `/compact` command compresses your conversation history by condensing earlier messages while preserving the essential information and context, allowing you to continue long sessions without hitting context limits or experiencing performance degradation. Instead of clearing everything like `/clear` or removing messages like `/rewind`, `/compact` intelligently summarizes older parts of the conversation into concise representations, maintaining the key decisions and context while reducing the total token count, essentially creating more room for new messages without losing important historical context.

---

## Key Concepts

- **Context Compression:** Reducing conversation size while preserving essential information
- **Intelligent Summarization:** AI condenses old messages into key points without losing meaning
- **Token Management:** Keeping conversation within model's token limits for optimal performance
- **Lossless Essentials:** Critical information preserved even after compaction
- **Automatic vs Manual:** Some versions auto-compact, others require manual trigger
- **Performance Optimization:** Smaller context = faster responses and lower costs

---

## Commands & Syntax
```bash
# Compact the conversation history
/compact

# Compact with aggressive compression
/compact --aggressive

# Preview what will be compacted before executing
/compact --preview

# Auto-compact when reaching threshold (if supported)
/compact --auto

# Check current context size before deciding to compact
/stats                                # Shows token usage
```

---

## When to Use

Use `/compact` when your session has been running for a long time with many exchanges, Claude Code responses are becoming slower, you're approaching context limits and getting warnings, you want to continue current session but history is cluttered with solved problems, or when working on multi-hour development sessions where early conversation is no longer actively relevant but contains important architectural decisions you want preserved.

---

## How It Works

**Step 1:** Claude Code analyzes your entire conversation history to identify key information

**Step 2:** Older messages that are no longer actively relevant get summarized into concise points

**Step 3:** Recent messages (usually last 10-20 exchanges) remain untouched for full detail

**Step 4:** Essential context like project structure, important decisions, and file paths are preserved

**Step 5:** Redundant or superseded information is removed or condensed

**Step 6:** You continue with the same effective context but significantly reduced token count

---

## Common Issues

### Issue: Lost important information after compacting
**Symptoms:** Claude doesn't remember a specific detail that was compacted away  
**Solution:** Provide the information again in current conversation, use `/compact --preview` in future to see what will be removed, avoid compacting if session contains unique critical details you'll need

### Issue: Compact didn't free much space
**Symptoms:** Token usage barely changed after compacting  
**Solution:** Most of your conversation is recent and wasn't compacted, may need to `/clear` instead if entire conversation is problematic, compact works best on long sessions with older content

### Issue: Session feels "different" after compacting
**Symptoms:** Claude's responses seem less contextually aware  
**Solution:** Some nuance is lost in compression - this is expected trade-off, provide additional context if Claude seems confused about something, consider if compaction was necessary or if `/clear` + fresh start is better

---

## Important Notes

- ⚠️ **Warning:** Compaction is one-way - cannot uncompress or restore original detailed history
- ⚠️ **Warning:** Some subtle context and nuance may be lost in compression process
- 💡 **Tip:** Compact proactively during long sessions before hitting limits, not after
- 💡 **Tip:** Use `/stats` to monitor context usage - compact when reaching 70-80% capacity
- 💡 **Tip:** Recent conversation (last 10-20 messages) typically isn't compacted - only older history
- 📌 **Remember:** Compact is middle ground between `/clear` (too aggressive) and doing nothing (hitting limits)
- 📌 **Remember:** Essential decisions and file context are preserved - Claude won't forget project basics

