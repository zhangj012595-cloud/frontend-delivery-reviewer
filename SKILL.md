---
name: frontend-delivery-reviewer
description: Use for frontend feature work, UI redesigns, dashboard/workbench changes, new pages, complex interactions, or any request where frontend quality, product fit, visual polish, responsive behavior, or delivery readiness matters. Runs a pre-implementation Solution Research Gate when needed, then a post-implementation Frontend Expert Review Gate with scoring, blockers, browser evidence, and pass/fail delivery criteria.
metadata:
  short-description: Frontend solution research and expert delivery review
---

# Frontend Delivery Reviewer

Use this skill whenever a task involves meaningful frontend work. It turns frontend delivery into a gated workflow:

```text
Requirement
-> Solution Research Gate
-> Implementation
-> Deterministic Checks
-> Browser Evidence
-> Frontend Expert Review
-> Fix Until Pass
-> Delivery
```

## Trigger Rules

Use the full workflow for:

- new pages, major modules, dashboards, workbenches, charts, data views, games, or multi-step flows
- redesigns or requests that mention poor interaction, bad layout, not beautiful, not polished, or "still looks the same"
- changes that affect information architecture, navigation, default states, or repeated UI patterns
- frontend work where the user expects a professional product surface

Use a lighter review for:

- small bug fixes, obvious local UI fixes, copy tweaks, small styling adjustments, or one-field changes

Skip only when the task is clearly non-frontend or purely backend.

## 1. Solution Research Gate

Before implementing, classify the research level:

- `Level 0`: no research. Small bug, copy, color, or local fix.
- `Level 1`: lightweight research. New local module, interaction state, layout adjustment, or component choice. Inspect the existing app and choose a pattern.
- `Level 2`: full research. New core workflow, page, dashboard/workbench, data visualization, or anything that could cause feature pile-up. Inspect the current product structure and, when useful, reference public examples, design systems, or GitHub projects.

For `Level 1` or `Level 2`, produce a short Solution Research Brief before coding. Use `references/solution-research-template.md`.

## 2. Implementation Rules

- Preserve the existing product language and component patterns unless the brief explicitly changes them.
- Remove or demote stale UI that conflicts with the chosen architecture.
- Define default state, empty state, loading/error state, and at least one key interaction path.
- Avoid adding decorative cards or sections just to expose a feature. Every visible module must have a workflow purpose.
- Keep the scope tied to the selected solution. Do not expand into unrelated features.

## 3. Deterministic Checks

Run the checks available in the project, such as:

- syntax check (`node --check`, framework compiler, or equivalent)
- lint/typecheck/build/test if configured
- backend/API tests when the UI depends on API shape
- `git diff --check`

Do not mark review passed if relevant checks were skipped without explanation.

## 4. Browser Evidence

For meaningful frontend work, inspect the actual rendered app when feasible:

- desktop around `1440x900`
- tablet around `768x1024`
- mobile around `390x844`
- core click path or state transition
- console errors and obvious network failures

If browser automation is not available, state that limitation and use the best available evidence, but do not overclaim visual certainty.

## 5. Frontend Expert Review Gate

After implementation, review against `references/frontend-review-rubric.md`.

Pass criteria:

- total score >= 85
- no blocker
- Requirement Fit, UX Flow, Visual Design, and Responsive Layout are each at least 75% of their category score
- deterministic checks pass or any skipped checks are justified
- browser evidence exists for meaningful frontend work, unless environment limitations are documented

If the result is `FAIL`, fix required items and rerun review until pass or until a real blocker requires user input.

## 6. Delivery

Final delivery must include:

- what changed
- review status and score
- checks run
- any remaining risks or verification limits

Use `references/frontend-review-template.md` for structured review output when the task is substantial.
