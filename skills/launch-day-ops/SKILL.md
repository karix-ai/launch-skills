---
name: launch-day-ops
description: Run the launch day — the reply loop, issue triage, hot-fix releases, and how to answer hostile or skeptical comments. Use on launch day, when the user is overwhelmed by comments and issues, or asks how to respond to criticism.
---

# Launch-day operations

Ninety-two percent of launch stars arrive in the first 48 hours, and most of those in the
first six. The author's job in that window is not to code; it is to answer. Every reply
within minutes raises the thread, every unanswered comment lowers it, and the people
reading the thread decide whether this project has a maintainer.

## The reply loop (first 6 hours)

Every 10 minutes, in this order:

1. **HN thread** (or whichever is the hub): new comments → reply.
2. **GitHub issues**: new issues → acknowledge within the hour, label, fix if < 15 minutes.
3. **Reddit threads**: new comments → reply.
4. **X mentions / DMs**: like, reply briefly, retweet anyone who posted the demo.
5. **Discord/Slack**: answer questions where you posted.

Keep a single scratch file with the HN link, repo link, demo GIF link, install command, and the three most common answers, so each reply is a paste plus one personal sentence.

## How to reply

- **Lead with the fact, not the feeling.** "Yes — it does X; see `src/foo.ts:42`." Links to code are the highest-trust reply on HN.
- **Thank briefly, once.** "Thanks" + the answer. Not "Thank you so much for taking the time".
- **Concede fast.** If they are right, "You're right, fixed in a1b2c3" within the hour. A visible fix during the thread is worth more than a defence.
- **Never argue tone.** Reply to the substance of a rude comment as if it were polite. Readers side with the calm one.
- **"Why not just use X?"** → one sentence on what X does well, one on the concrete case where this differs, no adjectives. If the honest answer is "X is fine for most people", say so; HN rewards it.
- **"This is just a wrapper around Y."** → "Yes, it's Y plus A, B, C; A is the part I couldn't get from Y." Do not deny the wrapper; describe the delta.
- **"Did an AI write this?"** → answer honestly in one line and move on to what it does. Dwelling on it derails the thread.
- **Security or licensing concerns** → take them seriously in public, fix in private if needed, report back in the thread.
- **Feature requests** → "Opened #N, would take a PR" and open the issue. It converts commenters into contributors.
- **Do not reply to every upvote-seeking joke.** Reply to questions, bugs, and comparisons.

## Issue triage during the spike

- Label on arrival: `bug`, `enhancement`, `question`, `good first issue`, `wontfix`.
- Anything reproducible and under 15 minutes: fix now, reply with the commit, close.
- Anything larger: reply with "confirmed, scheduled for v0.2", leave open.
- Close duplicates with a link to the canonical issue; do not leave them open.
- The first outside PR: review within 2 hours, merge if reasonable, thank in the release notes. One merged outside PR on day 1 sets the tone for the next hundred.

## Hot-fix release

- Cut `v0.1.1` before the end of day 0 with every fix from the thread. Release notes list the reporters by handle ("Fixes #12, reported by @name on HN").
- Reply in each thread where the bug was reported: "Fixed in v0.1.1."

## What not to do

- Do not ask anyone to upvote anything.
- Do not edit the submission title after the first minutes.
- Do not post the same link again in the same channel.
- Do not delete negative comments on Reddit or lock the thread.
- Do not push large refactors during the spike; ship fixes only. A broken install at hour 3 ends the launch.
- Do not sleep until the hub thread has been quiet for 90 minutes.

## Procedure

1. Prepare the scratch file (links, install command, top-3 answers) before posting.
2. Set a 10-minute timer; run the loop until the thread is quiet.
3. Keep a running list of bugs; cut the hot-fix release before midnight local time.
4. At end of day, write five lines: stars gained, comment count, top 3 criticisms, what shipped, what is scheduled.

## Output

The scratch file, labeled issues, the hot-fix release, and the end-of-day summary.
