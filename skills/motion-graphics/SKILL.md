---
name: motion-graphics
description: Plan and build motion graphics with HyperFrames — kinetic text ads, product and app promos, graphics over talking-head or real footage, sound effects, transparent overlays, Reels-safe exports, and polish fixes. Use whenever the user asks for motion graphics, animated text, cards, counters, overlays, a promo, a spec ad, a HyperFrames render, or wants an edit to look more polished or less like a template — and to pick a distinct visual style for each brand or niche.
---
# Motion Graphics (HyperFrames)

HyperFrames (open source, by HeyGen) turns a small web page into a video: `index.html` (what is on screen) + a timeline (what moves, when) + a render (headless Chrome captures every frame, FFmpeg joins them). Because the video is text, changes are made by talking: "slower", "move it up", "make the number bigger".

## Where each part runs
- **Claude Code (or a local coding agent) on your computer** renders. It needs Node 22+, FFmpeg, `whisper-cpp`, and the HyperFrames skills (Prompt 01). Chat-only interfaces cannot render HyperFrames videos.
- **Chat (optional, for planning)** handles the approved script, Style Card, claims check, and final prompt assembly. Then paste the final prompt into your local coding agent.

## Production & brand safety rules
1. **Truth.** Never let a prompt invent numbers, results, reviews, UI, or features. Supply real figures in `FACTS.md` with sources, or use visible placeholders like `[NUMBER]` and stop. Use real screenshots as they are — no made-up dashboards.
2. **Human voice.** Keep on-screen words and voiceover natural and faithful to the approved script word for word. Don't let the model rewrite or bloat approved copy.
3. **Claims.** Every on-screen number, comparison, result, or offer must be verified before rendering. Re-check claims if any words change during polish.
4. **People.** Practice clips with AI-generated people are for testing only — never use them in client or public work, and never present an AI person as a real customer.
5. **Brand IP.** Only use a client's logo, mascot, product, and screens with permission. Spec ads for brands you don't work with are portfolio experiments only and should be labelled `"Spec ad · not affiliated with [BRAND]"`.
6. **Approval gates.** Never "make every call yourself" on client work. Stop for approval of the Style Card, then of a still frame, before the full render.
7. **Licences.** Fonts must be free for commercial use (Google Fonts are). Music and sound effects must be client-owned, code-synthesized, or verified CC0. Record the source of every audio file.
8. **Distinct per client.** Every client gets its own Style Card; no two clients share the same style (see `references/03-niche-style-system.md`).

## Workflow
1. **Plan:** Pick the use case (`references/02-prompt-library.md`) and build the brand's Style Card (`references/03-niche-style-system.md`). Run the distance check against your other active clients' cards.
2. **Assemble prompt:** Combine use-case prompt + `STYLE` block + safe-area rule + `FACTS.md`. Verify all copy and claims.
3. **Prepare folder (local):** Create a new folder per video and copy in `fonts/`, `sfx/`, footage/screenshots, and `FACTS.md`. Paste the final prompt and ask for one still frame first.
4. **Render & polish (local):** Approve the still, render, then adjust one change at a time (knobs, moves, fixes). End iterations with `"keep everything else the same"`.
5. **Finish (local):** Add sound (Prompt 13), verify the Reels safe-area proof frame (Fix 07), and export at target resolution/FPS.
6. **Final check:** Review the output against the script and claims, and log style, prompt, version, files, and audio sources.

## References
- `references/01-setup-and-basics.md` — setup, first render, knobs, the 10 moves, export commands, fix-it list, gotchas.
- `references/02-prompt-library.md` — 15 tested prompts plus production/client-ready versions and 7 polish fixes.
- `references/03-niche-style-system.md` — Style DNA (8 dials), distance check, Style Card template, and 15 niche style blocks.
