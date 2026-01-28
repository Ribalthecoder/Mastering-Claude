# /security-review Command

---

## What It Is

The `/security-review` command triggers a comprehensive security analysis of your code, scanning for common vulnerabilities, insecure patterns, potential exploits, hardcoded secrets, and other security issues within your project. Claude Code examines the codebase with a security-focused lens, identifying risks like SQL injection vulnerabilities, cross-site scripting (XSS) flaws, insecure authentication, exposed API keys, and compliance with security best practices, providing detailed findings with severity ratings and remediation recommendations.

---

## Key Concepts

- **Security Audit:** Systematic examination of code for vulnerabilities
- **Vulnerability Detection:** Identifying exploitable weaknesses in code
- **Best Practices Check:** Comparing code against security standards
- **Secret Scanning:** Finding hardcoded passwords, API keys, tokens
- **Severity Rating:** Classifying issues by risk level (critical, high, medium, low)
- **Remediation Guidance:** Suggestions for fixing identified issues

---

## Commands & Syntax
```bash
# Run security review on entire context
/security-review

# Review specific file or directory
/security-review src/auth/

# Run with specific severity threshold
/security-review --min-severity high

# Focus on specific vulnerability types
/security-review --check sql-injection,xss

# Generate detailed report
/security-review --report security-report.md

# Quick scan (faster but less thorough)
/security-review --quick

# Include dependency vulnerabilities
/security-review --include-dependencies
```

---

## When to Use

Use `/security-review` before deploying to production to catch vulnerabilities, after integrating third-party code or libraries, when working with authentication or payment systems, periodically during development as security hygiene practice, before code reviews to address issues proactively, or when handling sensitive data like personal information or financial records to ensure compliance with security standards.

---

## How It Works

**Step 1:** Command initiates security-focused analysis of code in context

**Step 2:** Claude Code scans for common vulnerability patterns (OWASP Top 10, CWE, etc.)

**Step 3:** Code is checked against security best practices for the language/framework

**Step 4:** Potential issues are identified and categorized by severity

**Step 5:** Each finding includes location, description, impact, and fix recommendations

**Step 6:** Results are presented in organized format, often prioritizing critical issues first

---

## Common Issues

### Issue: Review finds too many false positives
**Symptoms:** Many reported issues that aren't actual vulnerabilities  
**Solution:** Use severity filtering to focus on high/critical issues first, manually review findings to distinguish real vs false positives, provide more context about your security architecture to improve accuracy

### Issue: Hardcoded secrets flagged but they're test data
**Symptoms:** Test API keys or dummy passwords triggering security warnings  
**Solution:** Use proper test fixtures and environment variables even in tests, clearly label test credentials with obvious markers (TEST_KEY), consider excluding test directories from security review

### Issue: Review misses known vulnerability
**Symptoms:** Security issue you're aware of not detected  
**Solution:** Security scanning has limitations - cannot catch all logic flaws, manually review business logic and complex authentication flows, use `/security-review` as supplement not replacement for professional audits

---

## Important Notes

- ⚠️ **Warning:** Security reviews are helpful but not comprehensive - cannot replace professional security audits
- ⚠️ **Warning:** Address critical and high severity issues immediately before deployment
- 💡 **Tip:** Run security reviews regularly, not just before deployment
- 💡 **Tip:** Prioritize fixing critical issues first - don't get overwhelmed by low-severity findings
- 💡 **Tip:** Use findings as learning opportunities to improve security practices
- 📌 **Remember:** Some vulnerabilities require understanding business logic - AI cannot catch everything
- 📌 **Remember:** Remove all hardcoded secrets - use environment variables and secret management tools

