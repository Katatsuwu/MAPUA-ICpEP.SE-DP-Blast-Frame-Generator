# Frame Studio

A lightweight browser app for making framed Facebook profile pictures. Upload a profile photo, choose a frame from the organization's shared gallery (or upload one from your device), adjust the composition, and export a 1080 × 1080 PNG.

## Use the frame maker

1. To make it available to the organization, open the repository's **Settings → Pages** and choose **Deploy from a branch → main → /(root)**. GitHub Pages will serve the app. For a quick local try, open `index.html` in a modern browser.
2. Select a profile photo.
3. Choose an organization frame from the gallery, or upload a transparent PNG/WebP from your device.
4. Drag the photo to reposition it and adjust the zoom/frame-size controls.
5. Select **Download image**.

Profile photos are processed locally in the browser. They are not uploaded or posted to Facebook.

## Admin console and shared frames

Open `admin.html` (also linked from the frame maker). The starter password is `icpepse`.

To publish a frame for everyone:

1. Create a fine-grained GitHub personal access token limited to this repository.
2. Grant it **Contents: Read and write**.
3. Sign in to the admin console with the password, then enter the token, a frame name, and a transparent PNG or WebP file.
4. Upload. The image is committed to `frames/` on the `main` branch and appears in the shared gallery.

The token is sent from your browser directly to GitHub's API. The app does not save it, and clears the field after a successful upload.

**Security limitation:** this is a static GitHub Pages app. The password check is only a convenience gate and is visible in the public source. It does not securely restrict the admin page. GitHub token permissions are the actual protection on repository writes. For real password-only admin security, the app needs a server-side authentication and storage service.

## Frame file tips

- Use a square transparent PNG or WebP; 1080 × 1080 is recommended.
- Keep the center transparent so the profile photo shows through.
- Keep artwork inside the canvas boundaries.
- Avoid important details near the outer edge because Facebook may display profile pictures as circles in some places.
- Admin uploads are limited to 8 MB.

## Tech

Single-file HTML, CSS, and JavaScript. No build step or external dependencies. Shared frames are stored in the GitHub repository.
