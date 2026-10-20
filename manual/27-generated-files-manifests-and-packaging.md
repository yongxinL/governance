# 27. Generated Files, Manifests, and Packaging

**Part VI** · **Owns:** authoritative sources, generated files, Markdown versus HTML authority, source fingerprints, manifest format, sizes and SHA-256, safe paths, deterministic generation, ZIP construction, clean extraction, package validation.

## 27.1 Authoritative sources

Markdown files are authoritative. In this package, `instructions/README.md` is the source; `instructions/README.html` is generated.

## 27.2 Generated files

A generated file records, in machine-readable form:

- that it is generated and must not be edited directly;
- the authoritative source path;
- the governance version;
- the generation date;
- the source SHA-256;
- the generator name;
- the generator version.

If source and derivative disagree, the source prevails and the derivative is
regenerated. A derivative whose recorded source fingerprint no longer matches its
source is stale and fails validation. Never hand-edit a generated file to make it
appear current.

## 27.3 Manifest

`MANIFEST.json`:

- Is generated after every other file is final.
- Lists every package file except itself, with relative path, exact byte size, and SHA-256.
- Uses normalized forward-slash relative paths with no `..`, no leading `/`, and no duplicates.
- Sorts entries lexicographically by path.
- Declares its own exclusion explicitly (it does not hash itself).
- Uses stable JSON formatting (UTF-8, two-space indent, sorted keys, trailing newline).

## 27.4 File conventions

UTF-8, LF line endings, stable ordering, one package root. Excluded: temporary files, editor backups, secret files, caches, build output, unapproved hidden files, `.gitkeep`. The approved hidden path is `project-template/.codex/`.

## 27.5 ZIP construction

One root directory named `nexora-governance-vX.Y.Z/` using the complete semantic version, relative paths only, entries in sorted order, hidden files preserved.

## 27.6 Clean extraction validation

1. Extract into a new empty directory.
2. Recalculate every file's size and SHA-256.
3. Confirm each manifest entry matches and no unmanifested file exists except `MANIFEST.json`.
4. Re-run structural and link validation.
5. Calculate the ZIP's byte size and SHA-256 and publish them outside the ZIP (release notes or completion report).

## 27.7 Project use

Projects apply the same source-versus-generated rules to their own generated documentation (for example rendered HTML or API references): mark generated files, record their source, and never edit them directly.

### 27.8 Skills and prompt packaging

Released prompts, reusable skills, skill references, and skill templates are
package files and must appear in `MANIFEST.json` with exact byte size and
SHA-256. Any change to them requires regeneration of derived files, the manifest,
and clean-extraction validation before a new immutable tag is created.

When the optional governance skill is included in a release, **every** file under
`skills/` is a package file: `SKILL.md`, each file under `references/`, and each
file under `templates/`. Coverage is all-or-nothing. A partially manifested skill
is a packaging defect, because it would let a consumer verify the entry point
while an unverified reference or template is shipped beside it.

Approved hidden files inside `project-template/`, including `project-template/.codex/`,
are package files and must be manifested. Hidden status never exempts a file from
coverage.

### 27.9 Package versus repository-only content

Package content is what an adopting project receives. The following are
repository-only and are excluded from `MANIFEST.json` and from the release
archive:

- `.git/`, `.gitattributes`, `.gitignore`;
- `.forgejo/` workflow and pull-request templates;
- `maintenance/`, including any central decision records;
- the `skills/` directory when the skill is not included in a given release.

Exclusion is declared and reviewable, not incidental. If a file is neither
manifested nor declared repository-only, it is a packaging finding.
