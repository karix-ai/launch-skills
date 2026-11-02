---
name: demo-gif
description: Produce a short demo GIF or video for a README and social posts, including a VHS tape script for terminal tools. Use when a README has no demo, when the user asks for a GIF/screencast, or before any launch.
---

# Demo GIF

A README with a demo converts visitors to stars at several times the rate of one without.
The demo is also the only asset that works everywhere: GitHub, Hacker News comments,
Reddit, X, Discord. Make it once, make it right, reuse it all week.

## What a good demo shows

- **The result, not the setup.** Open on the one command the user would type; end on the output they want. Installation is a separate GIF if needed at all.
- **≤ 10 seconds for social, ≤ 20 seconds for the README.** Attention on a feed is 3 seconds; on a README it is 15.
- **One scenario.** The most common use, not the most impressive edge case.
- **Real output.** Never a mockup. If the output is long, the terminal scrolls; that is fine.
- **Readable at 600 px wide.** Large font, high contrast theme, no tiny panes. Most people will see it on a phone.
- **Loops cleanly.** End with a 1–2 second hold on the final frame so the loop does not feel like a glitch.

## Terminal tools: use VHS

[VHS](https://github.com/charmbracelet/vhs) renders a `.tape` script to GIF/MP4 deterministically, so the demo can be regenerated when the CLI changes.

Install: `brew install vhs` or `go install github.com/charmbracelet/vhs@latest` (needs `ttyd` and `ffmpeg`).

Template `demo.tape`:

```
Output demo.gif
Output demo.mp4

Set Shell "bash"
Set FontSize 22
Set Width 1200
Set Height 640
Set Theme "Catppuccin Mocha"
Set Padding 24
Set TypingSpeed 40ms
Set PlaybackSpeed 1.0

Hide
Type "clear" Enter
Show

Type "npx skills add karix-ai/launch-skills"
Sleep 600ms
Enter
Sleep 2.5s

Type "claude 'write my Show HN post'"
Sleep 600ms
Enter
Sleep 4s
Sleep 1.5s
```

Rules for the tape:
- `Hide`/`Show` around setup so the GIF starts on the first real command.
- `TypingSpeed 40ms` reads as human; 20ms looks fake, 80ms is boring.
- Sleep long enough for the viewer to read the output (roughly 1 s per 2 lines).
- Width 1200 × Height 640 at FontSize 22 scales well to 600 px.

Run: `vhs demo.tape`. Commit the `.tape` file so contributors can regenerate.

## GUI / web tools

- Record with the OS screen recorder or OBS at 1280×800, crop to the relevant window.
- Convert to GIF: `ffmpeg -i demo.mp4 -vf "fps=12,scale=800:-1:flags=lanczos" -loop 0 demo.gif`
- Or keep MP4/WebM and embed via a GitHub-uploaded video (drag the file into an issue or the README editor; GitHub hosts it). Video is sharper and smaller than GIF; GIF autoplays in more places. Make both.

## Size

GitHub renders README images via a proxy; keep the GIF under ~5 MB or it loads slowly on mobile. Reduce with `gifsicle -O3 --lossy=80 --colors 128 demo.gif -o demo.gif`.

## Placement

- README: directly under the pitch line, as `![demo](demo.gif)` or a `<video>`-style upload.
- Social: attach the MP4 (X compresses GIFs badly; MP4 looks better).
- HN: HN has no media. Link the GIF in the first comment only if it is essential; otherwise the README carries it.

## Procedure

1. Identify the single most common command or action. Confirm it works from a clean state.
2. Write the `.tape` (terminal) or a shot list (GUI): 3–5 steps, each with what is typed and what is shown.
3. Generate the GIF and MP4. Check: readable at 600 px, under 20 s, loops cleanly, under 5 MB.
4. Insert into the README; note the file paths for reuse in social posts.

## Output

`demo.tape` (or shot list), `demo.gif`, `demo.mp4`, and the README line that embeds it.
