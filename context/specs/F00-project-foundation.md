# F00 — Project and Engineering Foundation

- Status: Ready for implementation after repository decisions are reviewed
- Dependencies: none
- Goal: Create a clean, reproducible application foundation without implementing unrelated product features.

## In scope

1. Confirm supported Node.js/Python versions and package managers from current official docs.
2. Create or verify the web and AI-service project layout only after recording the approved boundary.
3. Establish formatting, linting, strict type checks, test runner, and a production build command.
4. Add environment validation and sanitized environment examples.
5. Add a health/readiness endpoint that does not reveal credentials or internal state.
6. Establish CI checks for scripts that actually exist.
7. Document local setup and safe database/migration workflow.
8. Ensure secret-safe .gitignore and no real private data in the initial commit.
9. Add an architecture decision for authentication and record the selection rationale before implementing auth.

## Out of scope

- Implementing all roles, assessment flows, AI grading, feedback, reports or F14.
- Rewriting the research pipeline.
- Deploying to a paid cloud or adding paid services.
- Loading real datasets or committing database files.
- Claiming end-to-end readiness before test infrastructure exists.

## Acceptance criteria

- AC-01: A new developer can follow README setup steps on a clean supported machine.
- AC-02: Dependency installation is reproducible with a committed lockfile.
- AC-03: Lint, typecheck, unit tests and build commands are documented and runnable; if a gate is not yet applicable, the reason is documented.
- AC-04: Environment variables are validated at startup and no secrets are committed.
- AC-05: The app and AI service, if both initialized, have explicit boundary documentation and no direct AI-service writes to the app database.
- AC-06: CI runs the defined quality gates and reports failures.
- AC-07: A fresh test database can be initialized with migrations without touching user data.
- AC-08: The initial diff contains no unrelated product features or speculative infrastructure.

## Verification

Use exact scripts defined in package/config files. Record versions and command outputs. Run a fresh-install check where feasible. Review the git diff and scan for secrets before commit.
