---
name: clean-architecture
description: Restructure existing code into clean/hexagonal architecture — separate concerns, increase modularity, reduce coupling, with behavior unchanged. Use when code mixes business logic with frameworks, DB, or UI, or when asked for clean architecture.
---
# Clean Architecture Rebuild

## Target layers (dependencies point inward only)
- **Domain** — entities, value objects, business rules. Pure; no framework, DB, or HTTP imports.
- **Application** — use cases orchestrating domain logic; defines *ports* (interfaces) for what it needs (repositories, gateways, clock).
- **Adapters** — controllers/handlers, presenters, DB repositories, external API clients implementing ports.
- **Infrastructure / composition root** — framework wiring, DI, config, main.

## Process
1. Write characterization tests around current behavior.
2. Identify business rules hidden in controllers, ORM models, or UI; extract them into domain/use cases.
3. Introduce ports at I/O boundaries; move concrete implementations to adapters.
4. Wire everything in one composition root.
5. Migrate incrementally (strangler fig), keeping tests green after each step.

## Pragmatism
Organize by feature first (`orders/`, `billing/`), layers inside each. Don't add interfaces with a single trivial implementation and no testing need. Small apps need fewer layers — match ceremony to complexity.

## Required output
1. **New folder structure** — tree
2. **Architecture description** — layers, dependency rule, how a use case flows
3. **Refactored code** — behavior unchanged, verified by tests
