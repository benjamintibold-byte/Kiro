# 🛟 TISIDIAN — SHOPIFY AI RESCUE & SAFE PROMPTS

A Shopify AI (Sidekick / Magic) **NEM tud** hosszú, többlépcsős tutorialt végrehajtani.
Ha bemásolsz neki egy 900 soros markdown doksit, **összezavarodik és törlést/módosítást csinál**, ami nem volt kérve.

Ez a fájl 3 dolgot tartalmaz:
1. **ROLLBACK** — visszaállítás, ha az AI elcseszte
2. **MIT NE ADJ AZ AI-NAK** — szabályok
3. **ATOMI PROMPTOK** — egyenként bemásolható mini-utasítások (1 prompt = 1 feladat)

---

## 1. 🔄 ROLLBACK — HA AZ AI ELCSESZTE

### A. Téma visszaállítása korábbi verzióra

A Shopify automatikusan menti az utolsó néhány theme verziót.

```
1. Shopify admin → Online Store → Themes
2. A jelenlegi Live theme mellett → ⋯ (3 pötty) → Edit code
3. A code editor BAL ALSÓ SARKÁBAN látsz egy linket:
   "Older versions" vagy "View older versions"
4. Kattints rá
5. Listát kapsz időpontokkal — válaszd a legutolsót, ami AI ELŐTT volt
6. "Restore" / "Visszaállítás" gomb
7. Confirm
```

> ✅ **Ez visszahozza:** minden theme code, CSS, Liquid, settings változást.
> ❌ **Ezt NEM hozza vissza:** törölt termékeket, page-eket, navigation menüt, metafieldeket.
> Ezeket alább kézzel kell javítani.

### B. Töröl page-ek visszaállítása

```
1. Online Store → Pages
2. Felső szűrő: "Status" → válaszd "Trash" / "Kuka"
3. Töröltek listája — kattints a kívántra → "Restore"
```

### C. Törölt termékek visszaállítása

```
1. Products → All products
2. Felső szűrő: kattints a státusz dropdown-ra → "Archived"
   (a Shopify nem tényleg törli, csak archiválja)
3. Kattints a termékre → "Activate"
```

### D. Főmenü helyreállítása

```
1. Online Store → Navigation → Main menu → Edit
2. Ha üres, hozzáadod manually:
   - Home          → /
   - Catalog       → /collections/all
   - Contact       → /pages/contact
3. Save
```

(A teljes "végleges" menüt majd a 3. szekcióban építjük fel.)

### E. Theme settings (színek, fontok) reset

```
1. Themes → Customize → Theme settings (alul)
2. Görgess végig — ha valamit "elszínezett" az AI:
   → Reset to default (minden szekció tetején van Reset link)
3. Save
```

---

## 2. 🚫 EZEKET SOSE ADD A SHOPIFY AI-NAK

A Shopify AI **jó** ezekre:
- ✅ Termékleírás megírás (1 termékre, 1 promptban)
- ✅ Kép alt-text generálás
- ✅ SEO meta description
- ✅ Email subject line ötletek

