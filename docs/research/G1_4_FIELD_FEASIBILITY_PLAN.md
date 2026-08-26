# RoadShield DZ — G1.4 Field Feasibility Plan

## Objective
Test whether smartphone GPS and motion signals can produce repeatable, geolocated candidate road-condition events under realistic variation.

## Core comparison

Baseline A: single-pass detection.

Baseline B: repeated-observation corroboration.

The project must determine whether corroboration improves confidence or reduces false positives enough to justify the product hypothesis.

## Experimental design

### Route selection

Use 2–3 short routes that contain a mixture of:
- reasonably smooth pavement;
- known or manually observed surface irregularities;
- speed variation;
- turns and braking zones;
- normal road interruptions.

Avoid intentionally dangerous driving. The driver must never interact with the phone while moving.

### Repeated passes

Where practical, perform at least 5 passes per route under comparable conditions. More passes are useful when available.

### Variables to record

- route id;
- date/time window;
- vehicle type;
- phone model;
- phone placement;
- approximate speed band;
- detector version;
- event location;
- manually observed ground truth label.

Do not publish personal home/work locations or device identifiers.

## Ground truth

Ground truth must be recorded independently from the detector output.

Use a simple label set:

- `surface_anomaly_observed`
- `no_surface_anomaly_observed`
- `uncertain`

Ground truth may be recorded by a passenger or after safely stopping, never through phone interaction while driving.

## Metrics

### Repeatability
For the same physical location, measure whether repeated passes generate events within a defined geospatial tolerance.

### Localization error
Distance between detector event location and manually recorded reference point.

### False positives
Candidate events with no corresponding manual anomaly.

### False negatives
Manually observed anomalies with no candidate event.

### Resource cost
- estimated battery use per hour;
- data generated per hour;
- local storage growth;
- CPU impact where practical.

## Acceptance guidance

A numeric threshold should not be invented before the first experiment. The first run establishes baseline distributions and failure modes.

The Gate 1 decision should consider:

1. Is the signal repeatable enough to justify further work?
2. Does geolocation stay within a useful tolerance?
3. Are false positives manageable with corroboration?
4. Does performance remain acceptable across devices/placements?
5. Is the privacy/resource cost compatible with adoption?

## Outcomes

### Continue
Evidence supports moving to architecture and a bounded MVP.

### Narrow
The idea is viable only for a narrower target or condition class.

### Revise
The core sensing hypothesis is unreliable; redesign before architecture.

### Stop
Evidence does not support the product hypothesis.

## Evidence artifacts

- sanitized event dataset;
- experiment log;
- replay fixtures;
- summary metrics;
- limitations report;
- decision memo.
