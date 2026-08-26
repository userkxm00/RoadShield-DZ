# RoadShield DZ — Project Constitution

## 1. Purpose

RoadShield exists to create a credible, measurable road-safety innovation prototype for Algeria. The product must prioritize real-world usefulness and evidence over feature volume.

## 2. Non-negotiable principles

### Safety
RoadShield is an assistive safety-information system. It must never claim to guarantee safety, predict a crash with certainty, or replace driver judgment, emergency services, road authorities, or official traffic systems.

### Evidence
No metric, accuracy claim, cost-saving claim, or safety-impact claim may be presented as a fact unless it is backed by a reproducible measurement or an authoritative source.

### Privacy
Collect the minimum data required. Avoid unnecessary continuous recording. Do not retain raw media by default. Location and telemetry must have an explicit purpose, retention policy, and access control.

### Cost
The MVP core must not depend on paid AI APIs. Local algorithms, deterministic rules, open-source/local models, and ordinary statistical methods are preferred until a paid dependency is justified.

### Testability
No feature is complete without appropriate automated tests and, where relevant, a reproducible field-test procedure.

### Simplicity
Do not build speculative abstractions or infrastructure before the product need is proven.

### Traceability
Requirements, architecture decisions, assumptions, risks, and changes must be documented.

## 3. Product boundaries

### In scope for the core MVP

- Mobile telemetry collection with user consent
- GPS-based event localization
- Accelerometer-derived abnormal-motion signals
- Road-hazard event representation
- Geospatial event aggregation
- Transparent road-risk scoring
- Map/dashboard visualization
- Reproducible field validation

### Explicitly out of scope for the first MVP

- Autonomous driving
- Vehicle control
- Emergency dispatch
- Medical or legal advice
- Guaranteed crash prediction
- Large-scale government integration
- Dependence on proprietary paid AI APIs

## 4. Innovation direction

The innovation target is not “add AI.” The target is a preventative road-risk intelligence layer that combines field observations, sensor signals, geospatial aggregation, and explainable scoring to identify persistent hazards before they become incidents.

## 5. Engineering rules

- Prefer typed interfaces and explicit contracts.
- Validate all external input.
- Keep secrets out of Git.
- Maintain deterministic development/test environments where practical.
- Keep commits focused and reversible.
- Use feature branches and pull requests for meaningful changes.
- Never bypass failing CI or required tests without documenting the exception.

## 6. Codex operating rules

Codex is an implementation agent, not the product owner.

Before implementing a substantial change, Codex must:

1. Read this constitution and the relevant project docs.
2. Inspect the existing repository state.
3. State the exact task scope in the work item.
4. Avoid unrelated refactors.
5. Add or update tests.
6. Run the applicable verification commands.
7. Report remaining assumptions, failures, and follow-up risks.

Codex must not silently change product scope, architecture, safety policy, privacy policy, or competition positioning.

## 7. Definition of Done

A task is done only when:

- the requirement is implemented;
- tests cover the expected behavior;
- relevant lint/type/build checks pass;
- documentation is updated when behavior or architecture changed;
- security/privacy implications were considered;
- the change is reviewable as a focused commit/PR.

## 8. Gate discipline

RoadShield uses explicit gates. A gate closes only after its acceptance criteria are satisfied.

Recommended sequence:

`Foundation → Product/Research → Architecture → Core MVP → Field Validation → Intelligence → Competition Package`

Never skip a gate solely to add more features.
