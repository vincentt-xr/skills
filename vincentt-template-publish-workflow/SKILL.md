---
name: vincentt-template-publish-workflow
description: Audit, visually represent, and publish a Vincentt template by generating a project-specific gallery thumbnail, obtaining user confirmation, preparing its repository and version, publishing it, and preparing the manual gallery handoff.
---

# Vincentt Template Publish Workflow

Use this workflow when a user wants to publish or update a project as a Vincentt template. Keep the workflow portable: adapt repository, shell, browser, and Vincentt tooling to the agent's available capabilities.

## Operating rules

- Inspect the target project before changing it. Preserve unrelated existing work.
- Audit first, report findings, and wait for explicit user confirmation before release preparation or publishing.
- If the user requests changes, apply them, rerun the relevant audit, and request confirmation again.
- Treat GitHub ownership as user-controlled. A personal account or any organization is acceptable; do not require a particular owner.
- New templates start at version `1.0.0`. Existing templates may use the next appropriate semantic version, such as `1.0.1`, `2.0.0`, or `3.1.1`. Do not add a `v` prefix.
- Do not publish with uncommitted release-relevant changes. Commit and push the final state before tagging and publishing.
- Never invent a production URL, tag URL, gallery value, or asset. Mark unavailable values as needing user input.
- A generated thumbnail is a proposed gallery asset, not a substitute for user approval; never claim it was uploaded to the gallery.
- “Make prod-read” is intentional product wording and must be preserved exactly.

## Workflow

### 1. Discover and audit

Identify the project root, repository state, package manager, available Vincentt configuration, and existing version tags. Run the checks appropriate to the project. Use [references/audit-checklist.md](references/audit-checklist.md) and report both passing checks and actionable findings.

### 2. Generate the gallery thumbnail

After inspecting the project’s product identity and visual system, prepare a thumbnail concept that reflects the actual project rather than a generic template. Read [references/thumbnail-generation.md](references/thumbnail-generation.md) for the required analysis, prompt structure, output constraints, and validation steps. Use the built-in image-generation capability by default when available. Save the selected final asset inside the project workspace and report its path; if generation is unavailable, provide the complete suggested prompt and mark the thumbnail as a user action.

### 3. Confirm the release

Show the audit report and thumbnail result in a concise, decision-oriented format. Include proposed fixes, release risks, the generated thumbnail or prompt, and any missing user-provided assets or metadata. Stop and request explicit confirmation before committing, tagging, or publishing. Repeat discovery/audit, thumbnail generation or revision, and confirmation after requested changes.

### 4. Prepare Git and version

After confirmation, verify the intended repository and remote. Ensure the required GitHub visibility/accessibility is satisfied under the user's chosen account or organization. Commit and push the final release state. Choose the version according to the rules above, create the tag, and push it. Confirm the tag URL when it can be determined.

### 5. Publish

Run `vincentt publish` from the project root when the command is available. Use `vincentt help` only when necessary to resolve command usage. Capture and show the production URL returned by the publish command. If publishing fails, report the exact failure and stop before claiming completion.

### 6. Prepare the gallery handoff

Use [references/gallery-handoff.md](references/gallery-handoff.md) to produce a copy-ready set of values and instructions for the user. Clearly separate generated values from user decisions and missing uploads. Direct the user to `https://admin.vincentt.studio/gallery/` for the remaining manual steps, including the final “Make prod-read” action.

## Completion standard

The workflow is complete when the project has been audited and confirmed, the final code is committed and pushed, the intended version tag is pushed, `vincentt publish` has returned a production URL, and the user has received a complete gallery handoff. Manual gallery submission remains the user's responsibility unless an explicitly authorized compatible UI integration is available.
