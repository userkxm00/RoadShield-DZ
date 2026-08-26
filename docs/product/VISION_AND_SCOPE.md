# RoadShield DZ — Vision & Scope

## Vision
Make road-condition evidence continuously discoverable from ordinary journeys so drivers and authorized road operators can act on persistent hazards earlier and with better evidence.

## Product promise
RoadShield turns low-cost, privacy-minimized smartphone telemetry into **location-aware, explainable road-condition evidence**.

It does not promise to predict crashes. It identifies candidate road-surface events, corroborates them across independent trips, and turns them into road-segment intelligence.

## Primary problem
A road user can experience a pothole, harsh surface, abrupt vertical movement, or other physical-road anomaly without producing reusable, structured evidence. A manual report is intermittent and subjective. Official crash systems are essential, but they are centered on recorded crashes and official data sources. RoadShield targets the complementary prevention layer: continuous field observations from ordinary journeys.

## Primary MVP user
A driver using an Android smartphone safely mounted in a vehicle.

## Secondary users
- Fleet operators
- Authorized road-maintenance / road-safety stakeholders
- Researchers and transport analysts

## MVP job-to-be-done
During a trip, collect a minimal set of location and motion signals, detect candidate abnormal road events, associate them with a road segment, and present evidence-backed confidence after repeated observations.

## Goals
- Demonstrate repeatable detection of abnormal road-motion events.
- Localize events with useful geographic precision.
- Corroborate events across separate trips.
- Explain why confidence increases or decreases.
- Operate without a paid cloud AI dependency.
- Produce a credible end-to-end prototype suitable for controlled field validation.
- Create evidence that can support the Projet Innovant label and competition dossier.

## Non-goals
- Navigation replacement.
- Autonomous driving.
- Guaranteed crash prediction.
- Emergency dispatch.
- Police or enforcement tooling.
- Medical or legal advice.
- Continuous cloud video upload.
- National government integration before validation and authorization.

## Innovation thesis
The novelty we will test is not smartphone pothole detection by itself; that is established research. The core differentiation hypothesis is a **privacy-minimized, multi-trip corroboration layer** that combines motion/location evidence, data-quality context, spatial clustering, temporal persistence, and optional on-device visual corroboration to create explainable road-segment evidence.

## North-star evidence
A useful RoadShield hazard record should answer:
1. Where is the event?
2. What signal was observed?
3. How strong was the signal?
4. How many independent observations support it?
5. How recent is it?
6. How reliable is the location/data quality?
7. Why did confidence change?

## Success definition for MVP
Success is not "AI detects potholes perfectly." Success is a reproducible demonstration that ordinary smartphone telemetry can generate useful candidate events and that repeated independent observations improve the reliability of the resulting road-segment evidence under a documented test protocol.
