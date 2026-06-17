# Web Projects

Static / Jamstack sites delivered behind a hardened, self-hosted edge.

## Live properties
- A network & security **consulting site** and multiple **resume builds** (Astro and hand-built
  static HTML).
- A reverse-proxy **edge with a WAF and automatic TLS** (Let's Encrypt) in front of every property,
  with security headers and per-host routing.
- **Push-to-deploy** via GitHub Actions — build → rsync → live, no container rebuilds.

## Where the stack is (2024–2026)
**Astro** became the fastest-growing framework for content sites — **Astro 5 (2024)** shipped the
Content Layer API and Server Islands (static-fast pages with islands of dynamic content), and in
**January 2026 Cloudflare acquired Astro** (framework still MIT/open-source), tightening the
static-site-to-edge story. That islands + edge model is exactly how I build: ship mostly static,
serve it from a hardened edge, keep interactivity surgical, and treat the delivery edge (WAF, TLS,
headers) as part of the project rather than an afterthought.

Designed, built, and operated end to end — from the page to the edge that serves it.
