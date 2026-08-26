# RoadShield DZ — Field Validation Protocol v1

## Objective
Determine whether smartphone motion/location signals can generate repeatable, geo-localized candidate road-risk events under realistic Algerian driving conditions.

## Hypotheses

### H1 — Repeatability
The same road segment produces statistically similar motion signatures across repeated passes when the underlying road condition is persistent.

### H2 — Corroboration
Independent passes over the same segment increase confidence more reliably than a single event.

### H3 — Confounder control
Speed, phone placement, vehicle type, and driving maneuver materially affect raw acceleration signals and must be captured or normalized.

### H4 — Event persistence
Persistent road defects produce repeated observations over time, while transient objects/conditions decay when they stop being observed.

## MVP instrumentation

Required:
- Android phone with GPS and accelerometer.
- Fixed and repeatable phone placement for the first controlled experiment.
- Vehicle with known route.
- Local event recorder with timestamp, coordinates, speed estimate, acceleration summary, device identifier pseudonym, and software version.

Optional later:
- Camera signal.
- Gyroscope.
- Additional vehicle metadata.

## Controlled experiment

### Route design
Select 2–3 short routes containing:
- at least one known bump or rough segment;
- at least one normal smooth segment;
- at least one potential confounder such as braking or a turn.

### Passes
Perform at least 5 passes per route under similar conditions before expanding to additional vehicles/devices.

Record:
- route identifier;
- pass identifier;
- approximate speed band;
- phone placement;
- device model;
- vehicle type;
- timestamp;
- candidate event location;
- motion features used by the detector.

## Ground truth
Each test segment must be manually reviewed after the run and assigned one of:
- persistent road defect;
- temporary obstruction;
- normal road feature;
- driving maneuver artifact;
- unknown.

Do not use the detector output itself as the ground truth.

## Initial metrics

Measure:
- event repeatability rate;
- false-positive count;
- false-negative count when ground truth is known;
- spatial localization error in meters;
- corroboration gain as independent observations accumulate;
- event confidence calibration;
- battery impact per hour;
- data volume generated per kilometer.

No target accuracy is declared until the baseline experiment is complete.

## Required experiment artifacts

Store under `artifacts/validation/` only sanitized/non-sensitive outputs:
- test route definition;
- anonymized event CSV/JSON;
- detector configuration version;
- experiment log;
- result summary;
- limitations.

Never commit raw personal location history, phone identifiers, or private telemetry to the public repository.

## Acceptance rule for Gate 1
The research phase is considered technically credible only when one controlled experiment has produced reproducible evidence that at least one candidate event can be localized and corroborated, or when the experiment documents a blocking technical failure and the product hypothesis is revised accordingly.
