# Setup, step by step (Mac and Windows)

You install one thing by hand: Claude Code. Then you paste one prompt, and Claude installs everything else.

**What it costs:** Claude Pro, $20 a month. The free Claude plan doesn't include Claude Code. Everything else is free: HyperFrames is open source and renders on your own computer, with no account needed.

**What you need:** a Mac (macOS 13 or newer) or a Windows 10 or 11 PC, 4 GB of RAM or more, and an internet connection.

## 1. Open a terminal

- **Mac:** press `Cmd + Space`, type `Terminal`, press Enter.
- **Windows:** press the Windows key, type `PowerShell`, press Enter. The line you type on starts with `PS`.

## 2. Install Claude Code

Copy the line for your computer, paste it into the terminal, and press Enter.

**Mac**

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell)**

```powershell
irm https://claude.ai/install.ps1 | iex
```

It shows no progress while it downloads. Wait until you can type again.

Then close the terminal, open a new one, and check that it worked:

```bash
claude --version
```

It should print a version number, like `2.1.314 (Claude Code)`.

- **"command not found" or "not recognized":** open a new terminal window and try again.
- **Windows, "'irm' is not recognized":** you're in Command Prompt, not PowerShell. Use this line instead:

  ```bat
  curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd
  ```

- **Windows, optional:** [Git for Windows](https://git-scm.com/downloads/win) lets Claude use Bash. Without it, Claude uses PowerShell, which works too.

## 3. Make a folder and start Claude

```bash
mkdir my-video
cd my-video
claude
```

The first time only, Claude Code asks you three things:

1. **Text style:** press Enter.
2. **Login method:** choose `1. Claude account with subscription`, press Enter, and sign in in the browser window that opens. Then come back to the terminal.
3. **"Quick safety check: Is this a project you created or one you trust?"** It starts on **No, exit**. Press the down arrow to **Yes, I trust this folder**, then press Enter.

## 4. Paste the setup prompt

Copy the whole prompt from [SETUP-PROMPT.md](SETUP-PROMPT.md), paste it into Claude, and press Enter.

- Claude asks before it runs each command. Read it, then choose **Yes**.
- **Mac:** if you don't have Homebrew yet, Claude gives you a line to paste into a new Terminal window (`Cmd + N`). It asks for your Mac password, and nothing shows while you type it. That's normal. Homebrew may also install Apple's Command Line Tools, which takes a while. When it's finished, go back to Claude and type `done`.
- **Windows:** if a box asks "Do you want to allow this app to make changes to your device?", click **Yes**.
- If Claude asks you to restart it halfway through, type `/exit`, run `claude`, and paste the prompt again. It skips whatever is already done.

At the end, Claude shows a checklist of what it installed.

## 5. Restart Claude

Claude loads new skills when it starts, so restart it once:

```text
/exit
```

```bash
claude
```

## 6. Make your first video

Paste this, or describe your own video:

```text
Using /hyperframes, create a 15-second Instagram promo for my café. Vertical, 9:16.
```

- Claude may ask you a few questions about the video first. Answer in plain words.
- When it's ready, it opens a preview in your browser.
- Ask for changes in plain English, like `make the price bigger` or `slow down the ending`.
- When you like it, say `render it`. Claude tells you where the MP4 is.

## 7. Make it yours

- **design.md** holds your look: colors, fonts, texture. It starts filled in for a made-up coffee shop. Ask Claude: `Rewrite design.md for my videos. My colors are ..., my fonts are ...`
- **CAMERA-RULES.md** holds how things move. When something looks off, tell Claude what's wrong, and add it as a rule. That's how mine grew.
- **CLAUDE.md** tells Claude to follow both files for every video in this folder, so you don't have to repeat yourself.

## If you get stuck

- **`claude` isn't found:** open a new terminal window.
- **Claude says your plan doesn't include Claude Code:** the free plan doesn't. You need Pro or higher.
- **Something failed during setup:** paste the error into Claude and ask it to fix it.
- Still stuck? DM me or comment, and I'll try my best.

## Doing it by hand

If you'd rather install the tools yourself instead of step 4:

**Mac**

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

When it finishes, run the "Next steps" lines it prints, then:

```bash
brew install node ffmpeg
```

**Windows (PowerShell)**

```powershell
winget install OpenJS.NodeJS.LTS
winget install Gyan.FFmpeg
```

Close PowerShell and open a new one before the next step.

**Both**, inside your `my-video` folder:

```bash
npx hyperframes skills update
npx hyperframes doctor
```

`doctor` should show a check mark next to Node.js, FFmpeg, FFprobe and Chrome. The others are optional. Then download `CLAUDE.md`, `design.md` and `CAMERA-RULES.md` from this repo into the folder, and continue with step 5.
