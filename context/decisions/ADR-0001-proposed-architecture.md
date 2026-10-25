# ADR-0001: Proposed application architecture

- Status: Proposed — approval required
- Date: 2026-10-25
- Context: The thesis combines role-based web workflows with an existing Python/RubroRAG research pipeline. Business state must be reliable, while research evaluation must be reproducible.
- Decision proposal: Start with a modular monolith for web/domain logic and a separately exposed Python service for the AI pipeline where required. Use PostgreSQL and Prisma for transactional app records if the hosting/education environment supports them. Retain the existing retrieval/vector technology until code and data are audited.
- Alternatives: single mixed Python/Node process; microservices for every domain; replace the AI pipeline with a new framework.
- Reasons: simple deployment boundary, explicit ownership, testable contracts, less operational complexity, avoids rewriting research internals merely to modernize the stack.
- Tradeoffs: two runtimes and service contract require local/dev orchestration; AI-service availability and versioning must be managed.
- Consequences: document API schema; add contract tests; keep app DB writes in web layer; review the proposal after source audit.
- Open questions: deployment target; authentication library; file storage; vector-store lifecycle; whether PostgreSQL is needed in early local development; retention and data policy.
