# 🔧 TISIDIAN WEBSHOP — VÉGLEGES MÓDOSÍTÁSOK

Step-by-step tutorial. Csak kövesd a lépéseket. ~2 óra munka és launch-ready.

---

## 1. VENDOR JAVÍTÁS (2 perc)

**Mi a baj:** 8 terméknél "RareZ" a vendor, nem "TISIDIAN".

**Hogyan javítsd:**
```
1. Shopify Admin → Products
2. Pipáld ki MIND a terméket (felső checkbox)
3. Kattints "Bulk edit"
4. Keresd a "Vendor" oszlopot
5. Mindegyiknél írd át: TISIDIAN
6. Save
```

---

## 2. FAKE ÁTHÚZOTT ÁRAK TÖRLÉSE (3 perc)

**Mi a baj:** Az AURELION-nál "$549.99" áthúzva → "$399.99". Dropshipping signal.

**Hogyan javítsd:**
```
1. Shopify Admin → Products → AURELION
2. Pricing rész → "Compare-at price" → TÖRÖLD, hagyd ÜRESEN
3. Save
4. Ugyanez VANTH-nál és minden terméknél ahol van compare-at
```

**Lényeg:** csak az ár látszik, semmi áthúzás. Nincs sale. Soha.

---

## 3. PRODUCT URL-EK ÁTÍRÁSA (15 perc)

**Mi a baj:** `/products/moissanite-mens-watch-automatic-european-and-american-mechanical-steel-belt`
A vásárló látja a böngészőben. Instant lebukás.

**Hogyan javítsd termékenként:**
```
1. Products → [kattints a termékre]
2. Scroll: "Search engine listing" → Edit
3. URL and handle mező → írd át:

   AURELION       → aurelion
   VANTH          → vanth
   OBSYRIAN       → obsyrian
   AETHERION      → aetherion
   LUMERA         → lumera
   PHANTOM        → phantom (vagy noctre ha átnevezed)
   VALTHER        → valther (vagy regent)
   VAULTRÉ Box    → vaultre
   ORIEN          → orien
   ELYRA          → elyra
   VOID           → void (vagy obscura)
   LYSERA         → lysera

4. Save
```

Shopify automatikusan 301 redirect-et csinál a régi URL-ről.

---

## 4. IMAGE FILENAME-EK JAVÍTÁSA (30 perc)

**Mi a baj:** `make_the_watch_more_beautiful_202605252035.jpg` — jobb klikk → save → catastrophic.

**Hogyan javítsd:**
```
1. Shopify-ban a filename-et utólag NEM lehet átírni
2. Megoldás: töröld a képet → nevezd át a gépeden → újra feltöltöd

LÉPÉSEK:
a) Termék → Media → kattints a képre → Delete (egyenként)
b) A gépeden NEVEZD ÁT a fájlt:
   aurelion-01.jpg
   aurelion-02.jpg
   aurelion-wrist.jpg
c) Töltsd ÚJRA fel az átnevezett képet
d) Alt text: "AURELION gold automatic watch on dark surface"
e) Save
```

**Filenév formátum:**
```
[terméknév]-[sorszám].jpg

aurelion-01.jpg, aurelion-02.jpg, aurelion-wrist.jpg
vanth-gold-01.jpg, vanth-silver-01.jpg
obsyrian-silver-01.jpg, obsyrian-rosegold-01.jpg
vaultre-open.jpg, vaultre-closed.jpg
```

**Bonus: TinyPNG.com-on tömörítsd a képeket feltöltés előtt** — feleakkorára csökkenti a fájlméretet → page speed up.

---

## 5. SKU KÓDOK ÁTÍRÁSA (10 perc)

**Mi a baj:** `CJJX257690201AZ` — CJ Dropshipping kód, megjelenik packing slip-en.

**Hogyan javítsd:**
```
1. Termék → Variants → kattints a variantra
2. SKU mező → írd át:

   AURELION Gold         → TIS-AUR-GLD
   VANTH Gold/Belt       → TIS-VNT-GLD
   VANTH Silver/Belt     → TIS-VNT-SLV
   OBSYRIAN Rose Gold    → TIS-OBS-RSG
   OBSYRIAN Silver       → TIS-OBS-SLV
   AETHERION A           → TIS-AET-A
   AETHERION D           → TIS-AET-D
   AETHERION G           → TIS-AET-G
   LUMERA Black          → TIS-LUM-BLK
   LUMERA White          → TIS-LUM-WHT
   PHANTOM Black         → TIS-PHT-BLK
   stb.

3. Save minden variantnál
```

---

