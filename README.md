# sort.land

The page at <https://sort.land/>: the name and a link to
[gunnaringe.sort.land](https://gunnaringe.sort.land/).

Plain HTML and CSS in `site/`. No build, no JavaScript, nothing from third
parties. The handwriting font and colours match gunnaringe.sort.land.

## Local preview

```sh
python3 -m http.server -d site 8000
```

## Deploy

Cloudflare Worker `sort-land` (static assets only), configured in
`wrangler.jsonc`. Set up once in Workers & Pages: "Import a repository", pick
this repository, name the project `sort-land` (must match `name` in
`wrangler.jsonc`), keep the default deploy command `npx wrangler deploy`.
After that every push to `main` deploys. The deploy attaches `sort.land` as a
custom domain, creating its DNS record and certificate; the mail records (MX,
SPF) are not touched.

## Checks

`.github/workflows/check.yml` validates the HTML and checks links on pull
requests and pushes to `main`.
