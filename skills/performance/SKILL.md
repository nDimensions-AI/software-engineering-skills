---
name: performance
description: Diagnose and improve latency, throughput, memory, or cost. Use when something is slow or before scaling.
---
# Performance Engineering
1. Define the target (p50/p95/p99 latency, throughput, memory, cost) and the workload.
2. **Measure first** — profile (CPU, memory, I/O, flame graphs, query plans). Never optimize by guess.
3. Fix the biggest bottleneck only (Amdahl). Usual order: algorithm/complexity → I/O & queries (N+1, indexes, batching) → caching → concurrency → micro-optimizations.
4. Re-measure; keep a benchmark/regression test. Document the trade-off (complexity, staleness, memory).
Caching: define key, TTL, invalidation, and stampede protection up front.

## Look for
Bottlenecks, inefficient logic (wrong data structure, O(n²) loops, repeated computation), unnecessary rendering in UIs (unstable props/callbacks, oversized state, missing virtualization), memory leaks and excess allocations, scalability limits (single points of contention, unbounded growth).

## Required output
1. **Performance issues** — ranked by measured impact
2. **Optimization strategies** — with trade-offs
3. **Improved code** — plus before/after measurements
