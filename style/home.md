# Home page style (`src/pages/index.astro`)

The home page is a short, centred overview of the company. It links out to app pages; it never carries full product detail.

## Structure (top to bottom)

1. **Topbar** — logo lockup only (no nav link on the home page).
2. **Hero** (`.hero`) — `h1` plus a short `.hero-lede`. No kicker.
3. **Consulting** (`.services`) — kicker, `h2`, `.services-lede`, email link (`.nav-link .services-link`).
4. **One teaser per app** (`.upcoming`) — kicker, linked `h2`, `.upcoming-lede`, and a "learn more" link (`.nav-link .product-link`).
5. **Footer**.

## Rules

- **Everything is centred.** Every section uses `text-align: center`; ledes are centred with `margin: … auto 0` and a `max-width` in `ch`.
- **Dividers are full width.** Each section after the hero has `border-top: 1px solid var(--line)` across the full `.page` width. Don't put `max-width` on a section that has a border — constrain the inner text instead.
- **Section padding:** `56px 0`.
- **Kicker** (`.kicker`) above every section `h2`: bold, uppercase, `0.85rem`, `letter-spacing: 0.12em`, accent orange.
- **App titles link to their page:** `<h2><a class="title-link" href="/<app>/">…</a></h2>`. No underline at rest; orange underline on hover.
- **Teasers stay short:** one or two sentences. Features, screenshots, and calls to action belong on the app page.
- Kicker wording for app teasers: what the thing is, as category + platform (e.g. "Android game", "Max for Live device"). Release status, price and "free" go in the lede, not the kicker. Downloadable files go in `public/downloads/` with a version in the filename (e.g. `… v1.amxd`).
