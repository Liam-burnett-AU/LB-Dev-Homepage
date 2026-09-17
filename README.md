# LB Dev Homepage

Source for [lbdev.app](https://lbdev.app) — Liam Burnett's personal lab and project showcase.

## Structure

- `index.html` — the whole site (single-page, tab-based routing, no build step).
- `manifest.json` — project list rendered on the `projects` tab. Edit this to add/remove projects; no code changes needed.
- `CNAME` — legacy GitHub Pages custom domain file. Not used by Cloudflare Pages (custom domains are set in the Pages dashboard instead) but harmless to keep.
- `_headers` — Cloudflare Pages security headers, applied automatically on deploy.

## Deploying (Cloudflare Pages)

1. Connect this repo in the Cloudflare dashboard → **Workers & Pages → Create → Pages → Connect to Git**.
2. Build settings: no build command, output directory `/` (it's static HTML).
3. **Custom domains** → add `lbdev.app` (and `www.lbdev.app` if wanted) and point your DNS at Cloudflare per the dashboard's instructions.

## Contact form

The contact form on the `contact` tab posts to the `LB-Dev-Help-Email-Discord-Webhook-API` Cloudflare Worker (see [that repo](https://github.com/Liam-burnett-AU/LB-Dev-Help-Email-Discord-Webhook-API) for setup), which forwards submissions to a Discord forum thread and an email copy. The endpoint is set in `index.html` as `CONTACT_API_URL`.
