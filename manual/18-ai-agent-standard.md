# 18. AI Agent Standard

**Part V** · **Owns:** AI authority boundaries, `AGENTS.md` purpose and content, required reading, prohibited assumptions and actions, escalation, validation, completion authority, owner approval, the Spec Kit managed block.

## 18.1 Authority boundaries

AI agents implement, analyse, draft, and review under authorization. They do not approve material artifacts, change approved specifications silently, accept their own work as complete, invent facts or decisions, or treat tool or conversation output as project authority (NX-3, NX-5, NX-6).

## 18.2 AGENTS.md

`AGENTS.md` at the repository root is a concise operational control document. It contains: governance precedence, adopted-governance reference, authoritative locations, required reading, Spec Kit ownership, primary-agent reference, tool boundaries, prohibited actions, escalation conditions, validation expectations, completion rules, and the owner-approval requirement.

It does not duplicate the central manual, the constitution, product requirements, specifications, ADRs, RFCs, or full installation instructions. Both OpenCode (v2 reads `AGENTS.md` only) and Codex read `AGENTS.md`.

## 18.3 Nested AGENTS.md

Nested files may specialize local behaviour (for example test commands for a sub-package). They must not weaken central or project governance, approved requirements, decisions, security controls, or quality gates. OpenCode combines nested files rather than resolving conflicts between them, so nested files must not contradict the root file.

## 18.4 Spec Kit managed block

Spec Kit (through its agent-context mechanism) may insert and refresh a delimited managed section in `AGENTS.md` that points to the active feature plan. This block is **permitted** under these conditions:

- It stays within its native markers, below the Nexora sections.
- It contains pointers only; it is non-authoritative.
- Nexora content is never placed inside the markers, and agents never hand-edit the block.
- Diffs to the block are reviewed like any generated change.

## 18.5 Required reading

Before material work an agent reads: `AGENTS.md`, `docs/governance/governance-adoption.md`, `docs/governance/source-of-truth-register.md`, the native constitution, the applicable specification, plan, and tasks, constraining ADRs, and `docs/governance/approved-tooling.md`.

## 18.6 Prohibited assumptions

Do not assume: product intent not written down, approval not recorded, a tool is enabled because it is installed, a default branch reflects adopted governance, prior conversation reflects current truth, or passing tests prove acceptance criteria are covered.

## 18.7 Prohibited actions

Create competing specifications, plans, task lists, analysis, or completion records; relocate or rename native artifacts; commit secrets; install or enable tools not in the register; publish, push to protected branches, merge, tag, release, deploy, or delete without owner authorization; perform material status transitions; rewrite accepted ADRs; delete governed history.

## 18.8 Escalation

Stop and report when: a specification is wrong, ambiguous, or conflicts with another authority; scope must expand; a security or data risk appears; a required tool or credential is missing; tests cannot be run; rollback is missing; or an instruction conflicts with governance.

## 18.9 Write discipline

Before any write, the agent states the scope it intends to change and reviews
the current state of those paths. During the work:

- review the working-tree state (`git status`) before and after;
- check for whitespace and conflict-marker defects (`git diff --check`);
- read the complete diff, not only the files expected to change;
- report the validation that was actually run, and report validation that was
  not run as `NOT_RUN` under
  [chapter 13](13-testing-evidence-and-verification.md);
- when work must be undone, revert or restore non-destructively. Do not use
  destructive history operations to recover from a mistake, and never discard
  uncommitted work that was not the agent's to discard.

Recovery guidance must be safe to follow. "Delete the branch" is not recovery.

## 18.10 Context and cost discipline

Keep context deliberate. Read what the task needs, avoid re-reading unchanged
files, and do not paste large artifacts into a conversation when a
repository-relative reference is sufficient. A handoff or repository record
outlives the context window; a conversation does not.

## 18.11 Agent neutrality

This standard describes behaviour, not a product. It applies to any approved
agent harness, including OpenCode and Codex, and does not bind governance to one
vendor. Where an agent-specific detail matters, it belongs in
`AGENTS.md` or the relevant tool chapter, not in the governance model.

## 18.12 Validation and completion

Run the project's test, build, and lint commands as recorded in `AGENTS.md`. Report what was run and the result. Completion requires native convergence and owner acceptance; an agent reports readiness, it does not declare completion.
