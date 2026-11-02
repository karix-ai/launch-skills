# Contributing

## Add or improve a skill

1. Each skill lives in `skills/<name>/SKILL.md` with YAML frontmatter:

   ```
   ---
   name: <name>            # lower-case, hyphenated, matches the folder
   description: <one sentence: what it does + when an agent should use it>
   ---
   ```

2. Write for an agent, not a reader: short imperative rules, a numbered procedure, an explicit output format. No marketing voice.
3. Any number must have a source. Add it to `data/launch-stats.md` in the same PR.
4. Keep a skill under ~200 lines. If it grows past that, split it.

## Validate locally

```bash
npx skills add . --list
```

Every skill should appear. Fix the frontmatter if one is missing.

## What we want

- Per-ecosystem channel maps (which subreddits, Discords, newsletters for Rust / Python / ML / mobile …)
- Launch post-mortems with numbers (stars per channel, HN points, time slot)
- Corrections to any statistic, with a link
- Translations of the subreddit/community map for non-English dev communities

## What we don't merge

- Anything that buys, trades or fakes stars, upvotes or reviews
- Growth-hack tactics that break a platform's rules
- Skills that are a product pitch for a paid tool
