# gocrewit-site

Credibility page for **gocrewit.com** — one hand-written page, no build step.
Spec: `Dispatcher_Pro/docs/specs/gocrewit-site-brief.md`.

Not a marketing site. One job: prove a real operator ships real software that
real customers pay for. No SEO, no funnel, no framework, no toolchain.

## Structure

```
index.html        one-scroll page: hero → who → work (3 job cards) → proof → hire → how → contact
privacy.html      legal — COPY MUST BE PORTED from Squarespace (/privacy-policy)
terms.html        legal — COPY MUST BE PORTED from Squarespace (/terms-of-service)
404.html          points back home
assets/style.css  hand-written; "ops board" design, system fonts (no web-font fetch)
CNAME             gocrewit.com
.nojekyll         serve files as-is on GitHub Pages
```

## Design

"Ops board / work-order ticket." Manila board (`#e9e5db`) + graphite ink, one
accent (signal green `#1c7c4a`) reserved strictly for status pills. System sans
for body, system mono for statuses/dates/IDs. Deliberately NOT Fire Inspect
Hub's navy/ember.

## Open items before go-live (Michael)

**`<VERIFY>` — content, must be true before publish:**
- [ ] §3.2 — 21K Home Care description + dates read right publicly
- [ ] §3.4 card 2 — Housing Inspect Hub status (defaulted to **IN BUILD** — do
      not upgrade to live/beta/customers unless true)
- [ ] §3.3 card 3 — can the California client be named, or stay anonymous?

**Build follow-ups:**
- [ ] Capterra: embed the official rating badge/widget (slot in `index.html`,
      §3.4) — do not hand-roll a quote or reproduce the full review body
- [ ] Port real Privacy + Terms copy from Squarespace into the two doc pages

## Deploy (last step — see brief §5–6)

GitHub Pages off `main`. **DNS cutover changes A + CNAME records ONLY** —
`MX` and `SPF` must stay untouched (`michael@gocrewit.com` carries Fire Inspect
Hub's transactional email *and* the Microsoft Ads verification path). Record the
four current apex A records first (rollback), pull GitHub Pages' current apex IPs
from GitHub's docs, then cut over. Verify mail both directions before cancelling
Squarespace.
