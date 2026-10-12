---
layout: decision-record
title: "Hybrid Modular Architecture Decision"
subtitle: "Golden Bike Shop System"
record_id: "MSSE601-ADR-hybrid-architecture"
course_short: "MSSE-601 · Software Engineering Foundations"
author: "Minnette Johnson"
course_term: "MSSE 601 – Software Engineering Fundamentals | Fall 2026"
week_owned: "Week 5 – Application Architecture; Team Decision Record and AI-use/rubric synthesis"
team: "SEF 1 – NCM Innovators"
decision_status: "Selected"
decision_summary: "Keep Retail, Service Booking, and Identity/Authorization in one Spring Boot modular monolith, and deploy the Telemetry Service independently."
description: "Minnette Johnson's Week 5 architecture decision record for the Golden Bike Shop System, documenting the hybrid modular architecture, rationale, alternatives, and trade-offs."
permalink: /msse601/MSSE601-ADR-hybrid-architecture/
---

## 1. Context and constraints

The Golden Bike Shop System must give four stores a consistent view of inventory and operations, prevent conflicting rental reservations and service-bay assignments, and ensure e-bike telemetry older than 15 minutes is not treated as current. Core retail and booking workflows need transactional consistency, while telemetry has a distinct ingestion workload and freshness rule.

As Week 5 deliverable owner and owner of Section 7, I was responsible for making the team's core architecture decision, alternatives, rationale, and trade-offs explicit in the Team Decision Record. This portfolio entry records the selected approach and the reasoning behind it.

## 2. Options considered

| Option | Proposed approach | Main advantage | Main trade-off |
|---|---|---|---|
| **A. Single monolith** | Put all business capabilities, including telemetry processing, in one deployable application. | Straightforward deployment and a single application boundary. | Telemetry workload and failures share the core application's deployment and scaling boundary. |
| **B. Full microservices** | Deploy Retail, Service Booking, Identity/Authorization, and Telemetry as separate services. | Each service can be deployed and scaled independently. | Adds service-to-service communication and distributed coordination for workflows requiring cross-store consistency and concurrency controls. |
| **C. Hybrid architecture — selected** | Keep Retail, Service Booking, and Identity/Authorization in a modular monolith; deploy Telemetry independently. | Preserves a shared transactional boundary for tightly coupled workflows while isolating telemetry's distinct workload. | The core remains deployed as a unit, and telemetry adds its own operational and freshness-management responsibilities. |

## 3. Decision

The team selected **Option C: a Spring Boot modular monolith for the core business domains, with an independently deployed Telemetry Service**. The BFF/API remains a logical layer inside the core deployment initially.

This decision is recorded in Week 5, Section 7.2, “Decision 1 – Core System Architecture.” The aim is not to split every capability into a separate service; it is to keep the closely related transactions together while giving telemetry a separate deployment boundary because its workload and freshness requirements differ.

## 4. Why this fits the requirements

- **NFR-01 — Consistent view across four stores:** Centralized core data and a shared application boundary support a consistent view of inventory and operations.
- **NFR-02 — Booking integrity:** Keeping rental and workshop workflows within the core supports the transaction and concurrency controls needed to prevent conflicting reservations and service-bay assignments.
- **NFR-03 — Telemetry freshness:** Separating telemetry allows its ingestion workload and failure behavior to be handled apart from core retail and booking transactions. The system must not treat telemetry older than 15 minutes as current.

Full microservices would create distributed coordination costs before every domain has a demonstrated need for independent deployment. A single monolith would be simpler to deploy, but would not isolate telemetry's distinct workload and failure profile. The hybrid option is the best fit for the requirements as they are currently understood.

## 5. Consequences and trade-offs

### What this approach gives us

- Core retail, service-booking, and identity capabilities can share a transactional boundary where consistency matters.
- Telemetry can be operated and scaled separately from the core application.
- Clear module boundaries preserve the option of extracting a core module later if evidence supports doing so.

### What it costs us

- Deployment remains coupled within the core: a Retail or Service Booking change may require the core application to be tested and deployed as a whole.
- The independent Telemetry Service adds messaging, snapshot maintenance, recovery, and explicit freshness enforcement.
- Because a snapshot can lag behind a device, stale or unverified bikes must be excluded from rental availability rather than presented as available based on outdated data.

The team accepted these costs in favor of core consistency and targeted isolation for telemetry.

## 6. When I would revisit the decision

I would revisit this architecture if the core modules needed different release schedules or scaling profiles, or if evidence showed that shared deployment was limiting reliability or delivery. Until then, a modular core keeps the system comparatively straightforward while preserving a path to evolve the architecture when the need is demonstrated.

## 7. Evidence and authorship

**Week owned and deliverable:** Week 5 – Application Architecture. Section 9.1 identifies Minnette Johnson as deliverable owner.

**Pointer in the team deliverable:** Section 7.2, “Decision 1 – Core System Architecture”; Section 8.4, “Team Decision Record and Rubric Synthesis.”

**My contribution:** I was responsible for making the architecture decision, alternatives, rationale, and trade-offs explicit in the Team Decision Record, so the decision could be understood and reviewed rather than left inside general discussion.

**AI use:** Gemini helped me review the compiled Week 5 draft against the rubric and identified that decisions and trade-offs were blended into general discussion. I accepted the structural suggestion and organized them into Section 7 without changing the team's underlying engineering decisions.

[← Back to my portfolio]({{ '/' | relative_url }}#portfolio)
