# theboombangisdead.com — static site on GitHub Pages

Hand-coded single-page site for **The Boom Bang**, hosted free on GitHub Pages on the
custom domain `theboombangisdead.com`. Migrated off the GoDaddy Websites + Marketing builder.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole site — HTML, CSS, JS inline. Self-contained. |
| `CNAME` | Binds the Pages deploy to the custom domain. One line: `theboombangisdead.com` |
| `robots.txt` | Allows crawling, points to the sitemap. |
| `sitemap.xml` | Single homepage URL for Search Console. |
| `README.md` | This file. |
| `photos/` | 38 optimized WebP gallery images (Doug Schwarz live shots). |

## Canonical values

| Field | Value |
|---|---|
| Custom domain | `theboombangisdead.com` |
| GitHub username | `charlesbwhetstone` |
| Pages URL | `charlesbwhetstone.github.io` |
| Repo name | `theboombangisdead` |
| Contact email | `theboombang@gmail.com` (Gmail — no domain mailbox to migrate) |
| DNS host | GoDaddy |

## DNS records (set at GoDaddy)

Delete any old forwarding / parked / Website-Builder records FIRST, then:

**Four A records on `@` → GitHub Pages:**
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME on `www` →** `charlesbwhetstone.github.io`

## Deploy steps

1. `gh auth status` (run `gh auth login` once if not logged in).
2. Paste the Phase 1 deploy prompt into Claude Code — it creates the repo, pushes,
   enables Pages, and curls the `*.github.io` URL to confirm it's live.
3. At GoDaddy: delete old records, add the 4 A records + `www` CNAME above.
4. Repo → Settings → Pages → set custom domain to `theboombangisdead.com`, deploy from `main` / root.
5. Tick **Enforce HTTPS** once the certificate provisions (may lag a bit after DNS).
6. Google Search Console: submit `sitemap.xml`, request indexing on the homepage.
7. Only after the domain serves the new site: cancel the GoDaddy **Websites + Marketing**
   subscription. **Keep the domain registration.**

## Notes

- This was multi-page on GoDaddy (`/listen`, `/get-in-touch`, `/tour-&-faq`, `/merch`).
  It's now a single page with in-page anchors (`#listen`, `#tour`, `#contact`). The old
  paths will 404 after migration; Google drops them on its own. Nothing to redirect.
- Contact is a `mailto:` link (static site = no form backend). To take real form
  submissions later, wire the form to a free Formspree endpoint.
- Hero background is the existing Vimeo reel (video id `554427806`), muted + looping.
- Photo gallery: 38 Doug Schwarz live shots in `/photos` (WebP, max 1600px), with a click-to-enlarge lightbox.
- Video section ("Caught On Tape"): 7 YouTube embeds (Final Show 3/22/2013 + 6 clips), via youtube-nocookie.com.
- Standalone site repo. Not tied to any other project — no other project's conventions apply.
