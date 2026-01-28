# Interactive Questions

---

## What It Is

Interactive Questions is a mode where Claude Code proactively asks clarifying questions before beginning implementation, ensuring it fully understands requirements, resolves ambiguities, identifies missing specifications, and aligns with your expectations before writing any code. Instead of making assumptions about unclear aspects of your request, Claude pauses to gather necessary information through structured questions, resulting in more accurate implementations that match your intent and reducing the need for revisions and rework.

---

## Key Concepts

- **Clarification Before Action:** Asking questions instead of assuming
- **Requirement Gathering:** Extracting complete specifications through dialogue
- **Ambiguity Resolution:** Identifying and addressing unclear aspects
- **Expectation Alignment:** Ensuring shared understanding of goals
- **Informed Implementation:** Building with full context and clarity
- **Reduced Rework:** Fewer revisions needed due to better initial understanding

---

## Commands & Syntax
```bash
# Enable Interactive Questions mode
/interactive-questions
/iq                                   # Short form

# Disable Interactive Questions mode
/interactive-questions off

# Request questions about specific topic
/ask-questions-about "database schema design"

# Answer all pending questions at once
/answer-all

# Skip question (use default assumption)
/skip-question

# Review questions that were asked and answered
/question-history

# Set question depth (how thorough)
/iq-depth minimal                     # Only critical questions
/iq-depth standard                    # Balanced approach
/iq-depth thorough                    # Comprehensive questioning
```

---

## When to Use

Use Interactive Questions mode when providing high-level requirements that need fleshing out, working in unfamiliar domains where your requirements might be incomplete, building critical features where mistakes are costly, collaborating with stakeholders who need to provide input, specifications are ambiguous or have multiple valid interpretations, or when you want Claude to help you think through all aspects of the problem before implementation.

---

## How It Works

**Step 1:** Enable Interactive Questions mode with `/interactive-questions`

**Step 2:** Describe your feature or task at high level

**Step 3:** Claude analyzes request and identifies ambiguities, missing information, or decision points

**Step 4:** Claude asks structured questions to gather needed information

**Step 5:** You answer questions, providing clarifications and decisions

**Step 6:** Claude may ask follow-up questions based on your answers

**Step 7:** Once all questions are answered, Claude proceeds with fully-informed implementation

---

## Common Issues

### Issue: Too many questions slowing down development
**Symptoms:** Question phase takes longer than implementation would have  
**Solution:** Use `/iq-depth minimal` for simple tasks, disable mode for straightforward requests, answer multiple questions at once with `/answer-all`

### Issue: Questions ask about things you don't know yet
**Symptoms:** Cannot answer questions because decisions haven't been made  
**Solution:** Skip questions with `/skip-question` and let Claude use reasonable defaults, use questions as prompts to make necessary decisions, break project into smaller pieces with clearer requirements

### Issue: Claude proceeds without asking important questions
**Symptoms:** Implementation has issues that could have been caught with questions  
**Solution:** Ensure Interactive Questions mode is enabled, increase depth with `/iq-depth thorough`, explicitly request questions with `/ask-questions-about` on critical topics

---

## Important Notes

- 💡 **Tip:** Interactive Questions mode is ideal for complex or unfamiliar features
- 💡 **Tip:** Use questions as a checklist of what you need to think through
- 💡 **Tip:** Share question/answer history with team for documentation
- 💡 **Tip:** If Claude isn't asking enough questions, manually request them
- 📌 **Remember:** Time spent answering questions upfront saves debugging time later
- 📌 **Remember:** Good questions reveal gaps in your own understanding
- 📌 **Remember:** You can adjust question thoroughness based on task complexity

