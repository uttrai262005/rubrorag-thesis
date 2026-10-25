# F14 — UML Diagram Workspace

- Status: Planned; user explicitly requested this feature
- Dependencies: F00 engineering foundation; F01 identity/access if exposed in the app
- Scope note: The approved product purpose needs review. The default proposal is a staff/admin-oriented workspace for creating, editing, previewing and exporting technical UML diagrams. It is separate from the repository's own architecture documentation. Do not expose to learners or claim automated code understanding without a separately approved requirement.

## User problem

Authorized staff need a controlled way to create and maintain understandable UML artifacts for architecture, workflows and technical documentation without manually editing images that drift from their source.

## Proposed first release

- Create a diagram with a title, diagram type, description, textual PlantUML source, owner, timestamps and version.
- Start from reviewed templates for use case, sequence, activity, class, component and deployment diagrams.
- Validate source syntax and show clear line-level errors.
- Preview the rendered diagram.
- Export SVG; add PNG only if the chosen rendering path is secure and tested.
- Save drafts and revisions with audit metadata.
- Search/list diagrams with pagination and enforce owner/role access.
- Store source text as the editable source of truth. Rendered outputs are derived artifacts.

## Not automatically included

- Arbitrary prompt-to-UML AI generation.
- Importing and executing uploaded code.
- Remote PlantUML includes or arbitrary URL fetches.
- Unlimited rendering, collaboration, live multi-user editing, or public sharing.
- Treating diagrams as verified truth without a review state.

## Security requirements

PlantUML input is untrusted. Use a maintained renderer with network access disabled or strict allowlisting, resource/time/size limits, no arbitrary filesystem access, and controlled temporary output. Reject remote includes and unsafe directives unless explicitly reviewed. Do not invoke shell commands by concatenating user input. Do not store SVG as trusted HTML without sanitization; prefer a safe preview approach and sanitize exports if necessary. Record renderer version and render errors.

## Acceptance criteria

- AC-01: Only authorized roles can create, edit, view, delete and export diagrams according to the approved permission matrix.
- AC-02: A user can create from a template, edit source, save a revision, reopen it and reproduce the preview.
- AC-03: Invalid syntax returns a helpful error and never destroys the saved last-valid source.
- AC-04: Valid source renders within configured resource limits; timeout or renderer failure is visible and recoverable.
- AC-05: Remote includes/unsafe external fetch paths are rejected or safely disabled.
- AC-06: SVG/PNG export, if enabled, matches the saved source revision and has a testable download path.
- AC-07: Cross-user access attempts are denied server-side and covered by tests.
- AC-08: Source and renderer versions are traceable; exported output cannot silently replace the source.
- AC-09: Keyboard navigation, accessible labels, focus states, loading/error/empty states and responsive layout are verified.
- AC-10: The feature is visually reviewed with actual rendered diagrams of varied size and complexity, not only a mocked screenshot.

## Test plan

Unit tests for source/metadata validation and authorization policy; integration tests for persistence/versioning; security tests for remote includes, oversized input, malformed source, SVG payloads and timeouts; E2E tests for create/edit/preview/save/export and denial flows.

## Open decisions

- Is this an end-user feature or a researcher/admin-only tool?
- Does the thesis require AI generation from natural language, or only author/edit/render PlantUML?
- Which diagram types are necessary for the thesis?
- Should diagrams persist in PostgreSQL or be versioned as files in Git?
- Which renderer/deployment method satisfies security, reliability and cost requirements?

No implementation begins until these open decisions have a documented safe default.
