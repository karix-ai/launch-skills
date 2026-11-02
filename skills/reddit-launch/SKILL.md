---
name: reddit-launch
description: Pick the right subreddits and write a post for each that survives moderation and gets upvoted. Use when the user wants to post a project on Reddit, asks which subreddit fits, or had a post removed.
---

# Reddit launch

Reddit sends fewer stars than Hacker News but is more forgiving: a post can be re-made
in a different subreddit, and a good comment thread lives for days. The failure modes are
specific and avoidable: wrong subreddit, auto-removal for a new account, and a post that
reads as an ad.

## Pick 1–3 subreddits, not 10

Cross-posting the same text to many subreddits gets flagged as spam across all of them.
Pick by audience, write a different post for each.

| Project type | Primary | Secondary |
|---|---|---|
| AI coding agent tools, skills, MCP servers | r/ClaudeAI, r/cursor, r/ChatGPTCoding | r/LocalLLaMA (only if it runs locally), r/artificial |
| Self-hosted / local tools | r/selfhosted | r/homelab, r/LocalLLaMA |
| CLI / dev tools | r/commandline, r/programming (strict) | language sub: r/rust, r/golang, r/Python, r/node |
| Web frameworks, frontend | r/webdev, r/reactjs, r/nextjs | r/javascript |
| Data / ML | r/MachineLearning (strict, tag [P]) | r/datascience, r/learnmachinelearning |
| Security | r/netsec (strict) | r/cybersecurity |
| Games / graphics | r/gamedev, r/proceduralgeneration | r/rust_gamedev |
| Side projects, anything | r/SideProject, r/opensource | r/coolgithubprojects |

Read each subreddit's rules before posting. Common constraints: self-promotion only on certain days, a flair is required, a minimum account age or karma, "no link posts". Breaking one gets the post removed silently.

## Account reality

- A brand-new account with 0 karma is auto-removed in most large subreddits. If the user has no aged account, say so and either: (a) spend two days commenting usefully in the target subreddits first, or (b) ask a collaborator with an aged account to post, with the author replying in comments.
- Post from the author's own account whenever possible. "My friend built this" posts underperform.

## Post format

Prefer a **text post** with the link inside, or an image/GIF post with the link in the first comment, depending on subreddit rules. Pure link posts get the fewest comments.

Title: plain, specific, no clickbait, no emoji, ≤ 100 characters. Say what it does and who it is for. Mentioning "open source" in the title is fine on Reddit (unlike HN).

Body, 100–250 words:

```
<One line: what it is.>

<Why I built it — one concrete frustration, first person, no sales voice.>

<What it does, 3–5 short bullets, each a capability a user would recognize.>

<What it doesn't do / known rough edges — one or two lines.>

<Link to the repo. One line install command.>

<One question for the community: a real one you want answered.>
```

Rules:
- Write for the subreddit's culture. r/LocalLLaMA wants VRAM numbers and model names; r/selfhosted wants a `docker-compose.yml`; r/ClaudeAI wants to know it works with Claude Code today.
- No "Check out my", no "revolutionary", no "excited to announce".
- The GIF matters more here than anywhere else: Reddit is a visual feed. Lead with it.
- End with a question. Posts with a question in the body get 2–3x the comments, and comments drive ranking.

## After posting

- Reply to every comment in the first 2 hours. Upvote nobody's comment but your own replies' parents is fine; asking for upvotes is a ban.
- If removed: message the moderators politely, ask which rule, fix, and ask if you may repost. Do not just repost.
- Post at 09:00–11:00 US Eastern on a weekday for English-language subreddits. Weekends are fine for r/selfhosted and hobby subs.

## Procedure

1. Classify the project; pick 1–3 subreddits from the table; fetch and summarize each subreddit's posting rules.
2. Check account age/karma constraints against what the user has; flag blockers.
3. Write one title + body per subreddit, each tailored. Include the GIF reference and the install command.
4. Give posting times in the user's time zone.

## Output

Per subreddit: rules summary, title, body, time to post. Plus any account blockers.
