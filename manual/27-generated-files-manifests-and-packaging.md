# 27. Generated Files, Manifests, and Packaging

**Part VI** · Owns: authoritative sources, generated files, Markdown versus HTML authority, source fingerprints, manifest format, sizes and SHA-256, safe paths, deterministic generation, ZIP construction, clean extraction, package validation.

## 27.1 Authoritative sources

Markdown files are authoritative. In this package, `instructions/README.md` is the source; `instructions/README.html` is generated.

## 27.2 Generated files

A generated file states: that it was generated from its source path, that it must not be edited directly, governance version, generation date, source path, source SHA-256, and generator and version. If source and derivative disagree, the source prevails and the derivative is regenerated.

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

One root directory (`nexora-governance-v1.0/`), relative paths only, entries in sorted order, hidden files preserved.

## 27.6 Clean extraction validation

1. Extract into a new empty directory.
2. Recalculate every file's size and SHA-256.
3. Confirm each manifest entry matches and no unmanifested file exists except `MANIFEST.json`.
4. Re-run structural and link validation.
5. Calculate the ZIP's byte size and SHA-256 and publish them outside the ZIP (release notes or completion report).

## 27.7 Project use

Projects apply the same source-versus-generated rules to their own generated documentation (for example rendered HTML or API references): mark generated files, record their source, and never edit them directly.
