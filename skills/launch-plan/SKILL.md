---
name: launch-plan
description: Build a day-by-day launch plan for an open-source repo that concentrates stars into one window to hit GitHub Trending. Use when the user wants to launch, asks how to get stars, asks which channels to post to, or asks for a schedule.
---

# Launch plan

GitHub Trending does not rank by total stars. It ranks by **stars gained in a short window**
relative to a repo's baseline. Eighty stars in one day puts a new repo on the daily list;
the same eighty stars spread over a month puts it nowhere. Every decision in a launch plan
follows from that: concentrate attention into one day, then ride the Trending page for the
second wave.

## Channels, ranked by stars per hour of effort

| Channel | Expected effect | Account needed | Notes |
|---|---|---|---|
| Hacker News (Show HN) | 100–2,000 stars if it lands; 0 if not | Any age works | See `show-hn-launch`. The whole plan is built around this. |
| GitHub Trending | 50–500/day while listed | – | A consequence of the HN spike, not a channel you post to. Pick the right primary language and topics (`repo-hygiene`). |
| Reddit (1–3 subreddits) | 20–200 | Account with some karma; new accounts are often auto-removed | See `reddit-launch`. |
| X / Twitter | 10–500 | Depends entirely on who reshares | One thread with the GIF; tag 2–3 people whose tools you integrate with, not influencers. |
| Awesome lists | 5–50/month, forever | – | Slow but compounding. See `awesome-list-pr`. |
| skills.sh / tool directories | 5–100 | – | For agent skills, MCP servers, CLIs. Submit the day you launch. |
| Dev.to / Hashnode / blog | 10–100 | – | Second wave material. See `second-wave`. |
| Newsletters (TLDR, Console, Bytes, etc.) | 50–500 if picked | – | Submit the HN link, not the repo. They pick from HN front page anyway. |
| Discord/Slack communities of the tools you build on | 10–50 | – | Post once in the right channel; do not spam. |
| Product Hunt | 10–100 | – | Weak for dev tools; skip unless there is a GUI. |
| Telegram/WeChat/local dev channels | 20–200 | – | Strong in RU/UA/CN/VN/BR communities. One post per channel. |

## The 7-day schedule

Day 0 is the launch day. Count backwards for prep and forwards for the second wave.

**Day −3 to −1: build the asset.**
- README passes `readme-that-sells`. Demo GIF exists (`demo-gif`).
- `repo-hygiene` complete: description, topics, license, social preview, v0.1.0 release, 3 good-first-issues.
- Show HN title + first comment written (`show-hn-launch`).
- Reddit posts written per subreddit (`reddit-launch`). X thread drafted.
- Awesome-list PRs prepared but **not yet opened** (open them on Day 0 so the repo already has stars when maintainers look).
- Dry run: a friend installs from the README on a clean machine. Fix whatever broke.

**Day 0: launch (pick the slot).**
- Slot A: Monday 00:00 UTC (Sunday evening in the Americas). Best odds of 50+ points.
- Slot B: Tuesday–Thursday, 08:00–10:00 US Eastern. Front page moves fastest.
- T+0: submit Show HN. T+1 min: first comment. T+5 min: post the **HN link** (not the repo link) to X and your communities — comments and clicks on HN help ranking; stars on GitHub do not.
- T+30 min: Reddit posts (link to the repo, mention the HN thread in a comment).
- T+1 h: open awesome-list PRs, submit to directories.
- T+0 to T+4 h: reply to everything, everywhere, within 10 minutes. This is the job for four hours.
- T+6 h: if on HN front page, email the newsletters with the HN link.

**Day 1: ride Trending.**
- Check `github.com/trending` for your language and "all". If listed, post a screenshot ("we're #N on GitHub Trending") on X and in communities — it is social proof that compounds.
- Fix every bug reported on Day 0 and cut v0.1.1. Reply "fixed in v0.1.1" in the threads.

**Day 2–3: the long tail.**
- Write the second-wave piece (`second-wave`): what you learned, a benchmark, or a technical deep-dive. Do not publish yet.
- Answer every issue within 24 h. Label good ones. Merge the first outside PR fast; a merged outside PR is the strongest signal to the next contributor.

**Day 4–6: second wave.**
- Publish the piece on your blog / Dev.to. Submit to HN as a normal link (not Show HN) at the other time slot. Post to the subreddits you did not use on Day 0.
- Reply to anyone who mentioned the repo on X in the past week.

**Day 7: measure and decide.**
- Pull star history (GitHub's star history endpoint or `star-history.com`). Note which channel produced which spike.
- Decide: another feature + launch cycle in 2–4 weeks, or let it coast. Do not post weekly; the second post about the same thing with nothing new gets flagged.

## Rules

- **One launch day.** Never spread posts across a week "to be safe". Spread equals invisible.
- **The HN thread is the hub.** Every other channel links to the thread on Day 0, because HN ranking responds to engagement on the thread and the thread sends people to the repo. Reddit is the exception: it links to the repo, because Reddit penalizes HN links.
- **Ship v0.1.0 before launch, v0.1.1 within 24 h.** A fast second release tells visitors the project is alive.
- **Never buy stars, never vote-ring, never fake comments.** GitHub removes purchased stars and HN kills vote-ringed posts; both are detectable and both are permanent reputation damage.
- **Time zone math is done twice.** Convert the slot to local time, then convert back to check. A missed slot is a missed week.

## Procedure

1. Ask (or infer) the repo URL, the user's time zone, and which accounts exist (HN, Reddit, X) with rough karma/age.
2. Audit against `readme-that-sells` and `repo-hygiene`; list blockers.
3. Pick the launch slot; produce the schedule above as concrete local dates and times.
4. For each channel, produce the exact text to post (delegate to the channel skills).
5. Output a single checklist the user can tick through on launch day.

## Output

A dated schedule in the user's time zone, a per-channel post list with links to the drafts, and a launch-day checklist.
