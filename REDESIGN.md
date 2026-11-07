# Zk Av Club — Website redesign

A static, no-build redesign of [zkav.club](https://zkav.club/), the home of the **Zero-knowledge Audiovisual Club**.

This version keeps **all website content from the original repository**, with the same URLs and the same page structure, and applies the cinematic black/red/cyan visual system built for the club.

---

## Preview locally

The site is plain HTML, CSS, and JavaScript. No install, no build step.

```bash
# from this folder
python -m http.server 8080
# or
npx serve .
```

Then open <http://localhost:8080/>.

---

## Content parity

Every page in the original repository is represented here with its full Markdown content:

| Section | Pages |
|---|---|
| Home | `index.html` |
| Recording Station | `recording-station/`, `recording-station/licensing/`, `recording-station/volunteer/` |
| Workshops | `workshops/`, `workshops/past/`, `workshops/ES/`, `workshops/PT/` |
| Archive Model | `archive-model/`, `archive-model/archivist/`, `archive-model/archivist/faq/` |
| Publishing Infrastructure | `publishing-infrastructure/`, `publishing-infrastructure/zcash/`, `.../moderation/`, `.../publishing/`, `.../reports/` |
| Opportunities | `opportunities/`, `opportunities/gigs/`, `opportunities/archivist/`, `opportunities/storyteller/` |
| Partner Communities | `partners/zechub.html` |
| Teams | `teams/devconnect-2025/` |
| Translations | `ES/`, `DE/` |

The only new copy is:

- image captions and small navigational labels (section names, “On this page” links, footer navigation);
- the redesigned visual chrome (eyebrows, buttons, captions).

All headings, paragraphs, lists, links, quotes, addresses, and technical documentation come from the original files verbatim.

The **file naming standard** panel now lives only on the Archivist page (`archive-model/archivist/`), as in the original site. It was removed from the home and from the Archive Model landing page.

---

## Design

The visual reference is **Video Editor 04** from [websitedemos.net](https://websitedemos.net/video-editor-04/?customize=template), adapted to the club's own palette:

- pure black canvas, Montserrat typography, cinematic photography;
- brand red `#D7192D` for actions, bright red `#FF4D5E` for hover/small emphasis;
- signal cyan `#36A9C1` for labels and metadata, light cyan `#67D3F1` for code;
- deep teal `#164455` for technical surfaces;
- 1px hairlines instead of cards; 0 radius on buttons/images, 6px on form-like panels;
- 150px section rhythm and a 100px transparent header.

The palette was sampled from the club's public X account (avatar, banner, and event imagery). The full token table and component rules are in [`DESIGN.md`](DESIGN.md).

---

## Images

The site uses the club's public imagery from its X account and the original repository:

- hero stills and Recording Station photos;
- the ZF AV Workshop graphic and ZconV Berlin poster;
- the ZecHub banner;
- a recorded community call, an IPFS desktop screenshot, and a Free2z profile screenshot;
- archive concept art and the ZF AV Club brand banner.

All images have `alt`, explicit dimensions, and lazy loading. Replace them with higher-resolution originals and add photo credits where available.

---

## Accessibility & performance

- Lighthouse (desktop): **100 / 100 / 100** on the home, Recording Station, volunteer kit, workshops, Archivist, Zcash PeerTube, gigs, ES, DE, and teams pages. The ZecHub partner page scores **100 / 100 / 80**; its only SEO note is the original link text “here”.
- Tested at 390, 768, 1024, and 1440px across all 24 pages: no horizontal overflow, no console errors, one `h1` per page, all images have `alt`.
- Keyboard-operable mobile menu, skip link, visible focus rings, reduced-motion support, and AA contrast.

---

## Deploying

The site mirrors the original URL structure, so it can replace the current GitHub Pages site directly:

- `index.html` is served at `/`.
- Every original folder is represented by an `index.html` (`recording-station/index.html`, `workshops/past/index.html`, etc.).
- `CNAME`, `LICENSE`, and the original QR assets are included.

Before a production switch:

1. **Old `.html` links.** The previous proposal used root files such as `recording-station.html`. Those are gone in favor of clean URLs. Add redirects only if any external link used them.
2. **Images.** Swap the public X images for originals/high-resolution files and add credits.
3. **Links that point to `watchz.cash`.** Confirm the PeerTube instance is public before launch.
4. **Translations.** The ES/DE home pages and workshops ES/PT pages are included; review the translated navigation labels if you add a language switcher.
5. **Re-run Lighthouse** on the production domain after deployment.

---

## Suggested next steps

- [ ] Replace placeholder photography with originals and add credits.
- [ ] Add redirects for any legacy `.html` links if needed.
- [ ] Review the ES/DE and ES/PT translations in the new layout.
- [ ] Connect the archive index to the metadata repository.
- [ ] Add an RSS/Atom feed for workshops and reports.
- [ ] Re-run Lighthouse on the production domain.

---

## Credits

Redesign proposal built for Zk Av Club. Content, brand, and public assets belong to the club and its contributors. Visual reference: [Video Editor 04](https://websitedemos.net/video-editor-04/?customize=template) by websitedemos.net.

Built in the open.
