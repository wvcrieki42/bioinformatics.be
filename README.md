# bioinformatics.be

Website for **The Hitchhiker's Guide to the Genome** — *a mostly harmless
bioinformatics textbook* (Wim Van Criekinge, UGent / BioBix, ed. 2026–2027).

Companion site to the manuscript in `~/The-Hitchhiker-s-Guide-to-the-Genome-2026-`.

## Layout

    site/    the public static site (the print edition)
    source/  the book artefacts the site is built from (PDF, cover art)
    notes/   scratch: content drafts, structure plans, decisions

## Two editions

The book exists in two forms, and the site must eventually serve both:

| Edition | Contents | Audience | Status |
|---|---|---|---|
| **Print** — v2.42, 713 pp | Ten chapters + **Appendix A only** | Public | Live in `site/` |
| **Online** | All chapters + **appendices A–D** | UGent students only | Not yet produced |

Appendices B (Python for Bioinformatics), C (Visualization) and D
(Collaborative Writing) were cut from the print edition to control page
count. They are **not gone** — they return in the student edition. The
public site must not advertise them; the student edition must.

**Unresolved:** how the student edition gets gated. Static hosting has no
native auth. See "Open decisions" below.

## Status — 2026-09-01

Project restarted as a **static site**, dropping the WordPress/LMS path that
was blocked all summer. The site has been rebuilt for edition v2.42:

- All 713 page scans re-rendered from the print PDF at 150 DPI
- Chapter quick-jump targets recomputed (they drift up to +144 pages)
- Version, academic year and page counts updated across all 15 pages
- Appendix B/C/D references removed (see "Two editions" above)

Serve locally with `python3 -m http.server 8765` from `site/`.

### The domain does not currently serve

Checked 2026-09-01:

- `https://bioinformatics.be` — TLS handshake fails, no certificate presented
- `http://bioinformatics.be` — returns 404

The SSL certificate ordered from Network Solutions in May 2026 never
materialised. **This is the open blocker for going live**, and it is a DNS +
hosting question, not a content question — so it doesn't block building the
site, only publishing it at this domain.

## Deployment (proposed, not yet decided)

Host the static site on GitHub Pages or Netlify — both give free, automatic
HTTPS — then repoint `bioinformatics.be` DNS there when we're ready. That
sidesteps the Network Solutions certificate entirely and removes the
WordPress/LMS decision from the critical path.

## Open decisions

1. **How the student edition is gated.** Static hosts have no native auth.
   Options: serve it from Ufora (students already authenticate there, costs
   nothing, but it leaves the site); Netlify password protection (paid tier);
   or an unlisted URL (convenience, not security — treat it as public).
2. Hosting target — GitHub Pages vs. Netlify vs. staying on Network Solutions
3. Whether the site stays hand-written HTML or moves to a static generator
   (Hugo/Eleventy/Quarto)
4. Scope — book companion only vs. the broader teaching platform sketched in May
5. Audience + language: EN vs. NL

## History

Started 2026-05-27 as a WordPress teaching platform on Network Solutions
hosting. Blocked on the SSL certificate from 2026-05-28 onward and never got
past a README. Restarted 2026-09-01 on the static-site path above.
