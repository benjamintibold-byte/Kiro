# 02 — VISUAL SYSTEM (KAIRO)

Lock these on day 2. Never change them. Visual continuity over time is the single biggest reason competitors can't catch up.

---

## 1. Color palette — DARK MODE STORE

The store is **dark.** Not cream-and-black like a luxury magazine — actual deep black like a vault interior. This is deliberate: watches photograph better on dark backgrounds, perceived value jumps 30–40% on dark stores, and it separates Kairo from 90% of Shopify stores instantly.

### The palette (only these, no exceptions)

| Name | Hex | Use |
|---|---|---|
| **Vault black** | `#0C0B0A` | Store background, primary surfaces |
| **Charcoal** | `#1A1816` | Card backgrounds, secondary surfaces |
| **Smoke** | `#2A2725` | Borders, dividers, subtle hover states |
| **Stone** | `#8A8279` | Secondary text, metadata, captions |
| **Bone** | `#D4CFC6` | Primary text, headings |
| **Parchment** | `#E8E2D5` | Dossier cards (print only), highlights |
| **Accent** | `#7A2A20` | Wax seals, single dot indicators, lot markers |

### Why dark and not cream

- **Watches pop.** Steel catches light on dark backgrounds. Dials become the brightest element in frame.
- **Perceived value.** Dark stores signal "gallery" not "shop." The buyer's brain associates black space with curated, expensive, exclusive.
- **Mobile experience.** 80%+ of traffic is mobile at night or in dim rooms. Dark backgrounds reduce eye strain → longer session time → more purchases.
- **Consistency with TikTok.** Your content is shot on dark surfaces with hard light — the store should feel like a continuation of the video, not a context switch.
- **Separates from competitors.** Most dropshipping stores use white/cream. Dark is immediately distinctive.

### Application rules

- **Store background:** always `#0C0B0A` (vault black). Never white.
- **Product images:** shot on dark walnut, charcoal concrete, or black linen. The images live inside the dark store seamlessly.
- **Text on dark:** primary text is `#D4CFC6` (bone). Secondary text is `#8A8279` (stone). Never pure white `#FFFFFF` — it's too harsh.
- **Accent use:** oxidized red `#7A2A20` used ONLY for: wax seal icons, active lot indicators, the single hover-state on the "acquire" button. Nowhere else. One accent touch per screen maximum.
- **Cards/containers:** `#1A1816` (charcoal) with `#2A2725` (smoke) borders. Barely visible separation — the darkness is the design.

### The contrast rule

Every text element must pass WCAG AA contrast against its background:
- Bone `#D4CFC6` on Vault `#0C0B0A` = ratio 12.5:1 ✓
- Stone `#8A8279` on Vault `#0C0B0A` = ratio 5.8:1 ✓
- Stone `#8A8279` on Charcoal `#1A1816` = ratio 4.7:1 ✓ (AA for large text)

---

## 2. Typography

### Two fonts only

**Serif:** Cormorant Garamond — weight 400 (regular) and 500 (medium). Body copy, mythology, headings, product titles.

**Monospace:** JetBrains Mono — weight 400. Metadata, lot numbers, dates, captions, prices.

### Type rules

- No sans-serif anywhere. Ever.
- No bold (`weight 700+`). Use italic for emphasis.
- No all-caps in body copy. All-caps ONLY for metadata labels (`ORIGIN`, `LOT`, `MOVEMENT`).
- Letter-spacing on metadata: `+0.08em` (slightly wider on dark backgrounds for readability).
- Line-height: `1.6` for body, `1.3` for metadata blocks.

### Font sizes (locked scale)

| Element | Size | Font | Color |
|---|---|---|---|
| Hero text | 24px / 1.5rem | Serif 500 | Bone |
| Body | 15px / 0.94rem | Serif 400 | Bone |
| Metadata labels | 10px / 0.625rem | Mono 400, caps | Stone |
| Metadata values | 11px / 0.7rem | Mono 400 | Bone |
| Caption / footnote | 10px | Mono 400 | Stone |
| Lot number (product page) | 13px | Mono 400 | Stone |
| Price | 16px | Mono 400 | Bone |
| Button text | 11px | Mono 400, lowercase | Bone on vault |

---

## 3. Photography rules (optimized for dark store)

### The grammar

Every photograph follows this grammar. If a shot doesn't conform, don't post it.

1. **Single object.** No clutter. One hero subject, max one supporting prop.
2. **Off-center.** Subject placed on the left third or right third. Never centered.
3. **Hard natural light from one side.** Window light, late afternoon. Strong shadows. No softboxes. No ring lights.
4. **Dark surfaces.**
   - Dark walnut wood
   - Charcoal concrete (or dark concrete-look textured paper)
   - Black linen or canvas
   - Aged dark leather
   - Matte black steel
