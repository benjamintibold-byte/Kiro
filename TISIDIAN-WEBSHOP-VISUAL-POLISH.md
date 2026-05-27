# 🎨 TISIDIAN WEBSHOP — VIZUÁLIS POLISH

Step-by-step tutorial a webshop **vizuális karakterének** felépítéséhez.
A `FINAL-MODS.md` lefedte a backend tisztaságot (vendor, SKU, URL).
**Ez a doksi arról szól, hogy NÉZZEN ki egyedien és prémiumban.**

> ⏱️ Becsült idő: 2–3 óra
> 🎯 Cél: a webshop ne nézzen ki "egy sötét Shopify boltnak" — legyen FELISMERHETŐ, KARAKTERES

---

## 📋 MIT LÁTOK A KÉPEKEN — DIAGNÓZIS

A screenshotok alapján a webshop alapja jó, **DE 7 dolog rontja a profizmust:**

| # | Probléma | Hatás |
|---|---|---|
| 1 | Hero-ban nincs sub-headline és CTA gomb | Vásárló tanácstalan, nincs vezérlés |
| 2 | "Signature" cím kicsi, baloldali, vékony — nem illik a hero-hoz | Vizuális hierarchia szétesik |
| 3 | "Selected" kollekció név nem mond semmit + olcsó órákat tartalmaz $29–$119 | Brand split: prémium vs olcsó keveredik |
| 4 | Termékkártya: csak név + ár, nincs micro-info | Üres kártya érzet |
| 5 | Nincs trust bar (warranty, shipping, secure) | Hideg, gyanakvó vásárló |
| 6 | Nav: Home / Catalog / Contact — kevés egy luxus brandhez | Nincs sztori, nincs mélység |
| 7 | Generikus sötét háttér — bármelyik dropshipping bolt lehetne | Nincs felismerhető brand identitás |

**Ezt mind orvosoljuk lent. Lépésről lépésre.**

---

## 🎨 1. LÉPÉS — A TISIDIAN SZÍNRENDSZER ("OBSIDIAN MYTHOS")

Ez a webshop **legfontosabb** módosítása. Most a háttér egy generikus sötét lila/fekete. Cseréljük le egy **névvel ellátott, konzisztens színrendszerre**, ami csak a TISIDIAN-é.

### A paletta — másold pontosan

```
═══════════════════════════════════════════════════════
   TISIDIAN COLOR SYSTEM — "OBSIDIAN MYTHOS"
═══════════════════════════════════════════════════════

 ── BACKGROUNDS ──
 --obsidian       #0A0813      primary background (mély violet-fekete)
 --ink            #14101F      cards, secondary surfaces
 --mist           #1F1A2E      elevated surfaces, drawers, hover bg
 --veil           #2A2440      borders, subtle dividers

 ── TEXT ──
 --bone           #F2EFE8      primary text (meleg krém-fehér)
 --smoke          #9590A8      secondary text, metadata
 --ash            #5B5670      muted, disabled, captions

 ── ACCENTS ──
 --gold           #C9A96E      primary accent — CTA, premium ("Aurelion gold")
 --gold-glow      #E0C088      hover state on gold
 --crimson        #6B1F2C      rare accent — sigils, alerts (alig használjuk)
 --diamond        #E8E6F0      sparkle glow, premium highlights
```

### Miért ez a paletta?

- **`#0A0813` (Obsidian)** — A pure black `#000000` túl sterile. A `#0A0813` egy szinte észrevehetetlen **violet undertone**-t ad — ettől felismerhető lesz a brand. Ha valaki látja, tudja: ez TISIDIAN.
- **`#C9A96E` (Aurelion gold)** — A hero termékről elnevezve. Ez NEM sárga gold, hanem **champagne** — az igazi luxus szín. Cartier, Rolex Daytona arany ezzel játszik.
- **`#F2EFE8` (Bone)** — Soha ne használj `#FFFFFF` fehéret sötét háttéren. A pure white túl éles, fárasztja a szemet, és olcsónak hat. A meleg krém-fehér prémium.
- **`#6B1F2C` (Crimson)** — Csak nagyon ritkán használjuk: pecsét ikonok, error állapot. **Egy színfolt egy oldalon, max.**

