# 04 — SHOPIFY BUILD

The store is a museum interface that happens to sell things. Every default Shopify pattern needs to be stripped, renamed, or hidden.

---

## 1. Stack

- **Shopify Basic** — $29/mo. Basic plan is enough for the first $100K. Don't upgrade prematurely.
- **Theme:** Dawn (free, fastest, easiest to strip). Or Symmetry/Impact if you want more flexibility ($300 one-time).
- **Domain:** `.com` only. Buy via Shopify or transfer in. Never use a free `.myshopify.com` for anything customer-facing.
- **Email infrastructure:** Klaviyo from day one. Free up to 250 contacts.
- **Payments:** Shopify Payments + PayPal as fallback. Apple Pay, Google Pay enabled.

### Apps stack (minimum viable)

| App | Purpose | Cost |
|---|---|---|
| Klaviyo | Email + SMS | Free → $20/mo |
| Judge.me | Reviews (rebrand to "Field Reports") | Free |
| Loox | Photo reviews (optional) | $10/mo |

That's it. **No popups, no spin-the-wheel, no exit-intent, no countdown timers, no "X people viewing now," no abandoned cart SMS popups.** Every one of those tools converts +2% short-term and destroys the brand long-term.

---

## 2. Theme settings (Dawn)

After installing Dawn, make these changes in **Online Store → Themes → Customize**.

### Theme settings → Colors

```
Background 1:       #0C0B0A    (vault black)
Background 2:       #1A1816    (charcoal)
Text:               #D4CFC6    (bone)
Buttons bg:         transparent (or #0C0B0A)
Buttons text:       #D4CFC6
Outline button:     #2A2725 border, transparent background
Accent 1:           #7A2A20    (oxidized red)
Accent 2:           #8A8279    (stone)
```

### Theme settings → Typography

```
Headings:    Cormorant Garamond, weight 500, scale 100%
Body:        Cormorant Garamond, weight 400, scale 100%
```

(Shopify font picker may not have Cormorant. Upload via custom font in Settings → Files, or use the Cormorant Garamond Google Fonts integration.)

### Theme settings → Layout

```
Page width:           1200px
Spacing between sections:  Large
Section padding:      Default
```

### Theme settings → Buttons

```
Border radius:        0px       (no rounded buttons)
Shadow:               None
Border thickness:     1px
```

### Theme settings → Cards

```
Card style:           Standard
Card color scheme:    Background 1
Border thickness:     0px
Corner radius:        0px
Shadow:               None
```

### Theme settings → Animations

```
Reveal sections on scroll:    OFF
Hover on images:              None
```

No motion. Everything still. Movement breaks the world.

---

## 3. Page structure

### Homepage (one screen, one decision)

Use the "Image with text" section, full-width, with these settings:

```
Image:                Full-bleed dimmed B&W photograph (you will shoot this)
Image height:         Large
Heading:              "An archive of unbranded objects."
Subtext:              "Selected, not designed."
Button:               "→ enter the archive"
Button style:         Outline / minimal
Button link:          /collections/archive
```

**Remove every other section from the homepage.** No featured products. No collection list. No testimonials. No newsletter sign-up section (handle that elsewhere). No "shop by category."

### Navigation

Header (top):
- **Brand wordmark only** (left or center). No tagline visible in header.
- **Hidden hamburger menu** containing:
  - Archive
  - Estates
  - Provenance
  - Correspondence
- **Cart icon** (right), labeled blank or with object count only

Footer:
- Correspondence (contact form)
- Provenance (about page)
- Field Reports (reviews aggregator)
- Logistics (shipping, returns, FAQ)
- The Ledger (signup, only after launch month 3+)

No social icons in footer except subtle small text links (`tiktok.com/@brand`). No `Follow us!` text.

### Catalog page (`/collections/archive`)

Layout:
- **Grid:** 3 columns desktop, 2 columns mobile
- **No filter sidebar with price/availability defaults**
- **Custom filters:** by Estate (collection), by Era (tag), by Material (tag)
- **Sort default:** Manual / "By estate"
- **Sold-out items remain visible**, marked `archived` in monospace below the title

Each tile:
```
[ Single object photograph, square, no hover effect ]
LOT 0049-A
129
```

That's it. No product description preview, no "Quick add" button, no rating stars on the tile.

### Product page

Use a custom Liquid template. Below is the structure:

