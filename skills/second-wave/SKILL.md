---
name: second-wave
description: Plan and write the follow-up content that produces a second spike 4–7 days after launch — an X thread, a technical write-up, a benchmark, and the "we're trending" post. Use after a launch, when stars have plateaued, or when the user asks what to post next.
---

# Second wave

The launch spike fades within a week. Repos that keep growing do one more thing:
they give people a second reason to look, on a different channel, with something new to say.
Re-posting the same repo is spam; posting a result produced *with* the repo is content.

## Four pieces, pick two

**1. The "we're trending" post (day 1, X + communities).**
A screenshot of the repo on `github.com/trending` with the position, one sentence of thanks, the install command. Social proof is the cheapest content you will ever make, and it compounds: people star things they see others starring. Only post it if it is true.

**2. The technical deep-dive (day 4–6, blog/Dev.to → HN as a regular link).**
Pick the one design decision that got the most questions in the launch thread. Write 800–1,500 words: the problem, the two obvious approaches and why they fail, what you did, the measured result. Code snippets, one diagram. Title it as a finding, not a product: "Why we parse X before Y" rather than "Introducing...". Submit to HN at the slot you did not use for launch. These posts hit the front page more often than Show HNs because they are not asking for anything.

**3. The benchmark or comparison (day 4–7, Reddit + X).**
A table: your tool vs 2–3 alternatives on 3–5 measurable axes (speed, memory, tokens, lines of config, accuracy). Methodology in a `bench/` folder anyone can run. Be fair; include a row where you lose. A fair benchmark gets reshared by the competitors' users, which is the audience you want.

**4. The "what I learned launching" post (day 7+, X thread or blog).**
Numbers: stars per channel, HN points, comment count, top criticism, the bug that cost the most. Builders love launch post-mortems and they get shared by people who never saw the original launch. End with the repo link once.

## X / Twitter thread format

- Tweet 1: the demo MP4 (not GIF) + one sentence pitch + the repo link. Media first; the link last.
- Tweet 2: the problem in one line.
- Tweet 3–5: one capability each, each with a screenshot or short clip.
- Tweet 6: the limitation / what's next.
- Tweet 7: install command + "star it if useful" is acceptable here (it is not on HN).
- Tag 2–3 accounts whose tools you build on or compare with; they have a reason to reply. Do not tag influencers who have no relation to the project.
- Post 09:00–11:00 US Eastern on Tuesday–Thursday.

## Newsletters

After the launch thread has peaked, email or submit the **HN thread link** (editors trust HN traction) to the newsletters that cover your category: TLDR, Console.dev, Bytes, JavaScript Weekly / Node Weekly, Python Weekly, This Week in Rust, Golang Weekly, Hacker Newsletter, Changelog News. One line: what it is, the HN link, the repo link. Many pick from the HN front page automatically; submitting makes sure.

## Cadence after the second wave

- One meaningful piece every 2–4 weeks, each tied to a release with something new: a feature, a benchmark, an integration.
- Every release: GitHub release notes + one tweet + a comment in the original HN/Reddit threads if the release addresses something raised there.
- Reply to every public mention within a day for the first month.
- Never post about the project more than once a week in the same channel.

## Procedure

1. Read the launch threads (HN, Reddit) and issues. Extract: the top question, the top criticism, the most-requested feature, the most-surprising number.
2. Pick the two pieces from the four above that those facts support best.
3. Write them. For the deep-dive, verify every number by running the code.
4. Schedule: dates and times in the user's time zone, channels, and the HN slot for the deep-dive.

## Output

The two pieces, ready to publish, plus a dated schedule and the newsletter submission list.