### Hogyan állítsd be Shopify-ban (Dawn téma)

```
1. Online Store → Themes → Customize
2. Theme settings (jobb oldali oszlop alja)
3. Colors → Color schemes
4. Cseréld a következőket:

   Scheme: "Background 1" (a fő scheme)
   ─────────────────────────────────
   Background:           #0A0813
   Background gradient:  ÜRES (kapcsold ki)
   Text:                 #F2EFE8
   Button:               #C9A96E
   Button label:         #0A0813
   Secondary button bg:  #0A0813
   Secondary button txt: #F2EFE8
   Secondary button bdr: #2A2440
   Links:                #C9A96E
   Badge bg:             #C9A96E
   Badge text:           #0A0813

   Scheme: "Background 2"
   ─────────────────────
   Background:           #14101F
   Text:                 #F2EFE8
   Button:               #C9A96E
   Button label:         #0A0813

5. Save
```

---

## ✍️ 2. LÉPÉS — TIPOGRÁFIA RENDSZER

A jelenlegi tipográfia kevert (a hero bold sans, a "Signature" cím vékony és inkonzisztens). Egy karakteres brand **MAX 2 fontot használ**.

### A TISIDIAN font stack

```
DISPLAY (logo, hero, section headings):
   Cormorant Garamond — 500 (medium) és 600 (semibold)
   Vagy fallback: Cinzel (még mythologikusabb)

BODY (termékleírás, nav, copy):
   Inter — 400 (regular) és 500 (medium)
   Tiszta modern sans, jól olvasható mobilon

METADATA (SKU, lot number, ár, "FREE SHIPPING" bar):
   JetBrains Mono — 400, ALL CAPS, letter-spacing +0.12em
   Adja a "kurátori" érzetet
```

### Hogyan állítsd be

```
1. Themes → Customize → Theme settings → Typography

   Headings:        Cormorant Garamond  weight 500
   Body:            Inter               weight 400
   Buttons:         JetBrains Mono      weight 400

2. Ha nincs JetBrains Mono Shopify font listában:
   Használj "IBM Plex Mono"-t (közel azonos)

3. Save
```

### Tipográfia szabályok

```
✅ DO:
- Section heading: ALL CAPS Cormorant, ritkítás +0.15em
- Termék név: Cormorant 500, NEM all caps
- Ár: JetBrains Mono, ALL CAPS
- Body szöveg: Inter 400, line-height 1.6

❌ DON'T:
- NE használj 3 fontot egyszerre
- NE keverj sentence case és ALL CAPS-et ugyanazon a hierarchia szinten
- NE használj BOLD (700+) — ettől olcsóvá válik. Italic > bold.
```

---

## 🎬 3. LÉPÉS — HERO SZEKCIÓ ÚJRAÉPÍTÉSE

A jelenlegi hero: csak `CRAFTED FOR PRESENCE.` headline + termékfotó.
**Hiányzik: sub-headline, CTA gomb, trust signal.**

### Új hero struktúra (fentről lefelé)

```
┌────────────────────────────────────────────┐
│                                            │
│         [ termékfotó háttér, pára ]        │
│                                            │
│                                            │
│         CRAFTED FOR PRESENCE.              │  ← Headline (Cormorant 600, 64px)
│                                            │
│   Diamond-set timepieces, engineered       │  ← Sub-headline (Inter 400, 18px, smoke)
│   for the few who arrive deliberately.     │
│                                            │
│         [  EXPLORE SIGNATURE →  ]          │  ← CTA (gold outline, mono caps)
│                                            │
│                                            │
└────────────────────────────────────────────┘
   FREE WORLDWIDE SHIPPING · 2-YEAR WARRANTY · SECURE CHECKOUT   ← Trust bar
```

