---
name: readme-that-sells
description: Write or rewrite a README that makes a stranger star the repo within 15 seconds. Use when creating a README, when the user says the README is weak, before any launch, or when a repo gets traffic but few stars.
---

# README that sells

A README is not documentation. It is a landing page that happens to live in a git repo.
A visitor decides in about 15 seconds whether to star, try, or leave. Everything above the
fold must earn the star. Documentation goes below the fold or into `docs/`.

## The 15-second test

Before writing anything, answer these in one line each. If you cannot, the README cannot either.

1. **What is it?** One sentence, no adjectives. "A headless browser for AI agents, written in Zig."
2. **Why does it exist?** The pain it removes, in the user's words. "Chrome eats 500 MB per tab; agents need 50 tabs."
3. **Proof it works.** A demo GIF, a benchmark number, or a before/after. Not a feature list.
4. **How do I try it in one command?** `npx ...`, `pip install ...`, `curl ... | sh`, `docker run ...`.

## Structure (in this order, no exceptions)

```
# project-name
One-sentence pitch. (what + for whom + the hook)

[demo GIF or screenshot — under 10 seconds, shows the result, not the setup]

## Install           ← one command, copy-pasteable, no prerequisites hidden
## Why               ← 3–5 lines: the pain, the existing alternatives, why this is different
## Usage             ← the single most common case, as a runnable example
## Features          ← optional, short, bullet list, no marketing adjectives
## How it works      ← optional, one paragraph or one diagram
## Comparison        ← optional table vs 2–3 alternatives, honest about trade-offs
## Contributing / License
```

## Rules

- **Pitch line:** ≤ 15 words. Name the category and the differentiator. Avoid "blazing fast", "powerful", "simple yet". If it has a number, use the number: "Cuts Claude Code token use by 40%."
- **Demo first, words second.** The GIF or screenshot goes immediately under the pitch. If there is no demo yet, make one before launching (see the `demo-gif` skill). A README without a demo converts at a fraction of one with.
- **Install is one block, one command.** If it needs an API key or a config file, show that too, in the same block. Hidden prerequisites are the #1 reason people leave after cloning.
- **"Why" is written for someone who already has a solution.** Name the alternatives. Say what they do well. Then say the one thing this does that they do not. Readers trust READMEs that are fair to competitors.
- **No emoji in headings** unless the project is deliberately playful. No badges above the pitch (a wall of badges is the first thing visitors scroll past). Two or three badges under the pitch is fine: build status, version, license.
- **One real example beats ten feature bullets.** Show input → output. Make it something the reader would actually run.
- **Say what it is not.** One line of honest scope ("Not a replacement for Playwright; no JS rendering yet") pre-empts the first hostile comment on Hacker News.
- **Link the social proof you have.** "Used by X", a benchmark, a Show HN thread. Do not invent any.
- **Keep the top 60 lines free of anything a first-time visitor does not need.** Architecture, roadmap, FAQ, changelog: all below or elsewhere.

## Anti-patterns that kill conversion

- Starting with a paragraph of background or history.
- A table of contents as the first thing on the page.
- "Features" before "Install".
- Install instructions that start with "First, clone the repo" for a tool meant to be used, not developed.
- Screenshots of config files instead of results.
- Marketing voice ("revolutionary", "next-generation", "effortlessly").
- Dead placeholders ("TODO: add demo").

## Procedure

1. Read the current README (if any) and the code's entry points. Extract the four answers from the 15-second test.
2. Draft the pitch line. Write three variants; pick the one with the most concrete noun and the fewest adjectives.
3. Write Install, then Usage, then Why. Run every command in Install to confirm it works from a clean directory.
4. Insert the demo under the pitch. If none exists, add a `TODO(demo)` marker and tell the user it blocks launch.
5. Cut everything above the fold that fails the question "does a stranger need this to decide?"
6. Read the top 60 lines as a skeptical engineer. Fix the first thing that would make them close the tab.

## Output

Return the full README.md. Then list, in ≤ 5 bullets, what you changed and what the user still has to supply (demo GIF, benchmark numbers, real user quotes).
