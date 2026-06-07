# Purpose / User-Visible Outcome

Describe the user-visible outcome and the exact workflow or problem this plan covers.

# Progress

- [ ] Read Mnemosyne root docs and any relevant extension docs.
- [ ] Trace the owning code paths and workflow boundaries.
- [ ] Implement the smallest safe change.
- [ ] Run focused validation and record results.

# Surprises And Discoveries

- Record anything non-obvious you learned while tracing the workflow.

# Decision Log

- Record important scope, architecture, or risk decisions here.

# Context And Orientation

- Route, command, job, service, page, report, or entrypoint:
- Owning code paths:
- Related docs:

# Plan Of Work

1. State the main workstreams.
2. Keep them ordered and concrete.

# Concrete Steps

1. List the exact implementation steps.
2. Include expected validation points or recovery points where relevant.

# Validation And Acceptance

- `git diff --check`
- `git status --short`
- `[[FOCUSED_VALIDATION_1]]`
- `[[FOCUSED_VALIDATION_2]]`

# Security Check

- Record the relevant request protection, authentication, authorization, validation, escaping, import/export, or credential concerns for this workflow.

# Outcomes And Retrospective

- Summarize what changed and any residual risks.

# Idempotence And Recovery Notes

- Explain how to retry, roll back, or re-run the workflow safely if relevant.

# Code Size Review

- Record line-count observations for touched hand-written files when code changed.
