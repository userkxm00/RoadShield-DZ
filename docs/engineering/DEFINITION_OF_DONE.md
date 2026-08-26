# RoadShield DZ — Definition of Done

A task is **Done** only when all applicable criteria below are satisfied.

## Product
- Requirement and acceptance criteria are explicit.
- Scope and non-goals are respected.
- User-facing behavior matches the approved specification.

## Engineering
- Implementation is complete and appropriately scoped.
- Types/contracts are explicit and validated.
- No unnecessary dependency or abstraction was introduced.

## Testing
- Relevant unit/integration/replay tests pass.
- Typecheck/lint/build checks required by the current stack pass.
- Edge cases and failure paths relevant to the change are covered.

## Security & privacy
- Inputs are validated.
- Secrets are not committed.
- Privacy impact is reviewed.
- No raw personal telemetry is included in public artifacts.

## Documentation & evidence
- Documentation is updated when behavior, architecture, safety, privacy, or competition claims change.
- Reproducible evidence exists for the completed behavior.
- Known limitations are recorded.

## Git & review
- Work is on the correct branch.
- Commit/PR scope is focused.
- Pull request review is complete.
- Merge is intentional.
- `main` is verified after merge.

## Gate rule
A task may be technically complete but still **not gate-complete**. Gate completion requires the acceptance evidence defined in the Gate Registry.
