---
name: debugging
description: Systematically find root causes of bugs, failing tests, crashes, flakiness, or production incidents. Use whenever behavior differs from expectation.
---
# Systematic Debugging

1. **Reproduce** reliably; get the exact error, stack trace, inputs, env, version. Minimize the repro.
2. **Observe, don't guess** — read the actual code path and logs. Add instrumentation if needed.
3. **Hypothesize** — list candidate causes ranked by likelihood × cheapness to test.
4. **Test one hypothesis at a time**; change one variable. Use bisection (git bisect, input halving, commenting out) when the space is large.
5. **Find root cause**, not the symptom: ask "why" until you reach the design/assumption that failed.
6. **Fix** with a regression test that fails before and passes after.
7. **Generalize** — search the codebase for the same bug pattern; fix or flag siblings.
8. **Explain** — state cause, fix, why it's correct, and what prevents recurrence.

## Heuristics
- Recently changed code is the prime suspect (`git log -p`, `git diff`).
- Check assumptions: is the code you're reading the code that runs? (build cache, version, config, env vars)
- Off-by-one, null/undefined, timezone, encoding, floating point, race conditions, caching, stale state — classic culprits.
- Flaky = hidden nondeterminism (time, order, shared state, network). Never "fix" with retries/sleeps alone.
- Never suppress errors (empty catch, `|| true`) to make symptoms disappear.

## Required output
1. **What the code does** — intended behavior
2. **What the problem is** — observed vs. expected
3. **Why it fails** — root cause with evidence
4. **Edge cases** — related inputs/states that also break, or could
5. **Fixed production-ready code** — with a regression test
