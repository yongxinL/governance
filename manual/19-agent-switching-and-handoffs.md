# 19. Agent Switching and Handoffs

**Part V** · Owns: primary agent, secondary-agent use, one active integration, switching, integration changes, repository-based handoff, temporary work handoff, incomplete work, conversation-history limitations.

## 19.1 Primary agent

Each project declares one primary implementation agent, `opencode` or `codex`, in `governance-adoption.md`, with the matching active Spec Kit integration.

## 19.2 Secondary agents

A secondary agent may review, analyse, or perform bounded tasks using the same repository artifacts. It creates no parallel specifications, plans, tasks, decisions, completion records, or sources of truth.

## 19.3 Switching procedure

1. Identify the current branch and commit.
2. Review the working tree; commit or stash with a clear message.
3. Review the current specification and task state.
4. Run tests and record the result.
5. Capture unresolved questions and deviations.
6. Write a temporary handoff if work is incomplete (19.5).
7. If the active Spec Kit integration changes, run the native integration switch, review all generated changes, and confirm no authoritative artifact was relocated or recreated.
8. Update `governance-adoption.md` (primary agent and active integration) in a governed commit.

Use prompt [21](../prompts/21-agent-switch-handoff.md).

## 19.4 Repository-based handoff

The repository is the handoff: committed artifacts, task state in native tasks, Git history, and indexes. A new agent session reconstructs context from these, not from prior conversation.

## 19.5 Temporary work handoff

For incomplete work, create a handoff from [`temporary-work-handoff-template.md`](../project-template/docs/templates/temporary-work-handoff-template.md) on the working branch (suggested path: `HANDOFF.md` at the root of the branch). It records branch, commit, specification, task state, completed and remaining work, tests, failures, uncommitted files, deviations, decisions needed, and next action. It never replaces authoritative artifacts, contains no transcripts or secrets, and is deleted before merge once its content has been resolved into authoritative artifacts.

## 19.6 Conversation-history limitations

Conversation history may be truncated, compacted, or unavailable to another agent. It is not durable project truth. Anything that matters is written to the repository.