```
[ Hero image, square, single shot — no carousel arrows ]

LOT 0049-A
Field automatic, off-white dial, 38mm

[ 3-line mythology, serif, italic ]
Recovered from an estate in Geneva.
The previous owner left only a name 
written on the inside of the case.
We have not verified it.

[ Metadata block, monospace ]
ORIGIN     Geneva, est. 1990s
CONDITION  Excellent, minor wear
MOVEMENT   Mechanical automatic
CASE       Stainless, 38mm
STRAP      Leather, brown, aged
RESERVE    ~38 hours
LOT        0049-A

129

[ acquire ]   ← single matte black button

──── below the fold ────

[ 3 secondary photographs, vertical stack, single column ]

[ Field reports section — 3-5 reviews max, styled as letters ]

[ "From the same estate" — 2 related products, smaller tiles ]
```

### Product page Liquid snippet (for `templates/product.json` or section)

```liquid
{%- assign product_metadata = product.metafields.custom -%}

<section class="product-archive">
  <div class="product-archive__hero">
    <img src="{{ product.featured_image | image_url: width: 1200 }}" 
         alt="{{ product.title }}" 
         loading="eager" />
  </div>

  <div class="product-archive__info">
    <p class="lot-number">{{ product_metadata.lot_number }}</p>
    <h1 class="product-title">{{ product.title }}</h1>
    
    <div class="mythology">
      {{ product.description }}
    </div>

    <dl class="metadata">
      <dt>ORIGIN</dt>     <dd>{{ product_metadata.origin }}</dd>
      <dt>CONDITION</dt>  <dd>{{ product_metadata.condition }}</dd>
      <dt>MOVEMENT</dt>   <dd>{{ product_metadata.movement }}</dd>
      <dt>CASE</dt>       <dd>{{ product_metadata.case_spec }}</dd>
      <dt>STRAP</dt>      <dd>{{ product_metadata.strap }}</dd>
      <dt>RESERVE</dt>    <dd>{{ product_metadata.reserve }}</dd>
      <dt>LOT</dt>        <dd>{{ product_metadata.lot_number }}</dd>
    </dl>

    <p class="price">{{ product.price | money_without_currency | remove: '.00' }}</p>

    {% form 'product', product %}
      <button type="submit" name="add" class="btn-acquire">acquire</button>
    {% endform %}
  </div>
</section>
```

### Product page CSS (paste into `assets/base.css` or theme custom CSS)

```css
/* See full dark-mode CSS in 02-visual-system.md section 9 */
/* Key values for the dark store: */

body {
  background: #0C0B0A;
  color: #D4CFC6;
}

.product-archive {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  max-width: 1200px;
  margin: 4rem auto;
  padding: 0 2rem;
  font-family: 'Cormorant Garamond', serif;
  color: #D4CFC6;
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

@media (max-width: 768px) {
  .product-archive {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
}
```

---

## 4. Cart drawer

Customize via `sections/cart-drawer.liquid` (or theme equivalent):

```
Header:           "Acquisitions in progress"
Empty state:      "No acquisitions in progress."
Subtotal label:   "Total"
Tax label:        "Duty"
Checkout button:  "Confirm acquisition"
```

Replace any "Edit cart," "Continue shopping" text with similar archival language ("Return to archive").

---

## 5. Checkout

Shopify checkout customization is limited on Basic plan. Focus on what you CAN change:

### Settings → Checkout → Customer information

- Order confirmation page heading: `"Your acquisition has been logged. A dossier will follow."`
- Customize the rest minimally.

### Order confirmation email (Settings → Notifications)

Replace default order confirmation HTML with a stripped-down version:

```html
<p style="font-family: 'Cormorant Garamond', serif; font-size: 14px;">
  Your acquisition has been logged.
</p>

<p style="font-family: 'JetBrains Mono', monospace; font-size: 11px; letter-spacing: 0.05em;">
  ORDER {{ order_name }}<br>
  {{ created_at | date: "%Y-%m-%d" }}
</p>

{% for line in line_items %}
<p style="font-family: 'JetBrains Mono', monospace; font-size: 11px;">
  {{ line.title }} — LOT {{ line.product.metafields.custom.lot_number }}
</p>
{% endfor %}

<p style="font-family: 'Cormorant Garamond', serif; font-size: 14px;">
  Your object will leave our handling facility within 48 hours. 
  A separate dispatch notice will follow.
</p>

<p style="font-family: 'Cormorant Garamond', serif; font-size: 11px; color: #7A756D;">
  — Section B
</p>
```

