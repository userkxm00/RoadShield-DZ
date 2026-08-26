# RoadShield DZ — G2 Technology Stack Options

## Status
Preparation only. No option is approved until Gate 1 records PASS/PROCEED and the evidence supports the decision.

## Decision criteria
1. Fast MVP delivery.
2. Reliable Android sensor access.
3. Deterministic replay/testability.
4. Low operational cost.
5. Strong geospatial support.
6. Maintainability with AI-assisted development.
7. Open-source friendliness and low vendor lock-in.
8. Privacy/security controls.
9. Ability to scale from prototype to a serious pilot.

## Mobile candidates

### Option A — Kotlin + Jetpack Compose
**Strengths**
- Native Android sensor/location APIs.
- Precise control over lifecycle, permissions, foreground services, and battery behavior.
- Strong fit for a sensor-heavy MVP.

**Risks**
- Android-only implementation cost.
- More platform-specific code.

**Assessment:** Strong candidate for the first sensing MVP if Android is the only required mobile target.

### Option B — Flutter
**Strengths**
- Fast UI development.
- Cross-platform potential.
- Good ecosystem.

**Risks**
- Native sensor/background behavior may require platform channels and careful testing.
- More layers between domain logic and sensors.

**Assessment:** Good product/UI option; needs evidence that sensor capture and background constraints remain reliable enough.

### Option C — React Native
**Strengths**
- Familiar web-oriented ecosystem.
- Fast UI iteration.

**Risks**
- Sensor/background/native integrations add complexity.
- Less attractive for the smallest sensor-first vertical slice.

**Assessment:** Not preferred for the initial sensing core unless project constraints change.

## Backend candidates

### Option A — TypeScript + Fastify/Nest-like layered service
- Strong typing and contract sharing.
- Good fit for rapid iteration.
- Easy integration with validation and OpenAPI.

### Option B — Python + FastAPI
- Excellent fit for scientific/data processing.
- Simple API development.
- Easy future ML integration.

### Option C — Rust service
- Strong performance and safety.
- Higher implementation complexity for the first MVP.

**Preliminary assessment:** TypeScript or Python should be compared after G1; Rust is better reserved for proven performance needs.

## Database candidates

### PostgreSQL + PostGIS
Preferred candidate because RoadShield is fundamentally geospatial. It supports spatial indexing, radius/area queries, temporal queries, and mature relational integrity.

### Alternative
SQLite/GeoPackage may be useful for local/offline replay, but not as the authoritative multi-observation backend once a shared dataset is needed.

## Mapping candidates
- MapLibre-based stack for low lock-in.
- OpenStreetMap-compatible data sources subject to license/attribution requirements.
- Commercial maps only if a later requirement proves their value.

## Default preparation direction
The architecture should remain:

`mobile sensing → deterministic domain core → versioned event contract → ingestion → PostgreSQL/PostGIS → corroboration engine → query API → dashboard`

This is a preparation baseline, not an approved final stack.
