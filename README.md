# Midnight: Product Case Study

[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-lightgrey)](LICENSE)
![Type: documentation](https://img.shields.io/badge/type-documentation--only-blue)

Midnight is a personalized AI tutor grounded in a student's actual course material. It connects
course context, explanations, generated visual lessons, targeted practice, and comprehension
checks. This case study covers my product and engineering work on the rebuild from an earlier,
broader education platform. Production source code remains private.

> This is a **documentation-only case study**. It contains no production source code, no user
> data, and no secrets. See [PRIVACY.md](PRIVACY.md).

> This is my personal, role-focused case study. Midnight is a team effort; the responsibilities
> below describe my contribution, not sole ownership of the product.

## One-sentence description
Midnight is a personalized AI tutor that turns a student's actual course material into
grounded explanations, practice, and generated visual lessons, supported by tools for
grading, quizzes, flashcards, and task management.

## Current status
Live at **[www.midapp.me](https://www.midapp.me)** and in active development. The current
platform is a refined rebuild of Midnight's earlier beta, applying lessons from that MVP;
it is currently in user testing, so usage counts are not published yet (see
[METRICS.md](METRICS.md)).

## My role
**Co-founder and Product/Engineering Lead.** Led the rebuild, coordinated 25 contributors across
the project's development, and worked with a co-founder on product planning, user research,
development priorities, testing, and launch strategy. Category-by-category ownership is in
[CASE_STUDY.md → My responsibilities](CASE_STUDY.md#7-my-responsibilities).

## Main problem
Students need help with the specific concept they are stuck on, in the context of their own
course. Midnight is designed around that learning loop: course material, grounded explanation,
a visual lesson or targeted practice, then a check of understanding. Grading, flashcards, and
LMS integration support that loop rather than define the product.

## Key contributions
- Led the rebuild and relaunch from the earlier beta to the current Midnight platform,
  applying lessons to product design, UX, team structure, and technical infrastructure.
- Owned the product cycle end to end: planning, user research, prioritization, testing, and marketing.
- Built the course-grounded tutor workspace, generated visual lessons, comprehension checks,
  and quiz/flashcard practice, with grading and Canvas LMS ingestion as supporting tools.
- Worked on the multi-provider AI routing layer serving model requests across providers.

## Results

**Current rebuild:**
- Working tutoring product at **www.midapp.me**, in focused user testing.
- Historical code-contribution figures are documented with their July 2026 snapshot and
  private-source limitations in [METRICS.md](METRICS.md), not presented as current usage.

**Reported (founder-reported, not independently verified):**
- Earlier beta (MVP): 1,500 registrations, 10M+ social-media views, 25 contributors.
- Beta-era and current numbers are kept **separate and precisely labeled** in
  [METRICS.md](METRICS.md), never combined.

## Technology overview
TypeScript monorepo (Turborepo + Yarn) on **Next.js / React**, **WorkOS** auth, **PostgreSQL
(Supabase)**, **Redis (Upstash)**, **Redux Toolkit + React Query**, **Tailwind CSS + Radix UI**,
**Trigger.dev** background jobs, **PostHog + Sentry**, tested with **Playwright + Vitest**, and
deployed on **Vercel** via **GitHub Actions**. AI: **multi-provider LLM integration** via the Vercel AI
SDK: OpenAI, Groq, Cerebras, and Fireworks AI, serving Llama, GPT-OSS, and GLM model families. A React Native
(Expo) mobile app is part of the product. Full (sanitized) detail in [ARCHITECTURE.md](ARCHITECTURE.md).

## Links
- **Live product:** [www.midapp.me](https://www.midapp.me)
- **Full case study:** [CASE_STUDY.md](CASE_STUDY.md)
- **Architecture:** [ARCHITECTURE.md](ARCHITECTURE.md) · **Metrics:** [METRICS.md](METRICS.md) · **Privacy:** [PRIVACY.md](PRIVACY.md)

---
*The production source code is private. Specific implementation details have been omitted
because the production system is proprietary.*
