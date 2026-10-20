# Nexora Governance Manual v1.0.1

**Version:** 1.0.1
**Planned release tag:** `v1.0.1`
**Status:** Draft for release
**Release date:** Pending
**Chapters:** 30

The `v1.0.1` tag does not exist yet. This manual describes the release in
preparation.

## Purpose

This manual is the authoritative organization-wide governance reference for projects that adopt a released Nexora Governance version. It defines authority, information ownership, proportional delivery controls, evidence, release practices, AI-agent boundaries, tooling security, migration, audit, and adoption.

## How to use this manual

- Read chapters 01 and 02 before adopting the package.
- Use the chapter owning a subject as the authority for that subject.
- Follow repository-relative links and the project source-of-truth register.
- Treat prompts, templates, tools, and skills as supporting mechanisms rather than authority.
- Apply proportionality: create artifacts only when their governance purpose applies.

## Authority

The adopted immutable governance release and foundational controls define governance authority. Project records specialize the adopted release without silently weakening it. The Project Owner retains material approval authority.

## Chapter index

### Part I: Governance Foundation

- [01. Governance Policy](01-governance-policy.md)
- [02. Information Architecture](02-information-architecture.md)
- [03. Document Taxonomy and Boundaries](03-document-taxonomy-and-boundaries.md)
- [04. Governance Versioning and Exceptions](04-governance-versioning-and-exceptions.md)
- [05. Lifecycle, Ownership, and Approvals](05-lifecycle-ownership-and-approvals.md)

### Part II: Product, Decisions, and Specification-Driven Delivery

- [06. Specification-Driven Development](06-specification-driven-development.md)
- [07. Spec Kit Standard](07-spec-kit-standard.md)
- [08. Product Requirements Standard](08-product-requirements-standard.md)
- [09. ADR Standard](09-adr-standard.md)
- [10. RFC Standard](10-rfc-standard.md)
- [11. Investigations and Lessons](11-investigations-and-lessons.md)
- [12. Planning and Cross-Specification Delivery](12-planning-and-cross-specification-delivery.md)

### Part III: Verification, Release, and Operations

- [13. Testing, Evidence, and Verification](13-testing-evidence-and-verification.md)
- [14. Release Management](14-release-management.md)
- [15. Operations, Backup, and Recovery](15-operations-backup-and-recovery.md)

### Part IV: Metadata, Indexing, and Source of Truth

- [16. Metadata, Naming, and Status](16-metadata-naming-and-status.md)
- [17. Indexing, Traceability, and Source of Truth](17-indexing-traceability-and-source-of-truth.md)

### Part V: Agents, Tooling, and Integrations

- [18. AI Agent Standard](18-ai-agent-standard.md)
- [19. Agent Switching and Handoffs](19-agent-switching-and-handoffs.md)
- [20. Developer Tooling and Security](20-developer-tooling-and-security.md)
- [21. Context7 Standard](21-context7-standard.md)
- [22. OpenAI Developer Documentation MCP Standard](22-openai-docs-mcp-standard.md)
- [23. codebase-memory-mcp Standard](23-codebase-memory-mcp-standard.md)
- [24. Ponytail Standard](24-ponytail-standard.md)
- [25. Playwright and Remote Integrations](25-playwright-and-remote-integrations.md)

### Part VI: Validation, Packaging, Migration, and Adoption

- [26. Validation and Quality Gates](26-validation-and-quality-gates.md)
- [27. Generated Files, Manifests, and Packaging](27-generated-files-manifests-and-packaging.md)
- [28. Archive, Retention, and Migration](28-archive-retention-and-migration.md)
- [29. Audit, Conformance, and Maturity](29-audit-conformance-and-maturity.md)
- [30. Adoption Playbook](30-adoption-playbook.md)

## Versioning

This manual belongs to release `1.0.1`, which is in preparation for tag
`v1.0.1`. The tag does not exist yet.

The `1.0.0` release was declared Released on 2026-10-12 at the verified source
baseline commit `d00dcab5f70c083a37d612e48eacb67e38aa272e`. No local or origin
`v1.0.0` tag was found; this manual neither claims that tag exists nor creates a
retrospective one. No existing tag is ever moved or rewritten.

Projects adopted on `1.0.0` require no migration for `1.0.1`.

The Project Owner approved shipping this corrective scope under a patch version
although parts of it would ordinarily be classified as minor. That exception is
recorded in `CHANGELOG.md` and `VERSION.md`. It creates no new mandatory
obligation and does not weaken any foundational control. See
[chapter 04](04-governance-versioning-and-exceptions.md).

## Generated and packaged content

Markdown sources are authoritative. Regenerate derivatives and `MANIFEST.json` after all source files are final, then validate a clean release archive extraction before tagging.
