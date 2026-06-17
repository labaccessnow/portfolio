# Web Projects

Static / Jamstack sites delivered behind a hardened, self-hosted edge. I treat the edge — WAF,
TLS, headers — as part of the project, not someone else's problem.

## What it looks like in practice

Astro 5's Content Layer API, defining a typed content collection from local files:

```ts
// src/content.config.ts
import { defineCollection, z } from 'astro:content';
import { glob } from 'astro/loaders';      // Astro 5 Content Layer

export const collections = {
  projects: defineCollection({
    loader: glob({ pattern: '**/*.md', base: './src/content/projects' }),
    schema: z.object({ title: z.string(), date: z.date(), tags: z.array(z.string()) }),
  }),
};
```

And the part people skip — the edge actually being secure:

```nginx
add_header Strict-Transport-Security "max-age=63072000" always;
add_header X-Content-Type-Options    "nosniff"          always;
add_header Content-Security-Policy    "default-src 'self'" always;
```

Push-to-deploy on top: a commit triggers a GitHub Action that builds and `rsync`s the output to
the edge — no container rebuild, rollback is just a redeploy.

## Best practices I follow
- **Static-first, islands for interactivity.** Ship HTML; keep JavaScript surgical.
- **The edge is part of the project** — WAF, automatic TLS, HSTS/CSP, rate limiting, built in.
- **Immutable, reviewable deploys.** Every change goes through CI.
- **Own the delivery path** — a self-hosted edge means no mystery layer between the page and the user.

## Lessons learned
- **A bind-mounted single FILE plus `rsync` goes silently stale.** rsync replaces the file via an
  atomic rename — a *new inode* — but the container stays pinned to the old inode. `nginx -t`
  happily validates the stale file and routing quietly goes wrong. Fix: recreate the container so
  it re-binds, or deploy with `rsync --inplace`. Directory mounts are fine; only single-file
  mounts pin the inode. (Cost me a real debugging cycle.)
- **Your own WAF will 403 your own probes.** My home egress IP tripped the per-IP rate limit and
  returned phantom 403s to my `curl` checks while the site was perfectly fine for everyone else.
  Now I verify from off-network.
- **A WAF blocks large uploads and WebDAV until you carve exceptions** — disabling the rule
  per-location for the upload path and raising the body limit is what finally let big files through.

## Where the stack went (dated)
- **Dec 3, 2024:** **Astro 5** ships the Content Layer API and **Server Islands** — Astro becomes
  the fastest-growing framework for content sites.
- **Jan 2026:** **Astro 6** beta (workerd dev server, dev/prod parity) and **Cloudflare acquires
  Astro** (still MIT/open-source), tightening the static-to-edge story.
