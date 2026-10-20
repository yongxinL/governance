# Maintenance

Repository-only material for maintaining Nexora Governance. Nothing under
`maintenance/` or `.forgejo/` is part of the released package or listed in
MANIFEST.json.

## Change process
1. Open a pull request using the template.
2. Classify the change as patch, minor, or major (manual chapter 04).
3. Record significant reasoning as a decision in `decisions/`.
4. CI must pass before merge.

## Release process
1. Update VERSION.md and CHANGELOG.md.
2. Regenerate instructions/README.html, then MANIFEST.json (in that order).
3. Merge, then create an annotated tag `vX.Y.Z` on main.
4. Create a Forgejo release with the ZIP and its SHA-256.
Tags are never moved or deleted.

## Decisions
`decisions/DEC-NNN-<title>.md` records why governance rules exist.
DEC-001 to DEC-020 correspond to the approved v1.0 decisions D1-D20.
These are not project ADRs.