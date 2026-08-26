# RoadShield DZ — G2 API Contract Draft

## Status
Draft only. No production API is authorized until G2 passes.

## Design principles
- Version external contracts.
- Validate every payload at the boundary.
- Keep ingestion idempotent.
- Separate authentication, authorization, validation, and domain logic.
- Do not expose raw mobility telemetry by default.
- Return explainable domain state rather than opaque model output.

## Candidate endpoints

### `POST /v1/observations`
Accept a bounded normalized observation or a small batch.

Request draft:
```json
{
  "schema_version": "1.0",
  "session_id": "opaque-session-id",
  "captured_at": "2026-08-26T12:00:00Z",
  "latitude": 35.123456,
  "longitude": -1.234567,
  "location_accuracy_m": 7.5,
  "speed_mps": 12.4,
  "accelerometer_magnitude": 10.8,
  "detector_version": "motion-0.1"
}
```

The public contract must reject impossible coordinates, invalid timestamps, missing required fields, and unreasonable numeric ranges.

### `POST /v1/candidate-events`
Create or submit a detector candidate event. This may be internal to the first vertical slice.

### `GET /v1/conditions`
Query corroborated road conditions by bounding box, radius, condition type, and freshness.

### `GET /v1/conditions/{condition_id}`
Return condition state, confidence, evidence summary, and timestamps.

### `POST /v1/condition-feedback`
Optional later endpoint for authorized feedback or ground-truth correction.

## Error model
Use stable machine-readable codes such as:
- `INVALID_PAYLOAD`
- `INVALID_COORDINATES`
- `STALE_EVENT`
- `DUPLICATE_EVENT`
- `UNAUTHORIZED`
- `FORBIDDEN`
- `RATE_LIMITED`
- `INTERNAL_ERROR`

Do not expose stack traces or sensitive implementation details.

## Idempotency
Ingestion requests must support a deterministic idempotency key or event identity so retries do not duplicate domain events.

## Versioning
- URL versioning for external API.
- Schema version embedded in event payloads.
- Detector/confidence versions stored with derived domain objects.

## Open questions
- Batch size limits.
- Authentication strategy for pilot users.
- Whether raw observation ingestion is server-side or local-first with summarized upload.
- Exact retention/aggregation policy.
