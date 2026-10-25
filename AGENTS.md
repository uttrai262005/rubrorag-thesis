# Repository Instructions for Codex

## Mandatory reading

Before a task, read:
1. This file.
2. context/01-project-overview.md.
3. context/02-architecture.md.
4. context/03-code-standards.md.
5. context/04-ai-workflow-rules.md.
6. context/06-progress-tracker.md.
7. The exact feature spec named by the user.
8. Any ADR and testing/security documents affected by the task.

Do not read or summarize the entire repository indiscriminately if focused inspection is sufficient. Search call sites before changing shared code.

## Scope control

- Implement only the requested feature and necessary tests.
- Do not opportunistically refactor unrelated files.
- Do not modify rubric wording, research prompts, model settings, thresholds, retrieval strategy, ground-truth labels, or evaluation protocol without explicit approval and an ADR.
- Never migrate, delete, reset, seed, or overwrite a database containing user/research data without explicit approval and a verified backup.
- Never introduce real credentials. Use a cleaned .env.example.
- Never add a paid service or dependency without explaining why it is needed, its cost/lock-in implications, and an alternative.
- For every uncertain requirement, list the ambiguity, evidence, safe default, and impact. Do not fabricate product behavior.
- Keep HR final authority over final scores and publication.
- Keep AI grading proposals, RubroRAG feedback, HR-approved results, and learner-released results as distinct concepts.

## Workflow for every feature

1. Inspect requirements, current code, callers, data model, permissions, and tests.
2. Summarize scope, assumptions, risks, files likely to change, and a test plan before implementation.
3. Implement the smallest coherent change.
4. Add or update automated tests for success, validation, authorization, failures, and boundary cases.
5. Run the checks that exist in the repository; do not invent npm scripts or claim unrun checks passed.
6. Inspect git diff, git diff --check, and git status.
7. Report exact commands and pass/fail outcomes. Explicitly list checks not run.
8. Update the relevant spec, context/06-progress-tracker.md, and ADR if a decision changed.
9. Do not commit or push unless the user explicitly asks.

## Quality and architecture

- Prefer clear module boundaries and simple designs that can be tested.
- Validate input at trust boundaries; authorize every sensitive server-side operation.
- Do not rely on hidden UI controls as authorization.
- Preserve data integrity with database constraints and transactions when appropriate.
- Use structured, sanitized errors; do not leak secrets, prompts, raw private answers, or stack traces.
- Use server-side rendering by default where suitable; add client-side code only for real interaction.
- Provide accessible labels, keyboard operation, focus visibility, loading, empty, error, and success states.
- Do not mark a feature Done until its acceptance criteria and evidence are recorded.
