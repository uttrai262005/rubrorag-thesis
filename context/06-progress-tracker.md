# 06 — Progress Tracker

Last updated: repository starter pack creation.
Overall status: Not started — no product implementation has been verified in this new repository.

## Status definitions

- Not started: no implementation.
- In progress: active changes, incomplete acceptance criteria.
- Implemented: code exists; verification may still be pending.
- Verified: all feature acceptance criteria have evidence, checks pass, and review completed.
- Blocked: dependency or unresolved decision prevents safe progress.
- Deferred: explicitly postponed with reason.
- Done: verified and accepted; documentation and status updated.

## Initial gate

- [ ] Read the approved thesis statement, assignment/rubric, source paper and research-data restrictions.
- [ ] Audit the source repository and identify reusable research pipeline interfaces; do not copy old code blindly.
- [ ] Establish a clean repository and secret-safe .gitignore.
- [ ] Confirm runtime versions and dependency-manager choice.
- [ ] Decide auth/session implementation, app/AI deployment shape, vector-store management, and data boundaries through ADRs.
- [ ] Create CI checks only for scripts that exist and can run reproducibly.
- [ ] Complete F00 foundation before product feature implementation.

## Feature status

| ID | Feature | Status | Evidence / notes |
|---|---|---|---|
| F00 | Repository and engineering foundation | Not started | First Codex task |
| F01 | Identity and role access | Not started | Requires auth/role ADR |
| F02 | Assessment and rubric management | Not started | Must preserve approved rubric |
| F03 | Assignment and learner access | Not started | Define access policy |
| F04 | Assessment attempt and submission lifecycle | Not started | Server-enforced timing/state |
| F05 | AI grading proposal (if approved scope) | Blocked on scope | Must be separate from HR final score |
| F06 | RubroRAG grounded feedback | Not started | Must validate evidence traceability |
| F07 | HR review, final decision and release | Not started | Human authority invariant |
| F08 | Personalized learning path | Not started | Ground recommendations in approved sources |
| F09 | Reports and export | Not started | Authorization and privacy |
| F10 | Audit/operations/recovery | Not started | Scope from real risks |
| F11 | UX/accessibility/performance hardening | Not started | Verify actual browser flows |
| F12 | Deployment and backup/recovery | Not started | Select target before deployment design |
| F13 | Research evaluation/reproducibility harness | Not started | Frozen data/config/version protocol |
| F14 | UML Diagram Workspace | Planned | User-requested; scope specified in dedicated spec |

## Decision log

For decisions, create an ADR in context/decisions/. Record context, alternatives, choice, tradeoffs, status, and date. Never silently overwrite an earlier decision; mark it superseded and link the replacement.
