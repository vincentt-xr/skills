# Gallery thumbnail generation

Use this procedure when the target project needs a Vincentt gallery thumbnail.

## Analyze the project

Inspect the project’s visible product identity before writing the prompt:

- product name, purpose, audience, and strongest differentiator;
- landing-page or app screenshots, layout, imagery, and visual tone;
- logo, palette, typography, iconography, and distinctive motifs;
- whether the thumbnail should show the product UI, a representative scene, or an abstract brand-led composition.
- entrypoints and scene files;
- interaction and gesture logic;
- referenced image/model assets and asset families;
- the strongest product differentiator.

Prefer real project UI or imagery as visual references when available. Do not invent features, claims, logos, slogans, or brand colors that are not supported by the project.
For scene-based AR projects, base the concept on the real scene composition and asset families. A project with podium, event, curtain, floral, courtroom, or stage assets should show those real visual motifs rather than a generic photobooth or unrelated environment.

## Prompt and generation

Create one focused 16:9 thumbnail prompt using the project context. Include:

- intended use: Vincentt template gallery thumbnail;
- the project’s actual subject and visual language;
- composition that remains legible at small size;
- palette and lighting derived from the project;
- whether product UI or a representative visual should be the focal point;
- exact text only when it is necessary and verified;
- constraints: no watermark, no unrelated branding, no invented claims, no illegible dense text.

Use the built-in image-generation tool by default. Treat repository screenshots or images as references, not automatic edit targets, unless the user specifically requests an edit. Generate a new image when the project has no suitable existing thumbnail asset.

## Validate and save

Inspect the result for visual fidelity to the project, readable hierarchy, correct aspect ratio, accidental text, artifacts, and resemblance to an unrelated stock image. If needed, make one targeted revision. Save the chosen asset in the project workspace with a clear non-destructive filename such as `thumbnail.png` or `thumbnail-v2.png`; do not overwrite an existing asset unless the user asked for replacement.

The gallery requirement is 16:9 and the file must be WebP, PNG, or JPEG under 2 MB. If the generated image does not meet these constraints, resize or convert it using an available local image tool. Verify that the final file exists inside the workspace, then verify and report its dimensions, format, and file size. Never report an asset as saved if the copy or conversion failed.

Report:

- **Generated:** verified local thumbnail path, dimensions, format, and file size;
- **Suggested:** the prompt or any proposed visual direction requiring approval;
- **User action:** upload the final thumbnail to the gallery after publishing.
