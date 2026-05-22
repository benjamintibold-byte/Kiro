# 02 — VISUAL SYSTEM

Lock these on day 2. Never change them. Visual continuity over time is the single biggest reason competitors can't catch up.

---

## 1. Color palette

Only these. No exceptions. No "one-off" colors for special posts.

| Name | Hex | Use |
|---|---|---|
| Off-black | `#0F0E0D` | Primary background, type |
| Cream | `#E8E2D5` | Document backgrounds, cards |
| Warm gray | `#7A756D` | Secondary type, captions |
| Stone | `#3A3633` | Surfaces, borders |
| Accent (pick ONE) | `#7A2A20` *or* `#C9A23A` | Single accent only |

**Accent rule:** pick oxidized red (`#7A2A20`) OR evidence yellow (`#C9A23A`). Never both. Use sparingly — wax seals, single highlight in metadata, dot indicators. Never on full surfaces.

**Recommended:** oxidized red. It's harder to imitate cheaply and reads as "institutional" rather than "trendy."

---

## 2. Typography

### Two fonts only

**Serif:** Cormorant Garamond — weight 400 (regular) and 500 (medium). Used for body copy, mythology, headlines, product titles.

**Monospace:** JetBrains Mono — weight 400. Used for metadata, lot numbers, dates, captions on photographs.

**Free alternatives if Cormorant feels too thin on small screens:** EB Garamond, Cormorant Infant.

### Type rules

- No sans-serif anywhere. Ever.
- No bold (`weight 700+`). Use italic for emphasis instead.
- No all-caps in body copy. All-caps only for metadata labels (`ORIGIN`, `LOT`, `MOVEMENT`).
- Letter-spacing on metadata: `+0.05em`. Default elsewhere.
- Line-height: `1.5` for body, `1.2` for metadata blocks.

### Font sizes (locked scale)

| Element | Size | Font |
|---|---|---|
| Hero text | 22px / 1.3rem | Serif 400 |
| Body | 14px / 0.875rem | Serif 400 |
| Metadata | 11px / 0.7rem | Mono 400 |
| Caption / footnote | 10px | Mono 400 |
| Lot number (product page) | 16px | Mono 400 |
| Price | 14px | Mono 400 |

Small. Restraint. The temptation will be to make things bigger. Resist.

---

## 3. Photography rules

### The grammar

Every photograph follows this grammar. If a shot doesn't conform, don't post it.

1. **Single object.** No clutter. One hero subject, max one supporting prop.
2. **Off-center.** Subject placed on the left third or right third. Never centered.
3. **Hard natural light.** Window light, late afternoon. No softboxes. No ring lights. No reflectors.
4. **Slightly underexposed.** Pull exposure down by 1/3 to 2/3 stop. Lifted blacks in post.
5. **Surface from approved list:**
   - Cracked concrete (or concrete-look textured paper)
   - Raw linen (off-white or oatmeal)
   - Cream document paper, slightly aged
   - Dark walnut wood
   - Brushed steel sheet
   - Aged book pages
6. **One "evidence" element in frame:**
   - Numbered tag (handwritten or stamped)
   - Date stamp
   - Ring stain (coffee, tea, water)
   - Dust mark
   - Faint pencil notation
   - Wax seal fragment
7. **Slightly mid-action framing.** Looks like the second photo of a series, not a hero shot. The viewer's brain wants the rest.

### Forbidden in photographs

- Wrist shots
- Any human, hand, or body part except in extreme macro of a finger winding a crown
- Lifestyle scenes (coffee + watch, laptop + watch, etc.)
- Multiple watches in one frame (except in archival "estate group shots")
- Seamless white backdrops
- Professional product photography lighting (softboxes, light tents)
- Color filters, vintage filters, Instagram presets

### Macro footage (for TikTok)

Shoot at 60fps minimum, 4K when possible. Slow it 50% in post. Topics for macro:
- Second hand sweep
- Crown knurl rotation
- Lug bevel catching light
- Dial texture under raking light
- Rotor spin (back of skeleton watches)
- Lume glow under UV
- Strap stitching
- Clasp click

Build a library of 80–100 macro clips before launch. Reuse forever.

---

## 4. The LUT (color grade)