## 6. COLLECTION TYPO JAVÍTÁS (30 sec)

```
1. Products → Collections
2. "accesories" → Edit
3. Title: "Accessories"
4. Handle: "accessories"
5. Save
```

---

## 7. PRODUCT LEÍRÁSOK CSERÉJE (20 perc)

A régi copy tele "luxury", "premium", "limited" szavakkal. Cseréld ezekre:

### AURELION
```
Light, made structural.

Hand-set moissanite stones across a sculpted stainless 
steel frame. The exposed automatic movement runs visible 
beneath the dial. The weight sits with intent on the wrist.

Built for evenings. Made for presence.

— Stainless steel, gold finish
— Hand-set moissanite stones
— Automatic mechanical movement
— Scratch-resistant crystal
— Steel link bracelet
— 42mm case
```

### VANTH
```
Mechanics, made visible.

A skeleton automatic housed in a sculpted square steel 
case. Every gear, every ruby, every motion — engineered 
to be seen. Paired with a textured leather strap and 
dual-sided crystal.

For those who study what others ignore.

— Automatic mechanical movement, fully exposed
— Stainless steel, sculpted square case, 41mm
— Dual-sided crystal
— Genuine leather strap
— 38-hour power reserve
```

### OBSYRIAN
```
Engineered to dominate light.

Fully flooded moissanite setting across a sculpted square 
steel architecture. Maximum reflection, dense stone 
coverage, engineered weight.

A statement piece. Worn deliberately.

— Full moissanite stone setting, hand-placed
— Sculpted square stainless steel case
— Reinforced crystal
— High-reflection finish
— Heavyweight build (170g+)
— 40mm case
```

### AETHERION
```
Precision, made theater.

A layered automatic dial architecture in polished stainless 
steel with deep blue detailing. Visible mechanical 
complications, sculpted subdials — every element designed 
to be observed.

For those who collect watchmaking, not just watches.

— Automatic mechanical movement
— Exposed multi-complication architecture
— Sapphire-grade crystal
— Stainless steel case, 44mm
— Textured genuine leather strap
— 42-hour power reserve
```

### LUMERA
```
Defined by contrast.

A fully iced bracelet construction paired with a clean 
circular dial. Engineered to shift under light — sharp 
reflections, depth, cold presence from every angle.

Made for evening.

— Black or white dial finish
— Fully iced bracelet, hand-set moissanite
— Stainless steel construction
— Reinforced crystal
— Heavyweight wrist presence
```

### PHANTOM (vagy NOCTRE)
```
Built around absence.

The dial removes everything unnecessary. Floating hands 
beneath dark crystal, ultra-thin case, stainless steel 
mesh band. Engineered for everyday weight without weight.

— Ultra-thin case construction (7mm)
— Frameless floating dial design
— Stainless steel mesh bracelet
— Dark reflective mineral crystal
```

### VALTHER (vagy REGENT)
```
Built for command.

A layered black dial under sculpted gold-tone architecture. 
Multi-level face structure, sharp metallic detail, deliberate 
weight on wrist.

— Sculpted multi-layer dial
— Gold-tone case detail
— Textured genuine leather strap
— Reinforced mineral crystal
— 42mm case
```

### VAULTRÉ Box
```
A case for what stays close.

Solid walnut construction with a tempered glass top and 
soft-lined interior. Three positions, magnetic closure, 
no exterior markings.

— Walnut-finish hardwood
— Tempered glass display top
— Soft microfiber interior lining
— Three-watch capacity
— Magnetic closure
```

**Hogyan cseréled:**
```
1. Termék → Description → jelöld ki MINDENT → Delete
2. Paste az újat
3. Save
```

---

## 8. OLDALAK LÉTREHOZÁSA (15 perc)

### About oldal
```
Online Store → Pages → Add page
Title: About
```

Tartalom:
```
TISIDIAN exists to make considered watchmaking accessible.

Without the markup theater of legacy houses. Without the 
compromise of mass production.

Each piece is selected around presence: weighted construction, 
exposed mechanics, and finishes designed to settle into a 
wardrobe rather than shout from it.

We don't run sales. We don't release seasonal collections. 
We add what we believe in. We discontinue what doesn't hold up.

Worn quietly. Engineered deliberately.
```

### Returns & Shipping oldal
```
Title: Returns & Shipping
```

Tartalom:
```
SHIPPING

All orders ship within 48 hours of purchase.
Free worldwide shipping on orders over $250.
Standard delivery: 7–14 business days.
Tracking provided via email.

RETURNS

TISIDIAN accepts returns within 30 days of receipt.
Pieces must be in original condition with packaging.
Return shipping is covered for first-time customers.
Refunds processed within 5 business days.

WARRANTY

All timepieces carry a 2-year movement warranty.
Contact: correspondence@tisidian.com
```

