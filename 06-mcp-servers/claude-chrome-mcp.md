# Claude in Chrome MCP

---

## What It Is

Claude in Chrome MCP is a specialized MCP server that enables Claude Code to interact with web browsers, allowing it to navigate websites, extract information from web pages, fill forms, interact with web applications, capture screenshots, and perform browser automation tasks. This integration bridges the gap between Claude Code's terminal environment and web-based interfaces, enabling Claude to access web data, test web applications, scrape information, and automate browser-based workflows that would otherwise require manual intervention.

---

## Key Concepts

- **Browser Control:** Programmatic control of Chrome browser from Claude Code
- **Web Scraping:** Extracting data from websites for analysis or integration
- **Form Automation:** Filling and submitting web forms automatically
- **Page Navigation:** Visiting URLs, clicking links, and browsing like a human
- **Screenshot Capture:** Taking visual snapshots of web pages for analysis
- **Web Testing:** Automated testing of web applications and interfaces

---

## Commands & Syntax
```bash
# Connect to Chrome MCP server
/mcp connect chrome

# Navigate to URL
/chrome goto "https://example.com"

# Extract text from current page
/chrome extract-text

# Take screenshot
/chrome screenshot

# Click element
/chrome click "button#submit"

# Fill form field
/chrome fill "input[name='email']" "user@example.com"

# Execute JavaScript on page
/chrome eval "document.title"

# Wait for element to appear
/chrome wait-for "div.content"

# Get page HTML
/chrome get-html
```

---

## When to Use

Use Claude in Chrome MCP when you need to gather data from websites that don't have APIs, test web applications by automating user interactions, fill out repetitive web forms or submissions, monitor websites for changes or specific content, capture screenshots for documentation or bug reports, scrape competitor information or market data, or automate any workflow that requires interacting with web-based interfaces.

---

## How It Works

**Step 1:** Chrome MCP server is installed and configured (typically runs as background service)

**Step 2:** Connect Claude Code to Chrome MCP using `/mcp connect chrome`

**Step 3:** Claude can now send browser control commands through the MCP protocol

**Step 4:** Chrome MCP server executes commands in actual Chrome browser instance

**Step 5:** Results (text, HTML, screenshots) are returned to Claude Code

**Step 6:** Claude processes browser data and incorporates into responses

**Step 7:** Browser can remain open for multi-step interactions or be closed after task

---

## Common Issues

### Issue: Chrome browser not responding to commands
**Symptoms:** Commands timeout or fail to execute  
**Solution:** Verify Chrome MCP server is running, check if Chrome browser is installed and accessible, restart Chrome MCP server, ensure no conflicting browser extensions

### Issue: Cannot find specific elements on page
**Symptoms:** Click or fill commands fail with "element not found"  
**Solution:** Use `/chrome get-html` to inspect page structure, verify CSS selector syntax is correct, wait for page to load completely with `/chrome wait-for`, check if element is in iframe

### Issue: Scraping violates website terms of service
**Symptoms:** Legal or ethical concerns about data extraction  
**Solution:** Always check website terms of service and robots.txt, use official APIs when available, implement rate limiting to avoid overwhelming servers, respect copyright and data privacy laws

---

## Important Notes

- ⚠️ **Warning:** Web scraping must comply with website terms of service and legal requirements
- ⚠️ **Warning:** Automated browser interaction can be detected and blocked by some sites
- ⚠️ **Warning:** Be respectful with request frequency - don't overload target servers
- 💡 **Tip:** Use Chrome DevTools to identify correct element selectors
- 💡 **Tip:** Take screenshots before and after interactions for debugging
- 💡 **Tip:** Wait for page loads and dynamic content before extracting data
- 💡 **Tip:** Prefer official APIs over scraping when available
- 📌 **Remember:** Chrome MCP requires Chrome browser installed on system
- 📌 **Remember:** Some websites actively block automation - respect their policies
- 📌 **Remember:** Screenshots and HTML can be large - manage context usage
