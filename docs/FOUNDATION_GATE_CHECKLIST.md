# RoadShield DZ — Foundation Gate Checklist

## G0 — Repository Foundation

This checklist is the formal final verification for Phase 0. No production implementation should begin until all required items are checked.

### Repository
- [ ] README links to the authoritative master plan.
- [ ] Master plan exists at `docs/MASTER_PLAN_V1.md`.
- [ ] Gate registry exists at `docs/GATE_REGISTRY.md`.
- [ ] Current project status exists at `docs/PROJECT_STATUS.md`.

### Product definition
- [ ] Vision is documented.
- [ ] Problem statement is explicit.
- [ ] Goals are explicit.
- [ ] Non-goals are explicit.
- [ ] Core MVP thesis is explicit.
- [ ] Competition target is documented.

### Engineering governance
- [ ] Coding standards documented.
- [ ] Testing strategy documented.
- [ ] Definition of Done documented.
- [ ] Git workflow documented.
- [ ] ADR/decision-log process documented.
- [ ] Security rules documented.
- [ ] Privacy constraints documented.
- [ ] Codex scope and authority documented.

### Gate governance
- [ ] Each phase has a named gate.
- [ ] Each gate has acceptance evidence.
- [ ] Gate progression requires review.
- [ ] `main` verification is required after merge.
- [ ] Gate status is tracked in GitHub.

### Product-safety constraints
- [ ] No guaranteed accident-prevention claims.
- [ ] No paid AI/API dependency in the MVP core.
- [ ] No raw personal telemetry committed to the repository.
- [ ] No premature production architecture commitment before G1 research is complete.

## G0 decision

**Status:** IN PROGRESS

**Decision owner:** Repository owner

**Required next action:** perform a document consistency audit, then mark PASS only after the repository state has been reviewed.
