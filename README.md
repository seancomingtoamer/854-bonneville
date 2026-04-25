# 854 Bonneville

A single-page marketing site for **854 Bonneville** — a private room at our
PadSplit co-living home in Atlanta. Every CTA routes visitors to the
PadSplit referral sign-up.

Plain HTML/CSS/JS. No framework, no build step, no dependencies.

## Live

- **Site:** <https://854bonneville.com> (also `www.854bonneville.com`)
- **Repo:** <https://github.com/seancomingtoamer/854-bonneville>
- **Vercel project:** `854-bonneville` (scope: `questfilmandmedia-6960s-projects`)
- **DNS:** GoDaddy → A `@` → `76.76.21.21`, CNAME `www` → `cname.vercel-dns.com`
- **SSL:** Let's Encrypt, auto-renewed by Vercel

## Stack

- `index.html` — markup, styles, minimal JS, all in one file
- `images/room.jpg` — the hero photo (only photo on the page)
- Google Fonts: Fraunces (display serif) + Work Sans (body sans)
- Inline SVG icons, CSS grain overlay
- `IntersectionObserver` for fade-up animations on scroll

## Run locally

```bash
python3 -m http.server 5500
```

Then open <http://localhost:5500>.

## Redeploy

The Vercel project is linked via local CLI. From this directory:

```bash
vercel --yes --prod --scope questfilmandmedia-6960s-projects
```

A `git push` does not auto-deploy yet — that link in the Vercel UI is
still TODO.

## Editing content

Every value that needs real-world content is flagged with an HTML comment:

```html
<!-- TODO: replace with actual rate -->
```

`grep -n "TODO:" index.html` from this directory shows everything still
stubbed. Currently:

- Weekly rate (`$XXX / week`) in the hero stats bar
- Three neighborhood commute times (grocery, downtown, transit)
- Neighborhood / zip in the hero location badge
- Full address details in the footer

The hero photo, gallery, and hosts portrait have all been removed —
this is now a single-photo, type-led editorial layout.

## Referral link

Every CTA opens the PadSplit referral link in a new tab. The URL lives in
`index.html` — search for `referralCode=F250E0F1` to find all five instances.
