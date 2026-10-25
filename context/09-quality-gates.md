# 09 — Quality Gates

## Before implementation

- Feature spec has unambiguous scope, assumptions, actors, permissions, failure cases and acceptance criteria.
- Data model/API changes have been identified.
- Dependencies and infrastructure requirements are justified.
- Security/privacy and data migration impact are considered.

## Before accepting a feature

- [ ] Acceptance criteria mapped to tests/evidence.
- [ ] Formatter/linter passed.
- [ ] Strict typecheck passed where applicable.
- [ ] Unit tests passed.
- [ ] Integration/contract tests passed for touched boundaries.
- [ ] E2E/browser verification passed for critical user-visible workflows.
- [ ] Accessibility keyboard/focus/labels/contrast checks completed where relevant.
- [ ] Build passed.
- [ ] Database migration reviewed and tested on disposable data if applicable.
- [ ] Authorization verified at server boundary.
- [ ] Error/loading/empty/expired states checked.
- [ ] No secret, raw private data, generated browser profile or accidental binary committed.
- [ ] Diff reviewed; unrelated changes removed.
- [ ] Documentation and progress tracker updated.

## AI-related gates

- Input and output schemas are validated.
- AI failures/timeouts do not silently produce a false success.
- The application records the relevant pipeline/model/prompt/index version as allowed.
- Evidence citation/grounding claims are tested against actual returned evidence.
- AI output never silently overwrites an HR-owned final score.
- Research metrics are computed by a reproducible harness, not manually fabricated.
- Evaluation set does not leak into prompt tuning or training unless the protocol explicitly allows it.

## Release gate

A green test suite is necessary but not sufficient. Record environment, test dataset, exact commands, actual browser checks and known limitations. Never claim full security, accessibility or research validity based solely on automated tests.
