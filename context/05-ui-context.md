# 05 — UI Context

## Product design direction

Build a calm, highly legible, operational SaaS interface. The aim is not a fashionable screenshot; the aim is that HR can complete review tasks accurately and learners understand the assessment state without confusion.

Reference products for principles, not copying: Linear for focus and navigation; Stripe for dense business information and forms; Vercel for typography and consistent system states. Do not reproduce their logos, exact pages, or proprietary visual identity.

## Visual principles

- A consistent spacing scale, typography scale, border/radius scale, and semantic color tokens.
- Neutral surfaces; restrained accent colors; no decorative gradients as a substitute for hierarchy.
- Clear page title, context, primary action, and supporting metadata.
- Tables for comparable structured data; cards only where grouping materially helps.
- Use icons only when recognizable and accompanied by labels where meaning is not obvious.
- Use skeleton/loading patterns sparingly and correctly.
- No fake charts or meaningless dashboard KPIs.
- Do not add animation unless it communicates state; respect reduced-motion preferences.

## HR experience

Prioritize queues, status, filters, review and approval actions, rubric evidence, history, and bulk operations only when there is a demonstrated workflow need. Clearly distinguish AI suggestions from HR-owned decisions.

## Learner experience

Prioritize task instructions, deadline/timer, progress, answer entry, submit confirmation, and explicit result-release state. Prevent accidental loss where technically feasible. Do not reveal another learner's data.

## Interaction states

Every important feature must design and test:
- loading and disabled state
- empty state with a useful next step
- validation failure with field-level messaging
- permission denied
- expired or invalid lifecycle state
- server/network failure and safe retry behavior
- success confirmation
- keyboard-only navigation and visible focus

## Responsive / accessibility

Target WCAG 2.2 AA as an engineering target, with manual and automated checks. Verify keyboard flows, meaningful names, contrast, zoom/reflow, focus, reduced motion, and screen-reader semantics. A passing automated scan alone is not proof of full conformance.

## Implementation policy

Build shared components after identifying repeated patterns. Prefer accessible primitives over one-off hand-built controls. Choose the final component library only after verifying active maintenance, license, framework compatibility, and required interaction patterns. Do not make every page a grid of cards.
