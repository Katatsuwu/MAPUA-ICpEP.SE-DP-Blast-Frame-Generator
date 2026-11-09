# Frame Studio

A browser app for an organization profile-frame campaign. Members choose an approved frame from the catalog, upload their profile photo, export a 1500 × 1500 PNG, and copy the caption prepared for that frame.

## Publish the app

In the repository, open **Settings → Pages** and choose **Deploy from a branch → main → /(root)**. GitHub Pages will serve `index.html`.

## Member flow

1. Open the frame catalog.
2. Select an organization-approved frame.
3. Upload a profile photo and adjust its crop.
4. Download the finished 1500 × 1500 PNG.
5. Copy the caption customized by the admin.

Members cannot add or upload custom frames. Their profile photos are processed locally in the browser.

## Admin flow

Select **Add a frame** from the catalog and enter the starter password `icpepse`. The upload page asks for:

- A frame title.
- A transparent PNG or WebP frame (1500 × 1500 recommended). The app does not impose a file-size cap; GitHub's own API and repository limits still apply.
- The caption members can copy.
- A GitHub fine-grained personal access token limited to this repository, with **Contents: Read and write** permission.

The token is used in the browser to save the image and its caption metadata to the repository's `frames/` folder. The app clears the token field after a successful upload.

## Security limitation

The password gate is client-side and visible in this public repository's source. It is only a convenience gate, not secure admin authentication. Repository token permissions protect actual uploads. For password-only authentication that cannot be bypassed, this static site needs a server-side authentication and storage service.

## Tech

Single-file HTML, CSS, and JavaScript. No build step or external dependencies.
