# The Quarter in Motion — Q3 2026 Web Newsletter

Interactive, responsive HTML5 corporate newsletter for **TVS Electronics (TVSE)** and **Harita Techserv**,
built from *TVSE Times — July, August, September 2026* and the *Haritans Q3 2026* draft.

- `index.html` — the complete single-page publication (HTML5, Tailwind CSS via CDN, vanilla JavaScript, CSS animations, IntersectionObserver reveals, accessible `<dialog>` menu and story reader).
- `assets/img/` — the 30 supplied newsletter photographs and posters, converted to WebP (plus two product crops of the KB-106 poster used in the hero and product spotlight).
- `assets/fonts/` — D-DIN Regular and Bold (Datto Inc., SIL Open Font License 1.1) self-hosted for the TVSE sections.

Open `index.html` directly, or serve the folder with any static server.

## Brand handling

| Topic | Implementation |
| --- | --- |
| Logos | Loaded from the supplied asset URLs, never redrawn. Always placed on a white plate for clear space. No shadows, rotation, recolouring or cropping. |
| TVSE colour | `--tvse-blue: #0000DA` plus tints and shades of the same hue only (`--tvse-deep`, `--tvse-ink`). |
| Harita colour | `--harita-green`, `--harita-blue`, `--harita-purple` tokens in `:root`. **Set these from the Harita brand guideline swatches** — the guideline PDF was not attached, so the current values are provisional and every Harita gradient and accent derives from these three tokens. |
| TVSE type | D-DIN (digital typeface), self-hosted. Headlines Bold, body Regular. |
| Harita type | `"DIN 2014"` is referenced by name and renders wherever the licensed font is installed; it is not redistributed. Fallback chain: D-DIN → Arial → Helvetica. |
| Shared shell | Inter (Google Fonts) is used only in the neutral header, hero, intro, transition, closing and footer. |
| Separation | TVSE and Harita sections are wrapped in `.brand-tvse` / `.brand-harita` scopes; palettes are never mixed inside one component. |

## Content placeholders

Everything on the page comes from the supplied documents. Items the source did not provide are marked in the page and should be filled before publishing:

- `[ADD IMAGE]` — all Harita visuals (the Haritans draft contained no photographs) and the ITIL Training photo.
- `[Achievement 01–04]`, `[Session Topic 01/02]`, `[Employee Name] — [Date]` — Harita milestones, knowledge-sharing sessions and birthday stars, as drafted.
- `[ADD CTA URL]` (HTML comments / `data-placeholder` attributes) — KB-106 product page, caption-challenge submission link, social profiles, Privacy and Terms pages. These currently point to the company home pages so every button works.
- `[ADD SOCIAL URLS]` — footer social icons.

No statistics, dates, partnerships or claims were invented; the "Q3 at a glance" counts are taken directly from the stories in the issue.

## Video

No video asset was supplied, so the page uses still photography. If a video is added, use
`<video data-ambient autoplay loop muted playsinline>` inside an image frame — the script sets `playbackRate = 0.7` and respects reduced motion.

## Accessibility and motion

Semantic landmarks, skip link, visible focus states, 44 px touch targets, `aria-label`s on icon buttons, ESC-closable dialogs with focus return, lazy-loaded images with alt text, and a `prefers-reduced-motion` mode that removes parallax, transforms and ambient animation while keeping simple opacity transitions.
