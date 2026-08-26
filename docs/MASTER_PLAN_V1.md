# RoadShield DZ — Master Plan v1

**Status:** Planning baseline
**Owner:** Karim Midoun
**Execution model:** Product/architecture decisions are human-controlled; Codex is implementation-only.
**Primary objective:** Build, validate, document, and present RoadShield DZ as an evidence-based innovative project suitable for the Algerian Label Projet Innovant and, if the label is obtained in time, the Best Innovative Project competition.

---

## 0. Operating Principles

1. **Evidence before expansion.** We validate the core hypothesis before building a large product surface.
2. **Gates before progression.** A stage is not complete because code exists; it is complete only when its acceptance evidence exists and review passes.
3. **Codex executes; humans decide.** Product scope, architecture, security posture, safety claims, competition positioning, and acceptance criteria require human approval.
4. **No paid AI dependency in the MVP core.** AI may be added later, but the core validation loop must work without a paid model API.
5. **Safety over novelty theatre.** We must never add AI merely to make the project look innovative.
6. **No unsupported claims.** We will not claim to predict accidents, guarantee safety, or be the first system to detect road hazards.
7. **Privacy by design.** Minimize collection, retain only what is necessary, anonymize where practical, and never publish raw personal mobility traces.
8. **Competition evidence is designed in.** Every important feature should produce evidence useful for the Label, pitch, demo, or impact case.
9. **Small reversible changes.** Each implementation task must be bounded, testable, and reviewable.

---

# Phase 0 — Project Foundation

## Purpose
Create the project constitution, repository structure, engineering rules, product baseline, and Gate system before production implementation.

## Required deliverables

- `README.md`
- `PROJECT_CONSTITUTION.md`
- `CODEX.md`
- `ROADMAP.md`
- Vision
- Problem Statement
- Goals / Non-goals
- Product Requirements
- Architecture baseline
- Security rules
- Coding standards
- Testing strategy
- Definition of Done
- Decision Log / ADR process
- Git workflow
- Competition/Label plan
- Gate registry

## Foundation repository structure

```text
RoadShield-DZ/
├── docs/
│   ├── vision/
│   ├── research/
│   ├── product/
│   ├── architecture/
│   ├── engineering/
│   ├── testing/
│   ├── security/
│   ├── competition/
│   └── decisions/
├── apps/
│   ├── mobile/
│   └── dashboard/
├── services/
│   ├── api/
│   ├── ingestion/
│   └── risk-engine/
├── packages/
│   ├── contracts/
│   ├── domain/
│   └── shared/
├── tests/
│   ├── fixtures/
│   ├── replay/
│   └── integration/
├── scripts/
├── .github/
│   ├── workflows/
│   ├── ISSUE_TEMPLATE/
│   └── pull_request_template.md
├── PROJECT_CONSTITUTION.md
├── README.md
├── CODEX.md
├── ROADMAP.md
└── SECURITY.md
```

## Foundation Gate

### Required evidence
- Repository structure exists.
- Rules are written and internally consistent.
- Product boundaries are explicit.
- No production feature work has started prematurely.
- CI/test strategy is defined.
- Git/PR workflow is documented.
- Gate registry exists.

### Verification
`repository state → document consistency → file inventory → workflow sanity check`

**Gate result:** PASS / FAIL

---

# Phase 1 — Research & Innovation Validation

## Purpose
Prove that the problem is real, the proposed solution is differentiated enough to justify further work, and the MVP hypothesis is technically testable.

## Core problem hypothesis

> Road users and road operators lack a low-friction, privacy-conscious mechanism that turns repeated road-condition signals collected during ordinary trips into corroborated, geospatially precise, explainable road-condition evidence that can support preventive action.

The core MVP is intentionally narrower:

> **Detect candidate road-hazard events from smartphone motion/location signals, geolocate them, and corroborate repeated observations into a confidence-bearing road-condition event.**

## Research tracks

### 1.1 Market and problem evidence
- Road safety burden in Algeria.
- Road-condition reporting pain points.
- Driver/fleet/operator workflows.
- Existing citizen-reporting behavior.
- Existing maintenance response workflows.

### 1.2 Competitive landscape
Explicit comparison against:
- Waze
- Google Maps
- Waze for Cities / partner feeds
- Waymo/Waze automated road-hazard data where relevant
- Algerian SNAR and related government systems
- Relevant pothole/road-condition research and products

### 1.3 Innovation analysis
We do **not** claim that hazard detection itself is new.

Our innovation hypothesis is the combination of:
- passive smartphone sensing;
- geospatial event representation;
- repeated-trip corroboration;
- evidence quality and confidence tracking;
- temporal state of a road condition;
- privacy-aware data minimization;
- a future operational layer for road operators.

Each element must be supported by evidence before being promoted to a competition claim.

### 1.4 IP hypothesis
Investigate whether protectable value may exist in:
- event fusion/orchestration;
- corroboration methodology;
- confidence/evidence model;
- temporal road-condition state model;
- privacy-preserving road-condition intelligence workflow.

