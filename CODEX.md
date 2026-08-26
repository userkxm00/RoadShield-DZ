# RoadShield DZ — Codex Execution Contract

## Mission
Implement RoadShield DZ according to the repository constitution, `docs/MASTER_PLAN_V1.md`, gate criteria, research evidence, product requirements, and approved architecture decisions. Optimize for correctness, evidence, safety, privacy, and reviewability — not code volume.

## Required reading order
Before any substantial task, Codex MUST read:
1. `PROJECT_CONSTITUTION.md`
2. `docs/MASTER_PLAN_V1.md`
3. `docs/GATE_REGISTRY.md`
4. `ROADMAP.md`
5. the relevant documents under `docs/`
6. the current repository state and recent commits

If a requirement conflicts with another document, STOP and report the conflict. Do not silently choose.

## Current execution state
The repository is in **Phase 1 — Research & Innovation**.

Codex must NOT start broad production application implementation until Gate 1 is explicitly accepted by the repository owner.

## Execution authority
- Product decisions: repository owner.
- Architecture decisions: repository owner, after documented review.
- Security/privacy decisions: repository owner with documented technical evidence.
- Competition/Label claims: repository owner; every claim requires traceable evidence.
- Codex: implementation, testing, documentation updates, and bounded technical investigation.

Codex may propose alternatives, but proposals are not decisions until approved and recorded.

## Current permitted Gate 1 work
Codex may:
- inspect current docs;
- perform bounded research-support tasks;
- build a minimal validation/replay harness when explicitly requested;
- create deterministic fixtures;
- add experiment logging and sanitized export support;
- identify contradictions, missing acceptance criteria, unsupported claims, or feasibility blockers.

Codex may NOT:
- build the full product;
- add navigation;
- add payments, fleet management, social features, billing, or unrelated modules;
- introduce paid AI/API dependencies into the MVP core;
- claim Gate 1 is validated without field evidence.

## Change discipline
- Make the smallest coherent change that satisfies the task.
- Do not perform opportunistic rewrites.
- Do not introduce a framework or dependency without documenting the rationale.
- Never commit secrets, credentials, API keys, device identifiers, raw personal data, or production telemetry.
- Preserve privacy-by-design requirements.
- Never silently widen scope.

## Testing discipline
Every behavior change requires relevant tests. Prefer unit tests for deterministic logic and integration tests for boundaries. For sensor/geospatial features, maintain deterministic fixtures/replay so behavior can be verified without a physical vehicle.

## Safety discipline
Never implement language or UI that implies guaranteed accident prediction or guaranteed protection. Risk scores must expose their basis and uncertainty. RoadShield is decision support, not autonomous control.

## Evidence discipline
Every public-facing quantitative claim must be traceable to:
- an official source;
- a RoadShield measurement;
- a clearly labelled hypothesis/target;
- or a clearly labelled estimate.

Never manufacture benchmark results, user counts, accuracy, savings, or accident-reduction claims.

## Completion report
For every task, report:
1. What changed.
2. Files changed.
3. Tests/checks run and results.
4. Known limitations.
5. Assumptions and decisions requiring documentation.
6. Gate status and unresolved acceptance criteria.
7. Evidence artifact locations.

## Gate discipline
Do not begin the next gate automatically when the current gate has unresolved acceptance criteria. The repository owner must review and merge work in small, understandable units.

## Git discipline
- Work on a dedicated feature/research branch when implementation is authorized.
- Keep commits small and semantically named.
- Never force-push or rewrite shared history.
- Do not merge work into `main` without passing defined gate checks.
- Never commit generated credentials, local environment files containing secrets, or large test artifacts unless explicitly required.
