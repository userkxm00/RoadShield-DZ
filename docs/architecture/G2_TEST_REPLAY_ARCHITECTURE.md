# RoadShield DZ — G2 Test & Replay Architecture

## Status
Preparation only.

## Objective
Make sensor/geospatial behavior reproducible without requiring a physical device for every test run.

## Test layers

### 1. Domain unit tests
Pure functions for:
- sensor normalization;
- candidate detection;
- spatial distance calculations;
- event deduplication;
- corroboration;
- confidence scoring;
- state transitions.

### 2. Replay tests
Use sanitized fixture streams containing:
- timestamp;
- GPS coordinate;
- location accuracy;
- speed when available;
- accelerometer-derived features;
- sensor health;
- detector version.

A replay must produce the same derived events for the same input and detector version.

### 3. Integration tests
Verify:
- API validation;
- idempotency;
- persistence;
- geospatial queries;
- event-state transitions.

### 4. Scenario tests
Examples:
- same condition observed on repeated passes;
- many samples from one trip must not inflate independence;
- noisy GPS near a cluster boundary;
- missing accelerometer;
- permission denial;
- duplicate upload;
- delayed/out-of-order samples;
- condition becomes stale.

## Fixture rules
- No raw personal mobility traces.
- All fixtures sanitized or synthetic.
- Each fixture declares schema version and detector version.
- Expected outputs are checked into the repository.
- Fixtures should include negative cases, not only successful events.

## Validation evidence
Each detector or scoring change should produce:
- test results;
- fixture version;
- configuration/version identifiers;
- known limitations.

## Principle
If the behavior cannot be replayed deterministically, it is not mature enough to be treated as a stable competition claim.
