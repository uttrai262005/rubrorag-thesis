# Codex Prompt Template — One Feature at a Time

Implement only: [FEATURE ID AND NAME]

## Read first

- AGENTS.md
- context/01-project-overview.md
- context/02-architecture.md
- context/03-code-standards.md
- context/04-ai-workflow-rules.md
- context/06-progress-tracker.md
- context/09-quality-gates.md
- context/10-testing-strategy.md
- context/11-security-and-privacy.md
- The exact feature spec: [PATH]
- Any related ADRs and callers/tests

## Rules

1. Inspect actual current implementation before proposing edits.
2. Restate scope, acceptance criteria, assumptions, risk and expected files before coding.
3. Do not implement unrelated future features.
4. Do not change research logic, rubric, model/prompt settings, thresholds, or evaluation protocol unless the feature spec and an approved ADR say so.
5. Do not claim a check passed unless you ran it and observed the result.
6. Do not run destructive database commands or use real private data.
7. Do not commit or push; report the suggested commit message only.

## Required output at completion

- Exact behavior implemented and files changed.
- Acceptance criteria matrix with evidence.
- Exact commands run and outcomes.
- Authorization/security/error paths tested.
- Migration/data effect.
- UI/browser/accessibility checks actually performed.
- Known gaps, assumptions, and not-run checks.
- Required updates to spec/progress/ADR.
- Suggested commit message.

If acceptance criteria cannot be met, state what is missing instead of weakening the criteria silently.
