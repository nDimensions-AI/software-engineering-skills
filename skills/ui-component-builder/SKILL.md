---
name: ui-component-builder
description: Build reusable, accessible, production-ready UI components or design-system pieces. Use when creating or refactoring a UI component (button, form, modal, table, combobox, etc.).
---
# Production UI Component Builder

Apply `frontend-ui-ux` principles. Think like a senior frontend / design-systems engineer.

## Props / API design
- Small, typed, predictable API; sensible defaults; composition (children/slots) over configuration flags.
- Controlled and uncontrolled modes for inputs (`value`/`defaultValue` + `onChange`).
- Forward refs and spread remaining native attributes; allow `className`/style extension.
- Variants via an enum prop (`variant="primary"`), not boolean soup.
- Never hard-code text; accept labels and support i18n.

## Must handle
- **States**: default, hover, focus-visible, active, disabled, loading, error, empty, success
- **Edge cases**: very long or missing text, zero/one/many items, slow or failed data, rapid repeated clicks, RTL, unexpected prop combos
- **Responsive**: works from 320px up; touch targets ≥44px
- **Accessibility**: semantic element first; follow the WAI-ARIA Authoring Practices pattern for widgets; full keyboard support; focus management (trap and restore for modals); labels and `aria-describedby` for errors; `aria-busy`/live regions for loading; contrast AA; `prefers-reduced-motion`
- **Performance**: avoid unnecessary re-renders (stable callbacks, memo where measured); virtualize long lists

## Verify
Unit and interaction tests (Testing Library), an axe accessibility check, a story/example per state, and a visual check at mobile and desktop widths.

## Required output
1. **Component architecture** — structure, subcomponents, state ownership
2. **Props design** — typed interface with docs and defaults
3. **Implementation**
4. **Usage examples** — basic, variants, controlled, edge cases
