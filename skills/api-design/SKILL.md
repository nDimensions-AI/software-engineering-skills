---
name: api-design
description: Design or review HTTP/REST, GraphQL, gRPC, library, or CLI interfaces. Use when creating or changing any interface others consume.
---
# API Design

- Start from consumer use cases; write example calls before implementation.
- Consistent naming (resources as plural nouns, verbs via HTTP methods), consistent casing, consistent pagination (cursor-based), filtering, sorting.
- Correct semantics: GET safe, PUT/DELETE idempotent, POST with Idempotency-Key for retries. Correct status codes.
- Errors: machine-readable code + human message + details (RFC 9457 problem+json). Never leak internals.
- Validate at the boundary; strict input, stable output. Explicit schemas (OpenAPI/protobuf) as source of truth.
- Versioning & evolution: additive changes only; never repurpose fields; deprecate with timeline.
- Security: authn on all, authz per resource, rate limits, least data returned.
- Performance: avoid chatty APIs; support batch & field selection where useful; set timeouts; ETags/caching.
- Libraries: small surface, hard to misuse, sensible defaults, immutable value types, no boolean trap params.
- CLIs: `--help`, exit codes, stdout for data / stderr for logs, `--json` output, non-interactive mode.
