# Younifiedd — Fitness + Finance + AI Automation (Unified)

Three static pages sharing one brand system, linked together with a smooth
cross-fade page transition via the same floating navbar:

- `index.html` — Fitness (YOUNIFIEDD) landing page. Home page.
- `trading.html` — Finance / Trading landing page.
- `ai-automation.html` — AI Automation landing page (premium dark + gold/purple theme).

## Navigation

Every page shares the identical floating glass-capsule navbar (logo, three
icons — Fitness / Finance / AI Automation — and a CTA pill). Tapping a nav
icon plays a short brand-colored fade transition, then loads the target page.
The active page's icon is highlighted; AI Automation's active glow uses the
page's purple accent, the other two use gold.

The transition is a small fixed-position overlay (`#pageTransition`) with a
~150–200ms fade-in, a short hold, then the browser navigates to the target
page. A `sessionStorage` flag (`yn_transition`) tells the destination page it
arrived via this transition, so it starts with the overlay visible and fades
it out on load instead of a hard cut.

## Deploy

Drag-and-drop this folder onto Netlify, or connect the GitHub repo — no
build step required, everything is static HTML/CSS/JS.
