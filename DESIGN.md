# ZK AV CLUB — Design System

A redesign proposal for [zkav.club](https://zkav.club/). The layout and visual language follow the **Video Editor 04** template from [websitedemos.net](https://websitedemos.net/video-editor-04/?customize=template): pure black, oversized Montserrat, cinematic photography, and hairline rules.

The interface palette is the club's own, extracted from the [@ZkAv_Club](https://x.com/ZkAv_Club) profile: **neon red, signal cyan, deep teal, black, and white**.

---

## 1. The reference

The reference is a dark portfolio template for a video editor. Its key traits:

| Trait | Observation |
|---|---|
| Canvas | Pure black `#000000`. No grids, gradients, or decorative backgrounds. |
| Type | Montserrat for everything. Headings 700 weight, 52–82px, tight tracking, sentence case. |
| Body | 16px, line-height ~1.65, `rgba(255,255,255,.75)`. |
| Buttons | Solid fill, **0 radius**, 15×30px padding, 16px/700. |
| Images | Full-bleed or large, **0 radius**, cinematic color, no frames or badges. |
| Structure | Thin 1px hairlines instead of cards and shadows. |
| Spacing | Very generous: `150px` section padding on desktop, `100px` header. |
| Header | Transparent over the hero, small white nav, letterspaced wordmark. |
| Forms | Dark fields with 1px borders and **6px radius**. |
| Footer | Black with a 1px top border, small gray text, social icons. |

### How it maps to Zk Av Club

- **Hero:** full-bleed, darkened event photography; huge white headline; red primary button.
- **Sections:** 1px top hairlines, large white headings, gray body, cyan section labels.
- **Cards:** no boxes. A hairline, a title, a short description, and a small arrow.
- **Images:** clean stills with a small caption underneath; no console chrome.
- **Support:** dark teal-tinted panels with 1px borders and 6px radius.
- **Join:** black CTA block with a huge headline, bordered link rows, and a red/cyan glow.
- **Footer:** minimal black footer with gray links and a hairline.

---

## 2. Brand palette

Colors were sampled from the club's public brand assets:

| Role | Hex | Source |
|---|---|---|
| Brand red (core) | `#D7192D` | Between the avatar's `#C81B1B` and the banner neon's `#D70C2A` |
| Red, bright | `#FF4D5E` | Neon highlight / small text on black |
| Red, deep | `#A80F22` | Button hover / shadow |
| Signal cyan | `#36A9C1` | Banner ambient light (`#36A9C1`) |
| Cyan, light | `#67D3F1` | Event graphics / code highlights |
| Deep teal | `#164455` | Night background around the neon sign |
| Ink teal | `#0B2A35` | Code and technical panels |
| Black | `#000000` | Canvas |
| White | `#FCFAFC` | Headings and body highlights |

**Rule of thumb:** red = action and emphasis; cyan = labels and metadata; deep teal = technical surfaces; black/white = everything else. Red is never used as a full-page background.

---

## 3. Design principles

1. **Cinematic, not decorated.** Photography and typography carry the page. No neon UI, no grid overlays, no glows.
2. **Two brand accents, clear jobs.** Red acts; cyan labels. They do not compete.
3. **Hairlines over boxes.** Structure comes from 1px rules and spacing, not cards and shadows.
4. **Big type, quiet body.** 52–82px headings; 16–18px body at comfortable line height.
5. **Full-bleed media.** Images are not framed; captions sit quietly underneath.
6. **Fast and quiet.** No framework, no tracking, no autoplay, no third-party embeds.
7. **Accessible by default.** Keyboard menu, focus rings, reduced-motion support, AA contrast.

---

## 4. Tokens

### Color

| Token | Value | Use |
|---|---|---|
| `--bg` | `#000000` | Page background |
| `--bg-soft` | `#050505` | Panels, wells |
| `--surface` | `#0A0A0A` | Raised dark surfaces |
| `--line` | `rgba(255,255,255,.12)` | Hairlines, panel borders |
| `--line-strong` | `rgba(255,255,255,.26)` | Inputs, ghost buttons |
| `--paper` | `#FCFAFC` | Headings, primary text |
| `--paper-dim` | `rgba(255,255,255,.75)` | Body copy |
| `--muted` | `rgba(255,255,255,.58)` | Secondary copy |
| `--muted-2` | `rgba(255,255,255,.5)` | Metadata |
| `--accent` | `#D7192D` | Buttons, fills, large emphasis |
| `--accent-bright` | `#FF4D5E` | Hover text, small red labels, arrows |
| `--accent-dark` | `#A80F22` | Button hover |
| `--secondary` | `#36A9C1` | Section labels, eyebrows, dates, indices |
| `--secondary-light` | `#67D3F1` | Code, chips, callout highlights |
| `--teal-deep` | `#164455` | Deep brand surfaces |
| `--teal-ink` | `#0B2A35` | Code panels, technical wells |

### Type

| Role | Family | Size / weight |
|---|---|---|
| Display / H1 | Montserrat | `clamp(48px, 6vw, 82px)` · 700 · 1.04 |
| Section H2 | Montserrat | `clamp(36px, 4.8vw, 58px)` · 700 · 1.15 |
| Feature H2 | Montserrat | `clamp(34px, 4.2vw, 54px)` · 700 · 1.15 |
| Card H3 | Montserrat | 21–34px · 700 · 1.25 |
| Body | Montserrat | 16–18px · 400 · 1.65–1.7 |
| Labels | Montserrat | 10–13px · 600 · uppercase · `0.1–0.18em` |
| Code | System mono | 0.86em |

### Space / shape

- Base spacing: **8px**; section rhythm `clamp(80px, 10vw, 150px)`.
- Content width: **1240px**; gutter `clamp(20px, 5vw, 64px)`.
- Header: **100px** desktop, 78px when scrolled, 78px mobile.
- Radius: **0** on buttons, images, and cards; **6px** on panels, form-like fields, and QR wells.
- Shadows: only the soft shadow under the floating hero still.
- Borders: 1px hairlines.

### Motion

- `cubic-bezier(0.22, 1, 0.36, 1)` for reveals and hovers.
- 18px fade-up reveals via IntersectionObserver.
- Slow ticker for the Record / Archive / Teach / Publish / Remix line.
- `prefers-reduced-motion: reduce` disables animation.

---

## 5. Components

| Component | Treatment |
|---|---|
| `.btn` | Red fill `#D7192D`, white 16px/700 label, 0 radius. Hover: deep red `#A80F22`. |
| `.btn--ghost` | Transparent, 1px white border. Hover: white fill, black text. |
| `.site-header` | Transparent over the hero; black blur bar + hairline after scroll. |
| `.hero` | Blurred, darkened brand photo backdrop with a red/cyan wash; white display headline; clean stills. |
| `.hero-media` | Two clean stills, no frames. Caption under the main still; floating still above the caption. |
| `.quick-links` | Two-column hairline index for the home Start here list; cyan numbers, white labels, arrows. |
| `.join-list` | Hairline list with cyan arrows and underlined links. |
| `.quote` | Hairline top, 64px red quote mark, gray quote, white author. |
| `.reading-item` | Date / title+summary / arrow, separated by hairlines. |
| `.partner-card` | 1px border + 6px radius, red letter mark, white title. |
| `.donate-card` | Teal-tinted panel + 6px radius, white QR well, dark address field, red copy button. |
| `.page-hero` | Blurred dark brand banner, cyan eyebrow, 82px title with one red word. Long titles use `.page-hero--long`. |
| `.page-aside` | Sticky hairline rail with small gray links, scrollable on long pages. |
| `.prose` | Main body typography for every ported Markdown page: headings, lists, quotes, code, images, tables. |
| `.media-frame--screen` | Teal-bordered panel for screenshots, with `object-fit: contain` and a caption bar. |
| `.file-format` | Ink-teal technical panel with cyan code. |
| `.prose .callout` | Dark panel with a cyan left rule. |

---

## 6. Layout patterns

- **Home:** hero → Start here → Recording Station → Workshops → Archive Model → Opportunities → Join the Club → Testimonials → Partner Communities → Additional Reading → Support → Thanks → Built in the open.
- **Inner pages:** cinematic page hero → prose (72ch) + sticky rail → footer.
- **Breakpoints:** 1080px (tighten nav), 900px (mobile menu, single-column features, hide rail), 640px (single-column grids, reduced display sizes).
- **Grids:** 2-col quick links/quotes, 3-col donation cards, 4-col footer, single-column prose.

---

## 7. Accessibility & performance

- Semantic landmarks, one `h1` per page, `h1 → h2 → h3` order.
- Skip link, keyboard-operable mobile menu, `aria-expanded`, Escape to close.
- Copy buttons announce through a `role="status"` toast.
- Visible 2px red-bright focus rings with 4px offset.
- AA contrast on black; audited with Lighthouse.
- Reduced-motion support; no autoplay; no tracking.
- One font family (Montserrat) plus a system monospace for code.
- Lighthouse (desktop, local): **100 / 100 / 100** on the home, Recording Station, volunteer kit, workshops, Archivist, Zcash PeerTube, gigs, ES, DE, and teams pages. The ZecHub partner page scores **100 / 100 / 80**; its only SEO note is the original link text “here”.

---

## 8. Content architecture

| Page | Source |
|---|---|
| `index.html` | Root `README.md` |
| `recording-station/index.html` | `recording-station/README.md` |
| `recording-station/licensing/index.html` | `recording-station/licensing/README.md` |
| `recording-station/volunteer/index.html` | `recording-station/volunteer/README.md` |
| `workshops/index.html` | `workshops/README.md` |
| `workshops/past/index.html` | `workshops/past/README.md` |
| `workshops/ES/index.html` | `workshops/ES/README.md` |
| `workshops/PT/index.html` | `workshops/PT/README.md` |
| `archive-model/index.html` | `archive-model/README.md` |
| `archive-model/archivist/index.html` | `archive-model/archivist/README.md` |
| `archive-model/archivist/faq/index.html` | `archive-model/archivist/faq/README.md` |
| `publishing-infrastructure/index.html` | `publishing-infrastructure/README.md` |
| `publishing-infrastructure/zcash/index.html` | `publishing-infrastructure/zcash/README.md` |
| `.../zcash/moderation/index.html` | `publishing-infrastructure/zcash/moderation.md` |
| `.../zcash/publishing/index.html` | `publishing-infrastructure/zcash/publishing.md` |
| `.../zcash/reports/index.html` | `publishing-infrastructure/zcash/reports.md` |
| `opportunities/index.html` | `opportunities/README.md` |
| `opportunities/gigs/index.html` | `opportunities/gigs/README.md` |
| `opportunities/archivist/index.html` | `opportunities/archivist/README.md` |
| `opportunities/storyteller/index.html` | `opportunities/storyteller/README.md` |
| `partners/zechub.html` | `partners/zechub.md` |
| `teams/devconnect-2025/index.html` | `teams/devconnect-2025.md` |
| `ES/index.html` | `ES/README.md` |
| `DE/index.html` | `DE/README.md` |

All page copy is ported verbatim from the original Markdown. The only additions are image captions, section labels, and navigation chrome. The file naming standard panel lives only on the Archivist page, matching the original site.

---

## 9. Do / Don't

**Do**
- Use black as the default canvas.
- Let images run edge-to-edge with no frames.
- Use red for actions and emphasis; cyan for labels and metadata.
- Use hairlines and space to separate content.
- Keep headings large, white, and sentence case.

**Don't**
- Use red as a full-page background.
- Use red for small body text without the brighter `#FF4D5E` variant.
- Add neon glows, cyberpunk grids, or outline type.
- Add rounded cards, soft shadows, or gradient buttons.
- Add a second display font.
- Frame images with borders, badges, or console chrome.

---

*Built in the open. The system is intentionally small enough for a community to maintain.*
