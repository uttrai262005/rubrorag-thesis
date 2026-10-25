# 01 — Project Overview

Status: Working baseline; verify against the final approved thesis and source materials before treating every statement as frozen.

## Thesis direction

Working thesis title: “Ứng dụng Agentic AI đánh giá năng lực và cá nhân hóa lộ trình đào tạo nhân sự vận hành Thương mại điện tử”.

The product should help HR assess competency evidence and support learners with actionable, evidence-grounded feedback and training recommendations. It must remain clear which decisions are made by deterministic application logic, AI proposals, the RubroRAG research pipeline, and HR.

## Primary actors

- HR / authorized reviewer: prepares and manages assessments, monitors submissions, reviews AI-supported output, determines final scores, approves publication, and views reports.
- Learner: receives assigned assessments, completes and submits work, and views only released outcomes and permitted learning recommendations.
- System administrator / researcher: maintains system configuration, research runs, knowledge assets, and operational evidence only where an explicitly authorized workflow requires this role.

The exact role matrix and any separate researcher role must be finalized in the relevant spec.

## Proposed in-scope capabilities

1. Authentication, role-based authorization, and secure sessions.
2. Assessment/rubric management with versioning and assignment.
3. Learner assessment attempts, timing rules, answer validation, and submission lifecycle.
4. AI-assisted grading proposal if supported by the approved thesis scope.
5. RubroRAG retrieval-grounded feedback and personalized learning path.
6. HR review, final score entry/confirmation, and controlled result release.
7. Reports and export with explicit data permissions.
8. Audit trail for sensitive actions and AI pipeline version/evidence metadata.
9. Research evaluation tools that preserve reproducibility.
10. Requested UML Diagram Workspace as feature F14; its actor, purpose, and scope must be confirmed in its spec before implementation.

## Out of scope unless separately approved

- Arbitrary AI decisions that bypass HR.
- Public multi-tenant SaaS billing, organization provisioning, or collaboration features without a demonstrated need.
- Replacing the research pipeline merely to modernize technology.
- Unreviewed imports of raw personal or classroom data.
- Claims that an assessment improves employee performance unless supported by evaluation evidence.

## Success criteria at product level

- Correct role boundaries and no cross-learner data leakage.
- Assessment and submission states are explicit and enforced server-side.
- HR can inspect, correct, and approve outcomes before learners see them.
- AI output is traceable to versioned inputs/configuration and cannot silently overwrite HR decisions.
- Critical user flows have automated tests plus browser verification.
- The system is accessible, responsive, observable, and reproducible enough for academic demonstration.
- Research claims are sourced to the actual paper/dataset and not inferred from the app alone.

## Decisions still open

- Final deployment target and budget.
- Exact authentication library and account lifecycle.
- Exact rubric/assessment schema and versioning requirements.
- Whether AI scoring is in the application scope or only an experimental module.
- Where research data may be stored and who is allowed to access it.
- Meaning and user-facing scope of F14 UML workspace.
