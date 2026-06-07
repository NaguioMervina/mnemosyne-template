# Architecture

This file is the durable structural reference for `[[PROJECT_NAME]]`.

## System Overview

`[[PROJECT_NAME]]` is a `[[SYSTEM_TYPE]]` that supports `[[PRIMARY_WORKFLOWS]]`.

## Codemap

- `[[ROUTE_OR_ENTRYPOINT_PATH]]` primary route or entrypoint registration
- `[[APP_LOGIC_PATH]]` application logic
- `[[MODEL_OR_DATA_PATH]]` data access and models
- `[[VIEW_OR_UI_PATH]]` UI templates or frontend application
- `[[CONFIG_PATH]]` configuration
- `[[DB_PATH]]` schema, migrations, fixtures, or SQL
- `plans/` ordered ExecPlans for substantial work

## Main Flows

### `[[FLOW_1_NAME]]`

1. `[[FLOW_1_STEP_1]]`
2. `[[FLOW_1_STEP_2]]`
3. `[[FLOW_1_STEP_3]]`

### `[[FLOW_2_NAME]]`

1. `[[FLOW_2_STEP_1]]`
2. `[[FLOW_2_STEP_2]]`
3. `[[FLOW_2_STEP_3]]`

## Architectural Invariants

- `[[INVARIANT_1]]`
- `[[INVARIANT_2]]`
- `[[INVARIANT_3]]`

## Boundaries And External Dependencies

- App-to-data boundary: `[[DATA_BOUNDARY]]`
- App-to-external-service boundary: `[[SERVICE_BOUNDARY]]`
- App-to-user boundary: `[[UI_BOUNDARY]]`
- Contributor-tooling boundary: `[[TOOLING_BOUNDARY]]`

## Cross-Cutting Concerns

- `[[CROSS_CUTTING_CONCERN_1]]`
- `[[CROSS_CUTTING_CONCERN_2]]`
- `[[CROSS_CUTTING_CONCERN_3]]`

## How To Extend Safely

- Locate the owning entrypoint, workflow, and data boundary first.
- Prefer additive changes that preserve current workflows while improving clarity and validation.
- For broad refactors, create an ExecPlan first and name the affected boundaries explicitly.