5. **Slightly underexposed.** Pull exposure down by 1/2 to 2/3 stop. Let the watch be the brightest thing in the frame.
6. **One "evidence" element in frame:**
   - Numbered tag (hand-stamped, cream on dark)
   - Faint pencil notation on dark paper
   - Wax seal fragment (red on black)
   - Single brass element (pen, key, clip)
7. **The watch catches light.** The dial or case should have one clear specular highlight. This is what stops the scroll on TikTok.

### Forbidden in photographs

- White backgrounds
- Wrist shots
- Any human, hand, or body part (except extreme macro of a finger winding a crown)
- Lifestyle scenes (coffee + watch, laptop + watch)
- Multiple watches in one frame
- Seamless backdrops
- Light tents or product photography boxes
- Bright, evenly-lit environments

### Product page images (5 per SKU)

1. **Hero shot** — full watch, angled 15°, on dark walnut. Light from upper-left.
2. **Dial macro** — fills 80% of frame. Extreme detail.
3. **Profile shot** — side view showing case thickness, crown.
4. **Caseback** — if skeleton or engraved.
5. **Environment shot** — watch on dark surface with one evidence prop.

All shot square (1:1) for Shopify grid consistency.

---

## 4. The LUT (color grade) — DARK VERSION

Apply this LUT to every photograph and every video. One LUT. One look.

### LUT spec (DaVinci Resolve or Lightroom)

```
EXPOSURE        -0.5             # darker than before — watches are the light source
CONTRAST        +15
HIGHLIGHTS      -15
SHADOWS         +10              # still lift blacks slightly for depth
WHITES          -20
BLACKS          +8               # lifted just enough to avoid crushed detail
TEMPERATURE     -200K            # cooler, but less extreme than cream version
TINT            +3               # very slight warmth to avoid clinical feel

HSL:
  Reds          sat -5, lum -5
  Oranges       sat -15, lum +5   # preserve warm metal tones
  Yellows       sat -25, lum +5   # preserve brass/gold glints
  Greens        sat -50, lum -15  # kill any green cast
  Aquas         sat -60, lum -10
  Blues          sat -35, lum -10
  Purples       sat -60
  Magentas      sat -60

GRAIN           amount 20, size 25, roughness 45
VIGNETTE        -20 amount, midpoint 40, feather 50
```

### The dark-store LUT difference

- Shadows are **barely** lifted (not as much as the cream-store version)
- Highlights are pulled harder — the brightest thing is the watch crystal catching light
- Warm metal tones (oranges/yellows) are preserved — steel and brass must glow
- Everything else is desaturated harder — the background disappears into darkness

**Test for consistency:** lay 9 of your photos in a 3×3 grid on a black background. They should look like objects floating in the same vault.

---

## 5. Audio identity

### The voice (lock day 3)

ElevenLabs voice — design or clone. Spec:
- Low male
- Perceived age 30–40
- Ambiguous European accent (avoid clearly British, French, German)
- Slow cadence, ~140 wpm
- Flat affect, no smile in voice
- Slight tape hiss/warmth in post

**Use this voice for 12+ months.** It becomes Kairo's signature.

### Sound design library

Build once, reuse forever. 50 clips total:

1. **Mechanical** — winding, ticking, rotor spin, crown click
2. **Paper** — rustle, fold, tear, page turn, envelope open
3. **Surface** — placing object on wood/concrete, scrape, slide
4. **Ambient** — distant hum, room tone, faint static, vinyl crackle
5. **Punctuation** — single tick, single click, soft thump

### The mix recipe (every video)

```
Voiceover                  -3 dB    main
Tactile sound (1 hit)      -8 dB    on action moment
Ambient bed                -24 dB   under everything (darker, quieter)
Vinyl crackle              -30 dB   subtle, constant
```

No music. Ever.

---

## 6. Motion design

### Video editing rules

- **Cuts:** straight cuts only. No fades except slow fade-to-black at end.
- **Speed:** macros at 50% speed. Reveals at 100%. Never speed-ramp.
- **Text on screen:** monospace only. On dark videos: `#D4CFC6` text, no background bar needed.
- **Text duration:** 1.5–2 seconds per line.
- **Text position:** lower-left third, monospace 11px equivalent.

### On-screen text format

```
LOT 0049 / GENEVA / 1991
```

Always `LOT [number] / [city] / [year]`. Slashes, not dashes. Monospace. Bone-colored on dark.

---

## 7. Store-specific dark design details

### The "acquire" button

```css
.btn-acquire {
  background: transparent;
  color: #D4CFC6;
  border: 1px solid #2A2725;
  padding: 1rem 3rem;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.15em;
  text-transform: lowercase;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-acquire:hover {
  background: #7A2A20;
  border-color: #7A2A20;
  color: #E8E2D5;
}
```

The button is nearly invisible until hovered — then the oxidized red appears. Subtle. Powerful.

### Scrollbar

```css
::-webkit-scrollbar {
  width: 4px;
}
::-webkit-scrollbar-track {
  background: #0C0B0A;
}
::-webkit-scrollbar-thumb {
  background: #2A2725;
}
```

