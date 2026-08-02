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
purple AI cube) are embedded on **every page**, not just their "home" page.
The moment you tap a nav icon, JS reads which link was tapped and shows the
matching scene immediately — so tapping Finance from the Fitness page shows
the emerald scene right away, not a mismatched gold one. That choice is also
carried across the page load (via `sessionStorage`) so the destination page
resumes the same themed scene instead of restarting on a different one.

Flow: tap → correct themed scene fades in on the current page (~650ms) →
browser navigates → destination page shows the same scene already active →
full cinematic plays (~1.9s) → scene fades out while that page's hero
scales/blurs in underneath, so it reads as one continuous motion.

Mechanics: `sessionStorage` flags (`yn_transition`, `yn_theme`) tell the
destination page it arrived via in-app navigation and which scene to show.
A tiny inline script at the very top of `<head>` reads `yn_transition`
synchronously and adds `pt-loading` to `<html>` before first paint, hiding
that page's hero (blurred/scaled out) until the loader finishes — no flash
of content. Direct visits (bookmark, fresh URL) skip the loader entirely.

## Deploy

Drag-and-drop this folder onto Netlify, or connect the GitHub repo — no
build step required, everything is static HTML/CSS/JS.