### Hogyan csináld Shopify-ban

```
1. Themes → Customize → Home page
2. Image banner sectiont kattints meg

3. Heading mező:
   CRAFTED FOR PRESENCE.

4. Heading size: H1 / Extra Large

5. Description / subtext mező (ha nincs, add hozzá Rich text block):
   Diamond-set timepieces, engineered
   for the few who arrive deliberately.

6. Button label #1:
   EXPLORE SIGNATURE
   Button link: /collections/signature
   Button style: Outline (NE solid)

7. Image overlay opacity: 30%
   (a fotó NE legyen túl sötét, de a szöveg legyen olvasható)

8. Section padding bottom: 80
9. Save
```

### Trust bar hozzáadása

```
1. A hero ALÁ adj egy "Multi-column" sectiont (vagy Custom HTML)
2. Háttér: #14101F (ink)
3. 3 oszlop, csak szöveg, középre:

   Oszlop 1:  FREE WORLDWIDE SHIPPING
   Oszlop 2:  2-YEAR MOVEMENT WARRANTY
   Oszlop 3:  SECURE STRIPE CHECKOUT

4. Font: JetBrains Mono / IBM Plex Mono
5. Méret: 11px, ALL CAPS, letter-spacing 0.12em
6. Szín: #9590A8 (smoke)
7. Padding vertical: 24px
8. Save
```

---

## 🏛 4. LÉPÉS — SECTION HEADING-EK ÚJRAÍRÁSA

A jelenlegi "Signature" és "Selected" feliratok kicsik, baloldaliak, élet nélküliek.

### Új formátum minden szekcióhoz

```
            ─────  SIGNATURE  ─────
            The cornerstone of Tisidian.
```

