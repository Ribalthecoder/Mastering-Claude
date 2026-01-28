# /permissions Command

---

## What It Is

The `/permissions` command allows you to view and manage what actions Claude Code is authorized to perform on your system, controlling capabilities like file read/write access, terminal command execution, network operations, and other potentially sensitive operations. This command provides a security layer where you can grant or restrict Claude Code's abilities, review what permissions are currently active, understand what Claude Code can and cannot do in your environment, and adjust access levels based on trust and project requirements.

---

## Key Concepts

- **Permission Management:** Controlling what Claude Code can do on your system
- **Access Control:** Limiting operations to prevent unintended or dangerous actions
- **Security Boundaries:** Defining safe vs restricted operations
- **Permission Levels:** Different granularity of access (read-only, read-write, execute, etc.)
- **Approval Workflow:** Some operations may require explicit user confirmation
- **Trust Settings:** Configuring how much autonomy Claude Code has

---

## Commands & Syntax
```bash
# View current permissions
/permissions

# View detailed permission status
/permissions --verbose

# Grant specific permission
/permissions grant file-write
/permissions grant terminal-execute
/permissions grant network-access

# Revoke specific permission
/permissions revoke file-write
/permissions revoke terminal-execute

# Reset to default permissions
/permissions reset

# Set permission level (if supported)
/permissions set file-access read-only
/permissions set file-access read-write

# Require approval for specific actions
/permissions require-approval file-delete
/permissions require-approval terminal-execute
```

---

## When to Use

Use `/permissions` when working in sensitive projects where you want to restrict Claude Code's file modification abilities, before allowing Claude Code to execute terminal commands on production systems, to understand what Claude Code is currently allowed to do in your environment, when transitioning from testing to production use and need tighter controls, or to troubleshoot why Claude Code cannot perform certain operations you've requested.

---

## How It Works

**Step 1:** Claude Code operates within a permission framework that controls its capabilities

**Step 2:** Use `/permissions` to view what is currently allowed or restricted

**Step 3:** Analyze your security needs and project sensitivity

**Step 4:** Grant or revoke specific permissions using appropriate commands

**Step 5:** Claude Code will only be able to perform operations within granted permissions

**Step 6:** Operations requiring revoked permissions will either fail or prompt for explicit approval

---

## Common Issues

### Issue: Claude Code cannot perform requested action
**Symptoms:** Error messages about insufficient permissions when asking Claude to modify files or run commands  
**Solution:** Check `/permissions` to see what's currently allowed, grant necessary permission with `/permissions grant <type>`, understand some restrictions may be intentional for safety

### Issue: Too permissive and concerned about safety
**Symptoms:** Worried Claude Code might perform dangerous operations  
**Solution:** Use `/permissions revoke` to restrict risky capabilities, enable require-approval mode for critical operations, work with read-only permissions when exploring unfamiliar code

### Issue: Permission changes not taking effect
**Symptoms:** Granted permission but Claude still cannot perform action  
**Solution:** Verify permission change with `/permissions --verbose`, restart Claude Code session to ensure changes apply, check if other security layers (OS, antivirus) are blocking

---

## Important Notes

- ⚠️ **Warning:** Granting terminal-execute permission allows Claude Code to run any command - use cautiously
- ⚠️ **Warning:** In production environments, use restrictive permissions and require-approval mode
- 💡 **Tip:** Start with minimal permissions and grant more as needed rather than starting fully open
- 💡 **Tip:** Use read-only file access when reviewing or analyzing code without making changes
- 💡 **Tip:** Require approval for file deletions to prevent accidental data loss
- 📌 **Remember:** Permission restrictions protect you - don't disable them unless necessary
- 📌 **Remember:** Some Claude Code functionality requires certain permissions - balance security with usability

