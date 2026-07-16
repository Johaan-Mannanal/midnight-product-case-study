# Metrics

> **Two different products, kept separate.** the beta (earlier product) and Midnight (current
> platform) numbers are **never combined**. Each figure is labeled with a definition, value,
> source, and whether it is independently verified. Product-analytics figures are founder-reported
> and aggregated, no user-level data appears here.

## Verified in this case study
| Metric | Definition | Value | Period | Source | Independently verified |
|--------|-----------|-------|--------|--------|------------------------|
| Code contribution (mine) | Share of total commits authored by me in the current repo | **1,684 / 3,607 commits (~47%)** | repo start → Jul 2026 | Private git history (`git shortlog`) | ✅ Yes (from git) |
| Contributors (current repo) | Distinct commit authors in the current repo | **~13+** | repo start → Jul 2026 | Private git history | ✅ Yes (from git) |

## Historical: the beta (earlier product)
| Metric | Definition | Value | Source | Independently verified |
|--------|-----------|-------|--------|------------------------|
| Live beta users | Users on the the beta beta | **~1,000** | Product analytics (founder-reported) | Self-reported |
| Social-media views | Video views across social channels | **10M+** | Platform analytics (founder-reported) | Self-reported |
| Contributors | People who contributed during the the beta stage | **~25** | Founder-reported | Self-reported |

## Current: Midnight
| Metric | Definition | Value | Source | Independently verified |
|--------|-----------|-------|--------|------------------------|
| Current users | Users of the current Midnight platform | **~400** | Product analytics (founder-reported) | Self-reported |

> The "~400" refers to current users of the Midnight platform. A precise active-user definition
> (registered vs. monthly/weekly/daily active) and detailed retention/growth breakdowns are not
> published here. the beta and Midnight figures are never combined.

## AI cost / infrastructure
No specific cost-reduction percentage is claimed in this case study. What can be stated from the
stack is architectural: the platform integrates **multiple AI model providers** (OpenAI, Groq,
Cerebras, Fireworks AI) behind a routing layer via the Vercel AI SDK, and uses **Upstash Redis**
for rate limiting and caching, both common enablers of cost and latency control.
