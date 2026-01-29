# MCP Tool Search

---

## What It Is

MCP Tool Search is a discovery and querying system that allows you to find available tools across all connected MCP servers, search for specific capabilities, understand tool parameters and requirements, and identify which tools can solve particular problems. This search functionality is essential for working with multiple MCP servers as it provides a unified way to discover what operations Claude Code can perform through external integrations, helping you leverage the full power of connected systems without memorizing every available tool.

---

## Key Concepts

- **Tool Discovery:** Finding available capabilities across all MCP servers
- **Capability Search:** Locating tools that perform specific functions
- **Tool Metadata:** Understanding parameters, permissions, and requirements
- **Cross-Server Search:** Querying tools from multiple MCP servers simultaneously
- **Tool Documentation:** Accessing usage instructions and examples
- **Dynamic Availability:** Tools may appear/disappear as servers connect/disconnect

---

## Commands & Syntax
```bash
# Search all available tools
/mcp-tool-search
/mcp tools

# Search for specific capability
/mcp-tool-search "database query"
/mcp tools --search "send email"

# List tools from specific server
/mcp tools --server database-server

# Show detailed tool information
/mcp tool-info tool-name

# Search by category
/mcp tools --category data-access
/mcp tools --category communication

# Show tool examples
/mcp tool-examples tool-name

# Filter tools by permission level
/mcp tools --permission read-only
```

---

## When to Use

Use MCP Tool Search when you need to find the right tool for a specific task across multiple servers, you're unsure what capabilities are available through MCP integrations, you want to understand tool parameters before using them, troubleshooting why certain operations aren't working (tool might not be available), discovering new tools after MCP servers are added or updated, or when teaching team members what's possible with your MCP setup.

---

## How It Works

**Step 1:** Claude Code maintains registry of all tools from connected MCP servers

**Step 2:** Use `/mcp tools` to query the complete tool catalog

**Step 3:** Search can filter by keywords, categories, server names, or permissions

**Step 4:** Results show tool names, descriptions, and which server provides them

**Step 5:** Use `/mcp tool-info` to get detailed information about specific tools

**Step 6:** Tool documentation includes parameters, return types, and usage examples

**Step 7:** Claude Code uses this information to correctly invoke tools when needed

---

## Common Issues

### Issue: Cannot find expected tool
**Symptoms:** Know a tool should exist but search doesn't return it  
**Solution:** Verify MCP server providing that tool is connected, check tool name spelling (may differ from what you expect), ensure you have permissions to see the tool, refresh tool cache with `/mcp refresh`

### Issue: Too many search results to review
**Symptoms:** Search returns hundreds of tools  
**Solution:** Use more specific search terms, filter by category or server, ask Claude to recommend appropriate tool for your specific task, review tool documentation to create personal favorites list

### Issue: Tool documentation is unclear
**Symptoms:** Don't understand how to use found tool  
**Solution:** Use `/mcp tool-examples` to see practical usage, ask Claude to explain tool in context of your use case, contact MCP server administrator for clarification, test tool with simple parameters first

---

## Important Notes

- 💡 **Tip:** Regularly explore available tools to discover new capabilities
- 💡 **Tip:** Save frequently used tool names for quick reference
- 💡 **Tip:** Use tool search to educate team on available integrations
- 💡 **Tip:** When MCP servers update, search for new tools that were added
- 💡 **Tip:** Ask Claude to recommend tools rather than searching manually
- 📌 **Remember:** Tool availability depends on which MCP servers are connected
- 📌 **Remember:** Some tools may require special permissions or authentication
- 📌 **Remember:** Tool search is real-time - reflects current server state