- **Cím:** Cormorant 500, ALL CAPS, ritkítás +0.2em, 24px, középre
- **Két vízszintes vonal** mellette (border-top, 1px, smoke)
- **Tagline alatta:** Inter 400 italic, 14px, smoke (#9590A8)
- **Padding top:** 80px (légy bőkezű a térrel — luxus = whitespace)

### Konkrétan mit írj át

#### "Signature" → maradjon SIGNATURE
```
            ─────  SIGNATURE  ─────
            The cornerstone of Tisidian.
```

#### "Selected" → ÁTNEVEZÉS: ESSENTIALS
A "Selected" semmit nem mond. Az **ESSENTIALS** azt sugallja: ezek az alap, mindennapos darabok.

```
            ─────  ESSENTIALS  ─────
            Quiet pieces, daily worn.
```

> 💡 **Ezzel rendezed a brand splitet is:** Signature = halo (ünnepi, $400+), Essentials = daily (mindennapos, $29–$119). Két különböző miszsion, egy brand alatt.

#### "Accessories" (ha van)
```
            ─────  ACCESSORIES  ─────
            Vaultré boxes and storage.
```

### Liquid kód a section headinghez

Ha custom Liquid sectiont raksz be (Sections → Add custom section), ezt másold be:

```liquid
{%- comment -%} TISIDIAN — Section heading block {%- endcomment -%}

<div class="tis-section-heading">
  <div class="tis-section-heading__inner">
    <span class="tis-section-heading__line"></span>
    <h2 class="tis-section-heading__title">{{ section.settings.title }}</h2>
    <span class="tis-section-heading__line"></span>
  </div>
  {%- if section.settings.tagline != blank -%}
    <p class="tis-section-heading__tagline">{{ section.settings.tagline }}</p>
  {%- endif -%}
</div>

<style>
  .tis-section-heading {
    text-align: center;
    padding: 80px 24px 40px;
    background: #0A0813;
  }
  .tis-section-heading__inner {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 24px;
    margin-bottom: 12px;
  }
  .tis-section-heading__line {
    width: 48px;
    height: 1px;
    background: #9590A8;
    opacity: 0.5;
  }
  .tis-section-heading__title {
    font-family: 'Cormorant Garamond', serif;
    font-weight: 500;
    font-size: 28px;
    letter-spacing: 0.2em;
    color: #F2EFE8;
    text-transform: uppercase;
    margin: 0;
  }
  .tis-section-heading__tagline {
    font-family: 'Inter', sans-serif;
    font-style: italic;
    font-size: 14px;
    color: #9590A8;
    margin: 0;
  }
</style>

{% schema %}
{
  "name": "TIS Section Heading",
  "settings": [
    {
      "type": "text",
      "id": "title",
      "label": "Title",
      "default": "SIGNATURE"
    },
    {
      "type": "text",
      "id": "tagline",
      "label": "Tagline (italic, alatta)",
      "default": "The cornerstone of Tisidian."
    }
  ],
  "presets": [
    {
      "name": "TIS Section Heading"
    }
  ]
}
{% endschema %}
```

**Hova mentsd:**
```
Online Store → Themes → Edit code → Sections folder
→ Add new section → tis-section-heading.liquid
→ Paste a fenti kódot → Save
```

Utána minden oldalon `Add section → TIS Section Heading`-ként megjelenik.

---

## 🎴 5. LÉPÉS — TERMÉKKÁRTYÁK FELDÍSZÍTÉSE

Most a kártyán: csak **név + ár**. Üres érzés.

### Új kártya struktúra

```
┌──────────────────────┐
│                      │
│   [ termékfotó ]     │
│                      │
├──────────────────────┤
│ AURELION             │ ← Név (Cormorant 500, 16px, bone)
│ Diamond-set · 42mm   │ ← Micro-line (Inter 400, 12px, smoke)
│ $329 USD             │ ← Ár (JetBrains Mono, 14px, bone)
└──────────────────────┘
```

### Hogyan add hozzá a "micro-line"-t

A Shopify nem ad ki dobozból ilyen mezőt. **2 lehetőség:**

**A) Egyszerű (5 perc):** Custom metafields
```
1. Settings → Custom data → Products → Add definition
2. Name: "Subtitle"
3. Namespace and key: custom.subtitle
4. Type: Single line text
5. Save

6. Minden terméknél töltsd ki:
   AURELION       → "Diamond-set · 42mm · Steel"
   VANTH          → "Skeleton automatic · 41mm"
   OBSYRIAN       → "Full moissanite · 40mm"
   AETHERION      → "Multi-complication · 44mm"
   LUMERA         → "Iced bracelet · 40mm"
   PHANTOM        → "Ultra-thin · 7mm case"
   VALTHER        → "Multi-layer dial · 42mm"
   ORIEN          → "Minimal automatic · 38mm"
   VOID           → "Dark dial · 40mm"
```

**B) Megjelenítés a kártyán:** Edit code
```
1. Themes → Edit code → Snippets → card-product.liquid
2. Keresd meg ezt a sort:
   <h3 class="card__heading...">
3. Az ALÁ szúrd be:

   {%- if product.metafields.custom.subtitle -%}
     <p class="card__subtitle">{{ product.metafields.custom.subtitle }}</p>
   {%- endif -%}

4. Save
```

### CSS a micro-line-hoz

```
1. Themes → Edit code → Assets → base.css (vagy theme.css)
2. Görgess a végére, paste:

.card__subtitle {
  font-family: 'Inter', sans-serif;
  font-size: 12px;
  font-weight: 400;
  color: #9590A8;
  letter-spacing: 0.02em;
  margin: 4px 0 8px 0;
}

.card__heading,
.card__heading a {
  font-family: 'Cormorant Garamond', serif !important;
  font-weight: 500 !important;
  font-size: 17px !important;
  letter-spacing: 0.12em !important;
  color: #F2EFE8 !important;
  text-transform: uppercase;
}

.price-item--regular {
  font-family: 'JetBrains Mono', 'IBM Plex Mono', monospace !important;
  font-size: 13px !important;
  color: #F2EFE8 !important;
  letter-spacing: 0.05em;
}

3. Save
```

