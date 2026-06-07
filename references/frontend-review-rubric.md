# Frontend Expert Review Rubric

Total score: 100.

## Categories

| Category | Points | Standard |
|---|---:|---|
| Requirement Fit | 20 | The implementation matches the user's actual request, removes conflicting old behavior, and does not substitute a different product idea. |
| UX Flow | 20 | Default state, navigation, primary actions, empty/error/loading states, and key interactions feel intentional and efficient. |
| Visual Design | 20 | Layout, hierarchy, spacing, typography, color, density, and component composition feel professional and domain-appropriate. |
| Responsive Layout | 15 | Desktop, tablet, and mobile avoid overlap, clipping, unreadable text, unstable layout shifts, and broken controls. |
| Accessibility | 10 | Contrast, focus, labels, semantic controls, keyboard reachability, and text sizing are acceptable for the surface. |
| Code Quality | 10 | Uses local patterns, keeps scope tight, avoids duplication, handles state/data safely, and is maintainable. |
| Stability | 5 | No console errors, obvious network failures, broken assets, or severe performance issues in tested paths. |

## Blockers

Any blocker forces `FAIL` regardless of score:

- user-requested core behavior is missing
- old/conflicting UI remains as the main experience
- primary action is broken
- layout is unusable on a common viewport
- major console/runtime error appears on the target route
- visual evidence was required but no rendered inspection was performed and no limitation was disclosed
- sensitive or destructive behavior is introduced

## Pass Threshold

- total score >= 85
- zero blockers
- Requirement Fit >= 15
- UX Flow >= 15
- Visual Design >= 15
- Responsive Layout >= 11

## Review Posture

Be strict. Prefer finding the real delivery risk over being polite. The review agent should not pass work merely because tests pass.
