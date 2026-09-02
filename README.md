# bioinformatics.be

Website for **The Hitchhiker's Guide to the Genome** — *a mostly harmless
bioinformatics textbook* (Wim Van Criekinge, UGent / BioBix, ed. 2026–2027).

Companion site to the manuscript in `~/The-Hitchhiker-s-Guide-to-the-Genome-2026-`.

## Layout

    site/    the static site itself — drop the download here (see site/PUT-DOWNLOAD-HERE.md)
    notes/   scratch: content drafts, structure plans, decisions

## Status — 2026-09-01

Project restarted as a **static site**, dropping the WordPress/LMS path that
was blocked all summer.

- Waiting on: the current static site, to be downloaded and unpacked into `site/`.
- `git` is initialised here. The first commit after the download lands will be
  the site **untouched**, so later changes read as a clean diff against today's state.

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

1. Hosting target — GitHub Pages vs. Netlify vs. staying on Network Solutions
2. Whether the site stays hand-written HTML or moves to a static generator
   (Hugo/Eleventy/Quarto) once we see the current site's shape
3. Scope — book companion only (chapters, code appendices, figures, errata)
   vs. the broader teaching platform sketched in May
4. Audience + language: EN vs. NL
5. Relationship to UGent Ufora — open access vs. gated

## History

Started 2026-05-27 as a WordPress teaching platform on Network Solutions
hosting. Blocked on the SSL certificate from 2026-05-28 onward and never got
past a README. Restarted 2026-09-01 on the static-site path above.