---

## 🧭 6. LÉPÉS — NAVIGÁCIÓ BŐVÍTÉSE

A jelenlegi `Home / Catalog / Contact` túl szegényes. Egy luxus brandnek **mélysége** kell.

### Új menü struktúra

```
COLLECTIONS  ▾   THE STORY   CRAFTSMANSHIP   CONTACT
  ├─ Signature
  ├─ Essentials
  └─ Accessories
```

### Hogyan állítsd be

```
1. Online Store → Navigation → Main menu → Edit
2. Töröld: Home, Catalog
3. Add menu items:

   Collections (parent, link: /collections)
     └─ Signature      → /collections/signature
     └─ Essentials     → /collections/essentials
     └─ Accessories    → /collections/accessories

   The Story            → /pages/story
   Craftsmanship        → /pages/craftsmanship
   Contact              → /pages/contact

4. Save
```

### Az új oldalak tartalma

#### `/pages/story` — THE STORY

```
1. Online Store → Pages → Add page
2. Title: The Story
3. Body:
```

```
                    ─── THE STORY ───

Tisidian was not invented. It was assembled.

We sourced from estates in Geneva, Antwerp, Osaka.
We retained what held weight on the wrist.
We discarded what didn't.

Each piece is named after something older than fashion —
constellations, forgotten gods, sealed archives.
The names carry weight the marketing cannot.

Worn quietly. Engineered deliberately.

                              — Section T
```

> 💡 Ez egy **mythology hook**, nem szimpla "About us". Ne írd át "we love watches"-re. A fent karakteres copy az, ami eladja a brandet.

#### `/pages/craftsmanship` — CRAFTSMANSHIP

```
                  ─── CRAFTSMANSHIP ───

MOVEMENT
Each automatic timepiece is fitted with a skeleton
mechanical movement. 38–42 hour power reserve.
Visible from front or caseback, depending on the model.

MATERIALS
Stainless steel cases. Hand-set moissanite stones
(Signature line). Sapphire-grade or reinforced
mineral crystal.

WEIGHT
Tisidian pieces are intentionally heavy. A watch
should be felt before it is seen.

WARRANTY
Two-year movement warranty on every timepiece.
Unconditional.
```

#### `/pages/contact` — már létezik, csak ellenőrizd

---

## 📜 7. LÉPÉS — ÚJ HOMEPAGE SZEKCIÓK (ALULRÓL ÉPÍTKEZÉS)

A jelenlegi homepage: hero → Signature → Selected → vége. **Ez sovány.** Egy prémium brand homepage struktúrája:

```
1. HERO                        (megvan, polish kell)
2. TRUST BAR                   (új — 4. lépés)
3. SIGNATURE collection        (megvan, heading polish)
4. THE STORY (mini)            (új — alul)
5. ESSENTIALS collection       (átnevezve "Selected"-ből)
6. CRAFTSMANSHIP (mini)        (új)
7. AS SEEN (TikTok video grid) (új — később, miután van content)
8. NEWSLETTER capture          (új)
9. FOOTER                      (lásd FINAL-MODS.md)
```

### A "THE STORY (mini)" szekció a homepage-en

```
Add ezt a Signature ALÁ:

Section type: Image with text
Background: #14101F (ink)
Image: a leg-cinematicabb Veo3 frame-et használd
Image position: Right
Heading: AN ARCHIVE. NOT A BRAND.
Body:
   Tisidian assembles what others overlook.
   Sourced from estates. Kept for weight.
   Each piece names itself.
Button: READ THE STORY → /pages/story
Button style: Outline gold

Padding top: 80
Padding bottom: 80
```

### Newsletter capture szekció

