# enoki/www

Marketing/company site for Enoki Solutions Inc., built with [Astro](https://astro.build) and published via GitHub Pages.

## Architecture

- `src/` — Astro source (pages, components, layouts). Edit here.
- `public/` — static assets copied as-is into the build output (includes `CNAME` for the custom domain `www.enoki.ca`).
- `docs/` — **build output only**. GitHub Pages is configured to serve from `main` / `/docs`. Never hand-edit files in `docs/` — they are overwritten by `npm run build`. It is committed to git (not gitignored) so Pages can serve it directly with no CI/build step on GitHub's side.

## Commands

- `npm run dev` — local dev server with hot reload
- `npm run build` — builds the site into `docs/`
- `npm run preview` — serve the built `docs/` output locally

## Workflow

Before committing any content/site changes, run `npm run build` so `docs/` is in sync with `src/`, and commit both together. A PR that changes `src/` without a matching `docs/` rebuild will not actually update the live site.

## Brand

The real Enoki Solutions identity (logo mark, wordmark, Karla typeface files, brand exploration deck) lives in the sibling repo `../design` (`~/play/enoki/design` on this machine) — not in this repo. Assets actually used on the site are copied into `public/brand/` (logo mark PNGs) and `public/fonts/karla/` (self-hosted Karla, OFL-licensed).

- Typeface: Karla only (regular/bold/italic), no second display face — matches the brand brief's request for one simple sans.
- Colors: black (`#1a1a1a`) on white, with Pantone Orange 021 (`#fe5000`) as the sole accent (from the original business card spec in `../design`).
- Tone: clean, minimalist, light — avoid heavy illustration or invented color palettes not sourced from `../design`.

## Deployment

GitHub Pages serves directly from the `docs/` folder on `main` — no GitHub Actions workflow needed. Custom domain is `www.enoki.ca`, configured via `public/CNAME` (copied into `docs/CNAME` on build) and DNS records at the domain registrar.
