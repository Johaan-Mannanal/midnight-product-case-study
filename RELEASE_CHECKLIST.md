# Pre-Release Security & Privacy Review

Complete this before making the repository public. Nothing here has been pushed or made public yet.

## Security & privacy review (current state)
| Area | Status | Notes |
|------|--------|-------|
| Production source code | ✅ None present | Documentation-only repo |
| Secrets / API keys / tokens | ✅ None present | No `.env`, no credentials |
| User data (names, emails, schools, messages) | ✅ None present | No user-level data |
| Database schemas | ✅ Omitted | Generalized in ARCHITECTURE.md |
| Endpoint names / internal routes | ✅ Omitted | — |
| Proprietary prompts / routing logic | ✅ Omitted | Named only as "AI routing layer" |
| Contributor personal emails/names | ✅ Not published | Referred to by count/function only |
| Live URL (www.midapp.me) | ✅ OK to include | Already public (product's own README) |
| Screenshots | ⚠️ None yet | Add only after sanitization (see assets/product-screenshots) |
| Metrics | ⚠️ Labeled, mostly unverified | the beta/Midnight kept separate; `[TO DO]` where unconfirmed |
| License | ⛔ Not set | Awaiting your choice (see below) |

## Final list to review before you make it public
- [ ] Confirm every `[TO DO]` is either filled with verified info or intentionally left blank.
- [ ] Confirm the ~400 figure is labeled precisely (registered vs MAU/WAU/DAU).
- [ ] Confirm the ~70% AI cost reduction claim (scope, baseline, method) or keep it marked unverified.
- [ ] Confirm the beta numbers (alpha users, 10M+ views, ~25 contributors) and their definitions.
- [ ] Confirm your title and category ownership in CASE_STUDY.md §7.
- [ ] Add real portfolio + LinkedIn URLs (README, CASE_STUDY).
- [ ] Add any screenshots — sanitized per the checklist — or leave the folder empty.
- [ ] Choose a LICENSE (see options below) and add it.
- [ ] Re-read every doc once for tone: no co-founder conflict, no overstated claims, no fake stats.
- [ ] Optional: run a secret scan (`gitleaks detect`) as a final backstop.

## License decision (pending your choice)
This is documentation, not open-source software — do **not** apply a code license (MIT, etc.).
Pick one:
- **All rights reserved** (default for proprietary product docs)
- **Creative Commons** (e.g., CC BY-NC-ND 4.0) — lets people read/share with attribution, no commercial use, no derivatives
- **No license until reviewed**

Once you choose, a `LICENSE` file will be added accordingly.