```
Section type: Email signup
Background: #0A0813
Heading: JOIN THE INNER CIRCLE
Subheading:
   Early access to released pieces.
   No noise. No promotions. One email per release.
Placeholder: your email
Button: SUBSCRIBE
```

> ⚠️ **Soha ne ígérj kedvezményt** ("10% off your first piece"). A brand voice (lásd `01-brand-bible.md`) tiltja a "discount", "sale" szavakat.

---

## 📱 8. LÉPÉS — MOBIL CHECKLIST

A vásárlók 80%-a mobilról jön. Mindent **mobilon ellenőrizz**.

```
[ ] Hero szöveg nem lóg ki képernyőről
[ ] Hero CTA gomb scrollozás nélkül látszik
[ ] Section headings középre vannak (nem balra lógnak)
[ ] Termékkártya képei nem torzulnak (1:1 arány tartva)
[ ] Trust bar 3 pontja egymás alatt szépen elfér
[ ] Newsletter input mező nem lóg ki
[ ] Footer linkek tappolhatók (min 44px target)
[ ] Page load < 3 másodperc (PageSpeed Insights)
[ ] Apple Pay gomb megjelenik checkout-ban
[ ] Cart drawer rendesen csukódik
```

**Hibák, amiket gyakran látok mobilon:**
- A hero termékfotó középre van vágva → a watch fele lemarad. Megoldás: használj **mobile-specific image cropot** Shopify-ban (image banner sectionben van külön mobile image mező).
- A "Signature" heading mobilon óriási lesz → set `font-size: clamp(20px, 5vw, 28px)` a CSS-ben.
- A trust bar 3 pontja egymás mellé szorul olvashatatlanul → mobile-on stackeld függőlegesen `flex-direction: column`.

---

## 🎨 9. LÉPÉS — MASTER CSS SNIPPET (MÁSOLD AZ EGÉSZET)

Ez a **teljes vizuális rendszer** egy CSS-ben. Ha bemásolod, automatikusan érvényesül a teljes shop-on.

```
Online Store → Themes → Edit code → Assets → base.css
→ A FÁJL ELEJÉRE szúrd be:
```

