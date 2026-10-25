# 03 — Code Standards

## General

- Optimize for correctness, clear ownership, readability, and testability before clever abstractions.
- Keep a feature's domain behavior in an explicit module/service; keep UI components focused on presentation and interaction.
- Avoid giant files, deep prop chains, duplicate business logic, magic values, and broad catch blocks.
- Add dependencies only when they provide material value; document the reason and maintenance/cost risk.

## TypeScript / Next.js

- Enable strict TypeScript checks and avoid any unless a narrow, documented boundary requires it.
- Validate external input at runtime with a maintained schema validation library.
- Separate browser-safe modules from server-only modules. Never import secrets or server database clients into client bundles.
- Keep authorization in server-side domain/application boundaries.
- Avoid placing database calls in reusable visual components.
- Handle pending, invalid, empty, denied, and unexpected states explicitly.
- Prefer semantic HTML, proper labels, keyboard support, and visible focus.
- Use safe error messages for users and structured context for server logs; do not expose stack traces in production.

## Python / FastAPI

- Use type annotations and explicit request/response models.
- Keep the API adapter separate from the core pipeline.
- Do not import web application Prisma/database concerns into the AI service.
- Validate input size and type, set bounded timeouts, and handle upstream/model failures explicitly.
- Avoid logging raw learner answers or sensitive data by default.
- Make pipeline versions and relevant run configuration observable.

## Database

- Treat schema and migrations as version-controlled contracts.
- Avoid hidden writes and implicit destructive operations.
- Use transactions for multi-step state changes that must succeed or fail together.
- Add constraints/indexes based on query and integrity requirements; avoid speculative indexing.
- Use pagination for unbounded lists.

## Naming / formatting

- Use names that communicate domain intent.
- Follow one automated formatter and linter per language.
- Avoid mixed languages in identifiers; user-facing content may be Vietnamese.
- Keep rubric wording and criteria exactly as approved unless a documented change is authorized.

## Dependencies

Before adding a major dependency, record purpose, active maintenance, license, version compatibility, security footprint, lock-in, and what simpler option was considered. Pin reproducibly through lockfiles.
