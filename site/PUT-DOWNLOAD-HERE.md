# Drop the downloaded site here

Unpack the static site export into **this directory**, so that the site's
entry page ends up at `site/index.html` — not nested inside an extra
wrapper folder like `site/bioinformatics.be/index.html`.

Then delete this file and tell me it's in. I'll commit it untouched as the
baseline, so every change we make afterwards shows up as a clean `git diff`
against the site exactly as it is today.

Expected shape after unpacking:

    site/
    ├── index.html
    ├── css/  (or styles/, assets/, wp-content/, …)
    ├── js/
    └── images/

Anything is fine — a wget/HTTrack mirror, a WordPress static export, a
Wix/Squarespace export, or a hand-built folder. Don't tidy it up first;
the messier the original, the more useful the untouched baseline.
