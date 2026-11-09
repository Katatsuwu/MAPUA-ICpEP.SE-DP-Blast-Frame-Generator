# Frame Studio

A lightweight browser app for making framed Facebook profile pictures. Upload a profile photo, add a transparent frame, adjust the photo and frame, then export a 1080 × 1080 PNG.

## Use it

1. Open `index.html` in a modern browser, or publish this repository with GitHub Pages.
2. Select a profile photo.
3. Upload a transparent PNG frame. A 1080 × 1080 PNG is recommended so it aligns with the preview.
4. Drag the photo to reposition it. Use the zoom and frame-size sliders to adjust the composition.
5. Select **Download image**.

The app processes images locally in your browser. It does not upload them to a server or post to Facebook.

## Frame file tips

- Use a square transparent PNG.
- Keep the center transparent so the profile photo shows through.
- Keep frame artwork inside the canvas boundaries.
- Avoid including important details too close to the outer edge, since Facebook may display profile photos as circles in some places.

## Tech

Single-file HTML, CSS, and JavaScript. No build step or external dependencies.