```css
/* ═══════════════════════════════════════════════════
   TISIDIAN — OBSIDIAN MYTHOS DESIGN SYSTEM
   ═══════════════════════════════════════════════════ */

:root {
  /* Backgrounds */
  --tis-obsidian:   #0A0813;
  --tis-ink:        #14101F;
  --tis-mist:       #1F1A2E;
  --tis-veil:       #2A2440;

  /* Text */
  --tis-bone:       #F2EFE8;
  --tis-smoke:      #9590A8;
  --tis-ash:        #5B5670;

  /* Accents */
  --tis-gold:       #C9A96E;
  --tis-gold-glow:  #E0C088;
  --tis-crimson:    #6B1F2C;
  --tis-diamond:    #E8E6F0;
}

/* ── Global background override ── */
body {
  background: var(--tis-obsidian) !important;
  color: var(--tis-bone) !important;
  font-family: 'Inter', -apple-system, sans-serif;
}

/* ── Hero headline polish ── */
.banner__heading,
h1.h1 {
  font-family: 'Cormorant Garamond', serif !important;
  font-weight: 600 !important;
  letter-spacing: 0.02em;
  color: var(--tis-bone);
}

/* ── Primary CTA (gold outline) ── */
.button--primary,
.button.button--primary {
  background: transparent !important;
  color: var(--tis-gold) !important;
  border: 1px solid var(--tis-gold) !important;
  font-family: 'JetBrains Mono', 'IBM Plex Mono', monospace !important;
  font-size: 11px !important;
  letter-spacing: 0.18em !important;
  text-transform: uppercase !important;
  padding: 16px 36px !important;
  transition: all 0.3s ease !important;
  border-radius: 0 !important;
}

.button--primary:hover {
  background: var(--tis-gold) !important;
  color: var(--tis-obsidian) !important;
  border-color: var(--tis-gold) !important;
}

/* ── Secondary outline button ── */
.button--secondary {
  background: transparent !important;
  color: var(--tis-bone) !important;
  border: 1px solid var(--tis-veil) !important;
  font-family: 'JetBrains Mono', monospace !important;
  font-size: 11px !important;
  letter-spacing: 0.15em !important;
  text-transform: uppercase !important;
  border-radius: 0 !important;
}

.button--secondary:hover {
  border-color: var(--tis-bone) !important;
}

/* ── Card background ── */
.card-wrapper,
.card {
  background: var(--tis-obsidian) !important;
  border: none !important;
}

/* ── Product card text ── */
.card__heading,
.card__heading a {
  font-family: 'Cormorant Garamond', serif !important;
  font-weight: 500 !important;
  font-size: 17px !important;
  letter-spacing: 0.12em !important;
  color: var(--tis-bone) !important;
  text-transform: uppercase;
}

.card__subtitle {
  font-family: 'Inter', sans-serif;
  font-size: 12px;
  color: var(--tis-smoke);
  margin: 4px 0 8px 0;
  letter-spacing: 0.02em;
}

/* ── Prices ── */
.price-item,
.price-item--regular,
.price__regular {
  font-family: 'JetBrains Mono', 'IBM Plex Mono', monospace !important;
  font-size: 13px !important;
  color: var(--tis-bone) !important;
  letter-spacing: 0.05em;
  font-weight: 400 !important;
}

/* ── Header / Nav ── */
.header,
.section-header {
  background: var(--tis-obsidian) !important;
  border-bottom: 1px solid var(--tis-veil) !important;
}

.header__menu-item,
.list-menu__item {
  font-family: 'Inter', sans-serif;
  font-size: 12px !important;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--tis-bone) !important;
  font-weight: 400 !important;
}

.header__menu-item:hover {
  color: var(--tis-gold) !important;
}

/* ── Footer ── */
.footer,
.section-footer {
  background: var(--tis-ink) !important;
  color: var(--tis-smoke) !important;
  border-top: 1px solid var(--tis-veil);
}

.footer a {
  color: var(--tis-smoke) !important;
}

.footer a:hover {
  color: var(--tis-bone) !important;
}

/* ── Selection highlight ── */
::selection {
  background: var(--tis-gold);
  color: var(--tis-obsidian);
}

/* ── Scrollbar (subtle, premium) ── */
::-webkit-scrollbar {
  width: 6px;
}
::-webkit-scrollbar-track {
  background: var(--tis-obsidian);
}
::-webkit-scrollbar-thumb {
  background: var(--tis-veil);
}
::-webkit-scrollbar-thumb:hover {
  background: var(--tis-smoke);
}

/* ── Trust bar (custom) ── */
.tis-trust-bar {
  background: var(--tis-ink);
  border-top: 1px solid var(--tis-veil);
  border-bottom: 1px solid var(--tis-veil);
  padding: 18px 24px;
  display: flex;
  justify-content: center;
  gap: 48px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--tis-smoke);
}

@media (max-width: 749px) {
  .tis-trust-bar {
    flex-direction: column;
    gap: 12px;
    text-align: center;
    font-size: 9px;
  }
}

/* ── Mobile hero polish ── */
@media (max-width: 749px) {
  .banner__heading,
  h1.h1 {
    font-size: clamp(28px, 8vw, 48px) !important;
  }
}

/* ═══════════════════════════════════════════════════
   END OF TISIDIAN OBSIDIAN MYTHOS SYSTEM
   ═══════════════════════════════════════════════════ */
```

---

## 🏷 10. LÉPÉS — FAVICON + LOGO POLISH

Egy karakteres brand felismerhető logoja **böngésző fülén** is.

### Favicon