Apply this LUT to every photograph and every video. One LUT. One look.

### LUT spec (build in Lightroom/Photoshop and export, or DaVinci Resolve)

```
EXPOSURE        -0.3
CONTRAST        +12
HIGHLIGHTS      -25
SHADOWS         +18
WHITES          -10
BLACKS          +15           # lifted blacks for archive feel
TEMPERATURE     -300K         # cooler base
TINT            +5            # slight magenta to fight green
SATURATION      -25
VIBRANCE        -15

HSL:
  Reds          sat -10, lum -5
  Oranges       sat -20, lum +5
  Yellows       sat -30, lum +5
  Greens        sat -40, lum -10
  Aquas         sat -50, lum -10
  Blues         sat -30, lum -5
  Purples       sat -50
  Magentas      sat -50

GRAIN           amount 25, size 25, roughness 50
VIGNETTE        -15 amount, midpoint 50, feather 50
```

Save as `.cube` or `.xmp`. Apply to every asset before export.

**Test for consistency:** lay 9 of your photos in a 3×3 grid. They should look like they came from the same archive.

---

## 5. Audio identity

The voice and the sound design are as important as the visuals.

### The voice (lock day 3)

ElevenLabs voice — design or clone. Spec:
- Low male
- Perceived age 30–40
- Ambiguous European accent (avoid clearly British, French, German)
- Slow cadence, ~140 wpm
- Flat affect, no smile in voice
- Slight tape hiss/warmth in post

Generate 20 voice samples in week 1. Pick the one that sounds most institutional. **Use that exact voice for 12+ months.** Voice drift is brand suicide.

**Backup voice prep:** generate 30 stock phrases now and save them as `.wav` files. If ElevenLabs ever loses your voice or changes pricing, you have a fallback library.

Stock phrases to pre-generate:
- "Recovered from."
- "Origin unconfirmed."
- "Provenance unverified."
- "Estate sealed in [year]."
- "Available now."
- "Lot [number]."
- "The remainder is archived."
- Plus 50 voiceover lines from the mythology bank (file 07).

### Sound design library

Build once, reuse forever. Spend one weekend on this.

Categories needed (50 clips total, ~10 per category):

1. **Mechanical** — winding, ticking, rotor spin, crown click
2. **Paper** — rustle, fold, tear, page turn, envelope open
3. **Surface** — placing object on wood/concrete, scrape, slide
4. **Ambient** — distant hum, room tone, faint static, vinyl crackle
5. **Punctuation** — single tick, single click, soft thump (for hooks)

Sources:
- Record yourself with phone (best for tactile)
- Free sound libraries: Freesound.org, Zapsplat
- Avoid YouTube music libraries — too clean, too produced

### The mix recipe (every video)

```
Voiceover                  -3 dB    main
Tactile sound (1 hit)      -8 dB    on action moment
Ambient bed                -22 dB   under everything
Vinyl crackle              -28 dB   subtle, constant
Tape hiss on VO            built into ElevenLabs preset
```

No music. Ever. Music breaks the world.

---

## 6. Motion design

### Video editing rules

- **Cuts:** straight cuts only. No fades except slow fade-to-black at end.
- **Speed:** macros at 50% speed. Reveals at 100%. Never speed-ramp.
- **Text on screen:** monospace only, white on black with 70% opacity background bar, or directly on dark surface.
- **Text duration:** 1.5–2 seconds per line.
- **Text position:** lower-left third, monospace 11px equivalent.

### On-screen text format

```
LOT 0049 / GENEVA / 1991
```

Always in this pattern: `LOT [number] / [city] / [year]`. Slashes, not dashes. Spaces around slashes. Monospace.

---

## 7. The visual moat

What makes this hard to copy:

1. **Time.** Six months of consistent output is the actual moat.
2. **The LUT.** Even if copied, applying it consistently across hundreds of assets is operational discipline most can't sustain.
3. **The voice.** The same ElevenLabs voice for 12 months becomes audio-recognizable.
4. **The grammar.** Photographic grammar is more sophisticated than it looks. Most copycats break a rule within 10 posts.

The visual system is not creative work. It's compliance. Every shoot, check this document. Every edit, check this document.
