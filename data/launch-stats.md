# Launch statistics and sources

The numbers the skills rely on, with where they come from. Corrections with a source are welcome as PRs.

## Hacker News

| Claim | Value | Source |
|---|---|---|
| Median Show HN score | 2 points | "Show HN by the Numbers" — 188,085 Show HN posts, 2012–Apr 2026, HN Algolia API. https://danfking.github.io/blog/2026/04/23/show-hn-by-the-numbers/ |
| A 50+ point Show HN is top | 6% | same |
| Best posting time for 50+ points | Monday 00:00 UTC (Sunday 19:00 US Eastern), 10.8% chance | same |
| Stars per HN upvote within 48 h | ≈ 1.4 | same (top 500 Show HN repos cross-referenced with GitHub star history) |
| Share of launch stars in first 48 h | ≈ 92% | same |
| Day-1 stars for a median successful (258+ pt) Show HN | ≈ 509, then ≈ 40 on day 2, ≈ 9/day on days 3–7 | same |
| Average stars from an HN launch | ≈ 121 at 24 h, 189 at 48 h, 289 at 7 days | "Launch-Day Diffusion: Tracking Hacker News Impact on GitHub Stars for AI Tools", 138 launches 2024–2025. https://arxiv.org/html/2511.04453v1 |
| "Show HN" tag effect after controls | not significant (β = −119, p = 0.39) | same |
| Median time to first comment on a Show HN that gets one | ≈ 4.4 hours (consistent Oct 2025 vs Oct 2026) | Show HN traction dataset, 70,894 posts Oct 2024–Oct 2026. https://github.com/m0nk111-qwen-agent/showhn-traction-24mo |
| Front-page Show HN | 500–2,000 stars in 24 h | AFFiNE launch case study (0 → 33k → 60k stars). https://gingiris.github.io/growth-tools/blog/2026/03/25/how-to-get-more-github-stars-the-definitive-guide-33k-stars-case-study/ |
| Secondary posting window | Tue–Thu 08:00–10:00 US Eastern | Multiple practitioner guides, e.g. https://repoclip.io/blog/how-to-get-more-stars-on-github |

## GitHub

| Claim | Value | Source |
|---|---|---|
| Trending ranks by | stars gained in the window (daily/weekly/monthly) relative to baseline, not total stars | GitHub Trending behaviour; practitioner analysis at https://repoclip.io/blog/how-to-get-more-stars-on-github |
| First 100 stars, warm community, typical | 3–5 days | AFFiNE case study (above) |
| Star history endpoint | daily counts available without a token since Sep 2026 | https://github.com/emanuelef/daily-stars-explorer |

## Reference launches (for calibration)

| Repo | Result | Note |
|---|---|---|
| mattpocock/skills | 307k stars | Most-starred agent-skills repo; opinionated, installable |
| anthropics/skills | 185k stars | Official skills repo |
| addyosmani/agent-skills | 102k stars | Production-engineering skills |
| forrestchang/andrej-karpathy-skills | 207k stars | A single CLAUDE.md with four principles |
| WenyuChiou/awesome-agentic-ai-zh | 852 stars in week 1 | A curated list in one language |
| AFFiNE | 5,000 stars in one week | Coordinated Show HN → r/selfhosted → Product Hunt |

Figures as of October–November 2026.