```
1. Canva.com → új design 32x32px
2. Háttér: #0A0813 (obsidian)
3. Szöveg: T (Cormorant Garamond, weight 600, color #C9A96E)
4. Letöltés: PNG, "favicon.png"
5. Shopify → Themes → Customize → Theme settings → Favicon → Upload
```

### Logo magasság a header-ben

```
Themes → Customize → Header
Logo width:
   Desktop: 140px
   Mobile:  100px
```

A jelenlegi logo (TISIDIAN nagy ritkításban) jó — csak ne legyen túl kicsi mobilon.

---

## ✅ VÉGSŐ CHECKLIST

```
═══ FOUNDATION ═══
[ ] Színpaletta beállítva (Obsidian, Ink, Bone, Gold)
[ ] Background: #0A0813 (NEM pure black)
[ ] Tipográfia: Cormorant + Inter + JetBrains Mono

═══ HOMEPAGE ═══
[ ] Hero: headline + sub-headline + gold CTA
[ ] Trust bar a hero alatt
[ ] SIGNATURE heading: középre, ALL CAPS, ritkítva, taglinnel
[ ] ESSENTIALS heading (átnevezve "Selected"-ből)
[ ] "An archive, not a brand" mini story szekció
[ ] Newsletter capture szekció

═══ PRODUCT ═══
[ ] Termékkártyán micro-line (Diamond-set · 42mm)
[ ] SKU mind TIS-XXX formátumban
[ ] Termék nevek serif, ALL CAPS, ritkítva

═══ NAVIGATION ═══
[ ] Menu: Collections / The Story / Craftsmanship / Contact
[ ] /pages/story létrehozva (mythology copy)
[ ] /pages/craftsmanship létrehozva

═══ DETAILS ═══
[ ] Favicon: T arany, obsidian háttér
[ ] CSS snippet bemásolva base.css-be
[ ] Mobile teszt minden szekcióra
[ ] Page speed > 80 mobilon
[ ] Selection highlight gold

═══ POLISH ═══
[ ] Section heading custom Liquid section létrehozva
[ ] Pure white #FFFFFF sehol — mind #F2EFE8 (bone)
[ ] Gold accent használata mértékkel (max 1-2 elem oldalanként)
```

---

## 🎯 MIÉRT EZ A RENDSZER NYER

A jelenlegi probléma a webshoppal: **nincs benne semmi felismerhető**.
Ha holnap dropolnád a logót, bármelyik dropshipping bolt lehetne.

Az "Obsidian Mythos" rendszer **3 dolgot ad hozzá**, amit a versenytársak nem fognak átkopipasztelni 5 perc alatt:

1. **Az obsidian-violet alapszín** (`#0A0813`) — mindenki vagy fekete vagy slate-et használ. A violet undertone = TISIDIAN signature.
2. **Az "Aurelion gold" champagne accent** (`#C9A96E`) — a hero termékről elnevezve. Brand-driven szín, nem random.
3. **A 3-fontos hierarchia** (Cormorant + Inter + JetBrains Mono) — ez egy múzeumi/archívum esztétikát ad ami illik a mythology naming-hez (Aurelion, Aetherion, Obsyrian).

**A vizuális moat 6 hónap konzisztens tartás után épül fel.** Ha most lefekteted ezt a rendszert és nem nyúlsz hozzá fél évig, a brand felismerhető lesz egyetlen képkockából is.

---

## 📚 KÖVETKEZŐ LÉPÉS

Ha ez a doksi végigment:

→ **`TISIDIAN-WEEK-1-TIKTOK-LAUNCH.md`** — ugyanezt a vizuális nyelvet kell vinni a TikTok content-be is. A Veo3 promptokba bele kell írni: "obsidian violet-black background, champagne gold accent, hand-set moissanite catching light".

A bolt és a TikTok content **egyazon vizuális világ** legyen. Ha a vásárló átjön a videóból a shopra, ne legyen context switch.

---

*Worn quietly. Engineered deliberately.*

— TISIDIAN
