---
name: refactoring
description: Improve code structure without changing behavior — reduce complexity, remove duplication, clarify naming, untangle modules. Use when code is hard to change or understand.
---
# Refactoring

1. Ensure behavior is pinned by tests (add characterization tests if missing).
2. Identify the smell: long function, large class, duplication, feature envy, primitive obsession, long parameter list, shotgun surgery, divergent change, deep nesting.
3. Apply small named refactorings (Extract Function, Inline, Rename, Introduce Parameter Object, Replace Conditional with Polymorphism, Guard Clauses, Move Function, Split Phase).
4. Run tests after each step; commit in small steps. Never mix refactoring and behavior change in one commit.
5. Stop when the code is clear enough for the next change — not "perfect".

Rules: Rule of three before abstracting duplication. Prefer deleting code. Keep public APIs stable or deprecate deliberately. Large rewrites → strangler fig, not big bang.
