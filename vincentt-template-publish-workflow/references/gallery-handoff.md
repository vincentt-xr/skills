# Manual gallery handoff

After publishing, provide this information in a copy-ready format.

## Gallery location

`https://admin.vincentt.studio/gallery/`

## Fields to provide

- **Title:** generated from the project or confirmed with the user.
- **Description:** final copy, no more than 280 characters.
- **Thumbnail:** verified local asset path for the user to upload; 16:9; WebP, PNG, or JPEG; under 2 MB. A local path is not an upload to the gallery.
- **Preview video:** user upload; MP4 with H.264 video and AAC audio or no audio; under 20 MB; under 30 seconds.
- **Source:** public GitHub URL for the exact pushed version tag, not the repository root.
- **Rank:** a number supplied or approved by the user; suggest one only when appropriate.
- **Vincentt production URL:** exact URL returned by `vincentt publish`; it may differ from the requested slug if the original address was taken.

## Final instruction

Tell the user to add the template in the gallery, fill the fields, upload the assets, paste the exact tagged source URL, and click **Make prod-read**.

Before handing off, verify the local thumbnail exists and is under 2 MB. Clearly distinguish generated local assets from user-uploaded gallery assets.

Label each value as one of:

- **Generated:** obtained from the repository or publish output.
- **Suggested:** proposed by the agent and requiring user approval.
- **User action:** must be supplied or uploaded manually.

## Final handoff checklist

- Title confirmed.
- Description is no more than 280 characters.
- Thumbnail path verified, 16:9, supported format, under 2 MB.
- Preview video supplied by the user or marked missing.
- Exact public GitHub tag URL supplied.
- Rank supplied or explicitly marked for user decision.
- Vincentt production URL copied from publish output.
- User instructed to click **Make prod-read**.
