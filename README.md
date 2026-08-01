# Younifiedd Fitness — "My Story" Background Fix

## What was wrong
The About/"My Story" section's background video had `mix-blend-mode:screen`
applied to it. Against the near-black section background, screen blending
only lets bright highlights show through — mid-tones and shadows in the
footage collapse to almost nothing. That's what produced the patchy,
partly-black look in your screenshot: only the bright equipment display
was visible, everything else read as empty black.

The hero section has the same `mix-blend-mode:screen` rule, but wasn't
touched — you didn't flag it, so it's left exactly as-is.

## What changed (About section only)
- Removed `mix-blend-mode:screen`; the video now renders normally.
- Added an explicit `opacity:0.58` at the base (desktop/tablet) level so
  removing the blend mode doesn't suddenly make it too bright/competing
  with the text — it now shows real footage instead of a patchy highlight.
- On portrait phones specifically, lowered opacity further from `0.42` to
  `0.28` for stronger text contrast, as asked. Cropping (`object-position`)
  was left untouched since it was already tuned for that breakpoint.

Everything else in the file is byte-identical to what you uploaded — this
was a 2-line CSS change, isolated to the About section's video treatment.

## Deploy to Netlify
Drag this folder onto https://app.netlify.com/drop, or connect it via
"Add new site" > "Deploy manually."

## Files
- `index.html` — the fitness site with the About-section fix applied
- `netlify.toml` — your existing publish config, unchanged
