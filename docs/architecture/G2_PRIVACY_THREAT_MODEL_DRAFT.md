# RoadShield DZ — G2 Privacy & Threat Model Draft

## Status
Draft for G2 review. Not a final security approval.

## Assets
- Road-condition events.
- Sensor-derived observations.
- Pseudonymous trip/session identifiers.
- User consent and preference state.
- Operator accounts and permissions.
- API credentials and secrets.
- Ground-truth/validation datasets.

## Threat actors
- Unauthenticated internet clients.
- Malicious or compromised app instances.
- Account takeover attempts.
- Data scraping/abuse.
- Insider misuse.
- Accidental publication of telemetry.

## Core privacy risks
1. Continuous mobility traces can reveal sensitive movement patterns.
2. Device identifiers can enable unwanted tracking.
3. Combining timestamp + location can re-identify users.
4. Raw sensor streams are more sensitive than derived road-condition events.
5. Public map data can unintentionally reveal private locations if aggregation is weak.

## Mitigations
- Data minimization by default.
- Session-scoped pseudonymous identifiers.
- No permanent hardware identifiers in public datasets.
- Coarse/aggregated public road-condition geometry when exact precision is unnecessary.
- Explicit retention periods.
- Separate research/validation data from production datasets.
- Encrypt data in transit and at rest where supported.
- Strict access control for operator/admin functions.
- Rate limiting and abuse monitoring.
- Sanitized demo exports.
- No secrets or raw telemetry in Git.

## Safety-specific risks
- False positives may distract users.
- False negatives may create false confidence.
- Users may misinterpret risk scores as accident predictions.
- Poorly timed alerts may increase distraction.

## Safety mitigations
- Conservative wording.
- Explainable confidence factors.
- Avoid intervention requiring phone interaction while driving.
- Do not claim guaranteed safety outcomes.
- Validate alert behavior before any live-driving alert feature.

## G2 threat-model deliverables
- Data-flow diagram.
- Trust boundaries.
- Abuse cases.
- Privacy retention matrix.
- Access-control matrix.
- Security test plan.
- Incident-response outline.
