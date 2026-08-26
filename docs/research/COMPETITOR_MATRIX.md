# RoadShield DZ — Competitor & Differentiation Matrix

## Purpose
Separate what already exists from what RoadShield must prove.

| Capability | Waze | SNAR (Algeria) | RoadShield MVP | Strategic position |
|---|---|---|---|---|
| Consumer navigation | Yes | No | No | Explicit non-goal |
| Manual hazard reporting | Yes | No | Not core | Not novel by itself |
| Pothole reporting | Yes | No | Yes, as a candidate output | Not novel by itself |
| Automatic phone-sensor candidate detection | Not the core Waze user flow | No | Yes | Core technical hypothesis |
| Multi-trip corroboration | Limited/unknown as public product behavior | Official crash data | Yes | Core differentiation to validate |
| Road-condition evidence history | Limited/publicly documented behavior | Crash records | Yes | Core differentiation |
| Explainable confidence | User/report based | KPI/statistical system | Yes | Core product requirement |
| Privacy-preserving event summaries | Product-dependent | Institutional data | Yes | Architecture requirement |
| Fleet/operational road-condition intelligence | Partner/data products exist | Public-sector focus | Planned | B2B expansion |
| Algeria-specific road-condition dataset | Global/community | Official crash dataset | Planned | Long-term data moat |

## Key competitor facts
### Waze
Waze supports user reports for hazards including construction, potholes, objects and stopped vehicles. Its partner data feed can contain user-reported hazards and potholes, and Waze for Cities partners can access Waymo pothole detections. Therefore manual reporting and simple pothole detection cannot be claimed as unique.

Sources:
- https://support.google.com/waze/answer/13739290
- https://support.google.com/waze/partners/answer/10618035
- https://support.google.com/waze/partners/answer/17021071

### SNAR
The Algerian Ministry of Interior describes SNAR as a national system for collecting and consolidating official bodily-injury accident data, spatial analysis, KPI generation and data-mining-based accident analysis/prediction.

Source:
- https://interieur.gov.dz/le-systeme-national-des-accidents-de-la-route-snar/

## RoadShield differentiation thesis
RoadShield should not compete on navigation, generic reporting, or a claim of being the first pothole detector. The project should compete on a different layer:

**Continuous, passive, privacy-conscious sensing → event normalization → spatial/temporal corroboration → evidence quality → explainable road-condition state.**

The product can then expose different views of the same evidence:
- driver safety awareness;
- fleet route-risk intelligence;
- road-maintenance prioritization.

## What must be proven experimentally
1. The sensing pipeline can identify repeatable candidate events.
2. Repeated observations improve confidence over one-off observations.
3. The system can distinguish at least some false-positive classes such as hard braking or device movement.
4. Event evidence can be summarized without keeping unnecessary raw telemetry.
5. Stakeholders can understand and act on the resulting evidence.

## Anti-claim rule
Do not use phrases such as "first in Algeria", "patented", "guaranteed accident prevention", or "AI predicts accidents" unless independently verified and documented.
