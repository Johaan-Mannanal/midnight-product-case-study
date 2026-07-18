# Midnight: Full Case Study

> Documentation-only. No production source code, user data, or secrets. Product-analytics figures
> are founder-reported and aggregated. Historical **the beta** figures and current **Midnight**
> figures are kept separate, see [METRICS.md](METRICS.md).

## 1. Executive summary
Midnight is an AI-powered student success platform ([www.midapp.me](https://www.midapp.me)) that
helps students turn scattered academic inputs into finished work through AI-assisted grading,
quiz generation, flashcards, tutoring, and Canvas LMS integration. It is a rebuild and relaunch of
an earlier product, **the beta**. Working in close coordination with a co-founder, I led product
planning, user research, development priorities, testing, and marketing strategy, and served as the
lead engineer and top code contributor (**1,684 of 3,607 commits, ~47%**, verified from the
private repository). This case study documents the product problem, the the beta→Midnight transition,
my responsibilities, the technical approach, and honest results and limitations, without exposing
proprietary code.

## 2. The student problem
Students manage assignments, study materials, deadlines, and feedback across many disconnected
tools. The work is fragmented: notes in one place, the LMS in another, study aids in a third.
The result is friction, dead ends, and time lost to tool-management instead of learning.
Midnight targets that gap with a single, student-first workspace where AI helps *create* and
*organize* academic work, and where long-running tasks keep progressing in the background.

## 3. The original the beta product
the beta was the earlier version of this idea, an AI-assisted academic product for students. It
validated demand and generated meaningful early traction: **approximately 1,000 live beta users**
and **more than 10 million social-media views**, built with a team of **~25 contributors** (all
founder-reported; see [METRICS.md](METRICS.md)).

## 4. Problems discovered during the beta
The the beta beta surfaced common early-product issues: unclear product focus, features that didn't
map cleanly to how students actually work, and operational cost pressure from AI usage. These
lessons directly shaped the decision to rebuild with a tighter product direction.

## 5. Decision to rebuild and rebrand
The original team and product structure changed, creating an opportunity to rebuild the platform
with a clearer product direction and a cleaner technical foundation. The rebuild became
**Midnight**: a focused, student-first workspace rather than a collection of loosely related
features.

## 6. Midnight product direction
Midnight is organized around a small set of AI-assisted tools that map to real student tasks:
- **AI Grader**: assignment feedback and rubric evaluation.
- **AI Quiz Generator**: quizzes from a topic, with practice/exam modes and resume.
- **AI Flashcards**: deck generation with spaced repetition (FSRS).
- **AI Tutor**: a tutoring workspace with interactive artifacts and generated study aids.
- **Tasks**: assignment tracking with Canvas LMS sync.

Design principle (from the product's own guidelines): *student work comes first; quiet confidence
over spectacle; real controls over decoration.* Long AI jobs run in the background so students can
navigate away while work completes.

## 7. My responsibilities
Ownership by category. **Engineering** is verified from git history (top contributor, ~47% of
commits); the product/research/testing/marketing leadership is self-reported.

| Category | Ownership | Basis |
|----------|-----------|-------|
| Engineering (frontend + backend) | **Led** | Verified: 1,684/3,607 commits (~47%), largest share |
| Product planning / strategy | **Led** (with co-founder) | Self-reported |
| User research | **Led** | Self-reported |
| Product requirements / development priorities | **Led** | Self-reported |
| Testing | **Led** | Self-reported (repo also has Playwright/Vitest suites) |
| Marketing strategy | **Led** | Self-reported |
| Contributor coordination | **Led / Co-led** | Coordinated ~25 contributors (the beta stage), with co-founder |
| AI infrastructure (multi-provider routing, background jobs) | **Contributed / Co-led** | Stack verified in repo |
| Analytics | **Contributed** | PostHog present in stack |
| Launch planning | **Co-led** (with co-founder) | Self-reported |

> Work was done in **close coordination with a co-founder**. This case study does not claim I
> personally built every part of the platform: Midnight is a team effort (10+ contributors in the
> current repo; ~25 during the the beta stage). My largest independently verifiable contribution is
> engineering (top contributor, ~47% of commits).

## 8. User research and feedback
Midnight's direction is explicitly student-first, and features map to observed student workflows:
turning class inputs into finished work, keeping background tasks moving, and reducing the need to
switch between tools. Feedback from the the beta stage informed which tools to keep, cut, or rebuild.

## 9. Product-development process
- Monorepo with shared packages and a single primary web application.
- CI-style quality gates (linting, type-checking, formatting, and tests) enforced in the repo.
- Background-job architecture so AI creation tools don't block the UI.

## 10. Technical challenges
- **Long-running AI tasks:** grading, quiz/flashcard generation, and tutoring artifacts can take
  time; the platform runs them as background jobs with progress tracking and completion
  notifications instead of blocking the user.
- **Multiple model providers:** the platform integrates several AI providers behind one interface
  (a routing layer), which adds complexity but enables flexibility across models.
- **Breadth of tools in one workspace:** grader, quizzes, flashcards, tutor, and tasks share a
  consistent UI system and state model.

## 11. AI infrastructure
The platform serves AI features through a **multi-provider routing layer** (Vercel AI SDK over
OpenAI, Groq, Cerebras, and Fireworks AI), with **Upstash Redis** for rate limiting/caching and
**Trigger.dev** running long AI tasks as background jobs. This architecture supports flexibility
across model providers and keeps latency and cost manageable. No specific cost-reduction
percentage is claimed here, see [METRICS.md](METRICS.md).

## 12. Team and collaboration
Midnight is built by a team (10+ contributors in the current repository; ~25 during the the beta
stage). I was the top code contributor and worked in **close coordination with a co-founder** on
product and leadership, while coordinating other engineers and contributors. Individual teammates
are referenced by function rather than by name.

## 13. Launch and growth
Midnight is live in production at [www.midapp.me](https://www.midapp.me), with a staging
environment used to validate configuration and deploys before release. Current usage is
approximately **400 users** (founder-reported; see [METRICS.md](METRICS.md)).

## 14. Metrics
All metrics, labeled, separated by product era, and marked verified/self-reported, live in
[METRICS.md](METRICS.md). the beta and Midnight numbers are **never combined**.

## 15. Mistakes and lessons learned
- Product focus matters more than feature count; the rebuild narrowed scope to real student tasks.
- Operational cost is a first-class design constraint for AI products, not an afterthought.
- A clean technical foundation and enforced quality gates make a multi-contributor project
  sustainable.

## 16. Current limitations
- Some current metrics (e.g., a precise active-user definition) are founder-reported and not
  independently audited in this public case study.
- This case study intentionally omits proprietary implementation details, schemas, prompts, and
  security specifics.

## 17. Next steps
Continued development of the core AI tools and the tutoring workspace, reliability and
performance work, and growth of the current user base. Specific roadmap details are kept internal.

## 18. Links and media
- Live product: [www.midapp.me](https://www.midapp.me)
- Architecture: [ARCHITECTURE.md](ARCHITECTURE.md) · Metrics: [METRICS.md](METRICS.md) · Privacy: [PRIVACY.md](PRIVACY.md)
