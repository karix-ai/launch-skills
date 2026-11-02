---
name: awesome-list-pr
description: Find the awesome-lists and directories where a project belongs and open PRs that maintainers merge. Use when the user wants long-term discovery traffic, asks "where should I list this", or after a launch.
---

# Awesome-list PRs

Awesome lists are the slowest channel and the only one that compounds. A line in
`awesome-selfhosted` or `awesome-mcp-servers` sends a trickle of stars every week for years.
The PR takes ten minutes; most are rejected for ignoring the list's rules, not for the project.

## Finding the right lists

1. Search GitHub for `awesome <category>` where category is each of: the ecosystem (`awesome-claude-code`, `awesome-mcp-servers`, `awesome-cursor`), the problem (`awesome-cli-apps`, `awesome-selfhosted`), the language (`awesome-rust`, `awesome-go`), and the audience (`awesome-devops`, `awesome-indie`).
2. Rank by: stars (≥ 1k), last commit (≤ 3 months), and whether the list has an entry comparable to your project. A list that already has three tools like yours will take a fourth; a list with none may be out of scope.
3. Pick 3–5. More than that and the maintainers start seeing the same account across lists, which reads as spam.
4. Also list the **directories** for your category: skills.sh for agent skills, the MCP registries (registry.modelcontextprotocol.io, glama.ai, lobehub), awesome-selfhosted's companion site, npm/PyPI keywords, Homebrew taps. Each is one form.

## Reading the rules (do this, every time)

Open the list's `CONTRIBUTING.md` and the last 5 merged PRs. Note:
- Exact line format (`- [Name](url) - Description.` vs `* **Name** – description`), including the dash type, the trailing period, and capitalization.
- Alphabetical or chronological ordering within sections.
- Minimum requirements (stars, age, license, a README, a demo, English docs).
- PR title format ("Add Name" is the usual) and whether one PR = one entry.
- Whether they require you to have used the list's lint (`awesome-lint`) locally.

A PR that matches the last five merged PRs exactly is merged in days. One that does not sits for months.

## Writing the entry

- Description: ≤ 100 characters, no marketing, no first person, no "a tool that". Say what it does in the same voice as the neighbors. Copy the register of the entry above yours.
- Put it in the most specific section that fits. Do not create a new section in the same PR.
- One entry per PR unless the list says otherwise.

## The PR

- Title: `Add <Name>` (or the list's format).
- Body, 2–4 lines: what it is, why it fits this section, a note that you followed the format/lint, and that you are the author (lists prefer disclosure).
- Branch from the current default branch; rebase if the list moves before merge.
- Do not ping maintainers. Do not open an issue first unless the rules say to. Wait two weeks; then a single polite comment is acceptable.

## Timing

Open the PRs on launch day or the day after, once the repo has its first stars and release. Maintainers look at the repo when reviewing; a repo with 200 stars and a release is an easy merge, one with 3 stars is a judgment call.

## Procedure

1. Classify the project (ecosystem, problem, language, audience). Search for lists in each; rank; pick 3–5. List the matching directories.
2. For each list, fetch CONTRIBUTING.md and the last merged PRs; extract the exact format and rules.
3. Write the entry line for each list in that list's format, placed in the right section and position.
4. Produce the PR title and body for each.
5. If `gh` and a fork are available, open the PRs; otherwise output everything for the user to paste.

## Output

A table: list, stars, section, exact entry line, PR title, PR body, status (opened / to open). Plus the directory submission links.
