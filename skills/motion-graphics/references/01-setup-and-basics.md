# Setup and basics (from "Motion Graphics with Claude Code", Damiano Caudullo, @damianodesu)

## What you need
- A paid Claude plan (Pro, Max, Team or Enterprise) or an API account, and Claude Code. Your organisation must allow Claude Code.
- Install Claude Code (one line in Terminal):
  - Mac: `curl -fsSL https://claude.ai/install.sh | bash`
  - Windows (PowerShell): `irm https://claude.ai/install.ps1 | iex`
  - Docs: code.claude.com/docs
- Start it: make an empty folder, open Terminal in it, type `claude`.
- The guide's kit (downloaded with the PDF) contains: `prompts.md` (every prompt, same numbers — copy prompts from here, PDFs break line endings), `sfx/` (9 sounds made in code: pop, tick, counter, chime, snap, star, switch, fill, success), `fonts/` (free fonts for the 4 styles), `clip.mp4` (18-second practice clip of an AI-generated person — practice only).
- Before each project, copy `fonts/` (and `sfx/` if adding sound) into the project folder. The prompts point at those paths.

## One-time setup
1. Paste Prompt 01 into Claude Code. It checks/installs Node.js 22+, FFmpeg, whisper-cpp, the HyperFrames skills, then runs `npx hyperframes doctor`. Ignore optional items (Docker, Kokoro, MusicGen).
2. If something needs your password, Claude gives you the command; you run it and tell Claude "done".
3. **Restart Claude Code** afterwards — new skills only load on a fresh start (the easiest step to skip).
4. Windows: if node or ffmpeg isn't found after installing, open a new terminal. (The author tested on Mac only.)

## How it works
1. index.html — the page; what's on screen.
2. The timeline — what moves, when, how fast.
3. The render — Chrome photographs every frame; FFmpeg joins them into an MP4.
Every project folder has an index.html; you can open it in a browser, but don't need to.

## Turn the knobs (stay in the same session after any render)
Tested lines, each worked first time:
- Surface: "Change the card from frosted glass to a solid purple-to-pink gradient card with white text."
- Colour: "Use my brand colours: background #111111, card #ff5a1f, text white."
- Type: "Switch the number to a serif font (Instrument Serif from Google Fonts) and make it 30% bigger."
- Motion: "Make every animation bouncier, with a bit of overshoot."
- Timing: "Make the green pill appear at 2 seconds instead of 4."
- Layout: "Move the card to the top-left corner and make it 20% smaller."
End every change with: "Keep everything else the same and render again to renders/first.mp4."

## The 10 moves (ask by name, e.g. "add a blur-in", "use the reframe move")
| Move | What it does | Best for |
|---|---|---|
| Rise | fades in while moving up a little | default entrance |
| Pop | scales up from small with a small overshoot | badges, prices, stickers |
| Count-up | a number rolls to its value | any stat |
| Checklist tick | lines get a green tick one by one | benefits, steps |
| Typewriter | text types itself | search bars, messages, prompts |
| Slide-in | comes in from the side | cards, comparisons |
| Blur-in | blurry to sharp | reveals, focus moments |
| Punch-in | whole frame zooms in fast | the line people should remember |
| Reframe | your video shrinks into a card and something new appears | talking head → proof |
| Bar fill | a progress bar fills up | progress, before/after |
Prompt 03 in the kit's prompts.md makes a 14-second demo of all 10 (its text isn't printed in the PDF).

## Workflow habit: base first, then one spot
Don't put everything in one prompt. Get a base you like, adjust until nothing bothers you, then change one moment at a time. Give Claude the real thing (real screenshots, real numbers). Describe moments by words spoken ("when I say 40 a week"), not seconds — Claude finds it in the audio.

## Export (or just ask: "Render it in 4K at 60 fps")
Run in the project folder; add `-o` and a file name.
| Want | Command |
|---|---|
| 60 fps | `npx hyperframes render . --fps 60` |
| 4K | `npx hyperframes render . --resolution 4k` |
| 4K at 120 fps | `npx hyperframes render . --resolution 4k --fps 120` |
| 24 fps | `npx hyperframes render . --fps 24` |
| ProRes MOV | `npx hyperframes render . --format mov` |
| PNG frames | `npx hyperframes render . --format png-sequence` |
Author's benchmark: a 90-second reel renders in under 2 minutes on his Mac.

## Fix-it list (plain requests)
1. Wrong font / plain fallback → put the font file in fonts/ and say "use the font file in fonts".
2. Text cut off on phones → "keep all text inside the middle 80% of the width".
3. A card covers the captions → "move every card above the caption area".
4. A card is early or late (speech-to-text can be up to ~1 s off) → "make the card appear when I say [word]".
5. File is huge → "render again with --crf 23".
If it still looks off, describe it like you'd tell a friend.

## Gotchas
- Film grain makes big files: a 15 s Editorial Grain test was 124 MB; --crf 23 brought it to 69 MB.
- Overlays for Premiere/After Effects: remove the background first, or you get a "transparent" file with a solid background. Frosted cards lose their blur with nothing behind them — use solid cards for overlays.
- Graphics over your own video: nothing in the first 3 seconds (the hook), off the face, out of the bottom third (captions), away from the left/right 10%.
- Reels safe area (1080×1920): nothing important in the top 10%, bottom 20% or right 15%. Render one proof frame with the Reels buttons drawn on.
- Prompt 15 phone-safe band: every word 170–1330 px from the top, right edge clear.
- Sound rule for graphics over a voice: no sound on slides or exits, no whooshes; small clicks only (tick, counter, chime), about 20 dB under the voice. A standalone spec film is different: a sound on every visible move.
- 3D in Blender: about 20 minutes to render 10 seconds on the author's laptop.
- Motion Graphics MAX (paid, damianodesu.gumroad.com/l/max) adds 58 looks, 195 sounds, Blender workflow and a reviewer. Not required for anything here.
