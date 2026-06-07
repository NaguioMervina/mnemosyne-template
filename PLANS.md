# ExecPlans

Use an ExecPlan when work is substantial, risky, or likely to span multiple files or decisions.

The point of the plan is to make the intended outcome, file touch points, validation, and recovery path obvious to a future contributor who does not have the original chat context.

## When To Use One

Create an ExecPlan for:

- substantial features,
- high-risk bug fixes,
- refactors,
- UI workflow changes,
- data-model or schema changes,
- and any task where sequencing matters.

Routine one-file edits do not always need one.

## Where Plans Live

Store plans under `plans/` using the next available two-digit prefix and a short kebab-case description.

## Required Sections

Each ExecPlan should be self-contained and should include:

- purpose / user-visible outcome,
- progress,
- surprises and discoveries,
- decision log,
- context and orientation,
- plan of work,
- concrete steps,
- validation and acceptance,
- outcomes and retrospective,
- and idempotence and recovery notes when relevant.

## Simplicity

As much as possible, prefer the simplest code that safely solves the task.

## Security

Every ExecPlan should include a brief security check for the changed workflow when relevant.

- verify request protection for state-changing actions,
- verify authentication and authorization boundaries,
- verify validation, input handling, and output encoding remain appropriate,
- verify file uploads, imports, or raw queries do not introduce avoidable attack paths,
- and note any security-sensitive assumptions or follow-up checks.

## UI Evidence

If the plan can affect presentation or interaction:

- capture baseline evidence when practical,
- capture matching after-implementation evidence,
- and review the evidence for regressions, clipping, overlap, confusing states, and workflow issues.

## Control Documents

If the work materially affects current behavior, update the relevant `Mnemosyne` docs in the same change.

## Validation Standard

Every plan must end in observable proof.

Prefer:

- syntax, lint, test, or runtime checks in the supported environment,
- targeted data verification when writes are involved,
- screenshot or browser review for UI-affecting work,
- focused regression checks for adjacent features that could be affected,
- and explicit mention of anything that could not be validated.
