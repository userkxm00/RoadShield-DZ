# RoadShield DZ — Gate 2 Architecture Preparation

## Status
Preparation only. Gate 2 is blocked until Gate 1 passes.

## Objective
Define the decisions that must be finalized once research and feasibility evidence are accepted, without prematurely locking implementation choices.

## Architecture principles
- Evidence-backed requirements drive architecture.
- Prefer a small, testable vertical slice before distributed complexity.
- Keep deterministic sensing/domain logic independent from infrastructure.
- Treat geospatial data as a first-class concern.
- Version event schemas and detection/scoring logic.
- Keep paid AI/API services out of the MVP core.
- Preserve a migration path from replay/test harness to real mobile capture.
- Minimize collection and retention of raw mobility data.

## Target logical architecture

```text
Mobile capture / replay
        |
        v
Sensor normalization
        |
        v
Candidate event detector
        |
        v
Versioned event contract
        |
        v
Ingestion boundary
        |
  +-----+------+
  |            |
  v            v
Event store  Corroboration / condition engine
  |            |
  +-----+------+
        v
Operator/query API
        |
        v
Dashboard + risk/condition map
```

## Decision areas to finalize at G2

### Mobile
- Framework/runtime.
- Android sensor APIs.
- Background execution model.
- Permission flow.
- Local persistence/buffering.
- Replay/debug tooling.

### Backend
- Runtime/framework.
- API style and versioning.
- Ingestion idempotency strategy.
- Authentication/authorization boundaries.
- Observability and audit requirements.

### Data
- PostgreSQL/PostGIS or validated alternative.
- Event schema.
- Geospatial precision and coordinate reference assumptions.
- Retention and aggregation rules.
- Pseudonymous identifiers.

### Domain
- Event taxonomy.
- Candidate-event semantics.
- Corroboration window and spatial tolerance.
- Evidence-quality model.
- Road-condition state machine.
- Versioning strategy for detector and confidence model.

### Dashboard
- Mapping library.
- Event detail model.
- Evidence timeline.
- Explainable confidence factors.

### Security/privacy
- Threat model.
- Consent model.
- Secret management.
- Rate limiting.
- Audit events.
- Data minimization.

## Required G2 artifacts
- Architecture decision record set.
- C4/context and container diagrams as useful.
- Domain model.
- Event schema.
- API contracts.
- Data retention specification.
- Threat model.
- Privacy model.
- Dependency decision register.
- Test and replay strategy.
- Local development instructions.

## Gate rule
No production architecture implementation is authorized by this document. Gate 2 opens only after the Research & Innovation Gate records a PASS/PROCEED decision.