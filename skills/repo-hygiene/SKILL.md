---
name: repo-hygiene
description: Audit and fix the repo-level details that affect discovery and conversion — description, topics, license, social preview, release, labels, templates. Use before any launch, when a repo looks unfinished, or when asked to make a repo "ready".
---

# Repo hygiene

These are the twenty-minute fixes that decide whether a visitor sees a project or a hobby.
Most are invisible until missing. Do all of them before launch day; none of them can be
done after the spike has passed.

## Checklist

### Discovery (how people find it)

- [ ] **Description** (the one-liner under the repo name): ≤ 120 characters, same pitch as the README's first line, keyword-dense. GitHub search and Trending show this line, not the README.
- [ ] **Topics**: 5–10. Include the category (`cli`, `mcp-server`, `agent-skills`), the ecosystem (`claude-code`, `cursor`, `nodejs`), and the problem (`token-optimization`, `screenshots`). Topic pages are a steady source of traffic; `github.com/topics/<topic>` lists repos by stars.
- [ ] **Primary language** is the one you want to trend in. GitHub picks it by bytes; if docs or vendored code dominate, add a `.gitattributes` with `linguist-vendored` / `linguist-documentation` so the real language wins.
- [ ] **Website field** set (docs site, or the repo itself).
- [ ] **Social preview image** (Settings → General → Social preview): 1280×640, project name, the pitch line, one visual. This is the card that appears when the link is shared on X, Slack, Discord, LinkedIn. Without it, shares show a grey GitHub placeholder.

### Trust (why people star instead of bookmark)

- [ ] **LICENSE** file at the root. MIT or Apache-2.0 for maximum adoption; a repo with no license is unusable for most companies and many people check this first.
- [ ] **A tagged release** (`v0.1.0`) with notes. "Releases: 0" reads as abandoned. Tag before launch, tag `v0.1.1` within 24 hours after.
- [ ] **CI badge** that is green. A failing or missing badge is worse than none; if there is no CI, add a 10-line workflow that runs the test or at least `--help`.
- [ ] **Recent commit**. Launch within 24 h of the last commit; the "updated N days ago" line is read as a heartbeat.
- [ ] **Author profile**: real name or consistent handle, avatar, one-line bio, pinned repo. Visitors click the avatar before starring.

### Contribution (how the first PR happens)

- [ ] **CONTRIBUTING.md**: how to run locally, how to run tests, how to add a thing (a skill, a plugin, a command). Keep it under 60 lines.
- [ ] **3–5 issues labeled `good first issue`** that are genuinely small (docs, a missing example, a config option). The label is indexed by GitHub and by sites that list beginner issues.
- [ ] **Issue templates** (bug, feature) and a **PR template** with a 3-item checklist. Optional but they cut triage time during the spike.
- [ ] **Code of conduct** if you expect a community; a one-line link to the Contributor Covenant is enough.

### Hygiene (what makes it look finished)

- [ ] No `TODO` in the README. No placeholder images. No `your-username` left in install commands.
- [ ] `.gitignore` present; no committed secrets, `node_modules`, `.env`, `.DS_Store`.
- [ ] Repository name is the product name, lower-case, hyphenated. Rename before launch, never after (links break).
- [ ] Default branch is `main`.
- [ ] The install command in the README works on a clean machine. Test it.

## Procedure

1. Fetch repo metadata (description, topics, license, releases, languages) via `gh repo view --json` or the GitHub API.
2. Walk the checklist; mark pass/fail.
3. Fix everything fixable from the terminal: write LICENSE, CONTRIBUTING.md, `.github/` templates, `.gitattributes`; set description and topics with `gh repo edit --description ... --add-topic ...`; tag and publish a release with `gh release create v0.1.0 --generate-notes`.
4. For items needing the web UI (social preview), produce the asset (1280×640 PNG) and tell the user exactly where to upload it.
5. Create the good-first-issues with `gh issue create --label "good first issue"`.

## Output

The checklist with pass/fail per item, the commands run, and the remaining manual steps with exact UI paths.
