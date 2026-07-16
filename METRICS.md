# Metrics

> **Two different products, kept separate.** the beta (earlier alpha) and Midnight (current
> platform) numbers are **never combined**. Every figure is labeled with a definition, value,
> period, source, and whether it was independently verified. Values marked `[TO DO]` are reported
> but not yet confirmed — do **not** publish them as fact until confirmed. No user-level data
> appears here.

## Verified in this case study
| Metric | Definition | Value | Period | Source | Independently verified |
|--------|-----------|-------|--------|--------|------------------------|
| Code contribution (mine) | Share of total commits authored by me in the current repo | **1,684 / 3,607 commits (~47%)** | repo start → Jul 2026 | Private git history (`git shortlog`) | ✅ Yes (from git) |
| Contributors (current repo) | Distinct commit authors in the current repo | **~13+** | repo start → Jul 2026 | Private git history | ✅ Yes (from git) |

## Historical — the beta (earlier product)
| Metric | Definition | Value | Period | Source | Independently verified | Notes |
|--------|-----------|-------|--------|--------|------------------------|-------|
| Live beta users | Users on the the beta beta | **~1,000** | [TO DO: date range] | Product analytics (founder-reported) | Self-reported | Precise label; not combined with Midnight |
| Social-media views | Video views across social channels | **10M+** | [TO DO: date range] | Platform analytics (founder-reported) | Self-reported | "Views" (not "reach"/"impressions") — confirm platform(s) |
| Contributors | People who contributed during the the beta stage | **~25** | [TO DO: date range] | Founder-reported | Self-reported | Mix of code and non-code contributors |

## Current — Midnight
| Metric | Definition | Value | Period | Source | Verified | Notes |
|--------|-----------|-------|--------|--------|----------|-------|
| Active users | Unique users completing ≥1 meaningful action in [TO DO: 7/30 days?] | ~400 *(reported)* | [TO DO] | [TO DO: product analytics] | ❌ Not verified | Pick MAU/WAU/DAU explicitly |
| Registered users | Accounts created (all-time) | [TO DO] | [TO DO] | [TO DO] | ❌ | |
| Monthly active users (MAU) | Unique users with ≥1 meaningful action in 30 days | [TO DO] | [TO DO] | Product analytics | ❌ | |
| Weekly active users (WAU) | Unique users with ≥1 meaningful action in 7 days | [TO DO] | [TO DO] | Product analytics | ❌ | |
| Daily active users (DAU) | Unique users with ≥1 meaningful action in 1 day | [TO DO] | [TO DO] | Product analytics | ❌ | |
| Retention | e.g., % of new users active in week 4 | [TO DO] | [TO DO] | Product analytics | ❌ | |
| Usage frequency | e.g., median sessions/active user/week | [TO DO] | [TO DO] | Product analytics | ❌ | |
| Growth period | Window the ~400 figure covers | [TO DO] | [TO DO] | — | ❌ | |

> ⚠️ The "~400" figure must be labeled (e.g., "~400 registered users" **or** "~400 monthly active
> users") — these mean very different things. Do not present it ambiguously.

## AI cost / infrastructure (not currently claimed as a headline metric)
No specific cost-reduction percentage is claimed in this case study. What can be stated safely
from the stack is architectural: the platform integrates **multiple AI model providers**
(OpenAI, Groq, Cerebras, Fireworks AI) behind a routing layer via the Vercel AI SDK, and uses
**Upstash Redis** for rate limiting/caching — both common enablers of cost and latency control.

> If you later want to publish a specific figure (e.g., an earlier "~70% reduction"), verify it
> first: define scope (AI API vs infrastructure vs total), baseline vs comparison period, whether
> usage/quality changed, and the specific method — then present a before/after. Until then, keep it
> qualitative and unquantified. `[TO DO: verify before quantifying]`
