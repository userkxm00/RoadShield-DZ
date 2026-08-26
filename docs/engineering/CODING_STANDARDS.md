# RoadShield DZ — Coding Standards

## General
- Prefer small, readable functions with one clear responsibility.
- Prefer explicit types and validated input/output contracts.
- Avoid speculative abstractions.
- Keep business/domain logic independent from UI and infrastructure where practical.
- Do not hide failures behind broad catch-and-ignore patterns.

## Domain logic
- Keep sensor normalization deterministic.
- Keep scoring rules pure where possible.
- Version algorithms that affect event classification or confidence.
- Make units explicit in names and schemas.
- Document coordinate systems and precision assumptions.

## Mobile
- Avoid unnecessary high-frequency background work.
- Handle missing sensors and permission denial gracefully.
- Keep battery impact measurable.
- Keep local buffering bounded.
- Never block the UI thread with sensor processing or network work.

## API/backend
- Validate every external payload.
- Use versioned contracts for externally consumed endpoints.
- Make ingestion idempotent.
- Return safe error messages.
- Separate authentication, authorization, validation, and business logic.

## Database
- Use explicit migrations.
- Index fields used for time- and geo-based queries.
- Avoid storing raw telemetry when an event summary is sufficient.
- Keep retention logic explicit and testable.

## Tests
Every production behavior change should include the smallest useful test set:
- domain unit tests;
- integration tests at system boundaries;
- deterministic replay tests for sensor/geospatial logic.

## Dependencies
- Prefer established open-source components.
- Every new dependency must have a documented reason.
- Avoid dependencies that create an unnecessary paid-service lock-in.
- Review license, maintenance status, and security advisories before adoption.

## Documentation
Behavior changes require documentation updates when they affect product behavior, architecture, privacy, safety, or competition claims.

## Commit quality
Commits should be focused, reversible, and named by intent, e.g.:
- `docs: define event taxonomy`
- `feat: add deterministic motion detector`
- `test: add replay fixtures for pothole candidates`
- `fix: reject stale telemetry uploads`
