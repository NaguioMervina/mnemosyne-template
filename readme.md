# [[PROJECT_NAME]]

`[[PROJECT_NAME]]` is a `[[PROJECT_TYPE]]` built with `[[PRIMARY_STACK]]`.

This repository uses a root control-document system called `Mnemosyne`. Those docs are the durable references for product scope, workflow expectations, roadmap, security, runbook operations, code style, design, architecture, and execution planning.

## Root Control Documents

- `MNEMOSYNE.md` definition and index for the root control-document system
- `AGENTS.md` repository-specific contributor and agent instructions
- `PRODUCT.md` current user-visible behavior and scope
- `WORKFLOW.md` standard execution and validation flow
- `ROADMAP.md` intended direction and priorities
- `SECURITY.md` workflow-level security expectations
- `RUNBOOK.md` operational commands and repeatable verification patterns
- `CODESTYLE.md` coding conventions
- `DESIGN.md` stable UI and interaction guidance
- `ARCHITECTURE.md` system boundaries and major workflow structure
- `PLANS.md` ExecPlan requirements and maintenance rules

## Runtime Notes

- Supported runtime: `[[SUPPORTED_RUNTIME]]`
- Primary database or persistence layer: `[[PRIMARY_DATA_STORE]]`
- Preferred local environment: `[[LOCAL_ENVIRONMENT]]`

## Common Commands

Replace these examples with the real command set for the new project:

```bash
[[BOOTSTRAP_COMMAND]]
[[TEST_COMMAND]]
[[LINT_COMMAND]]
[[TYPECHECK_OR_RUNTIME_CHECK_COMMAND]]
```

## Repository Layout

- `[[APP_DIR]]` application code
- `[[VIEW_OR_UI_DIR]]` UI, templates, or frontend assets
- `[[CONFIG_DIR]]` environment and app configuration
- `[[DB_DIR]]` schema, migrations, fixtures, or SQL
- `plans/` ordered ExecPlans for substantial work

## Safety Notes

- Document the real high-risk workflows in `PRODUCT.md`, `SECURITY.md`, and `ARCHITECTURE.md`.
- Prefer narrow changes in legacy or business-critical code until the new repo documents safer refactor boundaries.
