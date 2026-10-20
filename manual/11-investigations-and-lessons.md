# 11. Investigations and Lessons

**Part II** · **Owns:** investigation triggers, evidence and experiments, findings and limitations, non-decisional nature, lesson lifecycle, incorporation, `INV-NNN` and `LES-NNN`.

## 11.1 Investigation triggers

Use an investigation when material uncertainty blocks a specification, plan, RFC, ADR, or incident resolution: unknown root cause, unproven feasibility, unclear performance or capacity, unknown legacy behaviour, tool evaluation, or vendor comparison.

## 11.2 Content

`docs/investigations/INV-NNN-<kebab-title>.md` using [`investigation-template.md`](../project-template/docs/templates/investigation-template.md): question, scope, method, evidence and experiments (with environment and versions), findings, limitations, options, recommendation, follow-up artifacts.

## 11.3 Evidence handling

Commit summaries and reproducible scripts; reference large or sensitive raw evidence externally ([chapter 13](13-testing-evidence-and-verification.md)). Never commit secrets or personal data.

## 11.4 Non-decisional nature

An investigation recommends; it does not decide. Decisions are recorded in an ADR, RFC outcome, specification, or exception. An investigation's status `Completed` means the inquiry is finished, not that its recommendation is approved.

Statuses: `Planned`, `In Progress`, `Completed`, `Cancelled`, `Superseded`.

## 11.5 Lessons

`docs/lessons/LES-NNN-<kebab-title>.md` using [`lesson-learned-template.md`](../project-template/docs/templates/lesson-learned-template.md). Lessons come from incidents, failed verification, migrations, releases, and recurring friction.

Lifecycle: `Draft` -> `Accepted` (owner agrees it is valid) -> `Incorporated` (the action is now in an authoritative artifact such as a runbook, constitution, ADR, test, or governance record) -> `Retired` (no longer relevant). A lesson is not binding until incorporated; the incorporation target is linked from the lesson.

## 11.6 Identifiers

`INV-NNN` and `LES-NNN` follow [chapter 16](16-metadata-naming-and-status.md) allocation rules and are indexed in their area README.
