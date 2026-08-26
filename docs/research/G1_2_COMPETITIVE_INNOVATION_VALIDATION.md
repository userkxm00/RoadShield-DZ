# RoadShield DZ — G1.2 Competitive & Innovation Validation

**Phase:** 1 — Research & Innovation  
**Status:** Evidence captured; gate remains open pending repository review and field feasibility.  
**Date:** 2026-08-26

## 1. Purpose

Determine what already exists, what RoadShield must not claim as novel, and where a defensible product/innovation hypothesis may remain.

## 2. Executive conclusion

Road-hazard detection from smartphone GPS/accelerometer data is **not novel by itself**. Research has demonstrated smartphone-based pothole/bump detection and crowdsensing for many years, including systems using GPS + accelerometer and multi-device/multi-vehicle aggregation.

Waze already supports user reports for road hazards including potholes, and Waze partners can add hazard alerts. Therefore a product whose main promise is simply "report or detect potholes" would be insufficiently differentiated.

Algeria's SNAR already targets official accident-data collection, consolidation, spatial analysis, KPI generation, and data-mining-based analysis/prediction of bodily road accidents. RoadShield must therefore complement, not replace, SNAR.

### Current innovation hypothesis

RoadShield's potentially defensible value is **not raw hazard detection**. It is the combination of:

1. passive/mobile sensing during ordinary trips;
2. a normalized, versioned road-event representation;
3. multi-trip geospatial corroboration;
4. evidence-quality and confidence tracking rather than a binary report;
5. temporal road-condition state (new, recurring, weakening, unresolved, etc.);
6. privacy-conscious minimization of mobility data;
7. a future operational intelligence layer for authorized road-maintenance stakeholders.

This is a **hypothesis to validate**, not a patentability or "first in market" claim.

## 3. Competitive matrix

| System / approach | Primary purpose | Data source | Road-hazard detection | Multi-observation evidence | Official accident system | Key gap relative to RoadShield hypothesis |
|---|---|---|---|---|---|---|
| Waze | Navigation + community traffic/hazard reporting | User reports + platform data | Yes | Community corroboration exists, but public documentation does not establish our proposed evidence/state model | No | RoadShield focuses specifically on road-condition evidence and maintenance intelligence |
| Waze for Cities / Partners | Operator/partner alerts | Partner-entered alerts + Waze ecosystem | Yes | Operational alerts | No | RoadShield hypothesis is passive field sensing and evidence aggregation |
| Waymo/Waze partner data | Automated road observations supplied by Waymo to Waze ecosystem | Vehicle/sensor fleet data | Yes, including pothole-related data | Fleet-derived observations | No | Different data source and platform model; not a basis for claiming RoadShield uniqueness |
| Algeria SNAR | Official bodily road-accident data | Security, civil protection, health and civil-status sources | Accident-focused | Official accident records | Yes | Does not replace a field-sourced road-condition sensing layer; RoadShield must not duplicate SNAR |
| Academic smartphone crowdsensing | Road-surface monitoring/research | Smartphone GPS, accelerometer, sometimes camera | Yes | Yes, in several approaches | No | Prior art demonstrates feasibility; RoadShield needs a stronger system-level differentiation |

## 4. Prior-art evidence

### 4.1 Smartphone + GPS + accelerometer

Research has already used smartphone accelerometer and GPS signals to detect and geolocate potholes, bumps, and road-surface anomalies.

Examples:
- Li & Goldberg, *Toward a mobile crowdsensing system for road surface assessment* (2018): GPS + accelerometer, crowdsensing, transient event detection, reported 5–10 m positioning accuracy in field tests.
- Singh et al., *Smart patrolling* (2017): smartphone sensing + crowdsourcing for road-surface monitoring.
- Alam et al., *Crowdsourcing from the True crowd* (2020): multi-device and multi-vehicle road profiling with candidate detection and server-side classification/clustering.
- Additional work has used camera + accelerometer + GPS sensor fusion and clustering.

### 4.2 Implication

Do not claim:

> "RoadShield is the first app to detect potholes using a phone."

Do not claim:

> "RoadShield invents smartphone road sensing."

The novelty investigation must instead target the system-level combination and the exact workflow we can experimentally demonstrate.

## 5. Differentiation hypothesis

The most promising differentiation is an **evidence layer** rather than a detection layer.

### Candidate event

A single sensor anomaly is weak evidence because it may be caused by:
- phone placement;
- vehicle suspension;
- speed;
- driving maneuver;
- sensor noise;
- road geometry;
- a non-road event.

### Corroborated event

RoadShield should increase confidence only when independent or sufficiently distinct observations support the same geospatial condition while accounting for:
- observation quality;
- spatial tolerance;
- temporal recency;
- device/vehicle variability;
- detector version;
- duplicate/repeated passes;
- optional camera corroboration.

This leads to an explainable state such as:

> **Observed road-condition event — confidence: 0.78**
>
> Evidence: 8 observations, 3 device models, 2 vehicle types, repeated over 4 days.

This is a product hypothesis, not a measured result.

## 6. Innovation moat candidates

### A. Evidence-weighted corroboration

A reusable event model that treats observations as evidence with quality and provenance rather than simple reports.

### B. Temporal road-condition state

Track whether a condition is newly observed, persistent, unresolved, weakening, or likely remediated.

### C. Privacy-preserving sensing

Minimize raw mobility collection and retain event-level evidence where possible.

### D. Operator intelligence

Convert validated events into prioritized, explainable work items for authorized road operators rather than only displaying map pins to drivers.

### E. Algeria-first localization

Design for local road conditions, device diversity, connectivity constraints, and public-sector workflows without claiming these are unique globally.

## 7. IP position

At this stage:

- No patentability claim is made.
- No claim of global novelty is made.
- No legal opinion is implied.
- A dedicated prior-art and freedom-to-operate review is required before any public patent-related claim.

Potential IP workstream after feasibility:

1. Search patents and publications around evidence-weighted crowdsensing.
2. Search road-condition temporal state models.
3. Search privacy-preserving mobility sensing and event aggregation.
4. Identify the narrowest technically demonstrable inventive concept.
5. Seek professional IP advice before filing or public disclosure if appropriate.

## 8. Required next evidence

G1.2 is **not fully closed** until we have:

- product-positioning review against the matrix;
- field feasibility evidence;
- at least a small amount of primary user research;
- a written decision on whether the evidence-layer hypothesis survives;
- a decision not to use unsupported novelty claims.

## 9. Decision

**Current decision: CONTINUE, NARROW THE CLAIM.**

RoadShield remains viable as a research/product hypothesis, but the project will compete on **evidence-backed road-condition intelligence and corroboration**, not on the basic ability to detect potholes.
