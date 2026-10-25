# Codex Bootstrap Prompt — Start the New Thesis Repository

You are the implementation assistant for a thesis-grade application. Follow AGENTS.md strictly.

## Task

Work only on F00 in context/specs/F00-project-foundation.md. Do not implement the future product roadmap in this task.

## Required initial inspection

1. Read AGENTS.md.
2. Read context/01-project-overview.md through context/11-security-and-privacy.md, context/07-feature-roadmap.md, the F00 spec and ADR-0001.
3. Inspect the current workspace and all relevant files before modifying them.
4. Treat docs/diagrams/*.puml as proposed diagrams, not verified code architecture.
5. Identify what is known from the approved thesis/source materials and what is still an open decision.
6. Check current official documentation for any runtime/framework/library versions you propose. Do not invent version numbers or use outdated defaults.

## Before coding, report

- Proposed directory structure and reason for each boundary.
- Exact stack/version/package-manager recommendation with official-source links and tradeoffs.
- Authentication approach recommendation (do not implement auth in F00).
- Web-to-Python-service contract boundary.
- Database and local-development approach.
- Dependency and deployment risks/costs.
- Open decisions requiring human approval.
- F00 acceptance criteria and exact test commands that will exist after the work.

If a material decision conflicts with source documents or is not inferable, record it as an open decision and stop before implementing the affected decision. Otherwise, use the simplest reversible proposal and document it in an ADR.

## Implement only F00

Establish a reproducible project foundation, quality checks, environment validation, safe example environment files, clean module skeleton and CI checks that correspond to existing scripts. Add no secrets or raw research data. Do not copy the old repository's implementation wholesale. Do not install paid services or add Redis, queues, realtime collaboration or blob storage without an approved need.

Do not implement authentication, assessment management, learner workflows, AI scoring, feedback, reporting or F14 yet.

## Verification

Run the exact formatter, lint, typecheck, unit tests and production build created/confirmed by the project. Test fresh setup where feasible. Inspect git diff --check, git status and the full diff. Check no .env, credentials, database files, private research data or unrelated changes were added.

Do not commit or push.

## Final response format

1. Summary of F00 changes.
2. Files created/changed.
3. Decisions made and ADR links.
4. Exact commands run and their actual results.
5. Acceptance criteria as PASS / FAIL / NOT VERIFIED with evidence.
6. Security/data/migration implications.
7. Browser verification (only if actually performed).
8. Remaining open decisions and exact recommended next feature.
