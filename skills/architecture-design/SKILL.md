---
name: architecture-design
description: Design or change system architecture — new services, modules, data models, boundaries, scaling plans. Use before writing significant new code or when a change crosses module boundaries.
---
# Architecture & Design Thinking

## Process (do in order, write each down)
1. **Problem framing** — Who is the user, what job are they hiring this for, what does success look like (measurable)? State non-goals explicitly.
2. **Constraints** — load (QPS, data size, growth), latency/availability SLOs, consistency needs, budget, team skills, existing systems. Unknown? Ask or state the assumption.
3. **≥2 options** — sketch at least two genuinely different designs (incl. "do the simplest thing"). Compare on: complexity, failure modes, cost, reversibility, time to ship.
4. **Decide** — pick the simplest option that meets constraints. Record an ADR: context, decision, alternatives, consequences.
5. **Slice** — break into independently shippable, testable increments; first slice is end-to-end ("walking skeleton").

## Principles
- Optimize for change: high cohesion, low coupling, explicit interfaces. Depend on abstractions at boundaries only, not everywhere.
- Deep modules: simple interface, rich hidden implementation. Avoid shallow pass-through layers.
- Make illegal states unrepresentable (types, enums, value objects, validation at the edge).
- Functional core, imperative shell: pure business logic; I/O at the edges.
- Prefer boring tech. Each new dependency/infra piece must justify its operational cost.
- Reversible decisions fast; irreversible ones (data schema, public API, storage engine) slow and documented.
- Design for failure: timeouts, retries with backoff + jitter, idempotency keys, bounded queues, graceful degradation.
- Observability is part of the design: logs (structured), metrics (RED/USE), traces at boundaries.

## Patterns — use when the force exists, never pre-emptively
| Force | Pattern |
|---|---|
| Swap algorithms/providers | Strategy / ports & adapters |
| Complex object creation | Factory / builder |
| React to events, decouple producers | Observer / pub-sub / outbox |
| Wrap legacy/3rd-party API | Adapter / anti-corruption layer |
| Cross-cutting concerns | Decorator / middleware |
| Long-running multi-step workflows | Saga / state machine |
| Read/write scale asymmetry | CQRS (only if truly needed) |

## Anti-patterns to flag
Distributed monolith, shared mutable DB across services, premature microservices, god objects, speculative generality, config-driven everything, leaky abstractions.

## Output
Short design doc: problem, constraints, options table, decision + rationale, diagram (mermaid), data model, API sketch, risks, rollout & rollback plan, slice plan.
