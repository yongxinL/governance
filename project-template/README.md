# Nexora Project Template v1.0.1

This directory is the project-local scaffold copied from the released Nexora
Governance package into an adopting project.

## Authority

The template is non-authoritative until copied, customized, reviewed, and
approved in a target project. The central manual at the immutable adopted tag
remains authoritative for governance rules.

## Installation

Copy the **contents** of this directory into the project root, including hidden
files:

```bash
cp -a <central-governance-checkout>/project-template/. <project-root>/
```

Do not copy the central manual into the target project. Do not manually create
`.specify/` or `specs/`; GitHub Spec Kit owns those locations.

## Required sequence

1. Read `ADOPTION-INSTRUCTIONS.md`.
2. Replace known customization markers without inventing values.
3. Select one primary agent and create its live project configuration from the
   corresponding example.
4. Keep all conditional integrations disabled until permitted, registered, and
   authorized.
5. Create product vision and requirements from the product templates.
6. Install and initialize a pinned compatible Spec Kit release as a separate,
   reviewable stage.
7. Reconcile and approve the native constitution, then remove the temporary
   reconciliation template.
8. Run governance adoption and documentation validation prompts.

## Important boundaries

- Credentials and secret values never enter the repository.
- Example configuration is not live configuration.
- Unknown markers may remain only when the adoption record explains why and
  identifies the required follow-up.
- An AI agent may prepare and validate adoption work but cannot approve it.
