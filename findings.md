# Secure Coding Review Findings

## Summary
Audited the application `app_to_audit`. Identified potential vulnerabilities and recommended remediation steps.

---

## Findings

### 1. Hardcoded Passwords
- **File:** `app_to_audit/config.py`
- **Issue:** Passwords stored in plain text.
- **Recommendation:** Use environment variables or secure secret management.

### 2. Use of eval()
- **File:** `app_to_audit/main.py`
- **Issue:** `eval()` used on user input.
- **Recommendation:** Avoid eval, parse inputs safely.

### 3. Missing Input Validation
- **File:** `app_to_audit/utils.py`
- **Issue:** User inputs not validated, risk of injection attacks.
- **Recommendation:** Implement strict input validation and sanitization.

---

## Remediation Steps
1. Remove hardcoded credentials.
2. Replace eval with safe parsing.
3. Validate all user inputs.
4. Keep dependencies up to date using `pip list --outdated` and `safety check`.

---

## References
- [OWASP Top 10 Security Risks](https://owasp.org/www-project-top-ten/)
- [Python Security Best Practices](https://docs.python-guide.org/writing/security/)
