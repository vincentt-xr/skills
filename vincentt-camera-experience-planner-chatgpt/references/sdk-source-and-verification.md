# Vincentt XR SDK source and verification

This reference is a portable source locator, not a frozen API catalog. It must never be treated as proof that an API exists in a particular release.

## Canonical source

- Official SDK repository: <https://github.com/vincentt-xr/sdk>
- Package: `@vincentt-xr/sdk`
- The repository's `GROUNDING.md` is the broad API and composition guide. The SDK package also lists it among its published files. A consuming project may therefore have `node_modules/@vincentt-xr/sdk/GROUNDING.md`, but this skill must **not** depend on that local file: a skill may be used on another device or for a project without dependencies installed.
- Official docs and API pages live in the repository's `docs/` tree. Use the `docs/docs.json` navigation to locate the current canonical page, then inspect the relevant page and its release/tag.

Useful source paths (resolve against the verified release tag, not automatically against moving `main`):

- `GROUNDING.md`
- `package.json` (`version` and `exports`)
- `docs/SDK_DOCUMENTATION.md`
- `docs/api/` (API-specific pages, for example screen components, trackers, coordinates, and runtime 3D)
- `docs/examples/` and `docs/guides/` (usage examples and workflow guidance)

For a verified tag `TAG`, cite links in this form:

- `https://github.com/vincentt-xr/sdk/blob/TAG/GROUNDING.md`
- `https://github.com/vincentt-xr/sdk/blob/TAG/package.json`
- `https://github.com/vincentt-xr/sdk/tree/TAG/docs`
- For an API page: `https://github.com/vincentt-xr/sdk/blob/TAG/docs/api/PAGE.mdx`

Replace `TAG` and `PAGE` only after confirming they exist. If the public docs site provides a stable version-specific page, it may be cited alongside the repository source.

## Required verification procedure

1. Determine the target project's installed/requested SDK version from its package manifest or lockfile when accessible. If it is not available, ask only if version choice changes the correctness of the prompt; otherwise state the selected version as an assumption and use the current official published release after verifying it.
2. Locate that exact version's official tag/release in `vincentt-xr/sdk`. Confirm the tag's `package.json` version. Do not silently substitute the checkout's latest tag, a fork, a blog post, or the skill authoring machine's installed package.
3. Check `package.json` `exports` to verify that the import subpath is public. Check the release's `GROUNDING.md`, API docs, or public types/source to verify each named export and relevant props/arguments/behavior. The export map alone verifies a subpath, not a named symbol.
4. Cite the specific versioned file and relevant heading/API page in the generated prompt. Prefer a narrow direct link over a repository homepage.
5. When the exact release cannot be reached, do not guess from memory or from a different release. State which APIs remain unverified and leave a compact implementation-agent instruction to confirm them against the target version before coding.

## Import-door orientation

These domains are navigation hints only. Always verify the exact symbol and release before using them.

- `@vincentt-xr/sdk`: core scene, screen-space components, and general runtime APIs.
- `@vincentt-xr/sdk/tracking`: trackers and tracking-related components/hooks.
- `@vincentt-xr/sdk/face-effects`: deeper face-effect APIs.
- `@vincentt-xr/sdk/low-level`: lower-level runtime and diagnostics APIs.
- `@vincentt-xr/sdk/scene-object`: scene-object authoring APIs.
- `@vincentt-xr/sdk/product`: product placement AR APIs.

Choose the narrow task-appropriate public entrypoint. Do not invent an entrypoint based on an internal source directory. For ordinary screen graphics, investigate the versioned screen component docs (for example `ScreenText`, `ScreenImage`, and `ScreenShape`). For tracked/world-space content, investigate the relevant tracker and runtime 3D docs. Use `<Html>` only as an R3F/Drei capability after confirming the target project setup supports it; it is not an SDK export.
