# Tech Stack

> draft v0.1
> The frameworks, services, and languages that should be used (ideally)

## Frontend

- Deployed via Cloudflare Pages: It's free and is on the edge + no need to worry about a domain.
- Astro for the framework: it generates static HTML at build time (Fast + No need to worry about the 10ms CPU time limit on Cloudflare Pages).
- JavaScript or Typescript
- Rust compiled to WASM (for extra performance)

## Backend

- Deployed via Cloudflare Workers: Same reason as above, the only issue is the CPU time budget.
- Hono as the framework: ideal for Cloudflare Workers since it's fast and lightweight, meant for the edge.
- Rust(for extra performance)

## Storage

- D1 (SQLite): puzzle library, user scores, solve history
- KV Store: session state, algorithm result cache (fast reads)
- R2 (Object Storage): exported graph images, shareable graph snapshots

### Language Learning Targets

- Rust: implement graph algorithms, compiles to WASM
- TypeScript: Hono Worker API, Astro frontend glue
- SQL: D1 schema design, puzzle queries

## Cloudflare Services Used

- Pages: unlimited static deploys, hosts the Astro frontend
- Workers: 100k requests/day, API routes for algo runs, graph CRUD, puzzle validation
- D1: 5 GB, 5M rows, puzzle library + score tracking
- KV: 100k reads/day, 1k writes/day, session tokens, cached results
- R2: 10 GB storage, 1M ops/month, exported graph PNGs, shareable links
