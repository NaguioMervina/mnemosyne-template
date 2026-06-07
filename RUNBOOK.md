# Runbook

This file is the durable operations and verification runbook for the repository's supported environment.

## Purpose

Use this file for the standard commands and routine checks that repeatedly appear in plans and contributor workflows.

## Environment

- Application runtime: `[[APP_RUNTIME]]`
- Data runtime: `[[DATA_RUNTIME]]`
- Supported local environment: `[[LOCAL_ENVIRONMENT]]`
- Unsupported or misleading host assumptions: `[[HOST_WARNINGS]]`

## Start And Inspect The Stack

Replace these with the actual commands for the new project:

```bash
[[STACK_START_COMMAND]]
[[STACK_STATUS_COMMAND]]
```

## Test, Lint, And Runtime Checks

Document the supported commands for the new repo:

```bash
[[UNIT_TEST_COMMAND]]
[[LINT_COMMAND]]
[[TYPECHECK_COMMAND]]
[[RUNTIME_SYNTAX_OR_HEALTHCHECK_COMMAND]]
```

## Database Or Persistence Changes

- Document the approved rollout path for schema or storage changes.
- If direct SQL, migration tools, or background backfills are restricted, say so plainly here.
- When verifying risky data writes, prefer the narrowest query or inspection that proves the intended record scope.

## Standard Validation

At minimum, choose the smallest relevant proof for the change:

```bash
git diff --check
git status --short
[[FOCUSED_VALIDATION_COMMAND]]
```

Add one or more of the following when the workflow needs it:

- focused runtime or integration checks,
- data inspection for integrity,
- screenshot or browser review for UI changes,
- nearby regression checks when shared code or shared views were touched.

## Documentation Closeout

When behavior, process, or repo expectations change:

- update the relevant root control docs in the same change,
- update the active ExecPlan if one exists,
- and note any validation or evidence that could not be completed.
