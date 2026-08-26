# RoadShield DZ — Research & Innovation Gate v1

## 1. Competition alignment
The official 2026 President's Prize platform states that the Best Innovative Project category is for a holder of a valid **Projet Innovant** label presenting an innovative product/service with strong market growth potential. The product/service/project must be an innovative solution linked to new technologies. The current application deadline is 10 September 2026 and the award for this category is DZD 3,000,000. Source: official competition platform, checked 25 August 2026.

The Startup.dz application for the Projet Innovant label asks for a short innovation description, a detailed project/presentation of innovation, a prototype photo, project progress, business-model type, website, incubation details, intellectual-property information, and competition/award information. Source: Startup.dz label form, checked 25 August 2026.

## 2. The problem we are solving
RoadShield targets a preventative information gap around road conditions and hazards observed during travel. A user may experience a severe road-surface event without having a structured way to turn that observation into reusable geospatial evidence.

The official SNAR system is being developed to collect and consolidate crash data from official services and to support statistical analysis and national road-safety strategy. Its scope is therefore complementary to RoadShield's intended field-observation layer. Source: Ministry of Interior SNAR page, checked 25 August 2026.

## 3. Important positioning
RoadShield is NOT:
- a replacement for SNAR;
- a replacement for Waze or Google Maps;
- an autonomous driving system;
- an accident-guarantee or accident-prediction product;
- a police or emergency dispatch system.

RoadShield IS:
- a field-sourced road-condition intelligence layer;
- a way to aggregate repeated observations into road-segment evidence;
- an explainable risk/confidence system;
- a potential data product for fleets and authorized road-safety stakeholders.

## 4. Innovation thesis
The core innovation hypothesis is **multi-trip, multi-signal road-risk corroboration** using commodity smartphones rather than dedicated infrastructure.

Potential signals:
- GPS trajectory and accuracy
- accelerometer / gyroscope patterns
- speed/context
- repeated observations across separate trips
- optional on-device camera corroboration
- road-segment geometry
- time/recency

A single signal creates a candidate event. Repeated independent observations can raise confidence. This is more defensible than declaring a hazard from a single sensor spike.

## 5. Differentiation hypotheses
### Navigation products
Navigation products optimize route guidance and user-reported incidents. RoadShield's first thesis is not navigation; it is road-condition evidence and risk intelligence derived from passive sensor observations and repeated corroboration.

### Official crash data
SNAR focuses on recorded bodily-injury crashes and official data integration. RoadShield aims to capture signals **before a crash is recorded** and to identify physical-road patterns through distributed observations. RoadShield must remain complementary and must not imply access to official data unless an authorized integration exists.

### Generic crowdsourcing apps
RoadShield should differentiate through sensor-backed evidence, event quality metadata, repeated cross-trip corroboration, explainable confidence, and privacy-minimized telemetry.

## 6. Core innovation question
Can a low-cost smartphone, without a paid AI API, identify repeatable abnormal road-surface patterns and turn them into trustworthy road-segment evidence?

The MVP must answer this empirically.

## 7. Research hypotheses
H1: Repeated accelerometer signatures at approximately the same location can identify candidate road-surface anomalies more reliably than a single observation.

H2: Combining motion intensity with GPS quality and speed context reduces obvious false positives.

H3: A cluster built from multiple independent trips is a more useful signal than a single user report.

H4: An explainable confidence model can produce a usable risk/priority layer without paid cloud AI.

H5: On-device visual corroboration can later improve precision without requiring continuous video upload.

## 8. Validation design
The first field experiment should deliberately include known road conditions and normal-road controls.

For each route, collect:
- ground-truth label where practical
- repeated passes
- GPS accuracy
- speed band
- sensor window around event
- event score
- human confirmation

Metrics:
- precision
- recall / sensitivity
- false-positive rate
- localization error
- repeatability across runs
- battery consumption

No headline accuracy number should be used in the pitch until measured on a documented test set.

## 9. Competition evidence strategy
The strongest eventual application evidence should be:
1. working prototype;
2. controlled test results;
3. real-world route evidence;
4. clear differentiation;
5. concise market/business model;
6. privacy/safety design;
7. credible scale-up path.

## 10. Open research questions
- What minimum sensor sampling rate is sufficient for the first detector?
- What geospatial tolerance best correlates repeated events?
- How do speed and vehicle type affect motion signatures?
- Can a phone mounted in different positions remain robust enough?
- What data should be retained versus discarded?
- Which visual models can run locally on target devices?
- Which stakeholders can legally and commercially use aggregated road-risk data?

## 11. Research integrity rule
All numbers in public materials must be tagged internally as one of:
- Official source
- Measured in RoadShield testing
- User-reported
- Hypothesis / target
- Estimate

Never present an estimate or target as a measured result.
