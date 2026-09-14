# Audit checklist

Use only the checks relevant to the target project, and record commands or evidence when available.

## Project and repository

- Confirm the project root and identify the framework/runtime, including Remix information when present.
- Inspect Git status, current branch, remote, repository visibility/accessibility, and existing tags.
- Check for required Vincentt configuration and publish scripts.
- Inspect `.vincentt/project.json` for a binding to an unavailable project.
- Run `vincentt whoami` and record the active account/workspace when the CLI is available.
- Check requested Vincentt slug availability without silently reserving a fallback.
- Verify release-relevant untracked/modified files and package name/version/lockfile consistency.

## Product quality

- Review branding: name, logo, palette, typography, imagery, and visible product identity.
- Review SEO: title, description, metadata, canonical/robots behavior, social preview data, and meaningful alt text.
- Review SVGs for valid markup, correct sizing/viewBox, accessibility, and unsafe or accidental content.
- Inspect entrypoints, scene files, interaction/gesture logic, and referenced assets before creating marketing imagery.
- Flag generic identity values such as `v2-template`, `XR App - Vincentt`, or generic AR descriptions.
- Run typecheck, lint, tests, and build checks when configured.

## Report format

Summarize:

- Ready items
- Issues requiring fixes
- Warnings or decisions
- User decisions, including repository, slug, title, rank, and release confirmation
- Commands/checks that could not run and why
- Proposed version and missing release/gallery inputs
- Proposed slug and any available alternatives
- Missing thumbnail or preview-video uploads

Do not request release confirmation until the report is shown to the user.
