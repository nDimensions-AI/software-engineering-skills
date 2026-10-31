---
name: tdd
description: Implement features or fix bugs test-first. Use for any new behavior, bug fix, or when code lacks tests.
---
# Test-Driven Development

## Loop
1. **Red** — write the smallest failing test describing one behavior. Run it; confirm it fails for the *right* reason.
2. **Green** — write the minimum code to pass. No extra features.
3. **Refactor** — clean code and tests with all tests green. Commit.
Repeat. For bugs: first write a test that reproduces the bug.

## Good tests
- Test behavior through public interfaces, not implementation details. Refactors shouldn't break tests.
- One reason to fail per test; name = spec: `returns_empty_list_when_no_orders`.
- Arrange / Act / Assert, visibly separated. No logic (loops/ifs) in tests.
- Deterministic: control time, randomness, network, ordering. No sleeps.
- Fast: unit tests in ms. Fake I/O at boundaries; prefer fakes over deep mocks; never mock what you don't own — wrap it.
- Cover: happy path, edges (empty, one, many, max, unicode, negative, null), errors, concurrency where relevant.
- Pyramid: many unit, some integration (real DB/containers), few E2E on critical journeys.
- Consider property-based tests for parsers, serializers, math, invariants.

## Rules
- Never delete or weaken a failing test to go green. Never claim tests pass without running them.
- Run the full relevant suite before declaring done; report actual output.
