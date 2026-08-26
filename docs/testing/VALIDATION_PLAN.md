# RoadShield DZ — Validation Plan v1

## Purpose
Prove that the core RoadShield thesis works before claiming product effectiveness.

## Test layers
### Unit
Test:
- sensor normalization
- event-window calculations
- severity calculations
- GPS-quality rules
- spatial distance calculations
- confidence scoring
- clustering rules
- idempotency

### Replay / simulation
Create deterministic fixtures representing:
- normal smooth driving
- ordinary speed bump
- severe pothole-like impact
- rough-road segment
- repeated events at same location
- same event with poor GPS accuracy
- different users passing the same hazard
- duplicate upload
- offline trip followed by sync

### Integration
Test:
mobile/replay -> ingestion -> database -> risk engine -> dashboard API.

### Field validation
Use controlled routes where possible. Each route should have multiple passes and manually documented ground truth.

## Minimum evidence package
Every experiment should record:
- test ID
- date/time
- route ID
- device/model
- sensor sampling settings
- GPS quality
- event labels
- detector version
- results
- known limitations

## Core metrics
### Detection
Precision = true positive candidate events / all positive candidate events.

Recall = true positive candidate events / all ground-truth target events.

Use an appropriate event-matching tolerance and document it.

### Localization
Measure distance from detected event coordinate to ground-truth location or road segment.

### Repeatability
Measure whether multiple passes of the same known condition generate consistent events.

### Operational
- event-processing latency
- sync success rate
- battery drain per hour of trip
- offline recovery rate

## Gate rule
No measured accuracy, savings, or safety-impact number enters the pitch deck until it is backed by a reproducible experiment record committed under `docs/testing/evidence/`.
