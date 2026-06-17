# Web Projects

Static / Jamstack sites delivered behind a hardened, self-hosted edge.

## Live properties
- A network & security **consulting site** and multiple **resume builds** (Astro and hand-built
  static HTML).
- A reverse-proxy **edge with a WAF and automatic TLS** (Let's Encrypt) in front of every property,
  with security headers and per-host routing.
- **Push-to-deploy** via GitHub Actions — build → rsync → live, no container rebuilds.

## Best practices I follow
- **Static-first, islands for interactivity** — ship HTML, keep JavaScript surgical.
- **The edge is part of the project** — WAF, TLS, HSTS/security headers, and rate limiting are
  built in, not bolted on.
- **Immutable, reviewable deploys** — every change goes through CI; rollback is a redeploy.
- **Own the delivery path** — self-hosted edge so there's no mystery layer between page and user.

## Where the stack went (dated)
- **Dec 3, 2024:** **Astro 5** ships the Content Layer API and **Server Islands** (static-fast pages
  with islands of dynamic content) — Astro becomes the fastest-growing framework for content sites.
- **Jan 2026:** **Astro 6** beta (workerd dev server, dev/prod parity) and **Cloudflare acquires
  Astro** (framework stays MIT/open-source), tightening the static-site-to-edge story.

That islands + edge model is exactly how I build. Designed, built, and operated end to end —
from the page to the edge that serves it.
