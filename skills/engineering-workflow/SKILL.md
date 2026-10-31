---
name: engineering-workflow
description: Master workflow for any non-trivial coding task — understand, plan, implement, verify, deliver. Use at the start of every feature, bug, or refactor task.
---
# Engineering Workflow (orchestrator)
1. **Understand** — restate the goal and acceptance criteria. Read the relevant code, conventions, and tests before writing anything. Ask only when genuinely blocked.
2. **Plan** — for >1 file or unclear changes, write a short plan; use `app-from-scratch` for new apps, `codebase-onboarding` for unfamiliar code, `multi-agent-workflow` for large builds, `architecture-design` for structural changes, `api-design` for interfaces, `frontend-ui-ux` / `ui-component-builder` for UI.
3. **Implement** — follow `tdd`; match existing style; smallest change that fully solves the problem; no drive-by unrelated edits.
4. **Verify** — run tests, linters, type checks, and the app itself. Self-review with `code-review` + `security`. Report real results, including failures.
5. **Deliver** — follow `git-workflow`; summarize what changed, why, how verified, and any follow-ups.

Quality bar: correct > clear > simple > fast. Delete more than you add when possible. Leave the codebase better than you found it.
