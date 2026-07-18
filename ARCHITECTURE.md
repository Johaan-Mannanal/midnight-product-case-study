# Architecture (Sanitized)

> This is a **generalized** overview. Specific implementation details have been omitted because
> the production system is proprietary. No endpoint names, schemas, security rules, credentials,
> or prompts are included. See [PRIVACY.md](PRIVACY.md).

## High-level system

```
Student
  -> Frontend (Next.js / React, Radix UI + Tailwind)
      -> Application backend (server routes / API layer)
          -> Authentication (WorkOS)
          -> Database (PostgreSQL / Supabase)
          -> Cache and rate limiting (Redis / Upstash)
          -> AI routing layer (Vercel AI SDK)
              -> External model APIs (OpenAI, Groq, Cerebras, Fireworks AI)

Cross-cutting: background jobs (Trigger.dev) with progress notifications,
monitoring (Sentry), product analytics (PostHog).
Delivery: Turborepo monorepo, GitHub Actions, Vercel, staging then production.
```

The rendered diagram is in [assets/architecture-diagram.png](assets/architecture-diagram.png).

## Components (generalized)
- **Frontend**: Next.js 15 / React 19 single web application; component library built on Radix
  UI primitives with Tailwind CSS; server state via TanStack Query.
- **Application backend**: server-side routes handling requests, orchestration, and access to
  data and model providers.
- **Authentication**: managed auth via **WorkOS (AuthKit)**.
- **Database**: PostgreSQL (Supabase). *Schema intentionally omitted.*
- **Caching / rate limiting**: Redis (Upstash).
- **AI routing layer**: a single interface over **multiple model providers** (OpenAI, Groq,
  Cerebras, Fireworks AI) via the Vercel AI SDK, so requests can be served by different providers.
  *Routing logic and prompts omitted.*
- **Background jobs**: long-running AI work (grading, generation, tutoring artifacts, generated
  media) runs asynchronously via **Trigger.dev** so the UI stays responsive; progress is tracked
  and completion triggers notifications.
- **Monitoring & analytics**: error tracking (Sentry) and product analytics (PostHog).
- **Delivery**: monorepo (Turborepo + Yarn workspaces), deployed on Vercel, with staging used to
  validate configuration and deploys before production.

## Verified technology stack
Confirmed by inspecting the private repository's manifests (library names are not sensitive):

| Layer | Technology |
|-------|-----------|
| Language / tooling | TypeScript, Node.js, Turborepo, Yarn workspaces, Prettier, ESLint, Husky |
| Frontend | Next.js, React, Tailwind CSS, Radix UI |
| State / data-fetching | Redux Toolkit, React Query (TanStack Query) |
| Auth | WorkOS (AuthKit) |
| Database | PostgreSQL (Supabase) |
| Caching / rate limiting | Redis (Upstash) |
| AI | Multi-provider LLM integration via the Vercel AI SDK: OpenAI, Groq, Cerebras, Fireworks AI (Llama, GPT-OSS, and GLM model families) |
| Background jobs | Trigger.dev (long-running AI tasks) |
| Email | Resend / React Email |
| Analytics & monitoring | PostHog, Sentry |
| Testing | Playwright (E2E), Vitest (unit) |
| CI/CD & hosting | GitHub Actions, Vercel |
| Mobile | React Native (Expo) *(founder-reported; separate from the web repo inspected here)* |

> Interactive/rich tutor features (e.g., graphing, simulations, generated media, knowledge-graph
> visualization) exist in the product; specific libraries and implementation are omitted here to
> keep the case study non-sensitive.

## Deliberately omitted (for security and IP)
- Endpoint names, internal routes, and API contracts
- Database schemas and data models
- Authentication/authorization rules and security configuration
- Proprietary prompts and model-routing logic
- Environment variables, keys, project identifiers, and staging/production specifics
