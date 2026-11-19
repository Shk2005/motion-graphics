# Motion Graphics Skills

A shareable collection of AI agent skills for planning, coding, and rendering motion graphics and 4K product animations — no AI video generators required.

## Included Skills

| Skill | Folder | Best For |
|---|---|---|
| **`motion-graphics`** | [`skills/motion-graphics/`](skills/motion-graphics/) | HyperFrames motion graphics: kinetic text ads, product/app promos, graphics over talking-head footage, Reels safe-area exports, 15 prompt templates, 7 polish fixes, and 15 niche style blocks. |
| **`saas-animation`** | [`skills/saas-animation/`](skills/saas-animation/) | Storyboard-first, code-to-4K SaaS/product/brand animations (8–20 s): 3D UI camera moves, 2D puppet animation, photoreal Blender product shots, footage compositing, and sound design scripts. |

Ready-to-upload `.zip` bundles for Claude.ai are also pre-built in [`dist/`](dist/):
- `dist/motion-graphics.zip`
- `dist/saas-animation.zip`

---

## Quick Install

### Option 1: Claude Code (local rendering)

Clone the repo and copy the skill folders into `~/.claude/skills/`:

```bash
git clone https://github.com/Shk2005/motion-graphics.git
mkdir -p ~/.claude/skills
cp -R motion-graphics/skills/motion-graphics ~/.claude/skills/
cp -R motion-graphics/skills/saas-animation ~/.claude/skills/
```

Restart Claude Code so the new skills load.

### Option 2: Claude.ai (planning, storyboards & prompt assembly)

1. Open **Settings → Capabilities / Skills**.
2. Upload `dist/motion-graphics.zip` and/or `dist/saas-animation.zip`.
3. Toggle the skill(s) on.

> **Note:** Claude.ai chat can plan scripts, Style Cards, and prompts, while local video rendering runs in Claude Code (or another local coding agent).

### Option 3: Other Agent Harnesses (Codex, Antigravity, etc.)

Copy either folder from `skills/` into your agent's global or project skills directory (each skill follows the standard `SKILL.md` + `references/` layout).

---

## Local Prerequisites (for rendering)

- **Node.js 22+** and **FFmpeg** (required for both skills)
- **`whisper-cpp`** (optional — for word-timed graphics over talking-head footage in `motion-graphics`)
- **Python 3** (for audio mixing, compositing, and contact sheets in `saas-animation`)
- **Blender 4.2+** (optional — only needed for Level 3 photoreal 3D shots)

For `motion-graphics`, you can paste **Prompt 01 (Setup)** from [`skills/motion-graphics/references/02-prompt-library.md`](skills/motion-graphics/references/02-prompt-library.md) into Claude Code to install and verify HyperFrames automatically.

---

## Example Prompts

- **HyperFrames kinetic ad:** *"Use `motion-graphics`. Build a Style Card for a fintech app using Ledger Clean, then generate a 15-second Reels-safe text-led ad."*
- **Graphics over footage:** *"Use `motion-graphics` to transcribe `clip.mp4` and add animated counters and checklists synced to what I say."*
- **4K SaaS animation:** *"Use `saas-animation` to build a 12-second 4K product launch animation from the screenshots in this folder. Start with a numbered storyboard."*
