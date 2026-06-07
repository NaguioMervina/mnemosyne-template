# Code Style

This file is the durable code-convention reference for the repository.

## General Principles

- Prefer narrow, targeted changes.
- Match nearby conventions unless the existing pattern is actively harmful.
- Use clear names over abbreviations for new code, helpers, and extracted logic.
- Keep comments useful and specific to business rules, edge cases, legacy quirks, and side effects.
- Use ASCII by default unless a file already contains non-ASCII content for user-facing text.

## Language And File Conventions

- `[[LANGUAGE_1]]`: `[[STYLE_RULE_1]]`
- `[[LANGUAGE_2]]`: `[[STYLE_RULE_2]]`
- Markdown, YAML, and similar config docs: 2-space indentation where indentation matters

## File Size Guidance

- Keep new hand-written files reasonably small.
- Do not force incidental refactors just to satisfy a number.
- If a touched file is already oversized, keep the change narrow and call out size concerns at closeout.

## Commenting Standard

Add comments when they materially help a reviewer understand:

- why a business rule exists,
- why a sensitive calculation or side effect is necessary,
- why an early return or guard exists,
- or why legacy behavior must be preserved.

Avoid comments that only restate syntax.

## Validation Habits

Before finalizing a meaningful change, prefer the smallest relevant validation that proves safety:

- `git diff --check`
- `[[SYNTAX_OR_LINT_COMMAND]]`
- `[[FOCUSED_RUNTIME_OR_TEST_COMMAND]]`
- `[[DATA_CHECK_COMMAND]]`
