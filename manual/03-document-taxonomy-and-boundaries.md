# 03. Document Taxonomy and Boundaries

**Part I** · Owns: artifact types, what each may and may not contain, artifact-boundary rules, proportional creation triggers summary.

## 3.1 Taxonomy

| Artifact | Answers | Authoritative for | Must not contain | Location | Owning chapter |
|---|---|---|---|---|---|
| Product requirements | Why and for whom; what outcomes | Product intent, goals, non-goals, constraints | Feature behaviour detail, technical design | `docs/product/` | 08 |
| Specification | What observable behaviour | Requirements and acceptance criteria | Implementation design, task lists | `specs/` (native) | 06, 07 |
| RFC | Should we pursue this proposal? | Proposal evaluation and outcome | Proof of implementation | `docs/rfc/` | 10 |
| ADR | Which durable technical decision, and why? | One decision and its rationale | Multiple unrelated decisions, requirements | `docs/architecture/adr/` | 09 |
| Investigation | What is true? | Findings and limitations | Decisions or approvals | `docs/investigations/` | 11 |
| Plan | How will this feature be built? | Technical approach for one feature | New requirements | `specs/` (native) | 12 |
| Cross-specification delivery plan | How is multi-spec work coordinated? | Sequencing and dependencies | Feature plans or tasks | `docs/architecture/` | 12 |
| Tasks | What work units implement the plan? | Task breakdown and completion state | New scope | `specs/` (native) | 07 |
| Tests | Does it behave as specified? | Executable verification | New requirements | Source tree | 13 |
| Evidence | What proves verification? | Verification outcomes | Requirement changes | Native feature artifacts, `docs/testing/`, release records | 13 |
| Release record | What shipped, with what baseline? | Release content and approval | Specification changes | `docs/releases/` | 14 |
| Runbook | How to operate or recover? | Procedures | Design decisions | `docs/operations/runbooks/` | 15 |
| Lesson | What did we learn? | The lesson until incorporated | Binding rules | `docs/lessons/` | 11 |
| Archive | What is retired or displaced? | Nothing current | Current authority | `docs/archive/` | 28 |

## 3.2 Boundary rules

1. **One home per fact.** If a fact belongs to a specification, other artifacts link to it rather than restate it.
2. **Tests do not redefine requirements.** A test that disagrees with a specification is a defect in one of them, resolved through change control.
3. **Release records do not redefine specifications.** They reference specification baselines.
4. **Accepted RFCs do not prove implementation.** Implementation evidence comes from tests, verification summaries, and convergence.
5. **Investigations do not decide.** Decisions are recorded in ADRs, RFC outcomes, or specifications.
6. **Lessons are not binding** until incorporated into an authoritative artifact.
7. **Indexes do not reproduce content.** They record identity, location, status, supersession, and baseline references.
8. **Templates are not artifacts.** Never leave project facts only in a template file.

## 3.3 Proportional creation

Artifacts are created when their governance purpose applies (triggers are owned by chapters 06, 09, 10, 11, 12). Do not create artifacts to populate the scaffold. Low-risk maintenance (typographical fixes, formatting, mechanical cleanup, behaviour-preserving refactoring, routine test improvements, minor configuration correction, routine compatible dependency updates) proceeds with an ordinary reviewed commit.

## 3.4 Boundary violations

A boundary violation (for example, requirements embedded in an ADR, or decisions embedded in a runbook) is recorded as an audit finding and resolved by moving the content to its owning artifact and replacing it with a link. Do not resolve a violation by deleting content without owner review ([chapter 28](28-archive-retention-and-migration.md)).
