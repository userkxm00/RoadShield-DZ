# RoadShield DZ — Gate Registry

This file is the authoritative list of stage gates. A gate may be marked PASS only when its acceptance evidence exists in GitHub and the main branch has been verified after merge.

## Gate sequence

### G0 — Repository Foundation
**Purpose:** Establish project constitution, product baseline, engineering rules, security/test strategy, Git workflow, and Codex contract.

**Required evidence**
- Foundation documents present and internally consistent.
- Repository structure defined.
- Definition of Done documented.
- Git workflow documented.
- Codex instructions documented.
- No premature production implementation.

**Status:** In progress — final consistency audit required.

### G1 — Research & Innovation
**Purpose:** Establish a defensible problem statement, competitive boundary, innovation hypothesis, MVP boundary, and feasibility evidence.

**Required evidence**
- Official source register.
- Competitor matrix.
- Innovation differentiation.
- IP/prior-art hypothesis.
- Controlled field-validation protocol.
- Feasibility evidence.
- Decision: continue, narrow, or revise.

**Status:** In progress.

### G2 — Technical Architecture
**Purpose:** Freeze the MVP technical design before broad implementation.

**Required evidence**
- Technology stack.
- System architecture.
- Data model.
- API contracts.
- Event taxonomy.
- Threat model.
- Privacy model.
- Test/replay strategy.
- ADRs for major decisions.

**Status:** Blocked by G1.

### G3 — MVP Core
**Purpose:** Build and verify the minimum end-to-end product loop.

**Required evidence**
- Sensor capture.
- Candidate event detection.
- Geospatial binding.
- Backend ingestion.
- Storage.
- Corroboration.
- Confidence model.
- Dashboard/map.
- Passing automated checks.

**Status:** Blocked by G2.

### G4 — Intelligence
**Purpose:** Add measurable intelligence only after the deterministic baseline works.

**Required evidence**
- Baseline versus enhanced model comparison.
- Versioned models/algorithms.
- Resource/battery impact.
- Reproducible tests.

**Status:** Blocked by G3.

### G5 — Safety / Privacy / Security
**Purpose:** Ensure the product can be demonstrated and tested responsibly.

**Required evidence**
- Threat model review.
- Privacy review.
- Security tests.
- Safety UX/copy review.
- No critical unresolved issues.

**Status:** Continuous; mandatory before field demonstration and competition submission.

### G6 — Field Validation
**Purpose:** Prove that the core system behaves consistently in real conditions.

**Required evidence**
- Sanitized dataset.
- Experiment log.
- Repeatability results.
- Localization error.
- False-positive/false-negative observations where measurable.
- Battery/data observations.
- Limitations and decision.

**Status:** Blocked by G3 and required safety controls.

### G7 — Competition Package
**Purpose:** Produce a submission-ready product and evidence package.

**Required evidence**
- Prototype.
- Pitch deck.
- One-pager.
- Demo script.
- Competition matrix.
- Innovation statement.
- Business model.
- Impact metrics.
- Founder CV.
- Label-ready materials.
- Final consistency audit.

**Status:** Blocked by validated prototype and Label readiness.

## Gate protocol

```text
Task definition
  ↓
Implementation / research
  ↓
Automated verification
  ↓
Artifact / evidence
  ↓
Human review
  ↓
PR
  ↓
Merge
  ↓
origin/main verification
  ↓
Gate decision
```

No gate is considered passed from prose alone.
