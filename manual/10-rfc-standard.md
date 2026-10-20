# 10. RFC Standard

**Part II** · **Owns:** RFC triggers, proposal evaluation, alternatives, risk, security, data, operations, migration, outcomes, RFC versus ADR, accepted RFC not proving implementation.

## 10.1 Triggers

Use an RFC for material proposals that are cross-cutting, costly, difficult to reverse, operationally significant, security significant, vendor-locking, data-architecture changing, public-interface changing, standard-changing, or dependent on evaluating credible alternatives.

## 10.2 Location and template

`docs/rfc/RFC-NNN-<kebab-title>.md` using [`rfc-template.md`](../project-template/docs/templates/rfc-template.md).

## 10.3 Required evaluation

Problem and motivation · proposal · alternatives (including do nothing) · risks · security and privacy · data impact · operational impact · migration and rollback · testing approach · cost and effort · reversibility · success criteria · open questions.

## 10.4 Statuses and outcomes

`Draft` -> `In Review` -> `Accepted` | `Rejected` | `Deferred` | `Withdrawn`; `Accepted` -> `Superseded`. The outcome section records the owner decision, date, approval mode, and conditions.

## 10.5 RFC versus ADR

| | RFC | ADR |
|---|---|---|
| Purpose | Evaluate a proposal | Record a decision |
| Scope | May span many decisions | One decision |
| Timing | Before commitment | At commitment |
| After acceptance | Historical record of evaluation | Durable reference |

A small decision with clear alternatives goes straight to an ADR.

## 10.6 Accepted is not implemented

Acceptance authorizes pursuing the proposal. It does not specify behaviour (specification does) and does not prove implementation (tests, evidence, and convergence do). Accepted RFCs remain in `docs/rfc/` permanently.

## 10.7 Review

Use prompt [09](../prompts/09-rfc-review.md).
