# Niche style system — distinct per client, consistent in quality

## The idea
The guide's 4 base styles (Kinetic Type, Liquid Glass, Editorial Grain, Pop Bold) are families. Every client gets its own variant built from 8 dials, so no two clients look alike, while every video still follows the same quality rules (readable, safe area, one idea per screen, human words, real assets).

## Style DNA — the 8 dials
1. Family — which base style it grows from (04–07).
2. Palette — always from the client's brand guide/site; one accent only.
3. Type pairing — one display font + one text font (free for commercial use, e.g. Google Fonts; save `.woff2` files in `fonts/`).
4. Surface — glass, solid card, paper, flat block, none (type only), photo frame.
5. Texture — clean, grain, paper, gloss, noise, none.
6. Motion personality — snappy, calm, bouncy, unhurried, precise.
7. Signature element — one device that belongs to this client only (e.g. swing tags, receipt strip, notification stack).
8. Sound palette — none, soft clicks, crisp ticks, playful pops, cinematic.

## Distance check (run before approving a Style Card)
Compare the new card with your other active clients' cards. It must differ on at least 3 of: family, type pairing, surface, texture, motion personality, signature element. Palette alone never counts as different. If it fails, change the signature element first, then the type pairing.

## Choosing a variant
- Start from the niche block below, then let the client's brand override palette and (if they have brand fonts) type.
- Match the audience's mindset: anxious buyers → calm motion; impulse categories → bouncy; considered/expensive purchases → unhurried, editorial.
- Hooks: Kinetic or Pop variants open strongest; Glass and Editorial variants should still put a readable line on screen within 1 second.
- Within one client, you can run 2 variants as a test (e.g. text-led Kinetic vs product-led Glass), but keep the client's palette, fonts and signature element constant so the brand stays recognisable.

## Style Card template (save as `STYLE_CARD.md` in the project folder)
```
Client / market:
Family:
Palette (hex, from brand source):
Display font / text font (files in fonts/):
Surface:
Texture:
Motion personality (eases, durations):
Signature element:
Moves to favour (from the 10 moves):
Sound palette:
Safe area: Reels (top 10%, bottom 20%, right 15% clear)
Distance check vs other clients: passed / failed — notes
STYLE block (paste-ready):
```

---
## Niche style blocks
Each block is paste-ready under prompts 08–11. Replace the palette with the client's brand colours. Default fonts are free Google Fonts; download the `.woff2` files into `fonts/` and update file names if different.

