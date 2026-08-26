# RoadShield DZ — System Architecture v1

## Architecture goals
- local-first safety-critical sensing
- privacy minimization
- offline tolerance
- deterministic core logic
- replaceable AI components
- clear boundaries between mobile, API, risk engine, and dashboard
- testability before scale

## Logical architecture

```text
+----------------------- Mobile App -----------------------+
| Trip Controller                                         |
|   |                                                     |
|   +-- GPS Collector                                     |
|   +-- Motion Collector (accelerometer/gyro)             |
|   +-- Local Event Detector                              |
|   +-- Optional On-device Vision                         |
|   +-- Local Event Buffer                                |
|   +-- Consent / Privacy Controls                        |
+------------------------|---------------------------------+
                         |
                         | signed/validated event payloads
                         v
+---------------------- API / Ingestion -------------------+
| Auth | Rate Limit | Schema Validation | Idempotency       |
+------------------------|---------------------------------+
                         v
+------------------------- Data ---------------------------+
| PostgreSQL/PostGIS (target) | object storage only if     |
|                            | justified and minimized    |
+------------------------|---------------------------------+
                         v
+---------------------- Risk Engine -----------------------+
| Geospatial clustering                                |
| Event normalization                                   |
| Confidence scoring                                    |
| Road-segment aggregation                              |
| Temporal decay / recency                              |
| Replayable evaluation                                 |
+------------------------|---------------------------------+
                         v
+---------------------- Dashboard ------------------------+
| Map | Filters | Evidence | Segments | Demo mode          |
+---------------------------------------------------------+
```

## Recommended technology direction
The exact stack is a Gate-2 decision. Default preference is for mature, open-source, low-cost components.

Candidate direction:
- Mobile: Android-first, Kotlin or a cross-platform framework only if sensor access remains reliable and native performance is acceptable.
- Backend: TypeScript/Node.js or Python, subject to team/code-agent reliability.
- Database: PostgreSQL + PostGIS.
- Dashboard: React/Next.js or equivalent.
- CI: GitHub Actions.
- Containerization: Docker for reproducible development/testing.

No technology is locked until Gate 2.

## Event pipeline
1. Capture sensor sample.
2. Normalize timestamps and units.
3. Apply local filtering/windowing.
4. Detect candidate event.
5. Attach quality/context metadata.
6. Store locally.
7. Upload when connectivity is available.
8. Validate and deduplicate server-side.
9. Cluster geographically/temporally.
10. Recompute confidence.
11. Render evidence and map state.

## Data minimization
The backend should prefer event summaries over raw streams. Raw sensor streams should remain local or be retained only for a short, documented validation workflow. Raw camera frames are out of scope for the MVP backend.

## Failure modes
- GPS unavailable: event may be stored locally but must not be placed on the map until location quality is sufficient.
- Network unavailable: buffer locally and retry with bounded backoff.
- Sensor unavailable: degrade gracefully and mark data quality.
- Duplicate upload: idempotency key prevents duplicate events.
- Clock skew: use monotonic duration where possible and validate timestamps.
- Low battery: reduce sampling or notify the user.

## AI boundary
AI is optional and replaceable. No paid AI API may be a hard dependency of the MVP. Candidate local AI uses include:
- lightweight on-device visual hazard detection
- classification of motion windows after enough labelled data exists
- anomaly detection experiments

The core product must remain useful with deterministic signal processing and statistical/geospatial methods.

## Security baseline
- TLS in transit
- authenticated ingestion
- scoped admin access
- secret values only through environment/secret managers
- no secrets committed to Git
- input validation at every boundary
- dependency scanning in CI
- audit log for privileged actions

## Architecture decision rule
Do not add a component because it is fashionable. A component must have a measurable product or engineering reason and a documented trade-off.
