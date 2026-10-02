# Odoo Community / CRM Agent Contract

This repository is the governed Odoo Community source and CRM integration repository.

## Environment branch model

Promotion order is: `development` -> `testing` -> `staging` -> `production`.
`main` is the protected source-of-truth branch. Changes move between environment branches by reviewed pull request; do not force-push, rewrite history, or bypass required checks.

## Odoo rules

- Import and preserve the complete upstream Odoo Community source with its original license and history/provenance.
- Implement new work in `development`; validate in `testing`; certify deployment configuration in `staging`; promote only approved release candidates to `production`.
- Do not develop directly on `main` or `production`.
- Keep PostgreSQL schema/migration work reproducible and backed by tests.
- Keep secrets, database passwords, SMTP credentials, payment credentials, telephony credentials, and production tokens out of Git.
- Do not enable live email, SMS, calls, payments, or other provider effects from tests.
- Custom Codestra modules belong in explicit addon paths; do not silently modify vendored Odoo core when an addon/extension is sufficient.
- Preserve upstream copyright/license notices.

## Handoff

Record branch, exact HEAD, tests run, migration status, database target, deployment target, and any production-effect gate before promotion.
