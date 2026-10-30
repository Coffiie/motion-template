# Camera rules

Read this before you write any animation for this project. Every rule here came from a video that looked wrong until the rule existed.

## 1. One world, one camera

- Every scene is a region of one big canvas (the "world"). Put each scene at its own spot, e.g. 3600 px apart.
- Only the camera moves. It's one transform on the world container: translate plus scale.
- Cards never fly across the screen by themselves. They pop in where they live, and the camera travels to them.

## 2. The camera never parks

- After every move, the camera keeps creeping in, about 1.5% zoom per second.
- Add a faint sway on top: a few pixels of x/y and about 0.6% zoom on slow sine waves (6–10 s periods).
- Even a frame where nothing happens should be alive.

## 3. Whips have no motion blur

- A move that crosses more than about half a screen is a whip: about 0.55 s, ease `power3.inOut`.
- Instead of blur, throw speed lines: a few rounded pills in the text and accent colours, streaking opposite to the move and fading in about 0.3 s.

## 4. Cut, whip, or pull back

- **New topic:** hard cut.
- **Same topic, next point:** whip.
- **Reveal a diagram:** slow pull-back (1–1.6 s) until the whole thing fits.

## 5. Connected things move as one piece

- Connectors are SVG lines in the same coordinates as the cards they join. They grow from their start point to their end point.
- A card that a connector touches pops from the edge the line meets (`transform-origin` on that edge).
- Never flip or squash a card (no `scaleY` or `rotateY` tricks) while it's connected to something. To change what a card says, swap its content in place: old text out, new text in, and the box itself never moves.

## Text that doesn't jitter

These come from renders where text visibly snapped by a pixel during slow camera moves:

- Never leave `filter`, `backdrop-filter` or `will-change` on anything that holds text. A word can blur in, but set `filter: none` once it lands.
- Give the camera transform a tiny rotation (about 0.05°). A scale-only transform makes the browser round each line of text to whole pixels.
- Never leave a whole group of cards half-faded. Hide it with `visibility: hidden` (GSAP's `autoAlpha`), not just `opacity: 0`.
- Don't animate `box-shadow`. It flashes for a frame.

## Pace

- About 170 words a minute for explainers.
- Put each item of a list on its own line in the script, so it gets its own moment on screen.
- Words appear on the word that's spoken: tie every animation to a timestamp in the voiceover, not to hand-typed seconds.

## Frame for 9:16, check in 4:5

- Compose every shot for the tall phone frame (1080x1920).
- The 4:5 version for LinkedIn and X (1080x1350) is the same video with the camera zoomed out about 0.84. Keep each shot's subject out of the top and bottom 160 px of the 9:16 frame, and it works in both.

## Before you render

Take snapshots at 8–12 moments and look at them. Check for text running off the frame, overlapping cards, and empty frames. Fixing a snapshot takes seconds; a full render takes minutes.
