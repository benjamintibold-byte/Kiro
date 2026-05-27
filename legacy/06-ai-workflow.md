# 06 — AI WORKFLOW

How one operator runs this in 12–15 hours per week. AI handles mythology, voice, and document generation. You handle taste, sourcing, and shipping.

---

## 1. The stack

| Tool | Role | Cost |
|---|---|---|
| Claude or GPT-4 class | Mythology + copy generation | $20/mo |
| ElevenLabs | Voiceover (Starter or Creator plan) | $5–22/mo |
| Midjourney or Flux | Fictional documents, polaroids | $10–30/mo |
| CapCut Pro | Video editing | $8/mo |
| DaVinci Resolve (free) | LUT application, color grading | $0 |
| Phone + macro lens | Footage capture | $20 one-time |
| Metricool / Later | Multi-account scheduling | $18/mo |
| Notion / Airtable | Asset library, mythology storage | Free |

**Total tool cost:** ~$80/month at full setup.

---

## 2. The mythology generator (Claude system prompt)

Use this exact system prompt. It encodes the voice rules.

```
You write micro-mythology for [BRAND], an archive of unbranded mechanical 
objects presented as recoveries from estates.

VOICE
- Dry, archival, restrained. Like an estate handler writing a routine memo.
- Past tense. Passive voice often.
- 8–12 word average sentence length.
- No emotion. No selling adjectives. No exclamation points.

FORBIDDEN WORDS
luxury, premium, elegant, stunning, beautiful, gorgeous, crafted, exclusive,
limited, drop, launch, release, sale, discount, you, your, yours, we're, 
amazing, incredible, perfect, must-have, authentic, genuine, guaranteed,
certified.

NEVER ADDRESS THE READER. NEVER USE "YOU" OR "YOUR."

FORMAT
2–3 sentences max per object. Each must contain:
- One specific location (a real European, Japanese, or Eastern European city)
- One specific date or era (1970–2005 only)
- One detail of provenance ambiguity (something unverified, unexplained, partial)

EXAMPLES OF CORRECT VOICE
"Recovered from a closed brokerage in Antwerp. Found in a desk drawer 
alongside three unsent letters. We retained only the watch."

"Origin unconfirmed. The seller claimed it had not been wound since 1998. 
The rotor moved on the second day."

"Estate sealed in 2003 following a death without heirs. Items released to 
us in May. This is the last."

OUTPUT
Generate [N] mythologies for objects of type: [TYPE].
Each mythology stands alone. No headers. No numbering except a leading
LOT identifier.
```

### Use cases

**Generate 30 mythologies in one session:**

> User: Generate 30 mythologies for objects of type: skeleton automatic watch, off-white dial, 38mm.

**Generate a connected estate (8 objects from one fictional estate):**

> User: Generate 8 mythologies for objects from a single estate. The estate is sealed in 2003 in Antwerp following the death of a private archivist. Each object should reference the same estate consistently. Use lot numbers 049-A through 049-H.

**Generate variations on a single object:**

> User: Generate 5 mythology variations for the same skeleton automatic. Each variation should imply a different fictional origin and provenance. I'll pick the strongest.

---

## 3. ElevenLabs voice setup

### Voice spec

When designing or cloning your voice, the parameters that matter:

```
Gender:        Male
Perceived age: 30–40
Accent:        Ambiguous European (avoid clear British/French/German)
Style:         Slow, low, flat affect
Cadence:       ~140 words per minute
Energy:        Low — no smile, no warmth in delivery
```

### Two paths

**Path A: Voice Design (cheaper, faster)**
- ElevenLabs Voice Design tool generates voices from descriptions
- Generate 10 candidates with this prompt:
  > "Male, mid-30s, low pitch, slow cadence, slight European accent (continental, ambiguous), flat institutional affect, slight gravel, no warmth"
- Pick one. Lock it. Save to your library.

**Path B: Voice Clone (more authentic, requires source)**
- Record 1–3 minutes of clean audio with the desired voice characteristics
- Use a real person (with permission) or a public domain audio source
- Upload to ElevenLabs Instant Voice Clone or Professional Voice Clone