A Shopify AI **NEM jó** ezekre — ezeket **te csinálod kézzel**:
- ❌ CSS módosítás (`base.css` szerkesztés)
- ❌ Liquid kód írás vagy custom section létrehozás
- ❌ Theme settings (colors, fonts, layout) — Customize-ban kézzel
- ❌ Több page egyszerre létrehozás
- ❌ Navigation menu újraépítés
- ❌ Metafield definíciók
- ❌ Bármi, amiben "minden" / "the whole shop" / "all products" szerepel
- ❌ Markdown formátumú utasítások (`#`, `-`, ` ``` ` zavart okoz)

**Aranyszabály:**
> Ha az utasításod **több, mint 3 mondat**, vagy **több, mint 1 dolgot** csinál, akkor NE add a Shopify AI-nak.

---

## 3. 🤖 ATOMI PROMPTOK A SHOPIFY AI-NAK

Ezeket **egyenként** másold be (CTRL+C → CTRL+V), egyik a másik után.
**Várj minden prompt után**, hogy az AI befejezze, mielőtt a következőt küldöd.
Minden prompt EGY dolgot csinál.

### PROMPT #1 — Subtitle metafield létrehozás
```
Create a single product metafield definition with these exact settings:
- Namespace: custom
- Key: subtitle
- Name: Subtitle
- Type: Single line text
- Description: Short product subtitle, shown under product name on cards.

Do not create any other metafields. After creating, only confirm completion.
```

### PROMPT #2 — Story page létrehozás
```
Create a single new page with these exact settings:
- Title: The Story
- URL handle: story
- Visibility: Visible
- Body content: paste the text below exactly, without any modifications, edits, formatting changes, or AI rewrites.

Body text:

Tisidian was not invented. It was assembled.

We sourced from estates in Geneva, Antwerp, Osaka. We retained what held weight on the wrist. We discarded what didn't.

Each piece is named after something older than fashion — constellations, forgotten gods, sealed archives. The names carry weight the marketing cannot.

Worn quietly. Engineered deliberately.

— Section T

After creating, only confirm completion. Do not modify the text.
```

### PROMPT #3 — Craftsmanship page létrehozás
```
Create a single new page with these exact settings:
- Title: Craftsmanship
- URL handle: craftsmanship
- Visibility: Visible
- Body content: paste the text below exactly, without any modifications.

Body text:

MOVEMENT
Each automatic timepiece is fitted with a skeleton mechanical movement. 38–42 hour power reserve. Visible from front or caseback, depending on the model.

MATERIALS
Stainless steel cases. Hand-set moissanite stones on Signature line pieces. Sapphire-grade or reinforced mineral crystal.

WEIGHT
Tisidian pieces are intentionally heavy. A watch should be felt before it is seen.

WARRANTY
Two-year movement warranty on every timepiece. Unconditional.

After creating, only confirm completion.
```

### PROMPT #4 — Főmenü újraépítés
```
Update the Main menu navigation to have these exact 4 items in this exact order. First, remove all existing menu items. Then add:

1. Collections — link: /collections
2. The Story — link: /pages/story
3. Craftsmanship — link: /pages/craftsmanship
4. Contact — link: /pages/contact

Do not add any other items. Do not add submenus. Save and confirm.
```

### PROMPT #5 — AURELION termék subtitle
```
Update only the AURELION product. Set its custom.subtitle metafield to exactly:
Diamond-set · 42mm · Steel

Do not modify any other field on this product. Do not modify any other product. Save and confirm.
```

### PROMPT #6 — VANTH termék subtitle
```
Update only the VANTH product. Set its custom.subtitle metafield to exactly:
Skeleton automatic · 41mm

Do not modify any other field. Save and confirm.
```

### PROMPT #7 — OBSYRIAN termék subtitle
```
Update only the OBSYRIAN product. Set its custom.subtitle metafield to exactly:
Full moissanite · 40mm

Do not modify any other field. Save and confirm.
```

### PROMPT #8 — AETHERION termék subtitle
```
Update only the AETHERION product. Set its custom.subtitle metafield to exactly:
Multi-complication · 44mm

Do not modify any other field. Save and confirm.
```

### PROMPT #9 — LUMERA termék subtitle
```
Update only the LUMERA product. Set its custom.subtitle metafield to exactly:
Iced bracelet · 40mm

Do not modify any other field. Save and confirm.
```

### PROMPT #10 — PHANTOM termék subtitle
```
Update only the PHANTOM product. Set its custom.subtitle metafield to exactly:
Ultra-thin · 7mm case

Do not modify any other field. Save and confirm.
```

### PROMPT #11 — VALTHER termék subtitle
```
Update only the VALTHER product. Set its custom.subtitle metafield to exactly:
Multi-layer dial · 42mm

Do not modify any other field. Save and confirm.
```

### PROMPT #12 — ORIEN termék subtitle
```
Update only the ORIEN product. Set its custom.subtitle metafield to exactly:
Minimal automatic · 38mm

Do not modify any other field. Save and confirm.
```

### PROMPT #13 — VOID termék subtitle
```
Update only the VOID product. Set its custom.subtitle metafield to exactly:
Dark dial · 40mm

Do not modify any other field. Save and confirm.
```

### PROMPT #14 — Selected → Essentials kollekció átnevezés
```
Rename the existing collection currently titled "Selected" to "Essentials". Change only the title field. Do not modify the URL handle, the products, the description, or any other setting. Save and confirm.
```

> ⚠️ **Ha az URL handle is változik**, az SEO-nak rossz. Ha az AI azt mondja megváltoztatja az URL-t is, állítsd le és csináld kézzel:
> Collections → Selected → Title-t írd át "Essentials"-re, de a "URL handle" mezőt **HAGYD úgy ahogy van** (selected). Save.

---

## 4. ✋ EZEKET KÉZZEL — NE AI-VAL

### A. Színek beállítása (5 perc, kézzel)

```
1. Themes → Customize → bal alsó sarok: Theme settings
2. Colors szekció → Color schemes
3. "Background 1" scheme:
   Background:           #0A0813
   Text:                 #F2EFE8
   Button:               #C9A96E
   Button label:         #0A0813
   Secondary button:     #0A0813
   Secondary button txt: #F2EFE8
   Links:                #C9A96E
4. Save
```

### B. Fontok beállítása (3 perc, kézzel)

```
1. Themes → Customize → Theme settings → Typography
2. Headings: Cormorant Garamond, weight 500
3. Body: Inter, weight 400
4. Save
```

### C. Master CSS bemásolása (2 perc, kézzel)

```
1. Themes → Actions → Edit code
2. Bal oldali fa: Assets → base.css (vagy theme.css)
3. A FÁJL LEGELSŐ sora elé másold be a teljes alábbi CSS blokkot:
```

```css
/* ═══ TISIDIAN — OBSIDIAN MYTHOS DESIGN SYSTEM ═══ */

:root {
  --tis-obsidian:   #0A0813;
  --tis-ink:        #14101F;
  --tis-mist:       #1F1A2E;
  --tis-veil:       #2A2440;
  --tis-bone:       #F2EFE8;
  --tis-smoke:      #9590A8;
  --tis-ash:        #5B5670;
  --tis-gold:       #C9A96E;
  --tis-gold-glow:  #E0C088;
  --tis-crimson:    #6B1F2C;
  --tis-diamond:    #E8E6F0;
}

body {
  background: var(--tis-obsidian) !important;
  color: var(--tis-bone) !important;
}

.banner__heading,
h1.h1 {
  font-family: 'Cormorant Garamond', serif !important;
  font-weight: 600 !important;
  letter-spacing: 0.02em;
  color: var(--tis-bone);
}

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
  border-radius: 0 !important;
  transition: all 0.3s ease !important;
}
.button--primary:hover {
  background: var(--tis-gold) !important;
  color: var(--tis-obsidian) !important;
}

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
}