### 1. Beauty & skincare — "Dew Glass" (family: Liquid Glass)
STYLE: Dew Glass
- Milky glass cards: white at 70% opacity, 24px blur, 28px corners, a faint wet highlight that slides across each card once.
- Background: soft skin-tone gradient (#f6ede8 to #efe2dc) with one slow blurred blob in the brand accent.
- Fonts: DM Serif Display for headlines (sentence case), DM Sans for labels.
- Signature: small "ingredient label" tags (name + what it does, from approved claims only) that clip onto the card.
- Motion: calm, blur-in for headlines, rise for cards (power2.out, 0.7 s). No bounce.
- Sound: soft clicks only.
Claims note: no before/after or efficacy words unless cleared; watch for local therapeutic/cosmetic regulations.

### 2. Fashion & apparel — "Lookbook Cut" (family: Editorial Grain)
STYLE: Lookbook Cut
- Looks like a printed lookbook spread: off-white #f3f0ea, light grain at 6%, generous margins.
- Fonts: Bodoni Moda for big headlines (mix italic), Space Grotesk uppercase letter-spaced for labels.
- Colours: ink #141414 plus one seasonal accent from the brand.
- Signature: garment swing tags (string + tag) that swing in with the size, fabric or price.
- Product photos in thin-bordered frames, slightly rotated (1–2°).
- Motion: page-turn wipes on the beat, hard cuts between looks, tags swing and settle. No glass.
- Sound: soft paper snaps.

### 3. Fintech & personal finance — "Ledger Clean" (family: Liquid Glass → solid)
STYLE: Ledger Clean
- Solid white cards with a 1px grey border and 16px corners on a very light grey background #f4f5f7; no blur, no blobs.
- Fonts: IBM Plex Sans for words, IBM Plex Mono for every number.
- Colours: brand primary for headings, green only for positive values, never red for anything decorative.
- Signature: a receipt/statement strip that prints line by line.
- Motion: precise and steady: count-up, bar fill, slide-in; power2.inOut, 0.5 s. Nothing bounces.
- Sound: crisp ticks on each line.
Claims note: only cleared rates, fees and figures with the required disclosures for the market; no "guaranteed", no implied approval.

### 4. Digital wellbeing, habits & productivity apps — "Quiet Mode" (family: Liquid Glass, muted)
STYLE: Quiet Mode
- Lots of empty space; a dim, low-contrast background #eceae6 that slowly brightens through the video.
- Fonts: Newsreader for the key line, Instrument Sans for small text.
- Signature: a stack of phone notifications that piles up fast, then clears one by one into calm.
- Accent: one brand colour used only once per screen.
- Motion: busy and jittery in the problem moment, then slow and smooth after the product appears (typewriter → rise).
- Sound: rapid soft pings in the problem, silence after.

### 5. Food & beverage — "Snack Pop" (family: Pop Bold)
STYLE: Snack Pop
- Flat colour blocks taken from the packaging, 4px dark outlines, hard 6px offset shadows.
- Fonts: Baloo 2 ExtraBold for headlines, Nunito for small text.
- Signature: ingredient and flavour stickers that pop on and slightly wobble; one splash/drip shape drawn in CSS.
- Real product photo always the hero, never redrawn.
- Motion: bouncy pops (back.out(1.8)), squash on landing; stickers rotate slowly.
- Sound: playful pops.

### 6. Fitness & sport — "Rep Counter" (family: Kinetic Type)
STYLE: Rep Counter
- Dark background #0d0d0d, white condensed type, one high-energy accent from the brand.
- Fonts: Anton for huge words, Barlow Condensed for counters and labels.
- Signature: a rep or timer counter in the corner that ticks with the beat.
- Motion: punch-in on the effort word, diagonal slash wipes, fast cuts on the beat (power4.out, 0.25 s).
- Sound: punchy ticks, a single hit on the punch-in.
Claims note: no body or performance results without proof and permission.

### 7. Pets — "Scrapbook Paws" (family: Pop Bold, softened)
STYLE: Scrapbook Paws
- Warm cream background #fff6e9, rounded shapes, no black outlines.
- Fonts: Fredoka for headlines, Nunito for text.
- Signature: real pet photos as polaroids with tape corners; small hand-drawn doodle arrows and paw dots.
- Motion: gentle bounce (back.out(1.4)), polaroids drop in and settle with a tiny rotation.
- Sound: soft pops.

### 8. Home & interiors — "Catalogue" (family: Editorial Grain)
STYLE: Catalogue
- Warm linen background #eee7dc, faint grain at 5%, thin rules, page numbers.
- Fonts: Cormorant Garamond headlines, Manrope labels.
- Signature: material swatch chips (colour, fabric, wood) that slide in beside the product with their real names.
- Motion: unhurried slides and fades, slight parallax between photo and text.
- Sound: none or very soft.

### 9. B2B SaaS & software — "Product Precision" (family: Kinetic + real UI)
STYLE: Product Precision
- Real screenshots only (Fix 06). Camera moves close through the UI, following the cursor and numbers.
- Fonts: Inter Tight for words, JetBrains Mono for numbers and labels.
- Background: the brand's darkest colour; screenshots on soft-shadowed panels.
- Signature: a highlight box that draws around the exact part that matters, then a short line explains it.
- Motion: fast zooms and pans on a steady beat; big bold words between screens.
- Sound: crisp clicks on highlights.

### 10. Consumer tech & gadgets — "Dark Spec" (family: Kinetic Type, dark)
STYLE: Dark Spec
- Near-black background #0b0c0e, product lit from one side (real photo), subtle vignette.
- Fonts: Space Grotesk headlines, JetBrains Mono for specs.
- Signature: thin callout lines that draw from a product part to a short spec label (cleared specs only).
- Motion: blur-in reveals, slow push on the product, callouts draw on beat.
- Sound: tight digital ticks.

### 11. Jewellery & luxury — "Noir Serif" (family: Editorial, no grain)
STYLE: Noir Serif
- Black #0a0a0a, one metal-tone accent from the brand, lots of space.
- Fonts: Playfair Display headlines (italic for one word), Inter small caps for labels.
- Signature: a slow light sweep across the product and across the key word.
- Motion: very slow blur-in and fades (1.0–1.2 s), nothing bounces, no stickers.
- Sound: none, or one soft chime at the end.

### 12. Health & supplements — "Evidence Card" (family: Liquid Glass → solid)
STYLE: Evidence Card
- Clean white solid cards on pale mint or brand tint; no glass.
- Fonts: Source Serif 4 headlines, Source Sans 3 text.
- Signature: small footnote markers (¹ ²) on cleared claims that link to a source line on the end card.
- Motion: calm checklist ticks and rises.
- Sound: soft ticks.
Claims note: highest-risk niche; only cleared wording; no disease or cure claims; check local health/advertising regulations.

### 13. Education, courses & coaching — "Notebook" (family: Editorial, light)
STYLE: Notebook
- Grid-paper background #fbfaf6 with faint blue grid lines.
- Fonts: Inter for main text, Caveat for one hand-written annotation per screen.
- Signature: underlines and circles that draw themselves around the key word.
- Motion: typewriter for questions, checklist ticks for steps, draw-on annotations.
- Sound: pencil-like soft ticks.
Claims note: no income or outcome promises without proof.

### 14. Travel & hospitality — "Postcard" (family: Editorial + Pop accents)
STYLE: Postcard
- Real location photos framed as postcards with a white border and a stamp.
- Fonts: Fraunces headlines, Work Sans labels.
- Signature: a dotted route line that draws between places; small passport-style stamps pop on.
- Motion: gentle slides, route draws, stamps pop with a small overshoot.
- Sound: soft stamp thuds.

### 15. Local services (cleaning, trades, clinics) — "Job Card" (family: Kinetic + solid cards)
STYLE: Job Card
- Bold solid cards in the brand colour, white text, strong contrast for small screens.
- Fonts: Archivo ExtraBold headlines, Archivo regular text.
- Signature: a before/after slider on real job photos (real, permissioned, unedited results only), plus a checklist of what's included.
- Motion: snappy slide-ins, bar fill for "booked in X steps", punch-in on the offer.
- Sound: crisp ticks.

---
## Keep variety alive across months
- Keep a simple "Style Register" (doc or spreadsheet): client, family, signature element, type pairing. Check it before every new Style Card.
- Refresh a client's style when performance data shows creative fatigue, changing one dial at a time.
