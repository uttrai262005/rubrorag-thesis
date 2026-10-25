# PlantUML diagrams

All files in this folder are editable text sources. The current diagrams are proposals, not verified as-built architecture.

## Rules

- Label each diagram as Proposed, As-Is, or To-Be.
- After each architecture-changing feature, review affected diagrams against the actual code and update the source in the same feature branch.
- Keep data ownership and trust boundaries visible.
- Do not add services, databases, events, or external providers that have not been decided.
- Render in CI or locally with a pinned, maintained PlantUML version where practical.
- Treat the UML Diagram Workspace (F14) as a separate product feature. These source-controlled documentation diagrams do not prove that F14 has been implemented.

Suggested initial set: system context, component architecture, critical assessment/review sequence, and data model/ER diagram after schema is approved.
