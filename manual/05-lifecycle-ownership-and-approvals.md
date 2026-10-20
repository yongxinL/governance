# 05. Lifecycle, Ownership, and Approvals

**Part I** · Owns: solo-owner mode, collaborative expansion, approval modes, approval evidence, baseline commits, material approval gates, status-transition control, high-risk review.

## 5.1 Solo-owner mode

Each project has exactly one Project Owner, named in `docs/governance/governance-adoption.md`. Artifacts use `owner: project-owner`. In `solo` mode the Project Owner performs product, technical, security, and operations review, implementation authorization, verification acceptance, and release approval. These are functional review responsibilities, not separate people.

## 5.2 Collaborative expansion

Introduce role separation (recorded as governance mode `collaborative` with a role table in the adoption record) when other contributors receive write access, decision authority is shared, the project serves external users, compliance or contractual obligations require it, or risk warrants independent responsibility. This is a governed change to the adoption record.

## 5.3 Approval modes

| Mode | Use |
|---|---|
| `owner-self-approval` | Owner approves their own material work after review |
| `enhanced-owner-review` | High-risk work without an independent reviewer; owner completes the enhanced checklist (5.7) |
| `independent-review` | A second human reviewed and approved |

AI-assisted review is recorded as supporting input, never as an approval mode. An AI agent cannot provide required owner approval (NX-3).

## 5.4 Approval evidence

An artifact may record `status`, `approved_by`, `approval_mode`, and `approved_on`. It does not record its own commit SHA. The baseline commit is recorded afterwards in the relevant index, release record, or approval record. Repository review records (Forgejo pull-request approvals) are supporting evidence.

## 5.5 Baselines

- **Ordinary baseline:** the commit containing the approved artifact.
- **Collective baseline:** an annotated tag for significant points (governance adoption, releases).
- **Historical recovery:** baselines remain recoverable through Git; do not rewrite published history.
- Accepted ADRs are immutable in meaning. Approved specifications are change-controlled.

## 5.6 Material approval gates

Gates and their entry and exit criteria are owned by [chapter 26](26-validation-and-quality-gates.md). Material changes require explicit owner approval at the applicable gates; trivial low-risk maintenance does not require formal approval metadata.

## 5.7 High-risk review

High-risk work includes security-sensitive change, authentication and authorization, data migration, destructive operations, production infrastructure, public interface breaks, and secret handling. Without an independent reviewer, use `enhanced-owner-review`:

1. Review after a break from authoring (a separate session).
2. Walk through threat, failure, and rollback scenarios explicitly.
3. Confirm tests cover failure paths, not only success paths.
4. Confirm rollback or recovery has been exercised or is credibly documented.
5. Obtain AI-assisted review as supporting input and record dispositions.
6. Record the approval mode honestly.

Independent human review is recommended where practical and required only where an external obligation, shared ownership rule, project policy, or applicable security requirement demands it.

## 5.8 Status transitions

Material status transitions (for example Draft to Approved, Proposed to Accepted, Candidate to Released) are owner-controlled. Agents may propose transitions; they may not perform them without owner instruction. Status vocabularies are owned by [chapter 16](16-metadata-naming-and-status.md).
