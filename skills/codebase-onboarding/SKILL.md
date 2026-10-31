---
name: codebase-onboarding
description: Understand a large or unfamiliar codebase and audit it — architecture, data flow, structural problems, duplication, performance and maintainability risks — then refactor without changing behavior. Use when joining a codebase, asked to "explain this repo", audit, or improve code quality.
---
# Codebase Understanding & Refactoring

Think like a senior engineer who just joined: understand before changing.

## Understand (read, don't guess)
1. Entry points, build/run/test commands, dependencies, config.
2. Map modules and their responsibilities; draw the dependency graph.
3. Trace 2–3 core flows end to end (request → handler → domain → storage → response).
4. Note conventions (naming, error handling, layering, testing) — new code must follow them.
5. Check test coverage and git history hotspots (`git log --format= --name-only | sort | uniq -c | sort -rn | head`): high-churn + complex files are highest risk.

## Identify
- **Structural problems** — layering violations, circular deps, god modules, misplaced logic, leaky abstractions
- **Duplicated code** — copy-paste logic, parallel hierarchies
- **Performance bottlenecks** — N+1 queries, repeated work, blocking I/O, unbounded data (see `performance`)
- **Maintainability risks** — no tests, dead code, magic values, outdated or vulnerable deps, unclear ownership

Prioritize by impact × likelihood ÷ effort.

## Refactor (apply `refactoring`)
Pin behavior with characterization tests first, then small reversible steps. **Functionality must remain unchanged.**

## Required output
1. **Architecture summary** — modules, data flow diagram, key abstractions, conventions
2. **Problem areas** — ranked list with file:line evidence
3. **Refactoring strategies** — what, why, order, risk
4. **Improved code** — with tests proving behavior is unchanged
