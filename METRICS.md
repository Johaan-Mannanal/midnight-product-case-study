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

## Historical — the beta (earlier alpha)
| Metric | Definition | Value | Period | Source | Verified | Notes |
|--------|-----------|-------|--------|--------|----------|-------|
| Alpha users | *[TO DO: define — sign-ups? registered? active?]* | ~4,000 *(reported)* | [TO DO] | [TO DO: analytics / founder recollection] | ❌ Not verified | Label precisely before publishing |
| Social-media views | *[TO DO: define — video views? impressions? which platform(s)?]* | 10M+ *(reported)* | [TO DO] | [TO DO: platform analytics] | ❌ Not verified | "Views" ≠ "reach" ≠ "impressions" — pick one |
| Contributors | People who contributed to the beta | ~25 *(reported)* | [TO DO] | [TO DO] | ❌ Not verified | Distinguish code vs non-code contributors |
| AI cost reduction | See AI cost section below | ~70% *(reported)* | [TO DO] | [TO DO] | ❌ Not verified | Scope of "cost" must be defined |

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

## AI cost optimization
The reported **~70% AI cost reduction** cannot be published as fact until verified. Confirm each
item below, then fill the table.

**Verification checklist**
- [ ] Scope: is "cost" **AI/model API cost**, **infrastructure**, or **total operational cost**?
- [ ] Baseline period (before) and comparison period (after)
- [ ] Cost per request before vs after (or total cost normalized by usage)
- [ ] Did usage volume/patterns change between periods? (a drop in usage is not an optimization)
- [ ] Did output quality change? (cheaper but worse is not a clean win)
- [ ] What caused the reduction? (do not state a method until confirmed — e.g., model routing,
      caching, prompt compression, response-length limits, batching, provider change, architecture)

**Before / after (fill after verification)**
| | Baseline (before) | After | Change |
|--|-------------------|-------|--------|
| Period | [TO DO] | [TO DO] | — |
| Cost basis (per request / per user / total) | [TO DO] | [TO DO] | [TO DO] |
| Normalized cost | [TO DO] | [TO DO] | ~70% ↓ *(reported, unverified)* |
| Method(s) | — | [TO DO: only if verified] | — |
| Quality impact | — | [TO DO] | — |

*Observed from the stack (not proof of the number): the platform integrates multiple AI providers
behind a routing layer, which is a common enabler of cost control. This does not by itself confirm
the 70% figure or its cause.*
