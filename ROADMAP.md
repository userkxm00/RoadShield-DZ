# RoadShield DZ — Master Roadmap

## Mission
Build a credible, privacy-conscious road-safety intelligence prototype for Algeria that detects and aggregates road hazards from ordinary smartphone/vehicle telemetry, turns repeated observations into geospatial risk signals, and produces actionable safety intelligence.

## Competition target
- Category: Best Innovative Project
- Required label: Projet Innovant
- Current official deadline: 10 September 2026
- Official prize amount: DZD 3,000,000
- Rule: the competition requires a valid official label at application time.

## Delivery strategy
RoadShield will be built in gated increments. No large feature batch is accepted without tests, evidence, and a gate review.

### Gate 0 — Foundation
Status: COMPLETE
- GitHub repository created
- Core project constitution created
- Codex execution rules created
- Initial README established

### Gate 1 — Research & Innovation Definition
Status: IN PROGRESS
Deliverables:
- Problem evidence
- User/persona definition
- Existing-solution analysis
- Competitive differentiation
- Official-system boundary analysis
- Innovation thesis
- MVP scope
- measurable hypotheses
- Label/competition alignment

Exit criteria:
- One precise problem statement
- One primary user
- One primary MVP job-to-be-done
- Clear differentiation from navigation apps and SNAR
- No unsupported claims

### Gate 2 — Product & Technical Specification
Deliverables:
- Product requirements
- System architecture
- Data model
- API contracts
- event taxonomy
- privacy model
- risk-scoring specification
- mobile constraints
- dashboard requirements

Exit criteria:
- Architecture review complete
- Contracts versioned
- Threat/privacy review complete
- Test strategy approved

### Gate 3 — Telemetry Prototype
Deliverables:
- Mobile telemetry capture
- GPS normalization
- accelerometer event detection
- local event storage
- replayable test fixtures

Exit criteria:
- deterministic tests pass
- synthetic telemetry replay works
- no unnecessary continuous recording

### Gate 4 — Road Hazard Intelligence MVP
Deliverables:
- hazard event schema
- geospatial aggregation
- confidence scoring
- repeated-observation correlation
- risk map backend

Exit criteria:
- same-location events correlate correctly
- false-positive controls exist
- risk score is explainable

### Gate 5 — Dashboard & Demo
Deliverables:
- web dashboard
- map visualization
- hazard details
- fleet/admin view
- demo mode

Exit criteria:
- clean end-to-end demo
- reproducible seed dataset
- screenshots/video-ready

### Gate 6 — Field Validation
Deliverables:
- controlled road tests
- repeated routes
- ground-truth labels
- evaluation report
- measured precision/recall or equivalent metrics

Exit criteria:
- real-world evidence exists
- limitations documented
- no safety claims exceed evidence

### Gate 7 — Competition Package
Deliverables:
- Label Projet Innovant application inputs
- Pitch Deck
- innovation statement
- market analysis
- business model
- impact model
- prototype evidence
- demo script
- founder/team material
- website/landing page

Exit criteria:
- official submission fields checked
- all documents internally consistent
- final demo reproducible

## Product north star
A RoadShield alert is valuable only when it is:
1. location-aware,
2. evidence-backed,
3. explainable,
4. privacy-conscious,
5. useful for prevention or operational decision-making.

## Non-goals for MVP
- replacing Waze/Google Maps navigation
- claiming guaranteed accident prediction
- medical/emergency dispatch automation
- autonomous vehicle control
- paid cloud AI as a hard dependency
- nationwide deployment before field validation
