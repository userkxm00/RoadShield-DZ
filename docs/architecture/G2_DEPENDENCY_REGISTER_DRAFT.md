# RoadShield DZ — G2 Dependency Register Draft

## Status
Draft only. Every dependency remains subject to final review before G2 approval.

| Area | Candidate | Why | Main risk | Required check |
|---|---|---|---|---|
| Mobile | Android native APIs | Sensor/location control | Android-only | API/lifecycle/battery review |
| Mobile UI | Jetpack Compose or equivalent | Fast native UI iteration | UI scope creep | Accessibility/performance |
| Backend | FastAPI or typed TypeScript service | Rapid API work | Framework choice too early | Security, maintainability |
| Database | PostgreSQL + PostGIS | First-class geospatial support | Operational complexity | Version/licensing/security |
| Mapping | MapLibre/OpenStreetMap-compatible stack | Low vendor lock-in | Attribution/data-source constraints | License/usage review |
| Validation | CSV/JSON fixtures + replay tooling | Deterministic tests | Fixture drift | Schema/versioning |

## Rules
- No dependency is adopted only because it is popular.
- Each dependency needs a documented product/technical reason.
- Review license and maintenance status before production adoption.
- Prefer components with active security practices.
- Avoid creating a paid-service dependency in the MVP core.
- Keep domain logic replaceable from infrastructure libraries.

## Required evidence before G2 PASS
- Version selected for each production dependency.
- License compatibility reviewed.
- Known security advisories reviewed.
- Operational cost identified.
- Exit/migration strategy documented for important vendor dependencies.
