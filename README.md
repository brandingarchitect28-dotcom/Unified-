# Younifiedd — Fitness + Finance + AI Automation (Unified)

Three static pages sharing one brand system, linked with a cinematic
cross-page loading transition triggered from the same floating navbar.

- `index.html` — Fitness (YOUNIFIEDD) landing page. Home page.
- `trading.html` — Finance / Trading landing page.
- `ai-automation.html` — AI Automation landing page.

## Navigation

Every page shares the identical floating glass-capsule navbar (logo, three
icons — Fitness / Finance / AI Automation — and a CTA pill).

## Cinematic loading transition

All three themed loading scenes (gold fitness rings, emerald finance sphere,
purple AI cube) are embedded on **every page**. The moment you tap a nav
icon, JS reads which link was tapped and shows the matching scene
immediately, and that choice is carried across the page load via
`sessionStorage` so the destination page resumes the same themed scene.

## Trading page videos

- **Hero background** — swapped to the "person sitting" video (portrait,
  dark/moody), matching the page's dark aesthetic. `object-position` is
  tuned per breakpoint (desktop `50% 30%`, mobile `50% 25%`) so the subject
  stays framed as the crop area changes shape on smaller screens.
- **Final CTA background** — the hand-writing-on-charts video now plays
  behind the closing call-to-action section (previously a static image),
  reusing the same `.parallax-media` scroll behavior. Object-position is
  tuned per breakpoint here too (`60% center` desktop, `70% center` mobile)
  to keep the hand/chart subject in frame.
- Both videos autoplay muted/looped with a poster frame (extracted from
  each video) so there's no flash of blank space before playback starts.

## Deploy

Drag-and-drop this folder onto Netlify, or connect the GitHub repo — no
build step required, everything is static HTML/CSS/JS.
