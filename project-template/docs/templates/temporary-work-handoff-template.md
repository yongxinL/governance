# Temporary Work Handoff

> **Template (non-authoritative).** Create as `HANDOFF.md` at the root of the working branch when work is incomplete or the agent changes. It never replaces authoritative artifacts, contains no transcripts or secrets, and is deleted before merge once its content is resolved into authoritative artifacts.

| Field | Value |
|---|---|
| Created | YYYY-MM-DDThh:mm+hh:mm |
| Handoff type | Temporary secondary agent / permanent primary-agent or integration change |
| From agent | |
| To agent | |
| Branch | |
| Commit | |
| Specification | SPEC-NNN |
| Native task state | |

## 1. Task state (Mandatory)
*Reference native tasks by ID; do not copy the task list.*
## 2. Completed work (Mandatory)
## 3. Remaining work (Mandatory)
## 4. Tests (Mandatory)
*Commands run and results.*
## 5. Failures (Mandatory; "none" if none)
## 6. Uncommitted files (Mandatory)
## 7. Deviations (Mandatory; "none" if none)
## 8. Decisions needed from the Project Owner (Mandatory; "none" if none)
## 9. Integration-generated changes to review (Optional)
## 10. Next action (Mandatory)

## 11. Review and closure (Mandatory)

*How this temporary record is retired. A `HANDOFF.md` is working state, never a
source of truth.*

| Field | Value |
|---|---|
| Content moved to authoritative artifacts | |
| Reviewed by | |
| Delete or archive after merge | Pending |

If this handoff would still be needed after the work lands, its content belongs
in a committed governed artifact instead. Do not merge a temporary handoff as a
permanent duplicate of committed state.
