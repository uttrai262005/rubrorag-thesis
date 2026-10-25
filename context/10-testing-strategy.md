# 10 — Testing Strategy

## Layers

- Unit tests: pure domain rules, validators, state transitions, calculations, mapping.
- Component tests: accessible rendering, interactions, validation messages, loading/error/empty states.
- Integration tests: database constraints, service modules, authorization policies, AI-service contracts, transaction behavior.
- E2E tests: HR and learner critical flows in a real browser against an isolated test database.
- Contract tests: web-to-FastAPI request/response schema, timeout, malformed response and service failure behavior.
- AI evaluation tests: pinned minimal fixtures for deterministic validation and a separate controlled evaluation run for stochastic/model-dependent behavior.
- Operational tests: migration on fresh/test DB, backup restore exercise, health checks and logging redaction.

## Critical flows to test

1. Unauthorized users cannot call protected mutations directly.
2. A learner cannot access another learner's submission or feedback.
3. An attempt cannot be submitted twice with conflicting state.
4. Server-side timing/deadline checks cannot be bypassed by manipulating the browser clock.
5. HR's final score is not overwritten by AI proposal or regenerated feedback.
6. Unreleased results are not visible to learners.
7. AI timeouts, empty results, schema drift and upstream failures produce explicit recoverable states.
8. Reports and exports apply the same authorization and scope as the underlying data.
9. Research evaluations use the intended versioned data/configuration and preserve raw outputs.

## Test data rules

Use isolated databases and synthetic fixtures by default. Never run automated tests against a personal or production database. Do not seed destructive demo content into a shared database. Make randomized test cases repeatable with controlled seeds where randomness is needed.

## Evidence

Record exact command, environment, dataset/fixture version, pass/fail, and a concise output summary. Browser verification must state browser and viewport/flow actually checked. Tests not run must be named explicitly.
