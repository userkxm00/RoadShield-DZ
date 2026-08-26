# RoadShield DZ — Security & Privacy Baseline

## Security objectives
RoadShield processes location and sensor telemetry. Security and privacy are product requirements, not a later hardening step.

## Data minimization
Collect only what is required to create and validate a road event:
- event timestamp or bounded time information;
- approximate event location with documented precision;
- motion-derived event features;
- speed/context features where needed;
- device/app capability metadata required for normalization.

Do not collect by default:
- contacts;
- microphone/audio;
- address book;
- unnecessary account profile data;
- continuous raw camera video uploads;
- direct personal identifiers inside telemetry events.

## Mobile privacy
- Explain why location and motion permissions are needed.
- Provide explicit trip start/stop controls.
- Minimize background collection.
- Prefer local processing and local buffering.
- Allow deletion of locally buffered telemetry.
- Never silently record audio.

## Camera policy
Camera processing is optional and future-facing. The default design is on-device inference with event metadata sent upstream. Raw frames must not be uploaded or retained unless a specific, documented validation experiment requires it and the user explicitly consents.

## API security
- TLS in production.
- Authentication for ingestion.
- Server-side schema validation.
- Rate limiting.
- Idempotency for event uploads.
- Authorization boundaries for dashboards and administrative actions.
- Strict CORS/origin policy where applicable.
- Safe error responses that do not leak secrets or internal state.

## Secrets
- No API keys, tokens, passwords, signing keys, or `.env` files containing secrets in Git.
- Use environment variables or a supported secret manager.
- Rotate compromised credentials immediately.

## Logging
Logs must avoid sensitive payloads. Do not log raw location histories or raw media. Security/audit logs should capture administrative actions without exposing secrets.

## Retention
A documented retention policy must exist before field testing. Event summaries should have the shortest practical retention period that still supports product validation.

## Threat areas
At minimum consider:
- fake/spam telemetry;
- replayed events;
- location poisoning;
- account takeover;
- abusive API clients;
- unauthorized dashboard access;
- correlation attempts against user trips;
- dependency and supply-chain vulnerabilities;
- accidental publication of private test data.

## Security gate
No real-world field trial is considered ready until the project has:
1. permission/privacy flows;
2. authenticated ingestion;
3. secret scanning;
4. dependency scanning;
5. input validation;
6. documented retention/deletion behavior;
7. a reproducible process for removing test data.