(Replace `Section B` with whatever signature your brand uses internally.)

---

## 6. Pages

### Provenance (`/pages/provenance`)

Single page, ~200 words. Example:

> The archive holds objects of partial provenance.
> 
> Items are received in lots from estates, brokerages, and private handlers. Their condition is documented at receipt. Their full history is rarely complete.
> 
> Where possible, we record what we know. Where we do not know, we say so.
> 
> Acquisitions are routed through Section B. Correspondence may be sent to the address below.
> 
> — Section B

### Logistics (`/pages/logistics`)

The shipping/returns page. Same voice. Example:

> **Dispatch.** Objects leave the handling facility within 48 hours of acquisition. Tracking is provided by separate dispatch notice.
> 
> **Transit.** Standard transit is 5–10 days within Europe and North America, 8–14 days elsewhere. Customs duties are the recipient's responsibility.
> 
> **Returns.** Objects may be returned within 14 days of receipt in original condition. Return postage is borne by the recipient. Refunds are processed within 5 business days of receipt.
> 
> **Inquiries.** Routed via Correspondence.

### Correspondence (`/pages/correspondence`)

A simple form, no chatbot. Fields:
- Name (initials accepted)
- Email
- Subject
- Message

Submit button: `"Send."` Confirmation: `"Your message has been logged."`

### Field Reports (`/pages/field-reports`)

Aggregated reviews. Style each review as a typed letter. Use Judge.me's template customization or build via Liquid loop over reviews.

---

## 7. Metafields setup

Set up product metafields in **Settings → Custom data → Products**.

| Namespace | Key | Type | Description |
|---|---|---|---|
| custom | lot_number | Single line text | e.g., "0049-A" |
| custom | origin | Single line text | "Geneva, est. 1990s" |
| custom | condition | Single line text | "Excellent, minor wear" |
| custom | movement | Single line text | "Mechanical automatic" |
| custom | case_spec | Single line text | "Stainless, 38mm" |
| custom | strap | Single line text | "Leather, brown, aged" |
| custom | reserve | Single line text | "~38 hours" |
| custom | era | Single line text | "1990s" (for filtering) |
| custom | material | List of single line text | ["steel", "leather"] |
| custom | estate_id | Single line text | "049" |

Use these in product templates and collection filters.

---

## 8. Collections

Create one collection per estate. Naming convention:

```
estate-049-geneva
estate-052-antwerp
estate-055-osaka
```

Display names: `Estate 049 — Geneva, sealed 2003`

Use these as your primary navigation. The "Archive" main collection contains everything; estate collections are the storytelling layer.

---

## 9. The launch checklist

Before going live, verify every item:

```
[ ] Brand wordmark in header, no other text
[ ] Homepage = single image + tagline + single CTA
[ ] No "Featured products" or "Best sellers" anywhere
[ ] No popup of any kind on first visit
[ ] No newsletter modal
[ ] Footer reads: Correspondence / Provenance / Field Reports / Logistics
[ ] Cart drawer says "Acquisitions in progress"
[ ] Checkout button says "Confirm acquisition"
[ ] Order confirmation email rewritten in voice
[ ] Shipping/dispatch email rewritten in voice
[ ] All product pages use the metadata block format
[ ] All photographs use the LUT
[ ] Klaviyo welcome flow live
[ ] Klaviyo post-purchase flow live
[ ] Provenance, Logistics, Correspondence pages written
[ ] Field Reports page exists (can be empty for first 30 days)
[ ] No emojis, "you," or exclamation points anywhere
[ ] Mobile experience checked (most traffic is mobile)
[ ] Page speed > 80 on Lighthouse
[ ] Free shipping threshold removed (no shipping bar nags)
[ ] Currency auto-detect enabled, no switcher prominent
```

---

## 10. The forbidden Shopify patterns

These ship by default and must be removed:

- ❌ "Featured collection" sections
- ❌ "Customers also bought" upsells on product page (use post-purchase only)
- ❌ "Free shipping over $X" announcement bar
- ❌ "Sign up for 10% off" newsletter popup
- ❌ "X people are viewing this" stock anxiety widgets
- ❌ Countdown timers
- ❌ "Sale" badges on collection tiles
- ❌ Compare-at-price strikethroughs
- ❌ "Add to wishlist" hearts (the world doesn't have wishlists)
- ❌ Live chat bubble in corner
- ❌ Trust badges row ("Free returns! Secure checkout!")

The store should feel **almost empty.** That's the point.
