# Web Projects

Static / Jamstack sites delivered behind a hardened, self-hosted edge.

## Live properties
- A network & security **consulting site** and multiple **resume builds**
  (Astro and hand-built static HTML).
- A reverse-proxy **edge with a WAF and automatic TLS** (Let's Encrypt) in front of
  every property, with security headers and per-host routing.
- **Push-to-deploy** via GitHub Actions — build → rsync → live, no container rebuilds.

Designed, built, and operated end to end: from the page to the edge that serves it.
