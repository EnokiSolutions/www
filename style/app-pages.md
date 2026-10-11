# App sub-page style (`src/pages/<app>/`)

Each app has its own folder: `src/pages/<app>/index.astro` → `/<app>/`. Images go in `public/images/<app>/`. All pages use `src/layouts/Base.astro`, which holds the shared head, topbar, footer, fonts, and all CSS (global).

## App landing page (`/<app>/`)

Left-aligned, full detail, inside one `<section class="product">`:

1. `.product-intro` — kicker (e.g. "Android app"), `h2` app name, `.product-lede`.
2. `.features` — list of `h3` and `p` pairs, each with the orange left border.
3. `.screens` — screenshots, `width="900" height="506"`, `loading="lazy"`, descriptive `alt` text.
4. `.cta` — status line and buttons (`.button-primary` for the main action, `.button-secondary` for the alternative). Beta and sign-up links go **here only, never in the topbar**.
5. Footer links such as "Privacy policy" (`.nav-link .product-link`).

An app with nothing released yet (e.g. Isaludo) uses a single centred `.upcoming` section instead.

## Legal pages (`/<app>/privacy/`)

- File: `src/pages/<app>/privacy.astro` (builds to `/<app>/privacy/`, which is a stable URL for store listings).
- Use `<article class="legal">`: kicker (app name), `h1` "Privacy Policy", `h2` per section, `p` body. Left-aligned, max width 680px.
- Topbar `nav` slot: a link back to the app page.
- Keep the policy text as the owner supplied it; only fix obvious typos, and say what you changed.

## Shared rules

- The topbar nav slot (`<a slot="nav" class="nav-link">`) is for navigation only, never for calls to action.
- Kickers, colours, and type follow the brand section in `CLAUDE.md`; don't add page-local `<style>` blocks. Add new classes to `Base.astro`.
- Set a `title` ("<App> — Enoki Solutions") and a one-sentence `description` on `<Base>`.
- When adding an app: create its folder, add a teaser to the home page (see `style/home.md`), and link its title to the new page.
