# Design

A starter design file. The CLAUDE.md in this folder loads it, so Claude follows it in every video you make here. Replace each example below with your own, or ask Claude: "Rewrite design.md for my videos. Here are my colors, my fonts, and a screenshot of a style I like."

The examples are for a made-up coffee shop, so you can see what a filled-in file looks like.

## The look in one sentence

Warm, slow and cosy: cream cards on a deep espresso background, with soft film grain. *(Yours: describe it the way you'd describe it to a designer.)*

## Colors

Pick one background, one text colour, and ONE accent. The accent marks the single thing the viewer should remember in each scene.

| Role | Example | Use |
| --- | --- | --- |
| Background | `#2b1d16` espresso | The whole frame, with a soft lighter glow in one corner |
| Card | `rgba(255, 244, 230, 0.08)` | Cards floating on the background |
| Text | `#f6eee3` cream | Everything you read. Never pure white |
| Muted text | `#b9a99a` | Lead-in words ("Meet our", "Only this") |
| Accent | `#e8a15d` caramel | The key word, the active card, connector lines |
| Good | `#9cc5a1` sage | "Yes", "done", prices that are a deal |
| Bad | `#c95c4b` | Mistakes and "no" only |

Rule: take your accent from your background or your logo, so it never fights the frame.

## Fonts

Three fonts, each with one job:

- **Headlines:** `Fraunces` (or any warm serif). A small muted lead-in line, then one or two big words in the accent colour.
- **Labels and UI:** `Inter` (or any clean sans): tags, prices, small captions.
- **Code or "data":** `JetBrains Mono`: anything a computer would print.

Use the font files from Google Fonts, put them in `fonts/`, and reference them in CSS.

## Texture

- A light film-grain overlay on top of everything (about 30% strength), re-rolled about 12 times a second.
- The background glow drifts slowly.

## Motion

Follow `CAMERA-RULES.md`. In short: one world, one camera, the camera never parks, whips instead of blur, and connected things move together.

- Cards pop in (a small scale-up with a little overshoot, about 0.35 s).
- Words appear one at a time, on the spoken word.

## Sound

- Short pops when cards land, soft whooshes on whips, a low thump on a hard cut.
- No music under the voice, or keep it at least 20 dB below the voice.

## Formats

- 9:16 (1080x1920) for Reels, Shorts and TikTok.
- 4:5 (1080x1350) for LinkedIn and X: the same video with the camera zoomed out.
- Keep important things out of the top and bottom 160 px of the 9:16 frame.

## Every video ends

On a call to action: what the viewer should do next, e.g. "Order at the counter" or "Full video on YouTube". *(Yours.)*
