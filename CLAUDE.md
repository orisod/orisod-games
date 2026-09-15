# Orisod Games — Project Context for Claude Code

## What this repo is

This is **games.orisod.com** — a free, browser-based arcade of small games,
published as a separate product line from the main Orisod toolkit
(orisod.com). It lives in its own repo (`orisod/orisod-games`) rather than
inside `orisod-site` **by design**: GitHub Pages only supports one custom
domain per repo (via the `CNAME` file), so a real subdomain with its own
domain needs its own repo. Don't try to fold this back into `orisod-site`.

For all shared conventions not repeated below (folder-based routing, GA4
setup, editorial rules, accessibility standards, git/PR workflow, etc.), see
the main site's CLAUDE.md: https://github.com/orisod/orisod-site/blob/main/CLAUDE.md
This file only documents what's specific to, or different about, this repo.

## Permanent rules

**Always run `git pull` at the start of every session before making
changes.**

**Never commit or push directly to `main`.** Same discipline as
`orisod-site`: feature branch → commit → push → open a PR → wait for CI to
pass → merge only after the user explicitly approves the merge. This applies
regardless of how the request is phrased.

**No game is linked from orisod.com until official launch.** This is a
standing rule, not a one-time note — until the site owner says otherwise,
nothing on orisod.com (nav, footer, blog, tool pages) should link to
games.orisod.com, and nothing here should be treated as publicly announced.

## Functional rules (same as orisod-site)

- 100% client-side. No backend calls, no data leaves the browser.
- Plain HTML/CSS/JS, no build step, no framework, self-contained per page
  (CSS and JS inline in the same HTML file).
- English at the domain root (`games.orisod.com/`), Spanish under `/es/`
  (`games.orisod.com/es/`) — same hub-and-spoke i18n pattern as orisod-site.
  Every EN page needs a Spanish counterpart with full functional parity, not
  just literal translation.
- Sentence case in titles/headings/meta descriptions. Zero em dashes
  anywhere in visible content.
- WCAG 2.2 AA baseline: real form labels, sequential heading levels, visible
  focus states, sufficient contrast.
- Same GA4 measurement ID as orisod.com (`G-V2GMNDCVMK`) — no new analytics
  scripts without an explicit decision to add them.

## Visual identity (different from orisod-site — this is deliberate)

This subdomain has its **own** visual identity, not orisod.com's toolkit
design. Dark, futuristic arcade-console aesthetic: cyan/blue/indigo neon glow
accents, Plus Jakarta Sans for headings/labels, Inter for body text, both
self-hosted as subsetted variable `.woff2` fonts under `assets/fonts/`
(same self-hosting approach as Andika in orisod-site, for the same reason:
no new CDN runtime dependency).

**Dark mode only.** Do not add a light/dark theme toggle or light-mode CSS
variables here — that's a orisod.com toolkit feature and does not extend to
this subdomain.

Non-negotiable brand anchors on every page regardless of how the visual
design evolves:
- Orisod logo/wordmark, clearly visible.
- `#2563eb` present somewhere as a recognizable accent color.
- A visible link back to `https://orisod.com`.

## Site structure as of now

- `/` (EN lobby) — the games catalog/lobby page.
- `/es/` (ES lobby) — Spanish counterpart.
- Game pages themselves don't exist yet; the lobby currently links nowhere
  (cards show a "coming soon" state).

## Ad policy

This subdomain has its own ad policy, separate from orisod.com's. No ads are
implemented yet — don't add any ad network/script without an explicit
decision recorded here first.
