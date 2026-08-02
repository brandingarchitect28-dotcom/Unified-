# Younifiedd — Fitness + Trading (Unified)

Two static pages sharing one brand system, linked together with a smooth
cross-fade page transition:

- `index.html` — Fitness (YOUNIFIEDD) landing page. Home page.
- `trading.html` — Trading (Younifiedd Trading) landing page.

## Navigation

- On the fitness page, tapping **Finance** in the floating nav plays a
  brand-colored fade transition, then loads `trading.html`.
- On the trading page, tapping **Fitness** (top-left of the nav) plays the
  same transition back to `index.html`.

The transition is a small fixed-position overlay (`#pageTransition`) with a
150–200ms fade-in, a short hold, then the browser navigates to the target
page. A `sessionStorage` flag (`yn_transition`) tells the destination page it
arrived via this transition, so it starts with the overlay visible and fades
it out on load instead of a hard cut — giving the illusion of one continuous
app even though it's two plain HTML files.

## Deploy

Drag-and-drop this folder onto Netlify, or connect the GitHub repo — no
build step required, everything is static HTML/CSS/JS with inline
base64 media.
