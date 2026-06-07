# Security

This file is the durable security baseline for workflow changes in this repository.

## Purpose

Security work here is mostly about preserving correct boundaries, explicit validation, and safe handling of sensitive reads and writes.

## Baseline Expectations

Every meaningful change should review the parts of security that apply to that workflow:

- CSRF or equivalent request protection for state-changing actions,
- authentication and role-appropriate access,
- authorization on the specific resource being viewed or modified,
- input validation and normalization,
- output escaping or encoding,
- file, import, export, and background-job safety,
- and integrity protections for high-risk writes.

## Request And Session Safety

- Keep state-changing routes or actions behind the appropriate middleware or guard layer.
- Do not trust client-posted flags when the server can derive the authoritative workflow path.
- Treat stale browser state, cached selections, and session hints as untrusted until revalidated.

## Authorization And Scope

- Scope reads and writes to the intended user, tenant, project, record, or environment.
- Avoid broad updates or deletes when the workflow expects a narrow target.
- Re-check permissions when a workflow can reopen, retry, or delete existing records.

## Credential Safety

- Do not change usernames, passwords, secrets, API keys, or other credentials unless the user explicitly requested that exact credential mutation.
- Do not use debugging or test setup as an excuse to reset credentials silently.

## Input Handling

- Validate required IDs and target contexts against the allowed source set.
- Normalize typed values before matching or saving when the UI allows free text or custom input.
- Reject ambiguous or missing workflow context instead of silently falling back to another record.

## Output And Rendering Safety

- Escape dynamic text unless raw rendering is intentionally required and reviewed.
- Review reports, PDFs, exports, and HTML fragments for leaked stale fields or misleading labels.

## Security Review Checklist

- Is the route or action protected by the right guard or middleware?
- Does the server validate the selected target IDs and workflow context?
- Could stale UI or session state cause the wrong record to be modified?
- Are dynamic outputs encoded correctly?
- Does the change create new import, export, or file-handling exposure?
- For sensitive writes, can the resulting records be traced and reconciled?
