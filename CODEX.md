# RoadShield DZ — Codex Execution Contract

## Mission

Implement RoadShield DZ according to the repository constitution, project requirements, architecture decisions, and gate criteria. Optimize for correctness, evidence, safety, privacy, and reviewability — not code volume.

## Required behavior

Before any substantial coding task:

- Read `PROJECT_CONSTITUTION.md`.
- Read the relevant documents under `docs/`.
- Inspect the current branch and repository state.
- Identify the exact acceptance criteria.
- Do not invent requirements that are not documented or explicitly requested.

## Change discipline

- Make the smallest coherent change that satisfies the task.
- Do not perform opportunistic rewrites.
- Do not introduce a new framework or dependency without documenting the rationale.
- Do not add paid AI/API services to the MVP core.
- Never commit secrets, credentials, API keys, device identifiers, or personal data.
- Preserve privacy-by-design requirements.

## Testing discipline

Every behavior change requires relevant tests. Prefer unit tests for deterministic logic and integration tests for boundaries. For sensor/geospatial features, also maintain a deterministic fixture/simulation path so behavior can be verified without a physical vehicle.

## Safety discipline

Never implement language or UI that implies guaranteed accident prediction or guaranteed protection. Any risk score must explain its basis and uncertainty.

## Completion report

For every task, report:

1. What changed.
2. Files changed.
3. Tests/checks run and results.
4. Known limitations.
5. Any assumptions or decisions that should be documented.

## Gate discipline

Do not begin the next gate automatically when the current gate has unresolved acceptance criteria. The repository owner must be able to review and merge work in small, understandable units.
