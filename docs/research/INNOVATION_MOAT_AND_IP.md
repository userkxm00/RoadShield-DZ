# RoadShield DZ — Innovation Moat & IP Hypotheses

## Innovation position
RoadShield's innovation is not the isolated act of detecting a pothole. The proposed innovation is the **evidence pipeline** that converts low-cost, passive road sensing into a persistent, explainable road-condition state.

### Proposed pipeline
1. Capture minimal mobile sensing signals during a trip.
2. Normalize sensor observations and reject unusable samples.
3. Generate candidate road-condition events.
4. Attach uncertainty and context such as speed, heading, location accuracy and device conditions.
5. Corroborate events across independent trips and time windows.
6. Separate persistent road conditions from transient driving events and sensor artifacts.
7. Maintain an evidence lifecycle: candidate → corroborated → active → stale/resolved.
8. Expose an explainable confidence score and the evidence behind it.

## Potential moat
### 1. Data moat
A growing, privacy-preserving road-condition dataset localized to Algeria and later other markets.

### 2. Algorithm moat
A versioned event-corroboration and quality-scoring pipeline tuned to local road and driving conditions.

### 3. Operational moat
A workflow connecting field evidence to fleet and maintenance prioritization rather than only displaying warnings to drivers.

### 4. Trust moat
Transparent evidence and uncertainty instead of opaque safety claims.

## IP hypotheses
These are hypotheses, not patent claims.

Potentially protectable subject matter may exist in:
- a specific multi-trip corroboration method;
- an event-quality/confidence calculation using heterogeneous sensor context;
- an evidence lifecycle for persistent road-condition states;
- privacy-preserving aggregation that retains utility while minimizing raw telemetry.

A patentability review should be conducted separately before any public disclosure that could affect rights. The project must not state that any component is patented until an official filing/grant exists.

## Open research questions
- Which sensor combinations are sufficient on common Android devices?
- How much does phone mounting location affect signal quality?
- What spatial tolerance should define the same road point?
- Which temporal window best balances persistence and freshness?
- Which false-positive classes matter most in practice?
- Can a robust rule-based MVP outperform a small on-device model at the prototype stage?

## Definition of an innovation result
For Gate 1, innovation is considered adequately defined when the repository can explain:
- what is already common;
- what RoadShield changes technically;
- why that change matters;
- how it will be tested;
- and what evidence would falsify the hypothesis.
