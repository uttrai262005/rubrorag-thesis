# 02 — Architecture

Status: Proposed architecture; not yet verified against a clean, executable implementation.

## Architecture style

Start with a modular monolith for the web product plus a separate Python AI service where the existing RubroRAG pipeline requires Python. Avoid splitting the web into multiple services until an independent deployment, scaling, security, or reliability need is demonstrated.

## Proposed logical components

- Web presentation: Next.js App Router, TypeScript, accessible component system.
- Application/domain modules: identity/access, assessment, attempts/submissions, AI grading proposal, feedback, HR review/release, reports, audit.
- Persistence: PostgreSQL with Prisma migrations for application-owned transactional data.
- AI boundary: FastAPI service wrapping the approved RubroRAG pipeline.
- Retrieval/vector store: retain the existing ChromaDB/retrieval approach only after inspecting how the current pipeline builds and queries it.
- Tests/evaluation: web unit/integration/E2E checks plus independent AI evaluation harness and frozen evaluation data versions.

## Ownership boundaries

The web application owns user identity mapping, role authorization, assessment assignment, attempts, final HR score, publication status, reports, and business audit events.

The Python service owns the AI pipeline interface and retrieval/generation execution. It should not directly mutate application tables. If a workflow must write results, return a validated response to the web application, which records it through the authorized application layer.

Vector store data is not the transactional source of truth for scores, assignments, or result publication.

## Important domain distinctions

- AI score proposal != HR final score.
- RubroRAG feedback != AI score proposal.
- HR-approved result != learner-visible result until released.
- Research evaluation dataset != demo fixture != production/business data != knowledge base.
- Request accepted != AI task completed.
- A generated UML diagram != verified implementation architecture unless checked against code.

## API boundary

Create a versioned, validated contract between web and AI service. Define request/response schemas, timeouts, bounded input size, structured errors, correlation/task identifiers where needed, pipeline/model/prompt version metadata, and safe logging. Never rely on undocumented internal Python objects.

Do not implement long-running task infrastructure until actual latency, retry, cancellation, or workload requirements justify it.

## Persistence and migrations

Use explicit, committed migrations. Review generated SQL and test the migration on a disposable database. Never use schema synchronization as a substitute for a reviewable migration workflow once migration history exists. Never run destructive resets against real data.

Enforce invariants at both application and database levels where appropriate, such as unique assignment identifiers, valid lifecycle transitions, and foreign-key integrity.

## Authentication and authorization

Use a maintained authentication solution after comparing requirements, ecosystem compatibility, security maintenance, and cost. Do not hand-roll password hashing or token verification. Authorize every server mutation and protected read; UI hiding is not authorization. Default-deny unknown roles.

## Frontend rules

Prefer Server Components for server-rendered/read-oriented surfaces; isolate Client Components to interactions that need state or browser APIs. Do not call the application's own Route Handler from a Server Component if it can call the underlying server-side data/service directly.

Model loading, empty, error, success, disabled, expired, and unauthorized states explicitly.

## Proposed deployment model

Begin with a local reproducible development setup. Select hosting only after confirming database, AI service, vector store, file-storage, secret-management, and budget constraints. Do not assume that hosting a Next.js app also hosts a persistent Python/vector-store workload correctly.

## Architecture diagrams

Editable PlantUML sources live in docs/diagrams/. Current files are proposals. Update them after architectural decisions and review them against the actual code; label as-is and to-be separately.
