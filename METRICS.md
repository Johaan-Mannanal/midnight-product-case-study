# Metrics

> **Two different products, kept separate.** the beta (earlier product) and Midnight (current
> platform) numbers are **never combined**. Each figure is labeled with a definition, value,
> source, and whether it is independently verified. Product-analytics figures are founder-reported
> and aggregated, no user-level data appears here.

## Verified in this case study
| Metric | Definition | Value | Period | Source | Independently verified |
|--------|-----------|-------|--------|--------|------------------------|
| Code contribution (mine) | Share of total commits authored by me in the current repo | **1,684 / 3,607 commits (~47%)** | repo start → Jul 2026 | Private git history (`git shortlog`) | ✅ Yes (from git) |
| Contributors (current repo) | Distinct people with commits (26 raw git identities deduplicated, bots excluded) | **10+** | repo start → Jul 2026 | Private git history | ✅ Yes (from git) |

"Founder-reported" and "self-reported" both mean the figure comes from the author (a founder of
the product) rather than from an independently auditable source.

## Historical: the beta (earlier product)
| Metric | Definition | Value | Source | Independently verified |
|--------|-----------|-------|--------|------------------------|
| Registrations | Accounts created on the the beta MVP | **1,500** | Product analytics (founder-reported) | Self-reported |
| Social-media views | Video views across social channels | **10M+** | Platform analytics (founder-reported) | Self-reported |
| Contributors | People who contributed during the the beta stage | **~25** | Founder-reported | Self-reported |

## Current: Midnight

The rebuilt platform is in **active development and user testing**. Usage counts are deliberately
not published at this stage: the product is being refined on lessons from the the beta MVP, and
early-testing numbers would say more about recruiting testers than about the product. Verified
engineering metrics (contribution share, contributor count) are above. the beta and Midnight
figures are never combined.

## AI cost / infrastructure
No specific cost-reduction percentage is claimed in this case study. What can be stated from the
stack is architectural: the platform integrates **multiple AI model providers** (OpenAI, Groq,
Cerebras, Fireworks AI) behind a routing layer via the Vercel AI SDK, and uses **Upstash Redis**
for rate limiting and caching, both common enablers of cost and latency control.