**Recommended:** Path A. Faster, cheaper, and you don't need to manage real-person permissions.

### Voice settings (when generating clips)

```
Stability:           45–55     (lower = more expressive, but inconsistent)
Similarity:          75
Style exaggeration:  10–20
Speaker boost:       ON
```

Generate the same line 3 times if it sounds off. Pick the take that's flattest.

### Stock phrase library (generate once, save forever)

Pre-generate these as `.wav` files. Saves credits later.

```
"Recovered from."
"Origin unconfirmed."
"Provenance unverified."
"Estate sealed in [year]."
"Available now."
"Lot zero zero four nine."
"The remainder is archived."
"Item one of seven."
"Field automatic, off-white dial."
"Mechanical, partially serviced."
"The dial has not been opened since."
"We have not verified it."
"Released this week."
"This is the last."
```

Plus generate the full 50 mythology lines from [07-mythology-bank.md](./07-mythology-bank.md) at once.

### Post-processing

Add to every voiceover in CapCut/Premiere:
- Slight tape hiss (find a free hiss sample, layer at -28dB)
- Vinyl crackle (-30dB)
- 2dB reduction on highs above 8kHz (slightly muffled, period-correct)
- Optional: very subtle phone-call/radio EQ for "found tape" feel

---

## 4. Image generation (Midjourney or Flux)

**Never AI-generate watches.** Real products only. AI-generate everything else:
- Fictional documents (letters, receipts, ledger pages)
- Polaroid-style photographs of "estates" (rooms, desks, drawers — never people)
- Map fragments, certificates, technical drawings
- Background textures (cracked concrete, aged paper) for content overlays

### Midjourney prompts (steal these)

**Faded letter on cream paper:**
```
typewritten letter, slightly faded ink, cream paper, 
edges yellowed, single coffee ring stain, 1970s document, 
shot from above, hard natural light, museum archive style, 
slightly desaturated, film grain, 35mm photograph
```

**Polaroid of a desk:**
```
polaroid photograph, 1980s, dim room, wooden desk, 
papers scattered, brass lamp, no people visible, 
warm window light, slightly faded, instant film aesthetic, 
mysterious, archival, no text
```

**Receipt fragment:**
```
torn receipt, monospace typewriter print, partial date 
visible "1991", cream paper edges yellowed, single 
coffee stain, shot on cream linen background, 
hard natural light, 35mm photograph, archival style
```

**Estate room (for field account ambient content):**
```
abandoned office, 1990s, file cabinets, papers on floor, 
single window with hard light, dust motes visible, 
no people, warm color cast, cinematic, slightly desaturated, 
film still, archival aesthetic
```

### Output handling

- Generate at 2048×2048 minimum
- Apply your LUT in Lightroom/Photoshop after export
- Add film grain layer if not already present
- Save to Notion/Airtable footage library tagged by use case

---

## 5. Footage library system

Build once, reuse for months.

### Initial shoot (one weekend, target 80+ clips)

Setup:
- Phone with macro lens ($20 clip-on macro)
- Window light, no other lighting
- Cracked concrete sheet, raw linen, cream paper, walnut surface
- Each watch shot from 5+ angles in 4K 60fps

Per watch, capture:
- 5x dial macros (different details)
- 3x crown/winding action
- 2x rotor spin (skeleton backs)
- 3x lug/case profile
- 2x strap stitching
- 2x clasp/buckle action
- 2x watch placed on different surfaces
- 1x watch flipped to caseback

Total: ~20 clips per watch × 5 watches = 100 clips.

### Storage and tagging

Build a Notion or Airtable database with these columns:

```
Clip ID    | Watch SKU | Type      | Surface  | Length | Used in posts
0001       | LOT0049-A | dial macro| linen    | 6s     | Reveal-Mon-W3
0002       | LOT0049-A | crown     | walnut   | 4s     | Detail-Tue-W3
0003       | LOT0049-A | rotor     | concrete | 8s     | Detail-Wed-W4
```

