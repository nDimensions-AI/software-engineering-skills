---
name: security
description: Secure-by-design review and implementation — auth, input handling, secrets, dependencies, data protection. Use for any code touching user input, auth, data, or infra.
---
# Security
- Threat model briefly (STRIDE): assets, entry points, trust boundaries, attackers.
- Validate & normalize all input at boundaries (allowlists); parameterized queries; context-aware output encoding; no shell string building.
- AuthN via proven libraries; AuthZ checked server-side on every request & object (no IDOR).
- Secrets: never in code, logs, or client bundles; use a secret manager; rotate.
- Least privilege everywhere (IAM, DB users, tokens, scopes).
- Crypto: never roll your own; use vetted libs, modern algorithms, hash passwords with argon2/bcrypt.
- Dependencies: pin, scan, minimize. Logging: no PII/secrets; audit security events.
- Fail closed. Safe defaults. Defense in depth. Check OWASP Top 10 / ASVS.