### Selection highlight

```css
::selection {
  background: #7A2A20;
  color: #E8E2D5;
}
```

### Links

```css
a {
  color: #8A8279;
  text-decoration: none;
  border-bottom: 1px solid #2A2725;
  transition: color 0.2s ease;
}
a:hover {
  color: #D4CFC6;
}
```

---

## 8. Print materials (packaging)

Packaging uses the **inverse** palette — cream/parchment paper with dark text. This creates a deliberate contrast:

- **Screen world:** dark vault, bone text, objects floating in darkness
- **Physical world:** cream dossier cards, dark serif text, wax seals

The contrast between screen and physical is intentional — it makes the unboxing feel like pulling a document out of an archive. The physical materials are the "old world." The store is the "vault."

| Print item | Background | Text | Accent |
|---|---|---|---|
| Dossier card | `#E8E2D5` parchment stock | `#0C0B0A` dark | `#7A2A20` stamp |
| Handwritten note | Cream paper, torn edges | Dark ink | — |
| Polaroid | Matte, aged warm | — | — |
| Ledger invitation | `#0C0B0A` black matte card | `#D4CFC6` bone foil/print | — |

---

## 9. The Shopify theme settings (Kairo dark)

### Colors (paste into Dawn theme customizer)

```
Background 1 (main):        #0C0B0A   (vault black)
Background 2 (alternate):   #1A1816   (charcoal)
Text:                        #D4CFC6   (bone)
Solid button background:     #0C0B0A   (matches bg — invisible button)
Solid button text:           #D4CFC6
Outline button border:       #2A2725
Outline button text:         #D4CFC6
Accent 1:                    #7A2A20   (oxidized red)
Accent 2:                    #8A8279   (stone)
```

### The dark-store product page CSS (full)

```css
/* ═══════════════════════════════════════════════════════
   KAIRO — DARK STORE PRODUCT PAGE
   ═══════════════════════════════════════════════════════ */

body {
  background: #0C0B0A;
  color: #D4CFC6;
  font-family: 'Cormorant Garamond', serif;
}

.product-archive {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  max-width: 1200px;
  margin: 4rem auto;
  padding: 0 2rem;
}

.product-archive__hero img {
  width: 100%;
  height: auto;
  display: block;
  border: 1px solid #1A1816;
}

.lot-number {
  font-family: 'JetBrains Mono', monospace;
  font-size: 13px;
  letter-spacing: 0.08em;
  color: #8A8279;
  margin: 0 0 1.5rem 0;
}

.product-title {
  font-size: 24px;
  font-weight: 500;
  color: #D4CFC6;
  margin: 0 0 2rem 0;
  letter-spacing: 0.01em;
}

.mythology {
  font-size: 15px;
  font-style: italic;
  line-height: 1.7;
  color: #8A8279;
  margin-bottom: 3rem;
  max-width: 32em;
}

.metadata {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.08em;
  display: grid;
  grid-template-columns: 100px 1fr;
  row-gap: 0.6rem;
  margin-bottom: 3rem;
  padding: 1.5rem;
  background: #1A1816;
  border: 1px solid #2A2725;
}

.metadata dt {
  color: #8A8279;
  text-transform: uppercase;
  font-size: 10px;
}

.metadata dd {
  margin: 0;
  color: #D4CFC6;
}

.price {
  font-family: 'JetBrains Mono', monospace;
  font-size: 16px;
  color: #D4CFC6;
  margin: 0 0 2rem 0;
}

.btn-acquire {
  background: transparent;
  color: #D4CFC6;
  border: 1px solid #2A2725;
  padding: 1rem 3rem;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.15em;
  text-transform: lowercase;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-acquire:hover {
  background: #7A2A20;
  border-color: #7A2A20;
  color: #E8E2D5;
}

/* ── Related lots section ── */
.related-lots {
  margin-top: 6rem;
  padding-top: 3rem;
  border-top: 1px solid #1A1816;
}

.related-lots h3 {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  letter-spacing: 0.1em;
  color: #8A8279;
  text-transform: uppercase;
  margin-bottom: 2rem;
}

/* ── Responsive ── */
@media (max-width: 768px) {
  .product-archive {
    grid-template-columns: 1fr;
    gap: 2rem;
    padding: 0 1rem;
  }
}
```

---

## 10. The visual moat

What makes this hard to copy:

1. **The dark store.** 95% of watch dropshippers use white backgrounds. Your store looks like nothing they've seen.
2. **The LUT.** Consistent color grading across hundreds of assets = operational discipline most can't sustain.
3. **The voice.** Same ElevenLabs voice for 12 months becomes audio-recognizable.
4. **The grammar.** Photographic grammar (dark surfaces, hard light, off-center, single evidence prop) is more sophisticated than it looks.
5. **Time.** 6 months of consistent output is the actual moat. No shortcut exists.

The visual system is not creative work. It's compliance. Every shoot, check this document. Every edit, check this document.
