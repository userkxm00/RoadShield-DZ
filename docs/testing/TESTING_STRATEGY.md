# RoadShield DZ — Testing Strategy

## Purpose
Testing is evidence that a behavior is correct enough for its current gate. A green test suite never replaces product or field validation.

## Test layers

### 1. Domain unit tests
Use for deterministic logic such as:
- sensor normalization;
- unit conversion;
- coordinate validation;
- candidate-event detection;
- corroboration rules;
- confidence calculations.

### 2. Replay / fixture tests
Sensor and geospatial logic must be testable from deterministic fixtures without a physical vehicle.

Replay tests must verify:
- identical input produces identical output;
- detector version is recorded;
- ordering/duplicate behavior is explicit;
- invalid data is rejected safely.

### 3. Integration tests
Use at system boundaries such as:
- ingestion API;
- database persistence;
- geospatial queries;
- dashboard data contracts.

### 4. Mobile/device validation
Use controlled manual tests for:
- sensor permissions;
- missing sensors;
- real GPS accuracy;
- sensor availability;
- battery/data impact;
- phone-placement variability.

### 5. Security and privacy tests
Verify:
- input validation;
- authorization boundaries when introduced;
- rate limiting where introduced;
- telemetry sanitization;
- retention behavior;
- secret handling.

## Required checks before merge
The applicable project commands will be defined with the selected stack in Phase 2. Each implementation task must run the smallest complete set of relevant checks, including tests and type/lint/build checks when available.

## Test evidence
Each non-trivial behavior should leave reproducible evidence in one of:
- automated test output;
- deterministic fixture/replay;
- sanitized experiment dataset;
- controlled device test log;
- documented limitation or failed hypothesis decision.

## Safety rule
Tests must never be presented as proof of accident prediction or guaranteed safety. They validate implementation behavior and research hypotheses within their measured scope.
