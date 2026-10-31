---
name: frontend-ui-ux
description: Build or review user interfaces with strong UX, visual design, accessibility, and frontend architecture. Use for any UI component, page, or flow.
---
# Frontend, UI & UX

## Design thinking first
Empathize (who, context, device) → Define (the one primary task per screen) → Ideate (≥2 layouts) → Prototype → Test with real flows.

## UX principles
- One primary action per view; clear visual hierarchy (size, weight, contrast, spacing).
- Nielsen heuristics: system status visible, match real world, user control (undo), consistency, error prevention, recognition over recall, flexibility, minimalism, helpful errors, help.
- Design every state: empty, loading (skeletons), partial, error (with recovery), success, offline, permission-denied, very long content.
- Fitts's law (big near targets, ≥44px touch), Hick's law (fewer choices), progressive disclosure.
- Optimistic UI for fast actions; feedback within 100ms; never lose user input.
- Copy: plain, specific, action-oriented button labels ("Save changes", not "OK").

## Visual design
- Design tokens for color, type scale, spacing (4/8pt grid), radius, shadows, motion. No magic numbers.
- Limited palette: neutrals + one accent + semantic colors. Support dark mode via tokens.
- Typography: 1–2 families, modular scale, 45–75 char line length, 1.4–1.6 line height.
- Alignment and whitespace do most of the work. Consistency > novelty.
- Motion: 150–300ms, purposeful, respect `prefers-reduced-motion`.

## Accessibility (WCAG 2.2 AA, non-negotiable)
Semantic HTML first, ARIA only when needed; full keyboard support & visible focus; contrast ≥4.5:1 text; labels for inputs; alt text; don't convey info by color alone; announce dynamic changes; test with a screen reader.

## Frontend architecture
- Components: small, composable, presentational vs. stateful separated; props typed.
- State: server state in a cache layer (e.g., query library), UI state local, global state minimal.
- Responsive mobile-first; no horizontal scroll; fluid layouts with grid/flex.
- Performance: Core Web Vitals (LCP <2.5s, INP <200ms, CLS <0.1); code-split, lazy-load, optimize images, avoid layout shift.
- Security: escape output, no `dangerouslySetInnerHTML` with user data, CSP.
- Verify visually: run the app, screenshot key states at mobile & desktop widths.
