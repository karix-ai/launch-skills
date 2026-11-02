---
name: launch-audit
description: Score a repo's launch readiness 0–100 and list the blockers, in one pass. Use first — when the user asks "is this ready to launch", "why isn't my repo getting stars", or wants a quick review before posting anywhere.
---

# Launch audit

One pass, one score, one list of blockers. Run this before any launch and again
after fixing. The score is not a vanity number: each line maps to a thing that measurably
changes whether a visitor stars the repo.

## Scoring (100 points)

### README — 40 points (see `readme-that-sells`)

| Check | Points |
|---|---|
| First line states what it is in ≤ 15 words, no marketing adjectives | 8 |
| A demo GIF/video/screenshot within the first screen | 10 |
| One-command install that works from a clean directory (run it) | 10 |
| A "why / vs alternatives" section that names the alternatives | 6 |
| A runnable usage example with real output | 4 |
| No TODOs, placeholders, or `your-username` in the top 60 lines | 2 |

### Repo signals — 30 points (see `repo-hygiene`)

| Check | Points |
|---|---|
| Description set, ≤ 120 chars, matches the pitch | 4 |
| 5–10 topics including ecosystem + category | 4 |
| LICENSE file (MIT/Apache-2.0/BSD) | 6 |
| At least one tagged release | 4 |
| Social preview image set (cannot be checked via API reliably; ask) | 3 |
| CONTRIBUTING.md + ≥ 3 `good first issue` labels | 4 |
| Last commit within 7 days | 3 |
| CI present and green (or no badge at all; a red badge scores 0) | 2 |

### Launch assets — 30 points (see `show-hn-launch`, `reddit-launch`, `demo-gif`)

| Check | Points |
|---|---|
| Show HN title drafted and scored | 6 |
| Show HN first comment drafted, includes the limitation line | 6 |
| Posting slot chosen and converted to local time | 4 |
| Demo MP4 + GIF exist, ≤ 20 s, ≤ 5 MB, readable at 600 px | 6 |
| Reddit posts drafted per subreddit, rules checked | 4 |
| Awesome-list entries prepared (not yet opened) | 2 |
| Launch-day scratch file (links, install, top-3 answers) | 2 |

## Interpreting the score

- **< 50:** do not launch. The one shot at HN will be wasted. Fix README and hygiene first; they are a day of work.
- **50–75:** launch is survivable but will underperform. Fix the 10-point items.
- **> 75:** launch. Remaining points are polish; ship and fix during day 1.

A 90 with no demo is still a no-go: the demo is a hard requirement, not a point item.

## Procedure

1. Fetch the README and repo metadata (`gh repo view --json name,description,repositoryTopics,licenseInfo,latestRelease,pushedAt,primaryLanguage`, or the API).
2. Actually run the install command in a clean temp directory. Record pass/fail and the error if any.
3. Score each line. Be strict: partial credit only where the table allows.
4. List blockers in order of points, each with the skill that fixes it and the estimated time.
5. If the score is < 75, offer to run the fixing skills in order: `readme-that-sells` → `demo-gif` → `repo-hygiene` → `show-hn-launch` → `reddit-launch` → `launch-plan`.

## Output

```
Launch readiness: NN/100

Blockers (highest impact first):
- [10] No demo in README → demo-gif (30 min)
- [10] Install command fails on clean machine: <error> → fix, then readme-that-sells (15 min)
- ...

Ready: <what already passes, one line>
Next: <the single next action>
```
