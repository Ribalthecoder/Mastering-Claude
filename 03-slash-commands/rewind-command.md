# /rewind Command

---

## What It Is

The `/rewind` command allows you to undo recent messages in your Claude Code conversation and return to an earlier point in the session, effectively rolling back the conversation history to a specific message while preserving everything before that point. Unlike `/clear` which wipes everything, `/rewind` is surgical - it removes only the messages after your chosen rewind point, letting you correct mistakes, explore alternative approaches, or recover from unhelpful responses without losing your entire conversation context.

---

## Key Concepts

- **Selective Undo:** Remove recent messages while keeping earlier valuable context
- **Conversation Rollback:** Return to a specific point in the conversation timeline
- **Context Preservation:** Keep all messages and context before the rewind point
- **Branching Point:** Creates an opportunity to take the conversation in a new direction
- **Message Targeting:** Specify exactly how far back to rewind
- **Non-Destructive Alternative:** More precise than `/clear` for fixing recent issues

---

## Commands & Syntax
```bash
# Rewind to previous message (undo last exchange)
/rewind

# Rewind multiple messages back
/rewind 5                             # Go back 5 messages

# Rewind to specific message by ID (if supported)
/rewind --to-message <message-id>

# Preview rewind before executing
/rewind --preview 3                   # Show what will be removed

# Alternative syntax
/undo                                 # Same as /rewind in some versions
```

---

## When to Use

Use `/rewind` when Claude generated incorrect code and you want to try a different prompt without clearing everything, you gave unclear instructions and want to rephrase from that point, Claude went down the wrong path and you caught it a few messages later, you want to explore an alternative solution without losing earlier good work, or you need to undo the last few exchanges while keeping the valuable setup and context from earlier in the session.

---

## How It Works

**Step 1:** Identify the point in conversation where things went wrong or where you want to try a different approach

**Step 2:** Count how many message exchanges you need to undo (or note the message ID if available)

**Step 3:** Use `/rewind` with the number of messages to remove, or `/rewind` alone to undo just the last exchange

**Step 4:** Claude Code removes those messages from the conversation history

**Step 5:** You're now at an earlier point - Claude's context is as it was at that moment

**Step 6:** Continue with a different prompt or approach, creating a new branch from that point

---

## Common Issues

### Issue: Rewound too far and removed important context
**Symptoms:** Went back too many messages, lost valuable conversation  
**Solution:** Unfortunately cannot "redo" a rewind - you'll need to repeat those prompts, be more careful with rewind count in future, consider forking before major rewinds as safety net

### Issue: Rewind didn't solve the problem
**Symptoms:** Rewound and tried different approach but issue persists  
**Solution:** Problem might be earlier in conversation than you rewound to, may need to `/clear` and start fresh with better initial context, or issue is with files on disk not conversation history

### Issue: Unsure how many messages to rewind
**Symptoms:** Don't know exact number to go back to the problem point  
**Solution:** Use `/rewind --preview <number>` if available to see what will be removed, start with small rewind (2-3) and increase if needed, examine conversation history to count exchanges

---

## Important Notes

- ⚠️ **Warning:** Rewind is permanent for those messages - cannot redo or recover them after rewind
- ⚠️ **Warning:** Files on disk are NOT affected - only conversation history is rewound
- 💡 **Tip:** Rewind immediately when you notice Claude going wrong direction - don't wait
- 💡 **Tip:** `/rewind` is better than `/clear` when only recent messages are problematic
- 💡 **Tip:** After rewind, rephrase your request more clearly to avoid same mistake
- 📌 **Remember:** Rewind affects conversation only - your actual code files remain as they are
- 📌 **Remember:** Start with small rewinds (1-2 messages) and increase if needed

