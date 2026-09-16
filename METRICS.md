# Metrics

> **Two eras, kept separate.** Figures from the earlier beta and from the current
> platform are **never combined**. Each figure is labeled with a definition, value,
> source, and whether it is independently verified. Product-analytics figures are founder-reported
> and aggregated, no user-level data appears here.

## Historical engineering snapshot: July 2026

The author checked these figures against private git history in July 2026. They are not
current totals or independently reproducible from this documentation-only public repository.
| Metric | Definition | Value | Period | Source | Independently verified |
|--------|-----------|-------|--------|--------|------------------------|
| Code contribution (mine) | Share of total commits authored by me in the rebuilt repo | **1,684 / 3,607 commits (~47%)** | repo start → Jul 2026 | Author's check of private git history (`git shortlog`) | No public independent verification |
| Contributors (rebuilt repo) | Distinct people with commits (26 raw git identities deduplicated, bots excluded) | **10+** | repo start → Jul 2026 | Author's check of private git history | No public independent verification |

"Founder-reported" and "self-reported" both mean the figure comes from the author (a founder of
the product) rather than from an independently auditable source.

## Historical: the earlier beta
| Metric | Definition | Value | Source | Independently verified |
|--------|-----------|-------|--------|------------------------|
| Registrations | Accounts created on the beta MVP | **1,500** | Product analytics (founder-reported) | Self-reported |
| Social-media views | Video views across social channels | **10M+** | Platform analytics (founder-reported) | Self-reported |
| Contributors | People who contributed during the beta stage | **25** | Founder-reported | Self-reported |

## Current: Midnight

The rebuilt platform is in **active development and user testing**. Usage counts are deliberately
not published at this stage: the product is being refined on lessons from the beta MVP, and
early-testing numbers would say more about recruiting testers than about the product. Historical
engineering metrics (contribution share, contributor count) are above. Beta-era and current
figures are never combined.

## AI cost / infrastructure
No specific cost-reduction percentage is claimed in this case study. What can be stated from the
stack is architectural: the platform integrates **multiple AI model providers** (OpenAI, Groq,
Cerebras, Fireworks AI) behind a routing layer via the Vercel AI SDK, and uses **Upstash Redis**
for rate limiting and caching, both common enablers of cost and latency control.
