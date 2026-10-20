# 15. Operations, Backup, and Recovery

**Part III** · **Owns:** deployment, configuration, monitoring, alerting, troubleshooting, runbooks, backup, restore, recovery, disaster recovery, operational exercises, operational evidence.

## 15.1 Operations overview

`docs/operations/README.md` describes the operational model: environments, hosting, deployment path, configuration sources, monitoring and alerting, backup scope, and links to runbooks. It does not contain secrets or design decisions (ADRs).

## 15.2 Deployment and configuration

Deployments are reproducible from the repository and documented in a runbook. Configuration sources and precedence are recorded; secrets are referenced by name and store, never by value. Deployment integrations are disabled initially for agents ([chapter 25](25-playwright-and-remote-integrations.md)).

## 15.3 Monitoring, alerting, troubleshooting

Record what is monitored, alert thresholds, notification targets (by role), and troubleshooting entry points. Each actionable alert links to a runbook.

## 15.4 Runbooks

`docs/operations/runbooks/<kebab-title>.md` using [`runbook-template.md`](../project-template/docs/templates/runbook-template.md). A runbook states purpose, triggers, prerequisites, required access, steps, verification, rollback, escalation, and last-exercised date. Destructive steps are marked and require confirmation.

## 15.5 Backup and restore

Document backup scope, method, frequency, retention, location, encryption, and credentials handling (by reference). A backup is not trusted until a restore has been exercised. Record restore exercises as committed summaries.

## 15.6 Recovery and disaster recovery

Define recovery objectives where they matter (acceptable data loss and downtime), recovery order for dependent services, and the location of recovery credentials outside the repository.

## 15.7 Exercises and evidence

Exercise restore and recovery procedures on a trigger basis: after initial setup, after material infrastructure change, after incidents, and before high-risk releases. Commit exercise summaries; reference raw logs externally. Failures produce a lesson and runbook update.

### 15.7.1 Operational evidence honesty

- Never claim that a backup, restore, rollback, or recovery exercise was performed
  when it was not. An unperformed exercise is `NOT_RUN` under
  [chapter 13](13-testing-evidence-and-verification.md), not a passed check.
- Do not invent recovery objectives, recovery times, recovery points, retention
  periods, or monitoring thresholds. Record the real approved values, or record
  that the value is still to be decided.
- Record the date, scope, environment, and operator of each exercise so a later
  reader can tell whether it covers the current system.
- A runbook is operational guidance. It does not become design authority or
  product authority, and a procedure recorded in a runbook does not override an
  accepted ADR or an approved requirement. Where they conflict, treat it as a
  finding and resolve it through [chapter 09](09-adr-standard.md) or
  [chapter 10](10-rfc-standard.md).
- Access and credential boundaries follow
  [chapter 20](20-developer-tooling-and-security.md). A runbook names the
  credential and its store; it never contains the secret.
