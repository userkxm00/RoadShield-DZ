# RoadShield DZ — G2 Domain Model Draft

## Status
Draft for review. Not an approved production schema.

## Core entities

### Observation
A normalized observation produced during a trip.

Suggested fields:
- `observation_id`
- `trip_id` (pseudonymous/session-scoped)
- `captured_at`
- `latitude`
- `longitude`
- `location_accuracy_m`
- `speed_mps` (nullable)
- `accelerometer_magnitude`
- `sensor_health`
- `detector_version`

### CandidateEvent
A deterministic detector output indicating that an observation or short temporal window contains an abnormal signal.

Suggested fields:
- `candidate_event_id`
- `event_type`
- `occurred_at`
- `latitude`
- `longitude`
- `location_accuracy_m`
- `signal_features`
- `detector_version`
- `candidate_confidence`

### Evidence
A bounded reference to the observations/features used to support a candidate or corroborated event.

Suggested fields:
- `evidence_id`
- `candidate_event_id`
- `evidence_type`
- `source_class`
- `captured_at`
- `quality_score`

Raw telemetry should not be retained unless explicitly required by a validated experiment.

### CorroboratedCondition
A geospatial road-condition record created when independent observations support a shared condition.

Suggested fields:
- `condition_id`
- `condition_type`
- `geofence/geometry`
- `first_observed_at`
- `last_observed_at`
- `observation_count`
- `independent_trip_count`
- `independent_device_count` (where privacy-safe)
- `confidence`
- `confidence_version`
- `state`

### ConditionState
Initial draft state machine:

`CANDIDATE → CORROBORATED → ACTIVE → STALE → RESOLVED`

Optional `DISPUTED` state may be added if evidence shows a need.

## Domain invariants
1. A candidate event must have a valid timestamp and coordinate uncertainty metadata.
2. Confidence must always be versioned.
3. Corroboration must distinguish repeated samples from independent trips where feasible.
4. A single device cannot inflate independence counts by producing many samples in one trip.
5. Event state transitions must be auditable and deterministic.
6. No domain object may imply guaranteed accident prediction or prevention.

## Open questions
- Exact spatial tolerance for clustering.
- Temporal corroboration window.
- Definition of independent trip/device under privacy constraints.
- Minimum evidence quality for each condition type.
- Which event types are in MVP scope.