No patentability claim is made without a dedicated prior-art review.

### 1.5 MVP feasibility
Validate:
- GPS quality;
- accelerometer signal quality;
- phone-placement sensitivity;
- vehicle variability;
- speed variability;
- repeatability across passes;
- false positives/false negatives;
- localization error;
- battery/data cost.

## Phase 1 Gate

### Acceptance evidence
- Research source register.
- Competitor matrix.
- Differentiation statement.
- Innovation hypothesis.
- IP hypothesis and limitations.
- MVP boundary.
- Controlled field-validation protocol.
- Feasibility/research decision: continue, narrow, or revise.

### Verification
`source audit → competitor review → hypothesis review → field evidence review`

**Gate result:** PASS / FAIL / REVISE

---

# Phase 2 — Architecture & Technical Specification

## Purpose
Choose the technology and define all contracts before large-scale Codex implementation begins.

## Target MVP architecture

```text
Mobile App
   │
   ├── GPS
   ├── Accelerometer
   ├── Camera (optional/phase-gated)
   └── Local Event Detection
            │
            ▼
      Ingestion API
            │
      ┌─────┴─────┐
      ▼           ▼
 Database      Risk Engine
 (PostgreSQL)  / Corroboration
      │           │
      └─────┬─────┘
            ▼
        Web Dashboard
            │
            ▼
       Risk / Condition Map
```

## Architecture decisions to finalize

- Mobile framework.
- Backend framework/runtime.
- Database and geospatial extension.
- Event/telemetry schema.
- API contract versioning.
- Local buffering/replay strategy.
- Corroboration engine boundaries.
- Risk/confidence algorithm versioning.
- Dashboard mapping stack.
- Authentication/authorization strategy for later phases.
- Observability and audit design.

## Phase 2 Gate

### Required evidence
- Architecture document.
- C4-level diagrams where useful.
- Data model.
- API contracts.
- Event taxonomy.
- Threat model.
- Privacy model.
- Test strategy and fixture strategy.
- Dependency decisions.
- ADRs for major decisions.

**Gate result:** PASS / FAIL

---

# Phase 3 — MVP Implementation

Codex works in bounded increments. Each increment is a separate task/PR and must pass tests before merge.

## MVP-01 — Sensor Capture

### Scope
- GPS capture.
- Accelerometer capture.
- Permissions.
- Local buffering.
- Sensor-health reporting.

### Evidence
- Unit tests.
- Device/manual test.
- Sanitized sample dataset.

## MVP-02 — Candidate Event Detection

### Scope
- Deterministic motion signal normalization.
- Candidate-event detector.
- Detector version identifier.

### Evidence
- Fixtures.
- Replay test.
- Expected outputs.

## MVP-03 — Geospatial Event Binding

### Scope
- Event coordinates.
- Timestamp.
- Accuracy metadata.
- Basic map representation.

### Evidence
- Geolocation tests.
- Invalid-coordinate tests.

## MVP-04 — Backend + Database

### Scope
- Ingestion endpoint.
- Idempotency.
- Persistence.
- Schema migrations.
- Retention controls.

### Evidence
- Integration tests.
- Migration verification.
- Security tests.

## MVP-05 — Risk/Condition Map

### Scope
- Candidate events displayed.
- Basic geospatial clustering.
- Event state.

### Evidence
- Map demo.
- Deterministic dataset replay.

## MVP-06 — Multi-Observation Corroboration

### Scope
- Multiple observations at the same area.
- Duplicate/repeat filtering.
- Evidence aggregation.

### Evidence
- Corroboration fixtures.
- Precision/recall-oriented measurements where meaningful.

## MVP-07 — Confidence / Risk Score

### Scope
- Explainable scoring model.
- Versioned score logic.
- Evidence factors shown to operator.

### Evidence
- Score fixture set.
- Explainability checks.

## MVP-08 — Dashboard

### Scope
- Overview.
- Map.
- Event details.
- Evidence timeline.
- Confidence factors.

### Evidence
- Demo workflow.
- Accessibility/basic UX review.
- Dashboard integration tests.

## MVP Gate Rule

Every MVP increment follows:

`Implement → Test → Review → Evidence → PR → Merge → Main verification`

No skipping ahead because a later feature looks more exciting.

---

# Phase 4 — Intelligence Layer

Only after the deterministic core is stable.

## Sensor Fusion

```text
Camera signal (optional)
+
GPS
+
Accelerometer
+
Speed
+
Repeated observations
+
Road context
=
Evidence-backed Hazard Confidence
```

## AI policy

- No mandatory paid AI API.
- Prefer on-device/open models where they are technically appropriate.
- AI must improve a measurable capability.
- Every AI component requires a baseline comparison against a non-AI method.
- Model/version/data assumptions must be documented.
- Safety wording must remain conservative.

## Phase 4 Gate

- Quantified improvement versus baseline.
- Model/version documentation.
- Resource/battery impact.
- Privacy review.
- Reproducibility evidence.

