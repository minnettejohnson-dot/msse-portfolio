---
layout: decision-record
title: "Portfolio Decision Record"
subtitle: "Golden Bike Shop System"
record_id: "MSSE601-ADR-hybrid-architecture"
course_short: "MSSE-601 · Software Engineering Foundations"
author: "Minnette Johnson"
course_term: "MSSE 601 – Software Engineering Fundamentals | Fall 2026"
week_owned: "Week 5 – Application Architecture; Team Decision Record and AI-use/rubric synthesis"
team: "SEF 1 – NCM Innovators"
description: "Minnette Johnson's Week 5 architecture decision record for the Golden Bike Shop System, documenting the hybrid modular architecture decision, its reasoning, and trade-offs."
permalink: /msse601/MSSE601-ADR-hybrid-architecture/
---

## 1. Context

The Golden Bike Shop System must give four stores a consistent view of inventory and operations, prevent conflicting rental reservations and service-bay assignments, and ensure e-bike telemetry older than 15 minutes is not treated as current. Core retail and booking workflows need transactional consistency, while telemetry has a distinct ingestion workload and freshness rule.

As Week 5 deliverable owner and owner of Section 7, I was responsible for making the team’s core architecture decision, alternatives, rationale, and trade-offs explicit in the Team Decision Record.

## 2. Options

### Option A — A single monolithic application

Put all business capabilities, including telemetry processing, into one deployable application. This would be straightforward to deploy, but telemetry workload and failures would share the same deployment boundary as core transactions.

### Option B — Full microservices

Deploy retail, service booking, identity, and telemetry as separate services. This would allow independent deployment and scaling, but would introduce more service-to-service communication and distributed coordination for workflows that depend on consistent cross-store data and concurrency controls.

### Option C — Hybrid architecture

Keep Retail, Service Booking, and Identity/Authorization in a modular monolith, and deploy the Telemetry Service independently. This retains a single transactional boundary for the tightly coupled core while isolating telemetry because its workload and failure profile differ.

## 3. Decision

The team selected Option C: a Spring Boot modular monolith for the core business domains, with an independently deployed Telemetry Service. The BFF/API remains a logical layer inside the core deployment initially. This decision is recorded in Week 5, Section 7.2, “Decision 1 – Core System Architecture.”

## 4. Reasoning

The hybrid architecture best matched the stated requirements. Centralized data and a shared core support a consistent four-store view (NFR-01), while keeping rental and workshop transactions together supports the integrity controls needed to prevent conflicting bookings (NFR-02). Telemetry is separate because its ingestion workload, 15-minute freshness rule, and failure behavior differ from core operations (NFR-03).

Full microservices would add distributed complexity before every domain needed independent deployment; a single monolith would not isolate telemetry’s distinct workload and failure profile.

## 5. Consequences

The main cost is deployment coupling: a Retail or Service Booking change may require the core application to be tested and deployed as a whole. The independent Telemetry Service also adds messaging, snapshot maintenance, recovery, and explicit freshness enforcement.

Because a snapshot can lag behind a device, stale or unverified bikes must be excluded from rental availability. The team accepted these costs in favor of core consistency and targeted telemetry isolation. I would revisit the choice if the core modules needed different release schedules or scaling, or if evidence showed that shared deployment limited reliability or delivery. Clear module boundaries preserve the option of later extraction.

## 6. Evidence and authorship

**Week owned and deliverable:** Week 5 – Application Architecture; Section 9.1 identifies Minnette Johnson as deliverable owner.

**Pointer in deliverable:** Section 7.2, “Decision 1 – Core System Architecture”; Section 8.4, “Team Decision Record and Rubric Synthesis.”

**AI use:** Gemini helped me review the compiled Week 5 draft against the rubric and identified that decisions and trade-offs were blended into general discussion. I accepted the structural suggestion and organized them into Section 7 without changing the team’s underlying engineering decisions.

[← Back to the portfolio]({{ '/' | relative_url }}#portfolio)
