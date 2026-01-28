# /model Command

---

## What It Is

The `/model` command allows you to switch between different AI models within the same Claude Code session, enabling you to choose the optimal model for your specific task based on factors like complexity, speed requirements, cost considerations, or token limits. Different models in the Claude family (like Opus, Sonnet, and Haiku) offer different trade-offs between intelligence/capability and speed/cost, and `/model` lets you dynamically adjust which model is handling your requests without exiting and restarting your session.

---

## Key Concepts

- **Model Selection:** Choosing which AI model processes your requests
- **Model Tiers:** Different models with varying capabilities (Opus = most capable, Sonnet = balanced, Haiku = fastest)
- **Dynamic Switching:** Change models mid-session without losing context
- **Task-Appropriate Models:** Using simpler models for simple tasks, powerful models for complex ones
- **Cost Optimization:** Lower-tier models cost less per request than higher-tier models
- **Performance Trade-offs:** More capable models are slower but handle complexity better

---

## Commands & Syntax
```bash
# View current model being used
/model

# List all available models
/model --list

# Switch to specific model
/model opus                           # Switch to Claude Opus (most capable)
/model sonnet                         # Switch to Claude Sonnet (balanced)
/model haiku                          # Switch to Claude Haiku (fastest)

# Switch with full model name
/model claude-opus-4-5-20251101
/model claude-sonnet-4-5-20250929
/model claude-haiku-4-5-20251001

# Return to default model
/model default
```

---

## When to Use

Use `/model` to switch to Opus when tackling complex architectural decisions, difficult debugging, or sophisticated algorithms that need deep reasoning; switch to Sonnet for balanced everyday development tasks; or switch to Haiku when doing simple code generation, basic questions, or repetitive tasks where speed matters more than sophistication. Change models based on current task complexity rather than staying on one model for entire session.

---

## How It Works

**Step 1:** Assess the complexity of your current task - does it need deep reasoning or is it straightforward?

**Step 2:** Use `/model --list` to see available models if you're unsure of options

**Step 3:** Execute `/model <name>` to switch to the appropriate model for your task

**Step 4:** Continue conversation with new model - it inherits the session context and history

**Step 5:** Claude Code routes subsequent messages through the newly selected model

**Step 6:** Switch models again as task complexity changes throughout your session

---

## Common Issues

### Issue: Model switch seems ineffective
**Symptoms:** Don't notice difference after switching models  
**Solution:** Difference is subtle for simple tasks - models diverge more on complex problems, verify switch succeeded with `/model` to confirm current model, try more complex request to see capability differences

### Issue: Switched to Haiku but responses are poor quality
**Symptoms:** Haiku gives incorrect or incomplete answers  
**Solution:** Haiku is optimized for speed not complexity - switch to Sonnet or Opus for better results, use Haiku only for straightforward tasks, understand model limitations

### Issue: Don't know which model to choose
**Symptoms:** Unsure if task needs Opus, Sonnet, or Haiku  
**Solution:** Default to Sonnet for most tasks (good balance), use Opus when Sonnet struggles or for critical decisions, use Haiku only for very simple repetitive tasks

---

## Important Notes

- ⚠️ **Warning:** All models have same context/conversation history - switching doesn't reset context
- 💡 **Tip:** Use Opus for architecture and complex debugging, Sonnet for general development, Haiku for simple generation
- 💡 **Tip:** Start with Sonnet - only switch up to Opus if task proves too complex
- 💡 **Tip:** Model switching doesn't lose context - you can freely experiment to find best model for task
- 📌 **Remember:** Higher-tier models may cost more if using API with usage-based billing
- 📌 **Remember:** Speed differences matter more in repetitive tasks - for one-off questions, use best model for accuracy

