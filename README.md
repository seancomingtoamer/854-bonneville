# 854 Bonneville

A single-page marketing site for **854 Bonneville** — a private room opening up
at our PadSplit co-living home in Atlanta. Every CTA routes visitors to the
PadSplit referral sign-up.

Plain HTML/CSS/JS. No framework, no build step, no dependencies.

## Stack
- `index.html` — the whole site (markup + styles + minimal JS)
- Google Fonts: Fraunces (display serif) + Work Sans (body sans)
- Inline SVG icons, CSS grain overlay
- `IntersectionObserver` for fade-up animations

## Run locally
From this directory:

```bash
python3 -m http.server 5500
```

Then open <http://localhost:5500>.

Any other static server works too — e.g. `npx serve .` or
`php -S localhost:5500`.

## Deploy to Vercel
Because this is a static site with no framework, the simplest path is:

1. Push this repo to GitHub (e.g. `gh repo create 854-bonneville --public --source=. --push`)
2. At <https://vercel.com/new>, import the repo
3. Framework preset: **Other** — leave build command empty, output directory `.`
4. Click **Deploy**

Or from the CLI (no GitHub required):

```bash
npm i -g vercel   # once
vercel            # preview deploy
vercel --prod     # promote to production
```

## Swapping in real photos
Every placeholder is marked with an HTML comment like:

```html
<!-- TODO: replace with actual photo — <img src="..." alt="..."> -->
```

Search the file for `TODO:` to find every spot that needs real content —
photos, weekly rate, commute times, address details.

## Content TODOs currently flagged
- Weekly rate (`$XXX / week`)
- Neighborhood commute minutes (grocery, downtown, transit)
- Full address details (footer + hero location badge)
- Hero photo, 4 gallery photos, hosts portrait

## Referral link
Every CTA opens the PadSplit referral link in a new tab. The URL lives in
`index.html` — search for `referralCode=F250E0F1` to find all instances if
you ever need to update it.
