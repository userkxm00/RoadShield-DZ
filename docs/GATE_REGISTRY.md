# RoadShield DZ — Gate Registry

## Gate model

A phase advances only when its acceptance evidence has been produced, reviewed, and the resulting repository state has been verified on `main`.

| Gate | Phase | Purpose | Status |
|---|---|---|---|
| G0 | Project Foundation | Establish product, engineering, security, Git, Codex, and gate governance | **PASS** |
| G1 | Research & Innovation | Prove problem, differentiation, MVP feasibility, and research direction | **IN PROGRESS** |
| G2 | Architecture & Technical Specification | Finalize stack, contracts, data model, security/privacy model | **BLOCKED BY G1** |
| G3 | MVP Core | Build bounded sensor-to-event-to-map core | **BLOCKED BY G2** |
| G4 | Intelligence | Add and quantify sensor fusion / local AI where justified | **BLOCKED BY G3** |
| G5 | Safety / Privacy / Security | Harden product and verify safety/security posture | **BLOCKED BY MVP BASELINE; CONTINUOUS THEREAFTER** |
| G6 | Field Validation | Validate the real-world hypothesis with controlled experiments | **BLOCKED BY G3 + G5** |
| G7 | Competition Package | Prepare Label and competition materials from verified evidence | **BLOCKED BY G6 + LABEL READINESS** |

## G0 evidence

- `docs/FOUNDATION_GATE_CHECKLIST.md`
- `docs/engineering/FOUNDATION_AUDIT_2026-08-26.md`

## G1 evidence set

- `docs/research/PROBLEM_EVIDENCE.md`
- `docs/research/COMPETITIVE_LANDSCAPE.md`
- `docs/research/RESEARCH_AND_INNOVATION.md`
- `docs/research/RESEARCH_EVIDENCE_2026.md`
- `docs/research/FIELD_VALIDATION_PROTOCOL_V1.md`
- `docs/research/GATE_1_ACCEPTANCE.md`
- GitHub Issue #1 — controlled field validation
- GitHub Issue #2 — controlled validation harness

## Non-negotiable rule

A green documentation checklist is not enough to pass a research gate. Research gates require external evidence, such as reproducible experiments or an explicit hypothesis revision based on observed failure.
