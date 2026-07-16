# Midnight — Product Case Study

Midnight is an education-technology platform focused on helping students use AI-assisted
academic tools more effectively. This repository documents the product-development process,
selected technical decisions, and lessons from rebuilding an earlier alpha product — while
keeping the production source code private.

> This is a **documentation-only case study**. It contains no production source code, no user
> data, and no secrets. See [PRIVACY.md](PRIVACY.md).

## One-sentence description
Midnight is an AI-powered student success platform that helps students turn scattered class
inputs (assignments, notes, topics) into finished work through tools for grading, quizzes,
flashcards, tutoring, and task management.

## Current status
Live in production at **[www.midapp.me](https://www.midapp.me)**. Actively developed; evolved
from an earlier alpha product called **the beta**. Approximately **400 [TO DO: confirm active-user
definition — see METRICS.md]** current users.

## My role
Lead engineer and the top code contributor on the rebuild. Verified from the private repository:
**1,684 of 3,607 commits (~47%)** — the single largest share among ~13+ contributors. Detailed,
category-by-category ownership (product, AI infrastructure, analytics, etc.) is in
[CASE_STUDY.md → My responsibilities](CASE_STUDY.md#7-my-responsibilities).
*[TO DO: confirm your preferred title — e.g., "Founding Engineer", "Co-founder & Lead Engineer".]*

## Main problem
Students juggle assignments, study materials, and deadlines across many disconnected tools.
Midnight aims to reduce that friction with a single, student-first workspace where AI helps
create and organize academic work while background jobs keep long tasks moving.

## Key contributions
- Led the engineering rebuild from the the beta alpha to the current Midnight platform.
- Built AI-assisted academic tools (grading, quiz generation, flashcards, tutoring workspace).
- Worked on the multi-provider AI routing layer that the platform uses to serve model requests.
- *[TO DO: confirm involvement in AI cost optimization, analytics, and launch — see CASE_STUDY.md.]*

## Verified results
- Top contributor: **1,684 / 3,607 commits (~47%)** (source: private git history).
- Production platform live at www.midapp.me with a multi-tool AI workspace.
- Historical the beta alpha and current Midnight metrics are listed **separately and precisely** in
  [METRICS.md](METRICS.md) — reported numbers (e.g., "4,000 alpha users", "70% AI cost
  reduction") are labeled and marked for verification; they are **not** combined.

## Technology overview
TypeScript monorepo (Turborepo + Yarn workspaces) on **Next.js 15 / React 19**, **Supabase**
(auth + database), the **Vercel AI SDK** with multiple model providers, **Radix UI + Tailwind
CSS**, background job processing, and **Sentry** monitoring, deployed on **Vercel**. Full
(sanitized) detail in [ARCHITECTURE.md](ARCHITECTURE.md).

## Links
- **Live product:** [www.midapp.me](https://www.midapp.me)
- **Full case study:** [CASE_STUDY.md](CASE_STUDY.md)
- **Architecture:** [ARCHITECTURE.md](ARCHITECTURE.md) · **Metrics:** [METRICS.md](METRICS.md) · **Privacy:** [PRIVACY.md](PRIVACY.md)
- **Portfolio:** *[TO DO: add URL]*
- **LinkedIn:** *[TO DO: add URL]*

---
*The production source code is private. Specific implementation details have been omitted
because the production system is proprietary.*
