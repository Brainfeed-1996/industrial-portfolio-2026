# ADR 005: Distributed Tracing with OpenTelemetry

## Status
Proposed

## Context
As the security mesh grows, debugging the lifecycle of a request across the Identity Service, Policy Engine, and Edge Agents becomes complex. We need a way to correlate logs and performance data across service boundaries.

## Decision
Adopt OpenTelemetry (OTel) for distributed tracing.
- Every SVID-authenticated request will carry a `traceparent` header.
- The Identity Service will start a span for every token issuance.
- The Policy Engine and Edge Agents will inject/extract context to maintain trace continuity.
- Use Jaeger or Tempo as the backend for trace visualization.

## Consequences
- Slight overhead in request latency due to span propagation.
- Improved Mean Time To Recovery (MTTR) during multi-service outages.
- Unified observability dashboard combining metrics (Prometheus) and traces (Jaeger).