.price-item,
.price-item--regular {
  font-family: 'JetBrains Mono', 'IBM Plex Mono', monospace !important;
  font-size: 13px !important;
  color: var(--tis-bone) !important;
  letter-spacing: 0.05em;
  font-weight: 400 !important;
}

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
}
.header__menu-item:hover {
  color: var(--tis-gold) !important;
}

.footer {
  background: var(--tis-ink) !important;
  color: var(--tis-smoke) !important;
}
.footer a { color: var(--tis-smoke) !important; }
.footer a:hover { color: var(--tis-bone) !important; }

::selection {
  background: var(--tis-gold);
  color: var(--tis-obsidian);
}

@media (max-width: 749px) {
  .banner__heading,
  h1.h1 { font-size: clamp(28px, 8vw, 48px) !important; }
}

/* ═══ END TISIDIAN ═══ */
```

```
4. Save (jobb felső sarok)
5. Nézd meg az áruházat — frissítsd (Ctrl+F5)
```

### D. Section heading custom Liquid (5 perc, kézzel)

```
1. Themes → Edit code
2. Bal oldali fa: Sections folder
3. Felül "+ Add a new section" gomb
4. Név: tis-section-heading (csak ezt írd be, ne .liquid)
5. A megnyíló üres fájlba másold be a kódot a
   TISIDIAN-WEBSHOP-VISUAL-POLISH.md fájl 4. lépéséből
6. Save
7. Customize-ben már megjelenik mint "TIS Section Heading"
```

### E. Hero szekció módosítás (10 perc, kézzel)

```
1. Themes → Customize → Home page
2. Az "Image banner" sectionre kattints
3. Heading mező: CRAFTED FOR PRESENCE.
4. Description / subtext mező:
   Diamond-set timepieces, engineered for the few who arrive deliberately.
5. Button label: EXPLORE SIGNATURE
6. Button link: /collections/signature
7. Button style: Outline (NE solid)
8. Save
```

---

## 5. 🎯 BIZTONSÁGI WORKFLOW MOSTANTÓL

Ha újra szeretnél valamit változtatni a shopon:

```
LÉPÉS 1 — Minden változtatás ELŐTT
   Themes → Actions → Duplicate
   (mostantól van egy backup verziód)

LÉPÉS 2 — Próbáld ki előbb a duplicate-en
   Themes → a duplicate-nél: Customize / Edit code
   (NEM a Live themen!)

LÉPÉS 3 — Ha a duplicate jól néz ki
   Actions → Publish (a duplicate lesz Live)
   A régi Live automatikusan archived-be kerül backupnak

LÉPÉS 4 — AI használat szabálya
   1 prompt = 1 atomi feladat (lásd 3. szekció)
   SOHA NE adj neki tutorialt vagy markdown listát
   Mindig kérd, hogy "After completing, only confirm. Do not do anything else."
```

---

## 6. 📞 HA NEM MEGY

Ha bármelyik lépésnél elakadsz:

1. **NE csinálj több AI promptot** — minden prompt további kárt okozhat
2. Csinálj screenshotot arról, amit látsz
3. Küldd át nekem chaten, és pontról-pontra végigvezetlek

A legtöbb dolgot **a Shopify Customize panelján kézzel 5-10 perc alatt** be lehet állítani — gyorsabb mint AI-t küzdeni.

---

*Worn quietly. Engineered deliberately.*

— TISIDIAN
