---
name: show-hn-launch
description: Write a Show HN submission (title, URL choice, first comment) and pick the posting time, using data from 188,000 Show HN posts. Use when the user wants to launch on Hacker News, asks for a Show HN title, or asks when to post.
---

# Show HN launch

Hacker News is the single largest star engine for developer tools. It is also brutal:
the median Show HN scores 2 points, and a post that reaches 50 points is in the top 6%.
The difference between 2 and 50 is mostly the title, the first comment, and the hour.

## What the data says

Numbers below come from public analyses of HN and GitHub star histories (see `data/launch-stats.md` in this repo for sources).

- **Each HN upvote ≈ 1.4 GitHub stars within 48 hours.** A 100-point post is roughly 140 stars from HN alone, plus the long tail from people who find the repo later.
- **~92% of launch stars arrive in the first 48 hours.** Day 1 is the spike; by day 3 it is single digits per day. Everything must be ready before posting.
- **Successful launches average ~289 stars in the first week**; a front-page run can do 500–2,000 stars in 24 hours.
- **Best posting window (by chance of reaching 50+ points): Monday 00:00 UTC**, i.e. Sunday 7 pm US Eastern. Second best: Tuesday–Thursday 08:00–10:00 US Eastern. Worst: Friday afternoon and weekends (except Sunday evening).
- **The "Show HN" tag itself does not add stars** after controlling for other factors. Use it because it is the correct tag, not because it is a boost.
- **Time to first comment is ~4.4 hours on median.** Most posts die in silence. You will seed the thread yourself (see below) and answer every comment within minutes for the first 3 hours.

## Title

Format: `Show HN: <Name> – <what it is, concretely>`

Rules, in priority order:

1. **Concrete noun phrase, no adjectives.** "Show HN: Lightpanda – headless browser for AI agents, 10x less RAM than Chrome" beats "Show HN: A blazing fast new browser".
2. **Lead with the category the reader already understands**, then the twist. Readers skim for "is this for me?".
3. **A number if you have one that is true and surprising.** "188k posts", "40% fewer tokens", "runs on a Pi".
4. **≤ 80 characters.** HN truncates long titles and the end is the part that gets cut.
5. **No "I built", no "introducing", no "open source" in the title** (the Show HN tag already says that). No emoji. No exclamation marks. No "v1.0".
6. **Do not mention the language unless it is the point.** "...written in Rust" only if Rust is the reason it exists.
7. **Say what it is, not what it is like.** "Like Vercel for X" is a weak title; HN readers dislike the pattern and it tells them nothing.

Generate 5 titles. Score each on: concrete (0–2), category clear (0–2), twist visible (0–2), length ok (0–1). Pick the top score; if tied, pick the shortest.

## URL

Link directly to the GitHub repo unless the project has a landing page with a live demo that works without signup. HN readers trust repos; they bounce from marketing pages. If linking to a page, the README must still be launch-ready because people click through to it.

## First comment (post it within 60 seconds of submitting)

The first comment is where you explain. The title sells; the comment convinces. 150–300 words, plain text, no markdown headings, no links except to the repo and at most one comparison.

Template:

```
Hi HN, I'm <name>, I built <Name>.

<One sentence: the problem, in the words of someone who has it.>

<Two or three sentences: what it does, and the one technical decision that makes it different.>

<One sentence: what it does NOT do yet, or the known limitation. Be the first to say it.>

<One sentence: what you'd like feedback on.>

Repo: <url>
```

Why the limitation line matters: HN's first instinct is to find the flaw. If you name it first, the thread is about the work, not the gap.

## While the thread is live (first 3 hours)

- Reply to every comment, including hostile ones, within 10 minutes. Thank, answer, link to the file or line that proves it. Never argue tone; argue facts.
- If someone reports a bug, fix it and reply "fixed in <commit>" — HN upvotes this behavior.
- Do not ask friends to upvote. Vote rings are detected and the post is killed. Asking people to *read and comment if they find it interesting* is fine.
- Do not edit the title after 10 minutes unless a mod asks.
- If the post is not on the front page after 90 minutes with fewer than 5 points, it is dead. Do not resubmit the same URL for at least 2 weeks; resubmit only with a different angle (a new feature, a benchmark, a write-up) and preferably at the other time slot.

## Procedure

1. Confirm the README passes the `readme-that-sells` skill and the repo passes `repo-hygiene`. If not, stop; launching early wastes the one shot.
2. Draft 5 titles, score, pick one. Show the user the scoring.
3. Write the first comment.
4. Convert the two posting windows to the user's local time zone and give both as concrete dates.
5. Produce a launch-hour checklist: post → first comment → share the HN link (not the repo) in the user's own channels → reply loop.

## Output

Title (with the two runner-ups), first comment, posting time in local time, and the checklist.
