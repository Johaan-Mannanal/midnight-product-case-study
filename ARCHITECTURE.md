# Architecture (Sanitized)

> This is a **generalized** overview. Specific implementation details have been omitted because
> the production system is proprietary. No endpoint names, schemas, security rules, credentials,
> or prompts are included. See [PRIVACY.md](PRIVACY.md).

## High-level system

```
                 ┌─────────────────────────────────────────────────────────┐
   Student  ───▶ │  Frontend (Next.js 15 / React 19 web app)               │
                 │  UI system: Radix UI + Tailwind CSS, TanStack Query     │
                 └───────────────┬─────────────────────────────────────────┘
                                 │
                                 ▼
                 ┌─────────────────────────────────────────────────────────┐
                 │  Application backend (server routes / API layer)        │
                 └───────┬───────────────┬───────────────┬─────────────────┘
                         │               │               │
             ┌───────────▼──┐   ┌────────▼────────┐  ┌───▼──────────────────┐
             │ Auth          │   │ Database        │  │ AI routing layer     │
             │ (Supabase)    │   │ (Supabase/       │  │ (Vercel AI SDK →     │
             │               │   │  Postgres)      │  │  multiple providers) │
             └───────────────┘   └─────────────────┘  └───┬──────────────────┘
                                                          │
                                          ┌───────────────▼───────────────┐
                                          │ External model APIs           │
                                          │ (multiple LLM providers)      │
                                          └───────────────────────────────┘
                 ┌─────────────────────────────────────────────────────────┐
                 │ Background jobs (long-running AI tasks) + notifications  │
                 │ Monitoring / error tracking (Sentry)                    │
                 └─────────────────────────────────────────────────────────┘
```

A rendered version is in [assets/architecture-diagram.png](assets/architecture-diagram.png).

## Components (generalized)
- **Frontend** — Next.js 15 / React 19 single web application; component library built on Radix
  UI primitives with Tailwind CSS; server state via TanStack Query.
- **Application backend** — server-side routes handling requests, orchestration, and access to
  data and model providers.
- **Authentication** — managed auth (Supabase).
- **Database** — Supabase / Postgres. *Schema intentionally omitted.*
- **AI routing layer** — a single interface over **multiple model providers** via the Vercel AI
  SDK, so requests can be served by different providers. *Routing logic and prompts omitted.*
- **Background jobs** — long-running AI work (grading, generation, tutoring artifacts, generated
  media) runs asynchronously so the UI stays responsive; progress is tracked and completion
  triggers notifications.
- **Monitoring** — error tracking / observability (Sentry).
- **Delivery** — monorepo (Turborepo + Yarn workspaces), deployed on Vercel, with staging used to
  validate configuration and deploys before production.

## Verified technology stack
Confirmed by inspecting the private repository's manifests (library names are not sensitive):

| Layer | Technology |
|-------|-----------|
| Language / tooling | TypeScript, Turborepo, Yarn workspaces, Prettier, ESLint, Vitest, Husky |
| Frontend | Next.js 15, React 19, Radix UI, Tailwind CSS, TanStack Query |
| Auth & data | Supabase (auth + Postgres) |
| AI | Vercel AI SDK with multiple model providers |
| Background / async | Background job processing for long AI tasks *[TO DO: confirm which items to name publicly]* |
| Monitoring | Sentry |
| Hosting | Vercel |

> Interactive/rich tutor features (e.g., graphing, simulations, generated media, knowledge-graph
> visualization) exist in the product; the specific libraries and implementation are omitted here
> to keep the case study non-sensitive. *[TO DO: confirm which, if any, you want named publicly.]*

## Deliberately omitted (for security and IP)
- Endpoint names, internal routes, and API contracts
- Database schemas and data models
- Authentication/authorization rules and security configuration
- Proprietary prompts and model-routing logic
- Environment variables, keys, project identifiers, and staging/production specifics
