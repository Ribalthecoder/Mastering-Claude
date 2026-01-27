# Using Screenshots

---

## What It Is

Screenshots is a feature in Claude Code that allows you to share visual information with Claude by capturing images of your screen, design mockups, error messages, UI layouts, or diagrams and including them in your conversation. Claude Code can analyze these images to understand what you're trying to build, debug visual issues, replicate designs, or provide guidance based on what it sees in the screenshot, making it especially useful for frontend development, UI/UX work, and debugging visual problems.

---

## Key Concepts

- **Visual Context:** Providing Claude Code with images to supplement text descriptions
- **Image Understanding:** Claude's ability to analyze screenshots and extract information from them
- **Design Replication:** Showing Claude a design and having it generate matching code
- **Error Debugging:** Screenshotting error messages for Claude to help diagnose
- **UI Reference:** Using screenshots of existing applications as reference for what to build
- **Multimodal Input:** Combining text and images in the same conversation for richer context

---

## Commands & Syntax
```bash
# Screenshots are typically handled through the Claude Code interface
# Exact commands depend on the specific Claude Code client you're using

# Common workflows:
# 1. Take screenshot using OS tools (Windows: Win+Shift+S, Mac: Cmd+Shift+4)
# 2. Paste or upload directly in Claude Code session
# 3. Ask Claude to analyze: "Look at this screenshot and recreate this button"

# Or use Claude Code's built-in screenshot feature (if available):
/screenshot                           # Capture screenshot (may vary by version)
/image path/to/image.png             # Reference existing image file
```

---

## When to Use

Use screenshots when describing something visually is much clearer than using words - such as showing Claude Code a design you want to replicate, sharing an error message with stack trace, demonstrating a UI bug, providing a wireframe or mockup to code from, or showing reference designs from other applications. Screenshots are particularly valuable for frontend development where visual accuracy matters.

---

## How It Works

**Step 1:** Identify what you want to show Claude Code (a design, error, UI element, diagram, etc.)

**Step 2:** Capture the screenshot using your operating system's screenshot tool or save the image file

**Step 3:** In your Claude Code session, upload or paste the screenshot (method varies by interface)

**Step 4:** Provide context with your request: "Based on this screenshot, create a similar login form"

**Step 5:** Claude Code analyzes the image and generates appropriate code or provides relevant guidance

**Step 6:** Iterate by sharing additional screenshots if needed to refine the implementation

---

## Common Issues

### Issue: Screenshot not being recognized
**Symptoms:** Claude Code doesn't acknowledge or respond to the screenshot  
**Solution:** Ensure image format is supported (PNG, JPG, JPEG), check file size isn't too large (usually under 5MB), verify you're using correct upload method for your Claude Code interface

### Issue: Claude misinterprets screenshot content
**Symptoms:** Generated code doesn't match the screenshot design  
**Solution:** Provide more specific text instructions alongside screenshot ("Focus on the navigation bar at the top"), highlight specific parts you want replicated, use multiple screenshots showing different angles or states

### Issue: Cannot upload images in terminal version
**Symptoms:** No option to add screenshots in command-line Claude Code  
**Solution:** Some Claude Code interfaces (pure terminal) may not support images - use web or desktop version of Claude Code, or describe visually with detailed text instead

---

## Important Notes

- ⚠️ **Warning:** Never screenshot and share sensitive information (passwords, API keys, personal data, financial info)
- 💡 **Tip:** Take clear, well-lit screenshots with good contrast - blurry or low-quality images make analysis difficult
- 💡 **Tip:** Screenshot only the relevant portion - crop out unnecessary parts to help Claude focus on what matters
- 💡 **Tip:** Combine screenshots with text descriptions: "This is a button [screenshot]. Make it rounded with a blue gradient"
- 📌 **Remember:** Claude can see colors, layouts, text, and general design but may not perfectly match fonts or exact pixel measurements
- 📌 **Remember:** Screenshots work best for UI/UX - they're less useful for showing code since Claude can't easily read text in images

