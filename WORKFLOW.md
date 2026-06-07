# Workflow

This file is the durable reference for how changes are typically executed in this repository.

## Purpose

The goal is to keep future work consistent, reviewable, and safe.

## Standard Change Flow

1. Read `Mnemosyne` before substantial work.
2. Identify the owning route, service, module, job, CLI command, UI surface, or data flow first.
3. Decide whether the task needs an ExecPlan.
4. Prefer the smallest change that safely solves the actual problem.
5. Validate the exact workflow that changed plus nearby regression risks.
6. Update the durable docs when current behavior, workflow boundaries, or contributor expectations materially change.

## When An ExecPlan Is Expected

Use an ExecPlan for:

- multi-file features,
- refactors,
- UI changes that alter layout or interaction flow,
- data-writing changes with recovery or integrity risk,
- high-risk workflow changes in `[[HIGH_RISK_AREAS]]`,
- and any task where the safe sequence is not obvious.

## Common Workflow Types

### Write Paths

- Validate the exact target scope before writing.
- Prefer explicit user choices over stale defaults.
- Check adjacent workflows when shared state or handoff parameters are involved.

### UI And Interaction Changes

- Preserve established workflow speed and clarity unless redesign is intentional.
- Review empty, loading, error, and changed-selection states, not only the happy path.
- Capture UI evidence when practical.

### Reports, Exports, And Background Tasks

- Keep filter semantics explicit and stable.
- Check output structure, target rows, and runtime safety.
- Prefer timeout-safe generation paths when output is large or slow.

### Documentation-Only Changes

- Update the root control docs when repeated practice is no longer obvious from the durable docs.
- Prefer one document per concern instead of burying process rules in old plans.

## Standard Validation Flow

Match validation to the risk of the change:

- syntax, lint, or type checks for touched files,
- focused runtime validation in the supported environment,
- data inspection when integrity is involved,
- screenshot or browser review for UI changes,
- and a short regression checklist for nearby affected workflows.

If a meaningful validation step could not be run, record that explicitly.

## Standard Closeout

Before calling work complete:

- confirm the changed behavior,
- note residual risks or unvalidated areas,
- update affected durable docs,
- and record outcomes in the ExecPlan when one exists.
