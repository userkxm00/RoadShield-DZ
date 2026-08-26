# RoadShield DZ — Git Workflow

## Goal
Keep every change small, reviewable, reversible, and traceable to a requirement, research task, or gate criterion.

## Branching
- `main` is the verified integration branch.
- Use one focused branch per task:
  - `research/*`
  - `docs/*`
  - `feat/*`
  - `fix/*`
  - `test/*`
  - `security/*`
  - `chore/*`

## Required flow

```text
Issue / approved requirement
        ↓
Dedicated branch
        ↓
Small implementation
        ↓
Tests / static checks
        ↓
Evidence / artifact
        ↓
Pull Request
        ↓
Review
        ↓
Merge
        ↓
Verify origin/main
        ↓
Close issue + record evidence
```

## Commit rules
- Use focused, semantic commits.
- Prefer Conventional Commit style where practical.
- Do not mix unrelated refactors with feature work.
- Never force-push shared history.
- Never commit secrets, credentials, raw personal telemetry, or private keys.

## Pull Request requirements
Every PR should state:
1. Problem / requirement addressed.
2. Scope and non-goals.
3. Files changed.
4. Tests/checks run and results.
5. Evidence produced.
6. Known limitations.
7. Gate impact.

## Merge rules
- A PR cannot advance a gate by documentation assertion alone.
- Required checks must pass.
- Review must confirm that scope stayed within the approved task.
- After merge, verify the resulting `main` state before closing the task.

## Gate discipline
If a change reveals an unresolved product, architecture, safety, privacy, or research question, stop and record the decision in an issue/ADR rather than silently changing scope.
