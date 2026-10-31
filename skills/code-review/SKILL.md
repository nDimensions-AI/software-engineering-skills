---
name: code-review
description: Review a diff, PR, or file for correctness, design, security, performance, and readability. Use before merging or when asked to review.
---
# Code Review

Review in priority order; report findings most-severe first with file:line, a concrete failure scenario, and a suggested fix.

1. **Correctness** — does it do what it claims? Edge cases, error paths, concurrency, off-by-one, null handling, resource leaks, transactional integrity.
2. **Security** — input validation, injection (SQL/shell/HTML), authz on every endpoint, secrets in code/logs, unsafe deserialization, SSRF, path traversal.
3. **Design** — right abstraction level? fits existing patterns? coupling, naming, single responsibility, public API stability.
4. **Tests** — do they test behavior and would they catch a regression? Missing cases?
5. **Performance** — N+1 queries, unbounded loops/memory, sync I/O on hot paths, missing indexes, needless allocations — only where it matters.
6. **Readability** — clear names, small functions, comments explain *why*, no dead code.
7. **Operability** — logging, metrics, feature flags, migrations reversible, backwards compatibility.

## Rules
- Verify each finding by reading surrounding code; no speculative noise. Label severity: blocker / should-fix / nit.
- Distinguish facts from preferences. Praise genuinely good decisions briefly.
- Prefer the smallest change that fixes the issue.
