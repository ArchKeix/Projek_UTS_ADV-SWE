# Copilot instructions

## Project overview

This is a static portfolio site for Muhammad Rayhanza Barraq. It is served as plain HTML/CSS/JavaScript and uses Bootstrap 5.3.3 from the jsDelivr CDN; there is no application framework, package manager, build step, or backend.

- `index.html` is the source of truth for all portfolio content, section order, semantic structure, navigation anchors, metadata, and CV links.
- `styles.css` contains the complete visual system, layout, responsive breakpoints, hover/focus states, and reduced-motion behavior. It uses CSS custom properties near the top for the main palette and typography.
- `script.js` only controls the mobile navigation menu: it synchronizes `aria-expanded`/`aria-label` with the `.is-open` class and closes the menu after a navigation link is selected.
- `assets/cv-muhammad-rayhanza-barraq.pdf` is the downloadable CV referenced by the page. Keep relative asset paths working from `index.html`.

The page is organized as one document with anchored sections: hero/home, projects and experience, skills, education, certifications/languages, contact, and footer. Desktop uses a centered max-width shell and multi-column layouts; the `760px` and `440px` media queries collapse those layouts for smaller screens.

## Build, test, and lint

There are currently no repository-defined build, test, or lint commands. Do not introduce a package install or generated build output for routine edits.

For manual verification, open `index.html` directly in a browser or serve the repository root with any local static HTTP server, then check:

- desktop and narrow/mobile layouts, especially the `760px` and `440px` breakpoints;
- all hash navigation links and both CV download links;
- mobile menu open/close behavior and its `aria-expanded`/`aria-label` state;
- keyboard focus visibility and the reduced-motion preference.

Because there is no test runner, a single automated test command is not available. If tests are added later, document the exact runner and single-test selector here.

## Implementation conventions

- Keep the site lightweight and preserve the current three-file split unless a new capability genuinely requires another file. Reuse Bootstrap 5 utilities and components before adding equivalent custom CSS.
- Update portfolio copy and section markup in `index.html`; do not duplicate content in JavaScript or CSS.
- Use the existing semantic sections, heading hierarchy, IDs, and anchor-based navigation when adding content. New navigation items must point to a matching section ID.
- Reuse the existing CSS custom properties and component patterns (`.section-shell`, `.section-heading`, `.button`, `.work-card`, and related modifiers) instead of adding one-off colors, spacing, or typography.
- Preserve the existing responsive strategy: desktop-first layout, mobile navigation at `max-width: 760px`, tighter phone adjustments at `max-width: 440px`, and `prefers-reduced-motion` support.
- Maintain accessibility details already present: meaningful `alt` text when images are added, semantic headings/sections, visible `:focus-visible` styles, the skip link, button state attributes, and `aria-hidden` for decorative symbols.
- Keep JavaScript defensive for pages where the mobile navigation elements may not exist; follow the existing null checks and avoid adding global behavior unrelated to the menu.
- Use relative, lowercase asset filenames and verify links against the actual files under `assets/`.
