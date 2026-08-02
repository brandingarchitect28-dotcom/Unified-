# Younifiedd — Fitness + Finance + AI Automation (Unified)

Three static pages sharing one brand system, linked together with a cinematic
cross-page loading transition triggered from the same floating navbar:

- `index.html` — Fitness (YOUNIFIEDD) landing page. Home page.
- `trading.html` — Finance / Trading landing page.
- `ai-automation.html` — AI Automation landing page.

## Navigation

Every page shares the identical floating glass-capsule navbar (logo, three
icons — Fitness / Finance / AI Automation — and a CTA pill).

## Cinematic loading transition

Tapping a nav icon plays a short themed "brand mark" glimpse (~650ms) on the
page you're leaving, then a full cinematic loading scene plays on the
destination page for ~1.9s before fading into that page's hero:

- **Fitness** (gold): concentric rotating rings around a glowing dumbbell,
  orbiting particles, a thin progress line with a traveling light.
- **Finance** (emerald): a glass sphere with an animated candlestick chart
  and world-map texture, orbiting currency symbols, an animated wave line.
- **AI Automation** (purple): a rotating translucent glass cube labelled
  "AI", surrounded by 8 floating nodes (OpenAI, Claude, Gemini, API, MCP,
  RAG, Workflow, Automation), a circular progress ring.

Mechanics: a `sessionStorage` flag (`yn_transition`) tells the destination
page it arrived via in-app navigation. A tiny inline script at the very top
of `<head>` reads that flag synchronously and adds `pt-loading` to `<html>`
before first paint, which hides that page's hero (blurred/scaled out) so
there's no flash of content before the loader finishes. The loader then
fades out and the hero animates in as one continuous motion. Landing on any
page directly (bookmark, fresh URL) skips the loader entirely — it only
plays for in-app navigation between the three pages.

## Deploy

Drag-and-drop this folder onto Netlify, or connect the GitHub repo — no
build step required, everything is static HTML/CSS/JS.
