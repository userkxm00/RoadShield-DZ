# RoadShield DZ — MVP Boundary & Success Criteria

## Product thesis for the first demonstrator
Build the smallest system that proves RoadShield can turn ordinary smartphone motion/location data into **repeated, georeferenced road-condition evidence**.

## In scope
### Mobile
- explicit start/stop trip session;
- GPS location and speed;
- accelerometer sampling at a bounded rate;
- local normalization and buffering;
- candidate anomaly detection;
- event preview with location and confidence basis.

### Backend
- authenticated ingestion endpoint;
- idempotent event ingestion;
- event persistence with PostGIS-capable geospatial fields;
- clustering/corroboration of nearby events;
- event lifecycle state;
- explainable confidence calculation.

### Dashboard
- map of candidate/corroborated events;
- event detail showing evidence basis;
- filters by state and time;
- basic route/trip replay for validation.

## Explicitly out of scope for MVP
- turn-by-turn navigation;
- insurance pricing;
- autonomous driving/control;
- official integration with government systems;
- large-scale city deployment;
- accident prediction for individuals;
- continuous background sensing without clear user consent;
- paid cloud AI APIs as a core dependency;
- complex fleet management;
- production monetization.

## Minimum event schema
Each event should capture only what is needed to reproduce and explain the result, for example:
- event_id;
- trip_session_id;
- event_type;
- observed_at;
- latitude/longitude;
- location_accuracy;
- speed;
- motion summary/features;
- device/session quality flags;
- algorithm_version;
- confidence_score;
- evidence_count;
- lifecycle_state.

Raw continuous telemetry should be retained only where justified for controlled research/validation, with documented retention and deletion rules.

## MVP demo scenario
1. Start a trip session.
2. Drive over a controlled road-surface anomaly.
3. Detect a candidate event.
4. Record its geolocation and context.
5. Repeat the trip or use an independent replay.
6. Corroborate the event.
7. Increase confidence and mark it active.
8. Show the same event on the risk map with its evidence trail.

## Success criteria
The MVP is successful only if a controlled validation run demonstrates all of the following:
- candidate detection works deterministically on a known replay;
- geolocation is captured with an explicit quality value;
- two independent observations can be associated with the same road segment;
- confidence changes according to documented evidence rules;
- common false-positive scenarios are represented in tests;
- the dashboard explains why an event is displayed;
- no paid AI API is required for the core demonstration;
- no secret or unnecessary personal data is stored.

## Non-success outcomes are useful
A failed hypothesis is a valid research result. If phone-only sensing is too noisy, the project should document the limitation and test alternatives such as optional camera evidence or a low-cost external sensor before expanding scope.
