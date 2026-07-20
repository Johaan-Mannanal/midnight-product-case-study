# Midnight: Product Case Study

Midnight is an education-technology platform focused on helping students use AI-assisted
academic tools more effectively. This repository documents the product-development process,
selected technical decisions, and lessons from rebuilding the platform's earlier beta, while
keeping the production source code private.

> This is a **documentation-only case study**. It contains no production source code, no user
> data, and no secrets. See [PRIVACY.md](PRIVACY.md).

## One-sentence description
Midnight is an AI-powered student success platform that helps students turn scattered class
inputs (assignments, notes, topics) into finished work through tools for grading, quizzes,
flashcards, tutoring, and task management.

## Current status
Live at **[www.midapp.me](https://www.midapp.me)** and in active development. The current
platform is a refined rebuild of Midnight's earlier beta, applying lessons from that MVP;
it is currently in user testing, so usage counts are not published yet (see
[METRICS.md](METRICS.md)).

## My role
Led product planning, user research, development priorities, testing, and marketing strategy, in
close coordination with a co-founder, and served as lead engineer and the top code contributor.
Verified from the private repository: **1,684 of 3,607 commits (~47%)**, the single largest share
among 10+ contributors. Category-by-category ownership is in
[CASE_STUDY.md → My responsibilities](CASE_STUDY.md#7-my-responsibilities).

## Main problem
Students juggle assignments, study materials, and deadlines across many disconnected tools.
Midnight aims to reduce that friction with a single, student-first workspace where AI helps
create and organize academic work while background jobs keep long tasks moving.

## Key contributions
- Led the rebuild and relaunch from the earlier beta to the current Midnight platform,
  applying lessons to product design, UX, team structure, and technical infrastructure.
- Owned the product cycle end to end: planning, user research, prioritization, testing, and marketing.
- As lead engineer, built across the codebase (AI-assisted grading, quiz/flashcard generation with
  spaced repetition, tutor workspace, Canvas LMS integration), top contributor at ~47% of commits.
- Worked on the multi-provider AI routing layer serving model requests across providers.

## Results

**Verified (from the private git history):**
- **Top contributor: 1,684 / 3,607 commits (~47%)**, the largest share among 10+ contributors.
- Production platform live at **www.midapp.me** with a multi-tool AI workspace.

**Reported (founder-reported, not independently verified):**
- Earlier beta (MVP): 1,500 registrations, 10M+ social-media views, ~25 contributors.
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
