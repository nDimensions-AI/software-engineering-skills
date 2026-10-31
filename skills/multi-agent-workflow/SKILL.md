---
name: multi-agent-workflow
description: Run a large build as four collaborating roles — Architect, Engineer, Reviewer, Optimizer — for higher-quality results. Use for big features or full builds, or when asked for a multi-agent or team workflow.
---
# Multi-Agent Workflow

Run the roles in order. Where the tool supports subagents (Claude Code Agent tool, Codex/Copilot agents), give each role its own agent with a clear brief; otherwise play each role in sequence, explicitly switching hats.

1. **Architect** → designs the system (`architecture-design`, `api-design`): architecture, data model, interfaces, slice plan, acceptance criteria. Hands off a written design.
2. **Engineer** → implements the design (`tdd`, `engineering-workflow`), following it exactly or flagging needed deviations back to the Architect.
3. **Reviewer** → independent quality control (`code-review`, `security`): checks against the design and acceptance criteria; findings ranked blocker / should-fix / nit. Engineer fixes blockers and should-fixes; repeat until clean.
4. **Optimizer** → measures and improves performance (`performance`) without changing behavior; tests must stay green.

Rules: every handoff is a written artifact; the Reviewer must not rubber-stamp — it must actually run the tests and read the code; stop iterating when no blockers remain.

## Required output
1. **Architecture**
2. **Implementation**
3. **Review feedback** — and how each item was resolved
4. **Final optimized version** — with before/after measurements