### Contact oldal
```
Title: Contact
```

Tartalom:
```
For orders, questions, or partnerships:

correspondence@tisidian.com

Inquiries answered within 48 hours.
```

---

## 9. FOOTER BEÁLLÍTÁS (10 perc)

```
1. Themes → Customize → Footer
2. Add menu: About / Returns & Shipping / Contact
3. Trust signal text block:
   "Free shipping over $250 · 30-day returns · 2-year warranty"
4. Social: CSAK TikTok + Instagram (ha nincs YouTube/FB content, ne legyen ott)
5. Save
```

---

## 10. NAVIGATION MENU (5 perc)

```
Online Store → Navigation → Main menu

Legyen ENNYI:
   Shop          → /collections/all
   Signature     → /collections/signature
   Accessories   → /collections/accessories
   About         → /pages/about
   Contact       → /pages/contact

Töröld: "Home", "Catalog", "Blog" stb.
Save
```

---

## 11. EMAIL SZÖVEGEK (10 perc)

### Order confirmation
```
Settings → Notifications → Order confirmation
Subject: "TISIDIAN — Order confirmed"
Body szöveg cseréje:
  "Your order has been received. 
   Dispatch within 48 hours. 
   Tracking will follow separately."
```

### Shipping confirmation
```
Subject: "TISIDIAN — Your order has shipped"
Body:
  "Your piece is on its way.
   Tracking: {{ tracking_url }}
   Estimated delivery: 7-14 business days."
```

---

## 12. PAYMENTS (5 perc)

```
Settings → Payments
✅ Shopify Payments
✅ PayPal Express
✅ Apple Pay
✅ Google Pay
✅ Shop Pay
Save
```

---

## 13. SHIPPING (2 perc)

**Egyszerű verzió:**
```
Settings → Shipping and delivery
Töröld minden meglévő rate-et
Add 1 rate: "Free shipping" — $0, no minimum
Save
```

A $329+ árak amúgy is fedezik.

---

## 14. BIO LINK (1 perc)

```
TikTok profil → Edit → Website:
https://[domained]/products/aurelion

NE homepage. DIREKT az AURELION oldal.
```

---

## 15. MOBILE TESZT (10 perc)

iPhone Safari-ban végigmenni:
```
Homepage → Shop → AURELION → Add to Cart → Checkout

Ellenőrizd:
[ ] Page load < 3 másodperc
[ ] Képek nem pixelesek
[ ] Szöveg olvasható, nem lóg ki
[ ] "Buy" gomb scrollozás nélkül látszik
[ ] Cart drawer megnyílik rendesen
[ ] Apple Pay gomb megjelenik checkout-ban
[ ] Footer rendben van
```

---

## 16. EXTRA POLISH (10 perc)

### Announcement bar
```
Themes → Customize → Header → Announcement bar
"Free worldwide shipping on all orders"
```

### Favicon
```
Themes → Customize → Theme settings → Favicon
Tölts fel egy "T" logót 32×32px (Canva)
```

### SEO
```
Online Store → Preferences
Title: "TISIDIAN — Modern Watchmaking"
Meta description: "Considered timepieces. Engineered for presence. Free worldwide shipping."
```

---

## ✅ VÉGLEGES CHECKLIST

```
[ ] Vendor: mind TISIDIAN
[ ] Compare-at-price: mind törölve
[ ] URL handle-ek: mind clean (aurelion, vanth, stb.)
[ ] Image filename-ek: átnevezve + újratöltve
[ ] SKU kódok: TIS-XXX-XXX formátum
[ ] Collection typo: "accessories" rendben
[ ] Product leírások: új copy minden terméknél
[ ] Pages: About + Returns + Contact létezik
[ ] Footer: trust signals + helyes menü
[ ] Navigation: clean, max 5 pont
[ ] Checkout email-ek: átírva
[ ] Payments: Apple Pay + Google Pay + Shop Pay BE
[ ] Shipping: free
[ ] Bio link: direkt /products/aurelion
[ ] Mobile teszt: minden OK
[ ] Favicon: fent
[ ] SEO: title + meta kitöltve
[ ] Announcement bar: aktív
```

Ha mind ki van pipálva: **TISIDIAN PROFI. LAUNCH READY.**

Innen → [`TISIDIAN-WEEK-1-TIKTOK-LAUNCH.md`](./TISIDIAN-WEEK-1-TIKTOK-LAUNCH.md)
