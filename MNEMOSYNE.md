# Mnemosyne

`Mnemosyne` is the local name for this repository's root control-document system.

It is the durable, version-controlled memory layer that contributors and agents should consult before substantial work and update when current behavior, workflow expectations, or repo standards materially change.

## What Mnemosyne Includes

In this repository, `Mnemosyne` means this root-doc set:

- `AGENTS.md`
- `PRODUCT.md`
- `WORKFLOW.md`
- `ROADMAP.md`
- `SECURITY.md`
- `RUNBOOK.md`
- `CODESTYLE.md`
- `DESIGN.md`
- `ARCHITECTURE.md`
- `PLANS.md`
- `readme.md`

## Optional Mnemosyne Extensions

Create these only when the new project needs them:

- `GLOSSARY.md` for business and implementation vocabulary
- `DATA_MAP.md` for high-risk table, queue, or event relationships
- `KNOWN_ISSUES.md` for accepted hazards and fragile behavior
- `[[DOMAIN_WORKFLOW_DOC]].md` for domain-specific operating playbooks

## Fresh-Start Rule

This template is a scaffold, not live memory.

- Replace placeholders with verified project truth.
- Remove sections that do not fit the new project.
- Do not treat template text as evidence that a workflow, command, or standard already exists.

## What "Validated By Mnemosyne" Means

When someone asks whether a change is `validated by Mnemosyne`, it means:

1. the relevant control docs were consulted before substantial work,
2. an ExecPlan was used when the task needed one,
3. the implementation followed the documented workflow, security, architecture, design, and validation rules that applied,
4. and the affected control docs were updated if current behavior or expectations changed.

## What It Does Not Mean

`Validated by Mnemosyne` does not automatically mean:

- runtime tests passed,
- browser review was completed,
- data integrity was manually inspected,
- or every regression risk was checked.

Those still require explicit validation evidence.

## Practical Rule

For non-trivial work, start with Mnemosyne first, then decide whether the task needs an ExecPlan, then implement, validate, and sync the affected docs.
