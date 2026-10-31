---
name: git-workflow
description: Commit, branch, and PR hygiene. Use when committing, opening PRs, or preparing changes for review.
---
# Git Workflow
- Small, atomic commits; each builds and passes tests. Separate refactor / feature / formatting.
- Messages: imperative subject ≤72 chars (`Add retry to payment client`), body explains *why* and trade-offs.
- Branch per change; rebase on main before PR; never force-push shared branches.
- PR: what/why, how tested, screenshots for UI, risks & rollback plan. Keep under ~400 lines when possible.
- Never commit secrets, generated artifacts, or unrelated changes. Review your own diff first.
