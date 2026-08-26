# RoadShield DZ — Research Evidence Register (2026)

## Purpose
This document records verified external evidence used to define RoadShield's problem, competitive boundaries, and innovation thesis. It is intentionally conservative: a claim is not treated as a product advantage unless the evidence supports it.

## 1. Road-risk data already exists in mainstream products
Waze officially supports user reports for road hazards including construction, stopped vehicles, broken traffic lights, potholes, and objects on the road.
Source: https://support.google.com/waze/answer/13739290

Waze's partner data feed includes user-reported accidents, hazards, construction, potholes, roadkill, stopped vehicles, objects, and missing signs. Waze also computes traffic slowdowns from current-versus-historical speeds.
Source: https://support.google.com/waze/partners/answer/10618035

In April 2026, Waymo and Waze announced a pilot that provides cities with Waymo-detected pothole data through Waze for Cities. The stated goal is to give cities more actionable road-condition information alongside user reports.
Source: https://waymo.com/blog/2026/04/partnering-with-waze-to-help-cities-patch-their-potholes/

## 2. Algeria already has a national crash-data system
The Algerian Ministry of Interior describes SNAR as the national system for collecting and consolidating bodily road-accident data from security and other public services. Its objectives include improving data quality, spatial analysis, KPI generation, and the use of data-mining techniques for analysis and prediction of bodily road accidents.
Source: https://interieur.gov.dz/le-systeme-national-des-accidents-de-la-route-snar/

## 3. Smartphone-based road-surface sensing is an established research field
Research has demonstrated that smartphone GPS and accelerometer data can be used to detect and geo-localize road-surface anomalies through crowdsourcing. Multiple studies report workable detection accuracy, but also identify strong sensitivity to vehicle type, phone placement, speed, road type, and driving behavior.

Examples:
- Smart Patrolling using smartphone sensors and crowdsourcing: https://www.sciencedirect.com/science/article/pii/S1574119216301262
- RoadSurP device/vehicle/road-surface independent profiling: https://www.sciencedirect.com/science/article/pii/S1574119219304687
- Smartphone sensing of road-surface condition and defect detection: https://pmc.ncbi.nlm.nih.gov/articles/PMC8401562/
- 2024 crowd-sourced urban road-surface condition sensing: https://www.mdpi.com/1424-8220/24/13/4093

## 4. Consequence for RoadShield
The following claims are prohibited:
- "RoadShield is the first pothole detector."
- "RoadShield invented smartphone road sensing."
- "RoadShield replaces Waze."
- "RoadShield replaces SNAR."

The defensible product hypothesis is narrower:

> RoadShield aims to create a privacy-conscious, Algeria-first evidence layer that turns repeated mobile observations into quality-scored road-risk events, with explicit corroboration and interpretable confidence, and exposes the resulting road-condition intelligence to drivers, fleets, and authorized stakeholders.

This is a product hypothesis, not a proven novelty claim. It must be validated experimentally and through prior-art review before any IP assertion.

## 5. Research gap to test
The research literature shows the technical feasibility of smartphone sensing, while mainstream products already provide reporting/alerting. The remaining product question is whether RoadShield can create materially better evidence quality and operational usefulness through:

1. repeated independent observations;
2. confidence/reliability scoring;
3. event aging and persistence/decay;
4. separation of transient obstacles from persistent road-condition defects;
5. privacy-preserving telemetry summarization;
6. explainable evidence for each risk event;
7. a stakeholder workflow designed around evidence quality rather than navigation.

These are hypotheses to validate, not assumptions to advertise as established facts.

## Gate-1 implication
Research Gate 1 cannot be closed by feature count. It closes only when RoadShield has:
- an explicit problem statement;
- a documented competitor boundary;
- a defensible innovation hypothesis;
- a narrowly scoped MVP;
- a repeatable field-validation protocol;
- an IP/prior-art caution statement;
- evidence sources recorded here.
