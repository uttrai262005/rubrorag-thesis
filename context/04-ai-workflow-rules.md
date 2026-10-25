# 04 — AI Workflow Rules

## Rule zero

The AI agent is an implementation assistant, not the owner of product scope, research truth, or academic claims.

## Required task protocol

1. Identify the requested feature spec and related architecture/ADR.
2. Inspect existing implementation, call sites, tests, and actual package scripts.
3. Restate scope, acceptance criteria, assumptions, risks, and intended files before editing.
4. If essential requirements contradict each other or the approved research material, stop before coding the affected behavior and report the contradiction.
5. Implement the smallest cohesive scope.
6. Test behavior and failure paths, including authorization where applicable.
7. Inspect the final diff and repository status.
8. Report commands run, exact outcomes, gaps, and evidence.
9. Update progress and decision documents.
10. Ask before committing, pushing, destructive database actions, or changing research methods.

## Forbidden shortcuts

- No fake test results or claims of visual verification without running it.
- No arbitrary upgrades of major frameworks during unrelated features.
- No changing research prompt/model/threshold/rubric to make results look better.
- No treating generated examples as real research data.
- No automatically committing .env files, database files, private raw data, credentials, or browser profiles.
- No applying broad formatting or refactoring across unrelated modules.
- No implementing all future features in one batch.
- No creating UI controls that do not have real, tested actions.
- No calling a feature “done” because the page renders.

## Reporting format

For each task report:
- Scope implemented.
- Files changed and why.
- Acceptance criteria: pass/fail/not verified.
- Tests and exact commands/results.
- Browser checks actually performed.
- Migration/data impact.
- Security/authorization considerations.
- Known gaps and next action.
- Whether a commit or push was performed (normally no, unless explicitly requested).

## Research discipline

If a requirement depends on a paper, rubric, dataset, architecture decision, or legal/security claim, cite the exact source/section internally. If the source does not support it, label it as an assumption/open decision. Web research can inform an engineering choice but cannot silently overwrite the thesis's source material.
