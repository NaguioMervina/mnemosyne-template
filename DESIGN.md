# Design

This repository's design guidance should capture stable UI and interaction rules, not temporary taste.

If the project has no end-user UI, keep this file short and document CLI, API, or admin ergonomics instead.

## Product Surface Split

- Public or customer-facing surfaces: `[[PUBLIC_SURFACE_RULES]]`
- Internal or operational surfaces: `[[INTERNAL_SURFACE_RULES]]`

## Existing UI Stack Reality

- Primary UI stack: `[[UI_STACK]]`
- Legacy constraints or shared components: `[[UI_CONSTRAINTS]]`

## UI Review Expectations

- Review labels, totals, spacing, overlap, clipping, and feedback states.
- Verify that validation and failure states are understandable.
- Review desktop and any relevant narrow/mobile states when practical.

## Stable Terminology Rules

- `[[TERM_RULE_1]]`
- `[[TERM_RULE_2]]`

## Visual Non-Goals

- Do not redesign screens for appearance alone.
- Do not introduce a new design language per module without an explicit decision.
- Do not trade workflow speed for decorative changes on high-touch operational screens.
