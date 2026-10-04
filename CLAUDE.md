# sort.land

Apex page for the sort.land domain. Plain HTML/CSS in `site/`, no build, no
JavaScript (the CSP in `site/_headers` has no `script-src`; add one if you add
a script).

- Deploy: Cloudflare Worker `sort-land`, Workers Builds on push to `main`.
  Pushing to `main` publishes.
- The domain also carries mail (forwardemail MX/SPF/TXT). Never touch those
  records; the Worker custom domain only owns the apex A/AAAA.
- `www.sort.land` is a separate, older DNS record (currently a dead origin),
  not handled here.
- Style is shared with gunnaringe.sort.land (`../gunnaringe.github.io`): same
  colour variables and the `gi.woff2` handwriting font. Keep them in step.
- Asset URLs are unversioned, so `_headers` caches `/assets/*` for a day only.
- Preview: `python3 -m http.server -d site 8000`. CI runs html-validate and lychee.