Tag every clip when used. Don't reuse a clip in the same week.

### The recombination rule

A single watch yields ~20 clips. With 4 watches, you have 80 clips. With 8 watches, 160. **You can produce 60 unique reels from 5 watches** by recombining clips with new mythology and voiceovers.

Re-shoot the same SKU only when you have a new angle worth capturing.

---

## 6. The weekly operator cadence

The complete schedule once the system is set up.

```
MONDAY (3 hours)
─────────────────────────────────────
0900-1000  Source review on 1688 / Yupoo
1000-1100  Confirm next 2 estates' inventory  
1100-1200  Place orders / sample orders
1200-1300  Update Airtable inventory + queue

TUESDAY (2 hours)
─────────────────────────────────────
1000-1100  Mythology generation (Claude, 30 lots)
1100-1200  Voiceover batch (ElevenLabs)
            - 30 mythologies
            - 5 stock phrases (replenish)

WEDNESDAY (4 hours)
─────────────────────────────────────
1000-1400  Photo + macro shoot day
            - One lighting setup
            - 80+ raw clips
            - 30+ stills for product pages
            - LUT preview check before wrapping

THURSDAY (4 hours)
─────────────────────────────────────
1000-1200  Edit dossier reels (8 reels)
1200-1300  Edit ambient pieces (4 for field)
1300-1400  Create text-on-black notes posts (5)

FRIDAY (1 hour)
─────────────────────────────────────
1000-1100  Update Shopify with new estate
            - Upload product images
            - Paste mythology + metadata
            - Set inventory levels
            - Schedule Klaviyo estate flow

SATURDAY (1 hour)
─────────────────────────────────────
Variable   Comment / DM engagement only
            (in voice, no exceptions)

SUNDAY (1 hour)
─────────────────────────────────────
Variable   Comment / DM engagement
            Review next week's schedule
            Note what hooks performed
```

**Total: ~15 hours per week** at steady state.

Months 0–2 will be 30+ hours/week building the library, brand bible, and Shopify shell. After that, the system runs on rails.

---

## 7. The performance review (weekly)

Every Sunday, 30 minutes:

```
[ ] Top 3 videos this week — what was the hook?
[ ] Bottom 3 videos — why did they fail?
[ ] Profile clicks → store clicks → orders
[ ] New Klaviyo subscribers
[ ] Any in-character comments worth replying to?
[ ] Any negative comments / refund requests?
[ ] Tag the top 3 hooks in your hook bank for reuse
```

**Don't optimize daily.** Daily optimization is noise. Weekly review captures signal.

---

## 8. The AI rules

These are the lines AI will not cross. Operator overrides them when needed.

### What AI does

- Mythology generation (you edit for voice consistency)
- Voiceover synthesis
- Fictional document generation
- Caption first drafts
- Email copy drafts
- Internal Airtable categorization

### What AI does NOT do

- Final voice approval (you listen to every clip before posting)
- Final mythology approval (you read every line — AI hallucinates real-world facts that can become fraud claims)
- Image generation of products themselves (real photos only)
- Customer service replies (templates yes, autosend no)
- Sourcing decisions (you handle every supplier)
- Quality control (you inspect every sample)

### The hallucination filter

When AI generates mythology, check for:
- Real brand names (Patek, Rolex, AP) — strip these
- Real historical figures — strip these
- Real specific factual claims that could be litigated ("worn by NASA in 1969") — strip these
- Locations that don't exist — verify
- Dates that contradict your timeline (post-2005) — fix

Edit pass takes 10 seconds per mythology. Worth it.

---

## 9. The compounding effect

After 90 days of disciplined AI workflow:

- ~2,700 mythologies generated, ~600 used
- ~600 voiceover clips in library
- ~500 macro footage clips
- ~200 fictional documents
- ~80 product pages live
- Same voice, same LUT, same grammar throughout

That's a moat. New entrants face a 90-day cold start to match it. By the time they catch up, you're 180 days deep.
