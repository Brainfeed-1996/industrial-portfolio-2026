# Industrial SRE & Telemetry

## Overview
In high-stakes industrial environments, uptime and security visibility are non-negotiable. This document outlines how the integrated telemetry stack enables Service Reliability Engineering (SRE) for our Zero-Trust and AI-driven security ecosystem.

## Key Pillars of Industrial Observability

### 1. Metric-Driven Reliability
We treat security events as operational metrics.
- **Identity Health**: Monitoring SVID issuance and revocation rates allows us to detect identity-based attacks or credential stuffing in real-time.
- **Inference Performance**: By tracking C++ engine latency at the edge, we ensure that AI-based intrusion detection doesn't become a bottleneck for industrial PLC/SCADA traffic.

### 2. Zero-Trust Mesh Health
The health of the mesh is monitored through the `industrial-ops-telemetry` hub.
- **Prometheus** scrapes metrics from all microservices.
- **Grafana** provides a "Single Pane of Glass" for both security teams and SREs.

### 3. Distributed Tracing for Root Cause Analysis (RCA)
Per our [ADR-005](./adr/005-distributed-tracing.md), we are moving towards an OpenTelemetry-based tracing strategy. This allows us to follow a single industrial command as it:
1. Requests an identity token.
2. Passes through the AI intrusion detection check.
3. Is verified by the security mesh policy engine.

## Telemetry-Enabled SRE Practices

- **Golden Signals**: We track Latency, Traffic, Errors, and Saturation across the mesh.
- **Alerting**: Automated alerts are triggered when SVID revocation spikes or AI inference latency exceeds the 99th percentile threshold.
- **Post-Mortems**: Telemetry data provides the evidence needed for blameless post-mortems after security incidents or system failures.
