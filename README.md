# The Quarter in Motion — Q3 2026 Web Newsletter

Interactive, responsive HTML5 corporate newsletter for **TVS Electronics (TVSE)** and **Harita Techserv**,
built from *TVSE Times — July, August, September 2026* and the *Haritans Q3 2026* draft.

- `index.html` — the complete single-page publication (HTML5, Tailwind CSS via CDN, vanilla JavaScript, inline SVG icons, CSS animations, IntersectionObserver reveals, accessible `<dialog>` menu and story reader).
- `assets/img/` — the 30 supplied newsletter photographs and posters, converted to WebP (plus two product crops of the KB-106 poster used in the hero and product spotlight).
- `assets/fonts/` — D-DIN Regular and Bold (Datto Inc., SIL Open Font License 1.1) self-hosted for the TVSE sections.

Open `index.html` directly, or serve the folder with any static server.

## Brand handling

| Topic | Implementation |
| --- | --- |
| Logos | TVSE logo loads from the supplied asset URL; the Harita logo (`assets/img/harita-logo.png`) is the official artwork extracted from the Haritans editions. Both sit together on a white plate in the header; never redrawn, shadowed, rotated, recoloured or cropped. |
| TVSE colour | `--tvse-blue: #0000DA` plus tints and shades of the same hue only (`--tvse-deep`, `--tvse-ink`). |
| Harita colour | `--harita-green` (#0B6B3A) is sampled from the official logo mark. `--harita-blue` and `--harita-purple` remain provisional until confirmed against the Harita guideline swatches; every Harita gradient and accent derives from these three tokens. |
| TVSE type | D-DIN (digital typeface), self-hosted. Headlines Bold, body Regular. |
| Harita type | `"DIN 2014"` is referenced by name and renders wherever the licensed font is installed; it is not redistributed. Fallback chain: D-DIN → Arial → Helvetica. |
| Shared shell | Inter (Google Fonts) is used only in the neutral header, hero, intro, transition, closing and footer. |
| Separation | TVSE and Harita sections are wrapped in `.brand-tvse` / `.brand-harita` scopes; palettes are never mixed inside one component. |

## Content placeholders

Everything on the page comes from the supplied documents. Items the source did not provide are marked in the page and should be filled before publishing:

- Stories without a supplied photograph (ITIL Training, the Harita timeline milestones, team moments, wellness and mindset rows) render as text-only layouts rather than empty image slots. The Harita featured story, technology feature and index rows use the engineering imagery from the Haritans editions; the customer-champion portraits are the four supplied photographs, named per the June'26 Client Appreciation page.
- `[Achievement 01–04]`, `[Session Topic 01/02]`, `[Employee Name] — [Date]` — Harita milestones, knowledge-sharing sessions and birthday stars, as drafted.
- `[ADD CTA URL]` (HTML comments / `data-placeholder` attributes) — KB-106 product page, caption-challenge submission link, Privacy and Terms pages. These currently point to the company home pages so every button works. The footer intentionally carries no social media links.

No statistics, dates, partnerships or claims were invented; the "Q3 at a glance" counts are taken directly from the stories in the issue.

## Video

The KB-106 product spotlight plays `https://www.tvselectronics.in/videos/kb-106.mp4` as an ambient film (`autoplay loop muted playsinline`, `playbackRate = 0.7`, poster falls back to the product still, paused under reduced motion). The hero is an animated six-tile image grid with staggered entrance, slow Ken Burns drift and cross-fading tiles.

## Accessibility and motion

Semantic landmarks, skip link, visible focus states, 44 px touch targets, `aria-label`s on icon buttons, ESC-closable dialogs with focus return, lazy-loaded images with alt text, and a `prefers-reduced-motion` mode that removes parallax, transforms and ambient animation while keeping simple opacity transitions.
