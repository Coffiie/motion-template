# The setup prompt

Paste this into Claude Code, started inside your empty `my-video` folder. It installs everything else for you. [SETUP.md](SETUP.md) walks you through getting to that point.

```text
Set up this folder so I can make videos with HyperFrames. I'm new to this, so before each step, tell me in one short sentence what it does.

1. Check what's already installed: Node.js 22 or newer (with npm), and FFmpeg. Skip anything that's already fine.

2. Install whatever is missing or too old.
   - Mac: use Homebrew (install Homebrew first if it isn't there), then: brew install node ffmpeg
   - Windows: use winget: winget install OpenJS.NodeJS.LTS and winget install Gyan.FFmpeg
   If a step needs my password or has to run in its own window (like the Homebrew installer), give me the exact line to paste into a new terminal window, wait until I say "done", then check that it worked.
   If a tool isn't found right after installing it, it's usually the PATH: refresh it in your command, or tell me to restart Claude Code. Don't install it twice.
   On Windows, if PowerShell says running scripts is disabled, use npx.cmd instead of npx. Don't change my system settings.

3. Install the HyperFrames skills: npx hyperframes skills update

4. Make sure HyperFrames has a browser to render with: npx hyperframes browser ensure

5. Run: npx hyperframes doctor
   Only Node.js, FFmpeg, FFprobe and Chrome have to pass. whisper-cpp, TTS (Kokoro), BGM (MusicGen) and Docker are optional extras, so skip them.

6. Download my template into this folder:
   https://raw.githubusercontent.com/Coffiie/motion-template/HEAD/CLAUDE.md
   https://raw.githubusercontent.com/Coffiie/motion-template/HEAD/design.md
   https://raw.githubusercontent.com/Coffiie/motion-template/HEAD/CAMERA-RULES.md

7. Finish with a short checklist of what's installed, with versions. Then tell me to type /exit and run claude again in this same folder, so the new skills load.
```

## What to expect

- Claude asks before it runs each command. Read it, then choose **Yes**.
- On a Mac, the Homebrew installer needs your Mac password. Claude gives you a line to paste into a new Terminal window. Nothing shows while you type the password. That's normal.
- On Windows, if a box asks "Do you want to allow this app to make changes to your device?", click **Yes**.
- If Claude asks you to restart it halfway through, type `/exit`, run `claude` again, and paste this prompt again. It skips whatever is already done.
