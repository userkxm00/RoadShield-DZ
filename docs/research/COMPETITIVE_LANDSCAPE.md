# RoadShield DZ — Competitive Landscape & Innovation Moat v1

## Research conclusion
RoadShield must NOT claim that smartphone-based pothole/road-surface detection is new. Published work has demonstrated smartphone GPS/accelerometer crowdsensing for road-surface monitoring for years, including pothole/bump detection and geospatial aggregation. Recent research also explores multi-sensor fusion and machine learning. citeturn572327search0turn572327search3turn572327search8

## Direct / adjacent solutions

### Waze
Waze lets users report hazards including potholes, objects, construction, and other road hazards. Reports are intentionally temporary and are strengthened or removed through subsequent user feedback. citeturn678783search0turn678783search6

**Implication:** RoadShield cannot differentiate merely by offering a pothole report button.

### Google Maps
Google Maps supports reporting road incidents such as crashes, traffic, construction, objects, flooded roads, low visibility, and other route issues in supported countries. It also lets users confirm whether an incident is still present. citeturn678783search3

**Implication:** RoadShield is not a generic incident-reporting layer.

### Waze / Waymo automated pothole data
Waze for Cities partners can receive Waymo pothole data. Waze describes Waymo's automated pothole feed as using perception and physical-feedback systems and applying confidence/quality controls; the partner feed can be consumed by cities and other approved partners. citeturn678783search7

**Implication:** automated pothole detection already exists at scale in some ecosystems. RoadShield's differentiation must be elsewhere.

### Academic smartphone road-surface sensing
Research has demonstrated GPS + accelerometer crowdsensing, road-quality indexes, and clustering. Some work explicitly studies device/vehicle/phone-position variability and notes that performance can fall across different vehicles and phone placements. citeturn572327search2turn572327search5turn572327search10

**Implication:** robustness across device placement, vehicle type, speed, and road conditions is a major technical challenge and therefore a key validation area.

### Algerian official road-safety data infrastructure
The Algerian Ministry of Interior describes SNAR as a national system for collecting and consolidating official bodily-injury crash data and generating statistical indicators for decision-makers. The ministry also describes information systems for monitoring accidents and identifying black spots. citeturn664413search1turn664413search0

**Implication:** RoadShield must complement, not replace, official accident systems.

## Differentiation hypothesis
RoadShield aims to create a **Road Evidence Graph** rather than a simple incident map.

A Road Evidence Graph links:
- candidate event signals;
- location quality;
- speed/context;
- repeated independent trips;
- temporal persistence/decay;
- optional visual corroboration;
- road-segment identity;
- confidence rationale.

The output is not simply "pothole reported." It is:

> **A road-segment condition record with traceable evidence and an explainable confidence state.**

## Proposed innovation moat
1. **Multi-trip corroboration:** confidence should depend on independent observations, not only one user report.
2. **Evidence quality model:** incorporate GPS accuracy, speed/context, sensor quality, and repetition into confidence.
3. **Temporal state:** distinguish a persistent road defect from a temporary anomaly or one-off event.
4. **Vehicle/device normalization:** explicitly model phone placement, device characteristics, speed and vehicle context instead of assuming one universal sensor signature.
5. **Privacy-minimized telemetry:** send event summaries rather than continuous raw streams by default.
6. **Explainable confidence:** expose evidence contributing to the confidence level instead of opaque AI-only scores.
7. **Operational output:** structure the result for road-segment prioritization and fleet risk intelligence, not only consumer alerts.

## What we will not claim
- "First pothole detector."
- "Only app that uses phone sensors."
- "AI can predict accidents with certainty."
- "RoadShield replaces Waze, Google Maps, or SNAR."

## Research implication
The strongest technical question is now:

> Can RoadShield produce more reliable and operationally useful road-segment evidence by combining repeated independent smartphone observations with quality-aware, explainable corroboration under varied devices, vehicles, speeds, and phone placements?

That hypothesis is testable and should drive the MVP.
