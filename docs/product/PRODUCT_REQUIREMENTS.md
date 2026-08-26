# RoadShield DZ — Product Requirements v1

## 1. Product statement
RoadShield is a road-safety intelligence platform that converts smartphone/vehicle telemetry and repeated field observations into explainable, location-aware road-risk information.

## 2. Primary problem
Road users and road operators often lack a timely, structured view of physical road hazards and abnormal road-surface conditions. Official accident systems are essential for analysing recorded crashes, but RoadShield focuses on an additional preventative layer based on observations collected during journeys.

## 3. Primary user for MVP
A driver using an Android smartphone mounted safely in a vehicle.

## 4. Secondary users
- Fleet operators
- Road-maintenance / authorized institutional stakeholders
- Researchers or safety analysts

## 5. MVP job-to-be-done
While travelling, capture a minimal set of motion/location signals, identify candidate abnormal-road events, associate them with a road segment, and show those events on a map with transparent confidence.

## 6. Core user journey
1. User starts a protected trip session.
2. App samples GPS and motion telemetry at controlled intervals.
3. Local detector identifies a candidate abnormal event.
4. Event is assigned a timestamp, approximate location, motion metrics, and data-quality metadata.
5. User can optionally confirm or dismiss the event.
6. Backend receives only the minimum necessary event payload.
7. Backend clusters nearby events and calculates confidence.
8. Dashboard shows candidate hazards and evidence.

## 7. Hazard model for MVP
Initial event classes:
- Pothole / severe surface impact candidate
- Speed-bump / abrupt vertical movement candidate
- Rough-road segment candidate
- Sudden braking anomaly (context signal, not necessarily a road defect)
- Road-obstacle candidate only when supported by future visual detection work

Important: an event is a **candidate hazard**, not a verified physical defect, until corroborated.

## 8. Risk / confidence principles
Risk must be explainable. Inputs may include:
- event severity
- GPS accuracy
- vehicle speed
- repetition count
- number of distinct trips/users
- temporal recency
- spatial clustering quality
- optional camera corroboration

No black-box risk score is allowed in the MVP if its output cannot be explained to the user.

## 9. Functional requirements
### Mobile
- explicit trip start/stop
- permission handling
- foreground telemetry capture
- local buffering during network loss
- battery-conscious sampling
- event timeline
- event confirmation/dismissal
- privacy controls

### Backend
- authenticated event ingestion
- schema validation
- idempotent event handling
- geospatial clustering
- confidence calculation
- rate limiting
- audit logging for administrative actions

### Dashboard
- map view
- road-segment hazard clusters
- confidence and evidence display
- filters by class, confidence, recency
- event drill-down
- demo mode using synthetic/replayed data

## 10. Quality requirements
- Tests for every core domain rule
- Deterministic replay of synthetic telemetry
- Clear error states
- Accessibility-conscious UI
- Secure defaults
- No sensitive raw telemetry retention beyond documented necessity

## 11. Privacy requirements
- Collect only data necessary for the MVP.
- Do not upload raw microphone data.
- Do not upload continuous raw camera streams.
- Camera processing, if later introduced, should prefer on-device inference and send event metadata rather than frames.
- Strip or avoid direct identifiers from telemetry records.
- Publish retention and deletion behavior before field testing.

## 12. Safety boundaries
RoadShield is decision support, not a guarantee of safety. It must never claim that a route is safe, that an accident will occur, or that a driver may ignore traffic laws because RoadShield scored a route highly.

## 13. MVP success metrics
The initial product experiment should measure:
- successful trip capture rate
- event detection repeatability
- location accuracy
- candidate-event confirmation rate
- false-positive rate under a controlled test protocol
- clustering consistency
- end-to-end latency
- battery impact during a normal trip

These are measurement targets, not pre-claimed results.
