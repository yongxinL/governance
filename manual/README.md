# Nexora Governance Manual v1.0

The manual contains the detailed rules of Nexora Governance. **Each detailed rule has exactly one owning chapter.** Other chapters summarize and cross-reference it rather than repeating it. When two chapters appear to differ, the owning chapter for that rule prevails, subject to the precedence in [chapter 01](01-governance-policy.md).

## How to use the manual

- Start with Part I to understand authority and structure.
- Use the chapter that owns a topic when you need the complete rule.
- Use [instructions](../instructions/README.md) for sequence, [templates](../project-template/docs/templates/README.md) to create artifacts, and [prompts](../prompts/README.md) to direct agents.

## Part I: Governance foundation

| # | Chapter | Owns |
|---|---|---|
| 01 | [Governance policy](01-governance-policy.md) | Authority, precedence, principles, non-exception controls |
| 02 | [Information architecture](02-information-architecture.md) | Central versus project governance, scaffold, canonical paths |
| 03 | [Document taxonomy and boundaries](03-document-taxonomy-and-boundaries.md) | Artifact types and boundaries |
| 04 | [Governance versioning and exceptions](04-governance-versioning-and-exceptions.md) | Releases, adoption, exceptions |
| 05 | [Lifecycle, ownership, and approvals](05-lifecycle-ownership-and-approvals.md) | Solo owner, approval modes, baselines |

## Part II: Requirements and development lifecycle

| # | Chapter | Owns |
|---|---|---|
| 06 | [Specification-Driven Development](06-specification-driven-development.md) | SDD principles and triggers |
| 07 | [Spec Kit standard](07-spec-kit-standard.md) | Spec Kit workflow, integrations, `bug` extension |
| 08 | [Product requirements standard](08-product-requirements-standard.md) | Product vision and requirements |
| 09 | [ADR standard](09-adr-standard.md) | Architecture decisions |
| 10 | [RFC standard](10-rfc-standard.md) | Proposals |
| 11 | [Investigations and lessons](11-investigations-and-lessons.md) | INV and LES artifacts |
| 12 | [Planning and cross-specification delivery](12-planning-and-cross-specification-delivery.md) | Plans |

## Part III: Verification, release, and operations

| # | Chapter | Owns |
|---|---|---|
| 13 | [Testing, evidence, and verification](13-testing-evidence-and-verification.md) | Evidence classes and verification |
| 14 | [Release management](14-release-management.md) | Release records and approval |
| 15 | [Operations, backup, and recovery](15-operations-backup-and-recovery.md) | Runbooks and recovery |

## Part IV: Metadata and navigation

| # | Chapter | Owns |
|---|---|---|
| 16 | [Metadata, naming, and status](16-metadata-naming-and-status.md) | Identifiers, metadata, statuses |
| 17 | [Indexing, traceability, and source of truth](17-indexing-traceability-and-source-of-truth.md) | Indexes and traceability |

## Part V: AI agents and tooling

| # | Chapter | Owns |
|---|---|---|
| 18 | [AI agent standard](18-ai-agent-standard.md) | Agent authority and `AGENTS.md` |
| 19 | [Agent switching and handoffs](19-agent-switching-and-handoffs.md) | Primary agent and switching |
| 20 | [Developer tooling and security](20-developer-tooling-and-security.md) | Tool trust classes and controls |
| 21 | [Context7 standard](21-context7-standard.md) | Context7 |
| 22 | [OpenAI Docs MCP standard](22-openai-docs-mcp-standard.md) | OpenAI Developer Documentation MCP |
| 23 | [codebase-memory-mcp standard](23-codebase-memory-mcp-standard.md) | codebase-memory-mcp |
| 24 | [Ponytail standard](24-ponytail-standard.md) | Ponytail |
| 25 | [Playwright and remote integrations](25-playwright-and-remote-integrations.md) | Playwright MCP, Forgejo, remote tools |

## Part VI: Quality, preservation, and adoption

| # | Chapter | Owns |
|---|---|---|
| 26 | [Validation and quality gates](26-validation-and-quality-gates.md) | Gates and finding severity |
| 27 | [Generated files, manifests, and packaging](27-generated-files-manifests-and-packaging.md) | Generated artifacts and packaging |
| 28 | [Archive, retention, and migration](28-archive-retention-and-migration.md) | Archive and existing-project migration |
| 29 | [Audit, conformance, and maturity](29-audit-conformance-and-maturity.md) | Adoption states and audits |
| 30 | [Adoption playbook](30-adoption-playbook.md) | Adoption procedures |

## Related material

- [Instructions](../instructions/README.md)
- [Project template](../project-template/README.md) and [templates index](../project-template/docs/templates/README.md)
- [Prompts](../prompts/README.md)
