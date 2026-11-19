# Prompt library
Original prompts from the guide are marked ORIGINAL (copy them from the kit's `prompts.md` when you have it, to keep line breaks clean). Client-ready versions add the guardrails production work needs. Replace `[BRACKETS]`.

Assembly for any video: `USE-CASE PROMPT` + `STYLE` block (file 03) + `SAFE AREA` line + `"Use only the facts in FACTS.md; if a number is missing, use [NUMBER] and tell me."`

---
## 01 Setup (ORIGINAL — once per computer, in Claude Code)
Set up this computer so I can make videos with HyperFrames. First work out if I'm on a Mac or on Windows, then:

1. Check I have Node.js 22 or newer. If not, install it (Homebrew on Mac, winget on Windows).
2. Check I have FFmpeg. If not, install it the same way.
3. Check I have whisper-cpp, which turns speech into timed text. If not, install it (Homebrew on Mac; on Windows use the latest release from github.com/ggml-org/whisper.cpp and add it to PATH).
4. Install the HyperFrames skills for Claude Code with `npx hyperframes skills`.
5. Run `npx hyperframes doctor` and read the result.

Ignore anything doctor calls optional (Docker, Kokoro, MusicGen). If something needs my password or admin rights, stop and give me the exact command to run myself.

When you're done, tell me in plain words: what was already there, what you installed, and anything I still need to do.

→ Then close Claude Code and open it again.

## 02 First render (ORIGINAL — practice, ~2 minutes)
Make me a 6-second video with HyperFrames in this folder, 1920x1080 at 30 fps.

One white frosted-glass card in the middle of a soft purple-to-blue gradient background. On the card: a small grey label that says MY FIRST RENDER, a big number that counts up from 0 to 100, and a green pill that says Made with Claude Code.

The card rises in at the start. The number counts up over 2 seconds. The green pill pops in at 4 seconds.

Use the Inter font. Render it to renders/first.mp4 and tell me where the file is.

## 03 All 10 moves demo
Text is in the kit's `prompts.md` only (not printed in the PDF). Makes a 14-second demo of every move.

---
## 04–07 Base styles (ORIGINAL — paste under prompts 08 to 11)

### 04 Kinetic Type — hooks, short punchy scripts
STYLE: Kinetic Type
- The text is the whole video. No cards, no boxes.
- Font: Archivo Black (fonts/ArchivoBlack-400.woff2), all caps, huge. The main word fills most of the width.
- Colours: black background, white text, one accent colour #c6ff3d for the most important word on each screen.
- Motion: words slam in one by one, fast and snappy (power4.out, 0.25 to 0.4 seconds). Mix the moves: slide in from the side, stretch from squashed to full height, split the letters apart and back together. Each screen exits fast before the next one hits.
- Cut the screens on the rhythm of the words, like a beat.

### 05 Liquid Glass — calm, premium, Apple-like
STYLE: Liquid Glass
- Frosted glass cards: white at about 80% opacity, 30px background blur, thin white border, big rounded corners (32px), soft shadow.
- Background: soft light gradient with two or three blurred colour blobs (pale blue, lilac, peach) drifting slowly.
- Font: Inter (fonts/Inter-700.woff2 for headings, fonts/Inter-400.woff2 for small text). Dark grey text #1d1d1f, small uppercase grey labels above headings.
- Accent: green #34c759, only for ticks and checks.
- Motion: calm and smooth. Cards rise 30px and fade in with power3.out over 0.6 seconds, scaling up slightly from 0.96. Text arrives piece by piece. Nothing bounces.

### 06 Editorial Grain — stories, opinions, anti-glossy (big files: use --crf 23)
STYLE: Editorial Grain
- It should look like a printed magazine page, not a screen.
- Background: warm paper colour #efe8dc with visible film grain over everything (an animated SVG noise layer at about 12% opacity).
- Font: Instrument Serif (fonts/InstrumentSerif-400.woff2 and fonts/InstrumentSerif-400-italic.woff2) for headlines, large, mixing upright and italic words. Small labels in Inter (fonts/Inter-400.woff2), uppercase, letter-spaced.
- Colours: ink black #1a1a1a and one deep red accent #c2412d.
- Shapes: cut-out paper rectangles behind key words, slightly rotated (1 to 3 degrees), thin rules, and small page numbers in the corners.
- Motion: unhurried and a bit imperfect. Staggered timings that are not perfectly even, gentle slides and wipes, no bounces.

### 07 Pop Bold — stop the scroll, loud, playful
STYLE: Pop Bold
- Loud, playful, flat colour. No gradients, no glass.
- Font: Bricolage Grotesque ExtraBold (fonts/BricolageGrotesque-800.woff2), big and chunky.
- Colours: flat blocks of #c6ff3d (lime), #8a3cff (purple), #ff4fd8 (pink) and #111111, with 4px black outlines and hard 8px offset shadows with no blur.
- Extras: rotating star and circle stickers, little arrows, a few simple shapes drawn in CSS.
- Motion: bouncy and springy. Things pop in with back.out(2.5), overshoot, wobble a little, squash and stretch. Stickers spin slowly the whole time.

---
## 08 Text-only video (ORIGINAL)
Make a 15-second vertical video (1080x1920, 30 fps) with HyperFrames in this folder, made only of animated text. No footage.

Script:
Most product videos lose people in 2 seconds. Here's how to keep them. Show the result first. Cut every pause. One idea on screen at a time. Then tell them what to do next.

Use my exact words. Don't rewrite or shorten the script. Show one sentence per screen, big enough to read on a phone. If a sentence is long, wrap it over two or three lines on the same screen. Each screen stays up long enough to read. Keep all text inside the middle 80% of the width so phones don't crop it. If there is a STYLE section below, follow it. If not, use clean white frosted cards on a soft light gradient, with the Inter font.

Render to renders/text.mp4.

### 08 Client-ready version — text-led ad
Make a [15]-second vertical ad (1080x1920, 30 fps) with HyperFrames in this folder for [CLIENT], made only of animated text[, plus the product image product.png if present]. No other footage.

Script (approved copy — use these exact words, don't rewrite or shorten):
[SCRIPT]

Show one line per screen, big enough to read on a phone; wrap long lines over two or three lines. Each screen stays up long enough to read aloud once. The first screen must land within the first second. The last screen is the CTA: [CTA]. Keep all text and key visuals inside the Reels safe area: nothing in the top 10%, the bottom 20% or the right 15%. Follow the STYLE section below.

Before rendering, show me one still frame of the first screen and the CTA screen and wait for my OK. Then render to renders/[client]-text-v1.mp4.

STYLE: [paste the client's Style Card block]

---
## 09 Product launch video (ORIGINAL)
Make a 12-second product launch video with HyperFrames in this folder, 1920x1080 at 30 fps.

The product is Tally, an app that shows what your online shop really earns after fees. If there is a product.png in this folder, use it as the hero image. If not, build the product in HTML and CSS (an app screen, a logo, or a phone with the app on it).

Structure:
1. 0 to 2 seconds: the logo or product name is revealed.
2. 2 to 9 seconds: three feature moments, one at a time. Each one shows the product doing the thing, not just a sentence. Features: connects to your store in one click / shows profit after fees, ads and refunds / sends you one number every morning.
3. 9 to 12 seconds: end card with the product name, one short line and a call to action: Join the waitlist.

If there is a STYLE section below, follow it. If not, use clean white frosted cards on a soft light gradient.

Render to renders/product.mp4.
(Author's note: give it your real numbers or it will invent example ones.)

### 09 Client-ready version — product feature video
Make a [12]-second product video for [CLIENT] with HyperFrames in this folder, [1080x1920 / 1920x1080] at 30 fps.

The product is [PRODUCT — one-line description from the brand brief]. Use the real product photos in product/ and the real logo in logo/. Never redraw, reshape or recolour the product or logo. If an asset is missing, stop and tell me.

Structure:
1. 0 to 1.5 seconds: the hook line [HOOK] with the product visible.
2. 1.5 to [9] seconds: three feature moments, one at a time, each showing the product doing the thing: [FEATURE 1] / [FEATURE 2] / [FEATURE 3].
3. Last 3 seconds: end card with logo, one short line [LINE] and CTA: [CTA].

Use only facts and numbers in FACTS.md. Never invent numbers, ratings or results; if one is missing, show [NUMBER] and tell me. Keep everything inside the Reels safe area if vertical. Follow the STYLE section below. Show me a still of each section first, then render to renders/[client]-product-v1.mp4.

---
## 10 SaaS promo (ORIGINAL)
You're an amazing motion graphics designer. Make a 1-minute promo video for my SaaS with HyperFrames, in this folder, 1920x1080 at 30 fps.

The product is Tally, an app that shows online shops what they really earn after fees, ads and refunds. The screenshots folder has real screens from the app.

1. Look at every screenshot first and work out what each one shows.
2. Build the video around them. Open with a short hook, then show each screen and zoom into the part that matters (the number, the chart, the button) with a short line of text that says what it does for the customer.
3. Use the screenshots as they are. Don't redraw them.
4. Kinetic style: fast zooms and pans into the screenshots, big bold words between the screens, cuts on a steady beat.
5. End on the logo, one short line and a call to action: Start your free trial.

Render to renders/promo.mp4.

### 10 Client-ready version — app/SaaS promo
Same as 10, with: product = [APP — one line]; `screenshots/` contains approved real screens with no customer personal data visible (blur any); the lines of text come from the approved script `[SCRIPT]`; length `[30 or 60]` seconds; vertical `1080x1920` for Reels with the safe area rule; end CTA `[CTA]`; show me stills of the hook and end card before rendering.

---
## 11 Graphics on your own video (ORIGINAL)
You're a top motion graphics designer. Add motion graphics to my video clip.mp4 with HyperFrames, in this folder.

1. Really analyse the video first. Transcribe it with npx hyperframes transcribe, check the word timings against the audio, and work out what the video is about and which moments matter most. If whisper isn't installed, stop and tell me to run the setup prompt.
2. Keep my video exactly as it is: same size, frame rate, audio and cut. You only add graphics on top.
3. At each important moment, add an animation made for what I'm saying right then: a number becomes a counter, a list becomes a checklist, a before and after becomes a comparison. Each one starts on the exact word.
4. Keep one style across the whole video, so it looks designed, not random.
5. Nothing in the first 3 seconds. That's the hook.
6. Keep graphics off my face, out of the bottom third where captions go, and away from the left and right 10% of the frame.

If there is a STYLE section below, follow it. If not, use clean white frosted cards.

Render to renders/with-cards.mp4.

### 11 Client-ready version — polish existing footage
Same as 11, with: the video is `[FILE — real creator/founder/product footage, with permission]`; only add graphics for verified claims and facts in `FACTS.md`; never add a graphic that implies a result the speaker didn't say; [keep "nothing in the first 3 seconds" for talking-head hooks / or: add the approved hook text `[HOOK]` in the first second if the script calls for it]; respect the Reels safe area; render to `renders/[client]-polish-v1.mp4`.

## 12 Fix one spot (ORIGINAL — after a base you like)
Now one spot. When I say Sales went from 40 a week to over 90, show the 5 screenshots in the screenshots folder popping up one after another, in order. Cut them in a way that matches the video and keep them in sync with my voice. Keep everything else exactly the same and render again to renders/with-cards.mp4.

Pattern: `"Now one spot. When I say [WORDS], show [REAL ASSET] [MOVE]. Keep everything else exactly the same and render again to [FILE]."`

## 13 Sound effects (ORIGINAL — copy sfx/ into the project first)
Add sound effects to this video using the files in the sfx folder. A tick when each list item or check appears, the counter sound while a number rolls, and the chime on the last card. No sound when a card slides in or leaves, and no whooshes. Keep the effects quiet under my voice. Render again to renders/with-cards.mp4.
(On the practice clip: ticks at 4.5 s, 7.0 s, 10.3 s; counter at 16.8 s; chime at 17.2 s; about 20 dB under the voice.)

## 14 Transparent export (ORIGINAL — for Premiere / After Effects / CapCut overlays)
Remove the background so only the card is visible, with everything around it transparent. Then export a transparent version I can put over my own footage in Premiere or After Effects: renders/card.mov (ProRes 4444 with alpha) and a PNG sequence in renders/card-png.
(Use solid cards — frosted cards lose their blur with nothing behind them.)

---
## 15 Spec ad, any brand (ORIGINAL — 23-second film, 16:9 + 9:16)
Make a 23-second spec ad for [BRAND] with HyperFrames. Don't stop to ask me anything: make every call yourself and show me the finished 16:9 and 9:16 videos.

THE STAR: [ICON], the brand's most famous real thing (a mascot, an icon, a screen everyone knows). Take it, and the brand's other characters if it has any, from the brand's real files (site, press kit, app). Never draw your own version.

MATCH ITS MEDIUM, so it never looks pasted in. Pixel art: a pixel or voxel world. A flat drawn mascot: a flat drawn world with parallax layers, no 3D camera. A real 3D object: Three.js, lit, soft shadows. Never move a flat cut-out through a 3D world.

IT ACTS, NEVER SLIDES: collect its official poses and animations (Lottie, Rive, GIF, stickers). Cut between real poses on the beat, squash and stretch between them. A walk is real steps, not a glide. Use the pose that fits each moment; if none fits, frame around the nearest real one, never fake it.

FACTS FIRST: use only 6 true details about [ICON] from official sources, listed in FACTS.md.

THE FILM, one continuous shot, no cuts:
- 0–1 s: the real screen everyone knows, pixel-perfect. Then a tap.
- 1–2 s: [ICON] pops off the screen as it breaks apart, and does its signature move with a camera shake.
- 2–9 s: it travels through a world built from the brand's own pieces (buttons, icons, colours), never plain boxes. Something new every second, each a real feature: a counter ticking up, a +points pop, a jump, a duck.
- 9 s: the turn, on the music drop: a mode the brand really has (dark mode, night, a new level), and the signature move, bigger.
- 10–16 s: three places people use [BRAND] (a train, a plane, a café), each revealed by a sweep with a STAGE 2 / 3 / 4 card. Each a full scene as detailed as the brand's own art: three layers of depth, real props, the brand's other characters, something moving (passing scenery, clouds, steam). [ICON] arrives with a real move and sits down: on the seat, by the window, at the table. Each place shows one real feature on a phone or screen.
- 16–19 s: pull back as the world becomes the official logo. Then the line: [TAGLINE, or write one].
- 19–20 s: old-TV power-off.
- 20–23 s: the opening screen again, same layout and font, with "Comment [KEYWORD]" as the biggest words on it and two lines under it saying what they get.
No name card, no watermark. Small at the end: "Spec ad · not affiliated with [BRAND]".

NOTHING PASSES THROUGH ANYTHING, NOTHING FLOATS: the star goes over, under or around every object. When it sits or stands on something, it touches the surface on the exact frame, with a contact shadow there. What's behind it stays behind (a seat back), what's in front stays in front (an armrest, a table edge). No sitting pose? Hide its legs behind the seat front or table edge; it never stands on a seat.

VOICE: 4 short lines, [TONE, e.g. hushed and cinematic, then it explodes on the turn]. Leave gaps for the big sounds. ElevenLabs if ELEVENLABS_API_KEY is set (max 1,500 credits), otherwise `npx hyperframes tts`.

MUSIC: one track that builds, its drop exactly on the turn, ducked under the voice: [MY TRACK] or a CC0 track from Openverse (api.openverse.org, free).

TEXT: 6 to 8 blocks of the voice's own words, in the brand's style, beside the star, never on it, each entering and leaving a different way. Every block stays whole and readable for 0.7 s or more: no half-typed words, no scattered letters.

SOUND: a real recorded CC0 sound (Openverse, kenney.nl) on every visible move: text, pops, landings, footsteps, each peaking on its exact frame. The signature moves get the biggest, in the gaps.

MIX: every voice line at least 12 LU over the music and effects together, measured on the render. Master at -14 LUFS, true peak under -1 dB.

CHECK before you render: a frame every 0.25 s through every move, plus a side view in 3D (`npx hyperframes snapshot --angle side`), then every place full-size, like a poster. Fix any touch or pass-through, any float or gap, any slide, any see-through body part, any plain shape or empty set, any cut or covered word, and any frame the brand wouldn't post as its own ad.

9:16: same files with a switch, not a crop. Re-frame every shot closer so the action fills the tall screen: keep every character from the 16:9 shot, and no empty band of floor or sky over a fifth of it. Every word 170–1330 px from the top, the right edge clear for Instagram's buttons.

### 15 Client-ready version — hero brand film (with client permission and assets)
Use Prompt 15 with these changes:
- Replace `"Don't stop to ask me anything: make every call yourself"` with: `"Before building, show me a one-page plan (star, world, three places, voice lines, music, sound list) and wait for my OK. Then show stills of 0 s, 9 s and the end card and wait again."`
- Assets come only from the client's files in `brand/` (logo, mascot, product, app screens), supplied by the client.
- Voice lines and text blocks come from the approved script and verified claims.
- Remove `"Spec ad · not affiliated"` for real clients; keep it for portfolio spec work.
- Music and sound: client-owned or verified CC0 only; list every audio file and its licence in `AUDIO_SOURCES.md`.
- Voiceover: HyperFrames' free TTS or an approved voice provider only; no voice cloning of a real person without written consent.

---
## Polish fixes — "7 fixes for videos that look cheap" (author's own films, not part of the 15 tested prompts)
01 Cards look flat → Make the cards clear liquid glass, no blur: you see straight through them, and whatever is underneath bends at the edges like real glass. Use an SVG displacement filter (feTurbulence into feDisplacementMap) as the backdrop-filter, with saturate(180%), a 5% white tint and a 1px highlight on the top edge. Put busy detail underneath (text, a grid, a chart) and slide the glass over it so the bending moves. Never put filter, opacity or clip-path on the card's parent.

02 Talking head looks flat → Make my talking head 3D. Cut me out with a clean matte. Put UI cards at three depths: far behind me (small and blurred), beside me (sharp) and close to the lens (big and blurred), each tilted in 3D, and let them morph from one shape into the next. Make every card clear liquid glass, no blur, so the city behind bends through it, with a thin light reflection along the edge and a soft shadow. Keep my face natural: no colour on it, no glow around me.

03 3D looks like a toy → Don't fake the 3D in the browser. Build it in Blender: real model, matte materials, one soft key light, a rim light and a real shadow on the floor. Show me a grey clay preview first. Only after I say OK, render the frames and bring them into the video.
Blender setup (free, once): install Blender 4.2+ from blender.org; ask Claude Code to install `uv`, then run `claude mcp add --scope user blender uvx blender-mcp`; download `addon.py` from github.com/ahujasid/blender-mcp and in Blender: Edit → Preferences → Add-ons → Install from Disk → turn on "Blender MCP"; in Blender press `N` → BlenderMCP → Connect; start a new Claude Code session and paste the fix.

04 Effects look like a template → The effect looks like a template. Before you build it, find a real reference for it (real footage or a real VFX shot) and copy how it moves, not only how it looks. Give every repeat its own shape, size and speed, keep the edges a little rough instead of perfect, and give everything weight: it reacts, overshoots, then settles. No straight lines, no identical copies, nothing flying straight at the camera.

05 Numbers are boring → My numbers just sit on the screen. Turn each key number into a soft 3D object with a personality: a glossy coin with the number on it, eyes, a little reaction. When the number drops, something takes a bite out of it or it melts, and the new number lands with a bounce. (Only real, verified numbers.)

06 UI looks fake → Rebuild my real app screens from these screenshots: the same layout, the same labels, crisp and readable. No made-up dashboard. Then move the camera through them up close, following the cursor and the numbers, instead of showing the whole screen flat.

07 Instagram covers your text → This is for Instagram Reels (1080×1920). Keep all text and key visuals inside the safe area: nothing in the top 10%, the bottom 20% (caption and username) or the right 15% (like, comment and share buttons). Then render one frame with the Reels buttons drawn on top to prove nothing important is covered.
(Run Fix 07 before posting any Reel.)