---

# Phase 5 — Safety, Privacy & Security Hardening

## Safety
- RoadShield is an assistive system.
- It never guarantees accident prevention.
- It must not instruct a driver to interact with the phone while driving.
- Alerts must be designed around low distraction.

## Privacy
- Data minimization.
- Consent.
- Anonymous/pseudonymous telemetry where feasible.
- No unnecessary raw location history.
- Retention limits.
- Sanitized datasets for public/demo use.

## Security
- AuthN/AuthZ separation.
- Strict input validation.
- Rate limiting.
- Idempotent ingestion.
- Audit logging.
- Secure secrets handling.
- Dependency/security scanning.
- Secure defaults.

## Phase 5 Gate

- Threat model reviewed.
- Privacy review completed.
- Security tests pass.
- Safety copy/UX reviewed.
- No known critical security issues.

---

# Phase 6 — Real-World Validation

## Experiment design

### Route A
Repeated passes on a controlled route.

### Route B
Second route with different conditions.

### Ground truth
Manually annotated, independently of detector output.

### Collected metadata
- route identifier;
- date/time;
- vehicle type;
- phone model;
- phone placement;
- speed band;
- detector version;
- event location;
- manually observed road condition.

## Measurements
- repeatability;
- localization error;
- false positives;
- false negatives where measurable;
- battery consumption;
- data volume;
- performance under different speeds/vehicles/placements.

## Phase 6 Gate

- Sanitized dataset.
- Experiment log.
- Metrics.
- Limitations.
- Decision: validated / narrow / revise.

No competition claim may use an unverified metric.

---

# Phase 7 — Competition & Label Package

## Label Projet Innovant package

Prepare the assets required by the official workflow, including where applicable:
- project name;
- sector/activity;
- short project description;
- pitch deck;
- detailed innovation presentation;
- prototype evidence/photo;
- progress level;
- business model;
- website/demo URL when available;
- incubation status if applicable;
- IP information if applicable;
- competition/award history if applicable.

## Competition package

- Pitch Deck.
- One-pager.
- Product demo.
- Demo script.
- Problem evidence.
- Market analysis.
- Competition matrix.
- Innovation statement.
- Technical architecture overview.
- Impact metrics.
- Business model.
- Go-to-market plan.
- Roadmap.
- Founder CV.
- Prototype screenshots/photos.
- Evidence appendix.

## Competition Gate

### Final verification
- All claims trace to evidence.
- No unsupported AI/innovation claims.
- Demo works offline where intended.
- No secrets in repository.
- Website/demo links work.
- Label materials are internally consistent with the product.
- Final GitHub state matches the submitted prototype.

**Final outcome:** Ready / Not ready

---

# Cross-Phase Definition of Done

A task is Done only when:

1. Requirements are explicit.
2. Implementation exists and is bounded to scope.
3. Automated tests cover critical behavior.
4. Relevant lint/type/build checks pass.
5. Security/privacy implications are reviewed.
6. Documentation is updated when behavior or architecture changes.
7. Evidence/artifact is attached or reproducible.
8. PR review is complete.
9. The change is merged intentionally.
10. `main` is verified after merge.

---

# Codex Execution Contract

Codex must:

- read the current repository rules before acting;
- never expand scope without an approved requirement;
- never make architecture decisions unilaterally;
- never skip tests to move faster;
- never introduce paid AI services into the MVP core without explicit approval;
- never invent metrics, research findings, user validation, or competition claims;
- produce a concise implementation report after each task;
- identify blockers instead of silently changing product scope.

Codex may propose alternatives, but proposals require human approval before they become project decisions.

---

# Git Workflow

```text
Issue
  ↓
Feature/Research branch
  ↓
Small implementation
  ↓
Tests / static checks
  ↓
PR
  ↓
Review
  ↓
Merge
  ↓
Verify origin/main
  ↓
Close issue / record evidence
```

Recommended branch prefixes:
- `research/*`
- `docs/*`
- `feat/*`
- `fix/*`
- `test/*`
- `security/*`
- `chore/*`

---

# Gate Registry

| Gate | Name | Status at plan creation |
|---|---|---|
| G0 | Repository Foundation | In progress / verify final consistency |
| G1 | Research & Innovation | In progress |
| G2 | Technical Architecture | Blocked by G1 |
| G3 | MVP Core | Blocked by G2 |
| G4 | Intelligence | Blocked by G3 |
| G5 | Safety / Privacy / Security | Blocked by MVP baseline, then continuous |
| G6 | Field Validation | Blocked by G3 and G5 |
| G7 | Competition Package | Blocked by validated prototype and Label readiness |

---

# Immediate Next Actions

1. Finish Gate 0 consistency audit.
2. Finish Gate 1 research evidence and controlled feasibility experiment.
3. Do not build the full application yet.
4. Once Gate 1 passes, finalize Gate 2 technology choices and contracts.
5. Then give Codex one bounded implementation task at a time.
