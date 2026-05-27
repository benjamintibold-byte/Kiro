# 🚀 TISIDIAN DEPLOY PACKAGE

5 fájl. 10 perc. Semmi AI. Az egész vizuális rendszer felkerül a shopra.

---

## ⚠️ ELŐKÉSZÜLET (1 perc) — KÖTELEZŐ

Mielőtt bármit teszel, csinálj backup-ot a témáról:

```
Shopify admin → Online Store → Themes
→ Live theme mellett: Actions (⋯) → Duplicate
```

Most van egy másolatod. Ha bármi rossz lenne, **Actions → Publish** a régi másolaton, és minden visszaáll.

---

## 📦 MI VAN A CSOMAGBAN

| # | Fájl | Hova megy | Mit csinál |
|---|---|---|---|
| 1 | `01-tisidian-system.css` | `Assets/` (base.css elejére) | A teljes vizuális rendszer (színek, fontok, gombok, kártyák) |
| 2 | `02-tis-section-heading.liquid` | `Sections/` (új fájlként) | Centered ALL CAPS section heading taglinevel |
| 3 | `03-tis-trust-bar.liquid` | `Sections/` (új fájlként) | "FREE SHIPPING · 2Y WARRANTY · SECURE CHECKOUT" sáv |
| 4 | `04-tis-story-block.liquid` | `Sections/` (új fájlként) | "An archive, not a brand" story szekció gombbal |
| 5 | `05-tis-newsletter.liquid` | `Sections/` (új fájlként) | "Join the inner circle" email capture |

---

## 🎬 DEPLOYMENT — 6 LÉPÉS

### 1. lépés — Nyisd meg a code editort

```
Shopify admin → Online Store → Themes
→ Live theme mellett: Actions (⋯) → Edit code
```

### 2. lépés — Másold be a CSS-t (2 perc)

```
1. Bal oldali fa → Assets folder
2. Görgess le, keresd: base.css (vagy theme.css)
3. Kattints rá — megnyílik a kód
4. Ugorj a fájl LEGELEJÉRE (Ctrl+Home)
5. Nyisd meg ebben a repóban: 01-tisidian-system.css
6. Másold a teljes tartalmát (Ctrl+A → Ctrl+C)
7. Vissza Shopify-ban → szúrd be a fájl ELEJÉRE (Ctrl+V)
8. Save (jobb felső sarok)
```

### 3. lépés — Add hozzá a 4 új sectiont (5 perc)

Mindegyik section esetén ugyanaz:

```
1. Bal oldali fa → Sections folder
2. Felül: "+ Add a new section" gomb
3. Adj meg nevet (a fájlnévből, .liquid kiterjesztés NÉLKÜL):
   pl: tis-section-heading
4. Az új üres fájl megnyílik
5. Töröld ki, ami benne van
6. Másold ki a repóból a megfelelő .liquid fájl tartalmát
7. Paste a Shopify editorba
8. Save

Ismételd ezt a 4 fájlra:
   - tis-section-heading
   - tis-trust-bar
   - tis-story-block
   - tis-newsletter
```

### 4. lépés — Theme settings (3 perc)

```
1. Themes → a Live theme nagy "Customize" gombja
2. Bal alsó sarok → "Theme settings"

   COLORS szekció — Background 1 scheme:
     Background:           #0A0813
     Text:                 #F2EFE8
     Button:               #C9A96E
     Button label:         #0A0813
     Secondary button:     #0A0813
     Secondary button txt: #F2EFE8
     Links:                #C9A96E

   TYPOGRAPHY szekció:
     Headings:  Cormorant Garamond, weight 500
     Body:      Inter, weight 400

3. Save
```

### 5. lépés — Homepage szekciók hozzáadása (5 perc)

```
1. Themes → Customize → bal oldalt fent: Home page
2. A bal oldali sávban látod a meglévő szekciókat
3. Hozzáadás: "Add section" gomb

Add hozzá EZT A SORRENDET:

   1. Image banner            (megvan, csak polish)
      → Heading: CRAFTED FOR PRESENCE.
      → Description: Diamond-set timepieces, engineered for the few who arrive deliberately.
      → Button label: EXPLORE SIGNATURE
      → Button link: /collections/signature
      → Button style: Outline

   2. TIS Trust Bar           (új)

   3. TIS Section Heading     (új)
      → Title: SIGNATURE
      → Tagline: The cornerstone of Tisidian.

   4. Featured collection     (megvan: Signature kollekció)

   5. TIS Story Block         (új)

   6. TIS Section Heading     (új, második példány)
      → Title: ESSENTIALS
      → Tagline: Quiet pieces, daily worn.

   7. Featured collection     (megvan: Selected/Essentials)

   8. TIS Newsletter          (új)

4. Save
```

### 6. lépés — Ellenőrzés (1 perc)

```
1. Új fülön: nyisd meg a shopot
2. Ctrl+Shift+R (force refresh)
3. Nézd:
   ✓ Háttér mély violet-fekete (#0A0813)
   ✓ Hero gomb champagne arany kerettel
   ✓ Trust bar a hero alatt
   ✓ "SIGNATURE" középre, ALL CAPS, ritkítva, két vonallal
   ✓ "ESSENTIALS" ugyanúgy
   ✓ Story block a Signature alatt
   ✓ Newsletter a végén
4. Mobilon is nézd (telóról vagy F12 → mobile view)
```

---

## 🐛 HA VALAMI ROSSZ

```
Themes → backup duplicate-edre menj → Actions → Publish
```

30 másodperc. Visszaáll minden.

---

## 🧠 EZUTÁN MI HIÁNYZIK MÉG

A csomag **csak a vizuális rendszert** telepíti. NEM telepíti:

- ❌ Page-eket (`/pages/story`, `/pages/craftsmanship`) — kézzel hozod létre
- ❌ Termék subtitle-eket — metafield + termékenként beírod
- ❌ Navigation menüt — kézzel állítod
- ❌ Selected → Essentials kollekció átnevezést

Ezekhez lásd: `TISIDIAN-SHOPIFY-AI-RESCUE.md` 3. és 4. szekció (atomi promptok + kézi lépések).

---

## ⚡ TLDR

```
1. Backup (Duplicate)
2. CSS-t base.css elejére
3. 4 új section fájl létrehozás + paste
4. Theme settings: színek + fontok
5. Homepage: szekciók hozzáadása sorrendben
6. Refresh, ellenőrzés
```

10 perc. Egy az egyben. Készen.

— TISIDIAN
