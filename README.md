# Younifiedd Fitness — Mobile "My Story" Video Fix (scoped)

## The one change
Inside `@media (max-width:700px) and (orientation:portrait)` only, the
About/"My Story" background video still had `mix-blend-mode:screen`
inherited from the base desktop rule. That blend mode is what was crushing
the video to black behind the title and timeline — screen blending against
a near-black backdrop only lets bright highlights through, so most of the
footage effectively disappeared, and it read as "the video isn't filling
the frame" even though `object-fit:cover` was already sizing it correctly.

Added `mix-blend-mode:normal;` to that one mobile-portrait rule. That's the
entire change — one line, inside the existing mobile-only block. Opacity
(0.42), cropping (12% center), desktop, tablet, and every other section are
untouched.

## Deploy to Netlify
Drag this folder onto https://app.netlify.com/drop, or connect it via
"Add new site" > "Deploy manually."
