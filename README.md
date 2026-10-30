# Motion template

Everything from my video "The second best time is now": how I make motion graphics videos with Claude Code and HyperFrames, and the files that make them look like mine instead of generic.

| File | What it's for |
| --- | --- |
| [SETUP.md](SETUP.md) | Every step from zero, for Mac and Windows. You install Claude Code yourself, and Claude installs the rest. |
| [SETUP-PROMPT.md](SETUP-PROMPT.md) | The one prompt that installs Node.js, FFmpeg, HyperFrames and its skills, then downloads this template. |
| [CAMERA-RULES.md](CAMERA-RULES.md) | How the camera moves, and the rules that keep text from jittering. Every rule came from a video that looked wrong until the rule existed. |
| [design.md](design.md) | A starter design file: colors, fonts, texture, motion and sound. It's filled in for a made-up coffee shop, so you can see what goes where. |
| [CLAUDE.md](CLAUDE.md) | Tells Claude to follow design.md and CAMERA-RULES.md in every video in your folder. |

## Quick start

1. Get Claude Pro ($20 a month). The free plan doesn't include Claude Code.
2. Install Claude Code, make a folder, and start `claude` in it ([SETUP.md](SETUP.md), steps 1 to 3).
3. Paste [the setup prompt](SETUP-PROMPT.md). Then type `/exit` and run `claude` again.
4. Ask for a video:

   ```text
   Using /hyperframes, create a 15-second Instagram promo for my café. Vertical, 9:16.
   ```

Stuck? DM me or comment, and I'll try my best.

HyperFrames is open source (Apache 2.0) and made by HeyGen: [hyperframes.heygen.com](https://hyperframes.heygen.com). Claude Code is made by Anthropic: [code.claude.com](https://code.claude.com).
