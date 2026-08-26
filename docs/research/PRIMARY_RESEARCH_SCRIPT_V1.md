# RoadShield DZ — Primary Research Script v1

## Purpose

Validate the problem and workflow before making RoadShield product or architecture claims.

## Participant groups

### Drivers
Ask 5–7 questions in 5–10 minutes.

1. What road problems do you encounter most often while driving?
2. Which road hazards have caused you to slow down, change lane, stop, or warn another driver?
3. When you encounter a serious road defect, what do you currently do?
4. Have you ever reported a road problem? How? What happened afterward?
5. What makes reporting a road problem inconvenient?
6. Would you trust a road-warning app that collects limited sensor/location data during trips? What would concern you?
7. Would repeated confirmation from several vehicles make a warning more trustworthy for you?

### Fleet / professional drivers

1. How do you currently record road-related incidents, hard impacts, or vehicle damage?
2. Do repeated road-condition problems affect maintenance, fuel, delivery time, or route planning?
3. How is this information shared with management?
4. What would make a road-risk data product useful enough to adopt?

### Road-maintenance / operator stakeholders

1. How are road-condition complaints currently received?
2. How are they verified?
3. How do you prioritize repair requests?
4. How often does stale, duplicate, or low-quality information create extra work?
5. What evidence would make a citizen/fleet report easier to trust?
6. Would aggregated repeated observations be useful for prioritization?

## Interview rules

- Do not lead participants toward RoadShield.
- Do not describe the proposed solution before collecting current-workflow answers.
- Record participant type, date, and high-level context only.
- Do not store names, phone numbers, precise home/work locations, or other unnecessary personal identifiers in the public repository.
- Quote participants only with consent; otherwise summarize anonymously.

## Evidence coding

For each answer, classify the finding as:

- `pain_confirmed`
- `pain_not_confirmed`
- `current_workaround`
- `trust_constraint`
- `privacy_constraint`
- `workflow_gap`
- `willingness_to_adopt`
- `feature_request`
- `unknown`

Do not convert a single participant statement into a market-wide claim.

## G1.1 success condition

Primary research should identify a repeated, material workflow problem that RoadShield's evidence/corroboration approach can plausibly improve. If not, revise the problem hypothesis before architecture work.