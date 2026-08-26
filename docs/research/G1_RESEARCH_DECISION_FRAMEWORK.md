# RoadShield DZ — G1 Research Decision Framework

## Current status

G1 remains open. Desk research supports the problem importance, but user and field evidence are still required before the project may claim validation.

## Evidence hierarchy

1. Official Algerian sources for national context and existing systems.
2. Primary user interviews for workflow pain, trust, and adoption.
3. Controlled field experiments for sensing feasibility.
4. Peer-reviewed/credible technical literature for prior art and methodology.
5. Product documentation from competitors for capability comparison.
6. Hypotheses/targets, clearly labelled as such.

## Current conclusions

### Problem
Road safety is a material national problem. Official 2025 urban statistics reported 842 deaths and more than 23,000 injuries from road crashes. The state is also actively pursuing road maintenance, safety technology, and information systems. These facts establish importance, not product-market fit.

### Existing ecosystem
SNAR is intended to consolidate official bodily-injury crash data, improve data quality and transmission, support spatial analysis, and use data-mining approaches for crash analysis and prediction. RoadShield must complement this ecosystem rather than duplicate it.

### Competitive reality
Hazard reporting and automated pothole detection already exist in products and research. Therefore “AI pothole detection” is not a sufficient innovation claim.

### Innovation hypothesis
The stronger hypothesis is an evidence layer that combines passive mobile sensing, geospatial event representation, repeated independent observations, evidence quality, temporal condition state, and privacy-conscious aggregation. This remains a hypothesis until demonstrated and differentiated with evidence.

## G1 acceptance matrix

| Criterion | Evidence required | Status |
|---|---|---|
| Problem importance | Official sources | PASSING |
| Target user pain | Sanitized interviews | OPEN |
| Competitive differentiation | Research matrix + bounded claim | PASSING / NARROWED |
| Technical feasibility | Controlled field experiment | OPEN |
| Repeated-observation value | Comparative experiment | OPEN |
| Privacy viability | Data minimization model + user feedback | OPEN |
| Business pathway | Interview evidence + market reasoning | OPEN |
| Innovation claim | Evidence-backed differentiation | OPEN |

## Gate decision rule

G1 can be marked PASS only if:

- primary research is complete enough to make a target-user decision;
- field feasibility is tested;
- the innovation claim is narrower than known prior art and supported by evidence;
- major risks are documented;
- the MVP boundary is stable;
- the final decision is explicitly recorded as Proceed, Narrow, Revise, or Stop.

## No-go conditions

Do not proceed to full architecture if:

- users do not care about the underlying problem;
- repeated observations do not improve evidence quality;
- sensing is too unstable across realistic conditions;
- privacy/resource cost makes passive sensing unacceptable;
- the proposed innovation is indistinguishable from existing products.
