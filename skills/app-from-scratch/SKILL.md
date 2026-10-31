---
name: app-from-scratch
description: Build a complete, production-ready application or MVP from scratch, or design a scalable system and implement its minimal production version. Use for "build me an app", new products, greenfield services, or system design + implementation requests.
---
# Application / System from Scratch

Think like a senior full-stack engineer and systems architect at a startup: ship a minimal MVP whose design scales without a rewrite.

## Process
1. **Frame** — users, core job-to-be-done, the 3–5 must-have features for v1, explicit non-goals, expected load (users, QPS, data growth).
2. **Design** (apply `architecture-design`): pick the simplest architecture that meets constraints — usually a modular monolith with clear domain modules, one relational DB, a stateless app tier that scales horizontally.
3. **Data first** — model entities, relationships, constraints, indexes; migrations from day one.
4. **API contract** (apply `api-design`) before the UI.
5. **UI architecture** (apply `frontend-ui-ux`): routes/screens, component tree, state strategy.
6. **Implement as a walking skeleton**: one thin vertical slice end-to-end, then add features slice by slice with tests (`tdd`).
7. **Production readiness**: config via env, input validation, auth, error handling, structured logging, health check, seed data, Dockerfile/CI, README with run steps.
8. **Run it** and verify the main user journeys work.

## Required output
1. **Architecture** — mermaid diagram + component responsibilities + key decisions & trade-offs
2. **Component structure & data flow** — how a request/action travels through the system
3. **File structure** — full tree
4. **Database schema** — tables/collections, fields, types, keys, indexes (SQL DDL or ORM schema)
5. **API endpoints** — method, path, request/response, errors, auth
6. **Caching strategy** — what, where (HTTP/CDN/app/DB), keys, TTL, invalidation; or why none yet
7. **UI architecture** — screens, components, state management
8. **Complete working code** — no placeholders or `TODO: implement`
9. **Scaling path** — what changes at 10× and 100× load (read replicas, queues, cache, splitting modules into services)
