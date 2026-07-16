# Midnight — Full Case Study

> Documentation-only. No production source code, user data, or secrets. Reported metrics are
> labeled and, where unverified, marked `[TO DO]`. Historical **the beta** figures and current
> **Midnight** figures are kept separate — see [METRICS.md](METRICS.md).

## 1. Executive summary
Midnight is an AI-powered student success platform ([www.midapp.me](https://www.midapp.me)) that
helps students turn scattered academic inputs into finished work through AI-assisted grading,
quiz generation, flashcards, tutoring, and Canvas LMS integration. It is a rebuild and relaunch of
an earlier product, **the beta**. Working in close coordination with a co-founder, I led product
planning, user research, development priorities, testing, and marketing strategy, and served as the
lead engineer and top code contributor (**1,684 of 3,607 commits, ~47%** — verified from the
private repository). This case study documents the product problem, the the beta→Midnight transition,
my responsibilities, the technical approach, and honest results and limitations — without exposing
proprietary code.

## 2. The student problem
Students manage assignments, study materials, deadlines, and feedback across many disconnected
tools. The work is fragmented: notes in one place, the LMS in another, study aids in a third.
The result is friction, dead ends, and time lost to tool-management instead of learning.
Midnight targets that gap with a single, student-first workspace where AI helps *create* and
*organize* academic work, and where long-running tasks keep progressing in the background.

## 3. The original the beta product
the beta was the earlier version of this idea — an AI-assisted academic product for students. It
validated demand and generated meaningful early traction: **approximately 1,000 live beta users**
and **more than 10 million social-media views**, built with a team of **~25 contributors** (all
founder-reported; see [METRICS.md](METRICS.md)). *[TO DO: confirm the beta's exact feature scope and
launch window.]*

## 4. Problems discovered during the alpha
The alpha surfaced the usual early-product issues: unclear product focus, features that didn't
map to how students actually work, and operational cost pressure from AI usage.
*[TO DO: confirm the specific top 2–3 problems the alpha revealed — e.g., retention, cost per
request, onboarding friction — with any supporting evidence.]*

## 5. Decision to rebuild and rebrand
The original team and product structure changed, creating an opportunity to rebuild the platform
with a clearer product direction and a cleaner technical foundation. The rebuild became
**Midnight**: a focused, student-first workspace rather than a collection of loosely related
features.

## 6. Midnight product direction
Midnight is organized around a small set of AI-assisted tools that map to real student tasks:
- **AI Grader** — assignment feedback and rubric evaluation.
- **AI Quiz Generator** — quizzes from a topic, with practice/exam modes and resume.
- **AI Flashcards** — deck generation with spaced repetition (FSRS).
- **AI Tutor** — a tutoring workspace with interactive artifacts and generated study aids.
- **Tasks** — assignment tracking with Canvas LMS sync.

Design principle (from the product's own guidelines): *student work comes first; quiet confidence
over spectacle; real controls over decoration.* Long AI jobs run in the background so students can
navigate away while work completes.

## 7. My responsibilities
Ownership by category. **Engineering** is verified from git history (top contributor, ~47% of
commits). The rest are marked for your confirmation so nothing is overstated.

| Category | Ownership | Basis |
|----------|-----------|-------|
| Engineering (frontend + backend) | **Led** | Verified: 1,684/3,607 commits (~47%), largest share |
| Product planning / strategy | **Led** (with co-founder) | Self-reported |
| User research | **Led** | Self-reported |
| Product requirements / development priorities | **Led** | Self-reported |
| Testing | **Led** | Self-reported (repo also has Playwright/Vitest suites) |
| Marketing strategy | **Led** | Self-reported |
| Contributor coordination | **Led / Co-led** | Coordinated ~25 contributors (the beta stage), with co-founder |
| AI infrastructure (multi-provider routing, background jobs) | **Contributed / Co-led** | Stack verified in repo; confirm exact split |
| Analytics | **Contributed** *[TO DO: confirm]* | PostHog present in stack |
| Launch planning | **Co-led** (with co-founder) | Self-reported |

> Work was done in **close coordination with a co-founder**. This case study does not claim I
> personally built every part of the platform: Midnight is a team effort (~13+ contributors in the
> current repo; ~25 during the the beta stage). My largest independently verifiable contribution is
> engineering (top contributor, ~47% of commits); the product/research/testing/marketing leadership
> above is self-reported.

## 8. User research and feedback
Midnight's direction is explicitly student-first, and features map to observed student workflows
(turning class inputs into finished work, keeping background tasks moving, reducing tool-switching).
*[TO DO: confirm how feedback was gathered (interviews, alpha usage, surveys, Discord/community)
and 1–2 concrete changes that resulted from it.]*

## 9. Product-development process
- Monorepo with shared packages and a single primary web application.
- CI-style quality gates (linting, type-checking, formatting, tests) enforced in the repo.
- Background-job architecture so AI creation tools don't block the UI.
*[TO DO: confirm your process specifics — sprint cadence, review process, how contributors were
onboarded.]*

## 10. Technical challenges
- **Long-running AI tasks:** grading, quiz/flashcard generation, and tutoring artifacts can take
  time; the platform runs them as background jobs with progress tracking and completion
  notifications instead of blocking the user.
- **Multiple model providers:** the platform integrates several AI providers behind one interface
  (a routing layer), which adds complexity but enables flexibility.
- **Breadth of tools in one workspace:** grader, quizzes, flashcards, tutor, and tasks share a
  consistent UI system and state model.
*[TO DO: confirm the single hardest technical problem you personally solved, so it can be
highlighted here.]*

## 11. AI infrastructure
The platform serves AI features through a **multi-provider routing layer** (Vercel AI SDK over
OpenAI, Groq, Cerebras, and Fireworks AI), with **Upstash Redis** for rate limiting/caching and
**Trigger.dev** running long AI tasks as background jobs. This architecture supports flexibility
across model providers and keeps latency and cost manageable. No specific cost-reduction
percentage is claimed here; if quantified later, it should be verified first (scope, baseline,
method) — see [METRICS.md](METRICS.md).

## 12. Team and collaboration
Midnight is built by a team (~13+ contributors in the current repository; ~25 during the the beta
stage). I was the top code contributor and worked in **close coordination with a co-founder** on
product and leadership, while coordinating other engineers and contributors. *[TO DO: confirm how
you want the co-founder and teammates represented — described by function rather than by name
unless they consent to being named.]*

## 13. Launch and growth
Midnight is live in production at [www.midapp.me](https://www.midapp.me), with a staging
environment used to validate configuration and deploys before release. Current usage is
approximately **400 [TO DO: confirm active-user definition]** users. Growth specifics (period,
channel, trend) are `[TO DO]` — see [METRICS.md](METRICS.md).

## 14. Metrics
All metrics — precisely labeled, separated by product era, and marked verified/unverified — live
in [METRICS.md](METRICS.md). the beta and Midnight numbers are **never combined**.

## 15. Mistakes and lessons learned
- Product focus matters more than feature count; the rebuild narrowed scope to real student tasks.
- Operational cost is a first-class design constraint for AI products, not an afterthought.
- A clean technical foundation and enforced quality gates make a multi-contributor project
  sustainable.
*[TO DO: add 1–2 personal, specific lessons in your own voice — these read as the most authentic
part of a case study.]*

## 16. Current limitations
- Some reported metrics (the beta cost reduction, current active-user counts) are not yet
  independently verified here.
- This case study intentionally omits proprietary implementation details, schemas, prompts, and
  security specifics.
- *[TO DO: add honest current product limitations you're comfortable sharing.]*

## 17. Next steps
*[TO DO: confirm roadmap items you're comfortable sharing publicly — e.g., new tools, mobile,
reliability, growth goals. Keep them non-sensitive.]*

## 18. Links and media
- Live product: [www.midapp.me](https://www.midapp.me)
- Architecture: [ARCHITECTURE.md](ARCHITECTURE.md) · Metrics: [METRICS.md](METRICS.md) · Privacy: [PRIVACY.md](PRIVACY.md)
- Screenshots: see [assets/product-screenshots/](assets/product-screenshots/) *(to be added after privacy review)*
- Portfolio: *[TO DO]* · LinkedIn: *[TO DO]*
