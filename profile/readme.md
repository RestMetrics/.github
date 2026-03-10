# RestMetrics

A sleep disturbance tracker — log nightly wake-ups, visualize patterns over time.

![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers-F38020?logo=cloudflare&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js_15-000000?logo=next.js&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?logo=supabase&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)

## Repositories

| Repo                                          | Description                                                      |
|-----------------------------------------------|------------------------------------------------------------------|
| [RestMetrics.API](../../../RestMetrics.API)   | Hono REST API on Cloudflare Workers, backed by Supabase          |
| [RestMetrics.Web](../../../RestMetrics.Web)   | Next.js 15 frontend deployed to Cloudflare Workers via OpenNext  |

## Quick Start

```bash
# Clone the monorepo
git clone <repo-url>
cd RestMetrics

# Install all dependencies
npm install

# Set up environment files (see each workspace README)
cp RestMetrics.API/.dev.vars.example RestMetrics.API/.dev.vars
cp RestMetrics.Web/.env.example RestMetrics.Web/.env.local

# Run both API and web in dev mode
npm run dev
```

API runs at `http://localhost:8787` — Swagger UI at `http://localhost:8787/docs` (requires `DEV=true` in `.dev.vars`).
Web runs at `http://localhost:3000`.

## Stack

- **API**: [Hono](https://hono.dev) + [`@hono/zod-openapi`](https://github.com/honojs/middleware/tree/main/packages/zod-openapi) — typed routes with auto-generated OpenAPI spec
- **Auth**: [Supabase Auth](https://supabase.com/docs/guides/auth) — HTTP-only cookie sessions
- **Web**: [Next.js 15](https://nextjs.org) App Router + React 19
- **Charts**: [Chart.js](https://www.chartjs.org) — bar and dispersion visualizations
- **Deployment**: [Cloudflare Workers](https://workers.cloudflare.com) for both API and web
