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
- Paper-and-ink style (system light/dark), the original look of
  gunnaringe.sort.land, which has since gone hacker-only. The `gi.woff2`
  handwriting font is for names only; names stay on one line (`cqi` sizing in
  `.name`). The portrait (`assets/portrait.svg`, copied from
  `../gunnaringe.github.io`) stays dark line art as drawn.
- Asset URLs are unversioned, so `_headers` caches `/assets/*` for a day only.
- Preview: `python3 -m http.server -d site 8000`. CI runs html-validate and lychee.
