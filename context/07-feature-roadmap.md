# 07 — Feature Roadmap

This roadmap is a planning proposal, not proof that any feature exists. The order may change after dependency and research review. Use stable IDs; do not copy conflicting historical feature numbers from the old repository without mapping them explicitly.

## Foundation
- F00 Repository and engineering foundation: clean scripts, tests, lint/typecheck/build, environment validation, CI and dev documentation.

## Core platform
- F01 Identity and role access: secure login/session, HR/Learner authorization matrix, server-side authorization tests.
- F02 Assessment and rubric management: CRUD, validation, versioning and immutable snapshot semantics where required.
- F03 Assignment and learner access: assignment windows, audience and ownership constraints.
- F04 Attempt/submission lifecycle: server-authoritative lifecycle, timing rules, idempotent submit, persistence and recovery.
- F05 AI grading proposal: only if approved by thesis scope; store proposal and evidence separately from final HR score.
- F06 RubroRAG feedback: grounded feedback, retrieved evidence/metadata, explicit pipeline version and failure states.
- F07 HR review/final decision/release: review, corrections, approval, release and learner visibility rules.
- F08 Personalized learning path: recommendations grounded in assessment evidence and approved learning resources.
- F09 Reporting and export: scoped aggregation, filters, pagination, safe export.
- F10 Audit and operations: high-value action trail, diagnostics, retention and recovery.
- F11 UX/accessibility/performance hardening: responsive flows, WCAG-oriented checks, load/performance assessment.
- F12 Deployment, backup and recovery: chosen hosting topology, secrets, migrations, backup restore exercise.
- F13 Research evaluation harness: versioned inputs/configuration, reproducible metrics, separation from product/demo records.
- F14 UML Diagram Workspace: explicit user-requested feature. Use context/specs/F14-uml-diagram-workspace.md. Confirm target user, threat model, and value before wiring it into core learner workflows.

## Feature completion contract

A feature is not Done until:
1. Scope and acceptance criteria are satisfied.
2. Tests cover success, validation, failure and authorization cases where relevant.
3. The relevant lint/typecheck/build and integration checks pass, or the exception is documented.
4. A reviewer inspected diff and data/security impacts.
5. Browser verification is recorded for user-facing flows.
6. Context/spec/status/ADR updates are committed.
7. No secret, private data or unrelated change is included.
