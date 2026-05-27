# 09 — EMAIL FLOWS

Klaviyo. Ready-to-paste copy. Every email in voice.

---

## 1. Klaviyo setup

### List structure

Build these lists/segments from day one:

- **Master list** — every email subscriber and customer
- **Customers** — Shopify-synced, anyone who has purchased
- **Ledger members** — customers who have replied to the Ledger invitation
- **One-time buyers** — purchased once, no repeat
- **Repeat buyers** — purchased 2+ times
- **Dormant** — no activity 90+ days
- **Engaged non-buyers** — opened 3+ emails, never purchased

### Sender identity

```
From name:     Section B
From email:    correspondence@[brand].com
Reply-to:      correspondence@[brand].com
```

Never send from `noreply@`. Always allow replies. Replies become Ledger candidates.

### Email design

- Cream background (#E8E2D5) or off-white (#F5F1E8)
- Serif body (Cormorant Garamond)
- Monospace metadata blocks (JetBrains Mono)
- Single-column, max 600px wide
- No images except the brand wordmark at top (small, ~80px wide) or single hero image when relevant
- No buttons except where absolutely needed (use text links instead)
- Plaintext-only fallback works (no broken HTML when previewed by minimal mail clients)

### Subject line rules

- Lowercase or sentence case only. NO ALL CAPS.
- No emojis
- No question marks
- No "[FREE]" / "[NEW]" / "[OPEN ME]"
- Match the voice: dry, archival, specific

Examples of subject lines that work:
- *Estate 053 opens Tuesday at 19:00 GMT.*
- *Your acquisition has been logged.*
- *We have not heard from you since LOT 0049-A.*
- *Three lots remain in Estate 053.*

---

## 2. The welcome series (4 emails over 14 days)

Trigger: someone subscribes via Shopify newsletter signup or store form.

### Email 1 — Day 0 (sent immediately)

**Subject:** *You have been added to the correspondence.*

```
Your name has been added to the correspondence list.

Estates are released to this list before they are released elsewhere. 
Notice is sent in advance.

We do not send promotional offers. There are no discounts.

— Section B
```

### Email 2 — Day 3

**Subject:** *Field correspondence — Trieste, May.*

(This is a fictional field report. Rotate the city and month.)

```
A field correspondence we thought may be of interest.

──────────────────────────────────────────────

Trieste, May.

The estate was held in a private apartment above a bookbinder's 
on Via San Nicolò. The owner had passed in February. The keys were 
released to us in April.

The objects were arranged on a wooden desk. Most were in their 
original wrappings. None had been moved in several years.

Eleven items were catalogued. Seven have been retained for the 
archive. The remaining four were returned to the family.

Estate 053 will open shortly.

— Section B
```

### Email 3 — Day 7

**Subject:** *A preview from Estate 053.*

(Single image preview — one watch, dimmed, no full reveal.)

```
[ Single image: macro detail of one watch from upcoming estate ]

LOT 053-C

A preview from Estate 053. Full release pending.

— Section B
```

### Email 4 — Day 14

**Subject:** *Estate 053 opens this week.*

```
Estate 053 opens this Tuesday at 19:00 GMT.

Eleven items have been catalogued. They will be released
in sequence. Items typically reach final disposition within
five days of opening.

Notice was sent first to this list.

— Section B

──────────────────────────────────────────────

[link: enter the archive]
```

---

## 3. Post-purchase series (5 emails over 30 days)

Trigger: customer places first order.

### Email 1 — Day 0 (immediate)

**Subject:** *Your acquisition has been logged.*

```
Your acquisition has been logged.

ORDER     {{ order_name }}
DATE      {{ order_date }}
LOT       {{ lot_number }}

The object will leave our handling facility within 48 hours.
A separate dispatch notice will follow.

— Section B
```

### Email 2 — Day 2 (or when shipping label generated)

**Subject:** *Dispatch — LOT {{ lot_number }}.*

```
The object has left the handling facility.

LOT       {{ lot_number }}
DISPATCH  {{ ship_date }}
TRACKING  {{ tracking_number }}

Standard transit is five to ten days within Europe and 
North America. Customs duties are the recipient's responsibility.

— Section B
```

### Email 3 — Day 7

**Subject:** *We hope LOT {{ lot_number }} has settled.*

```
We hope LOT {{ lot_number }} has settled.

The object was running when received by the archive.
It should require no immediate service.

If correspondence is needed, the address below remains open.

— Section B
```

This email is intentionally strange. It's the parasocial hook. Customers love it.

### Email 4 — Day 14

**Subject:** *Care notes for LOT {{ lot_number }}.*

```
Care notes for the object in your possession.

──────────────────────────────────────────────

WIND
Once weekly. Crown should be unscrewed before turning.

POSITION
Stored face-up when not worn. The mainspring rests evenly.

LEATHER
The strap will deepen with use. No conditioning required.

CRYSTAL
Mineral. Mild scratches may be polished by a watchmaker.
Do not attempt at home.

SERVICE
Mechanical movements benefit from servicing every five years.
A watchmaker familiar with vintage movements is preferred.

──────────────────────────────────────────────

— Section B
```

### Email 5 — Day 30

**Subject:** *Correspondence is open.*

```
You have held LOT {{ lot_number }} for one month.

Correspondence with the archive is open. Replies to this 
address are received.

Future estates are released to a list before they reach 
the wider archive. You may join by replying with your name.

— Section B
```

This email is the **Ledger invitation**. Everyone who replies becomes a Ledger member. Track replies via Klaviyo's reply-detection or a simple manual review of the inbox.

---

## 4. Estate launch flow

Trigger: manual send when a new estate goes live.

### Email A — T-24h (Ledger members only)

**Subject:** *Estate 053 opens tomorrow at 19:00 GMT.*

```
Estate 053 opens tomorrow at 19:00 GMT.

Eleven items have been catalogued. Notice is being sent 
to this list 24 hours in advance.

──────────────────────────────────────────────

[ Optional: 1–2 preview images ]

— Section B
```

### Email B — At launch (full list)

**Subject:** *Estate 053 is now open.*

```
Estate 053 is now open.

ORIGIN     [city, est. year]
ITEMS      11
OPENED     {{ launch_datetime }}

[link: view the estate]

— Section B
```

### Email C — T+48h (full list, conditional)

**Subject:** *Three lots remain in Estate 053.*

(Send only if inventory has dropped below 30% of estate.)

```
Three lots remain in Estate 053.

LOT 053-B   Field automatic, charcoal dial — 1 of 1
LOT 053-F   Skeleton automatic, off-white — 1 of 2
LOT 053-J   Brass loupe, oxidized brass — 1 of 1

[link: view the estate]

— Section B
```

### Email D — T+5–7 days

**Subject:** *Estate 053 is closed.*

```
Estate 053 is closed.

Of eleven items catalogued, ten reached final disposition.
One remains, marked archived.

The next estate will open in approximately one week.

— Section B
```

---

## 5. Win-back flow (90+ days dormant)

Trigger: customer hasn't purchased in 90 days, hasn't unsubscribed.

### Email — single send

**Subject:** *We have not heard from you since LOT {{ last_lot }}.*

```
We have not heard from you since LOT {{ last_lot }}.

A new estate opens this week. We thought of you.

[link: enter the archive]

— Section B
```

That's the entire win-back. One email. No discount. No "we miss you!" The restraint is the conversion.

If they don't return after this email, they're added to a deeper-dormant list and re-targeted only twice per year with a "year's archive" recap.

---

## 6. Abandoned cart (modified)

Klaviyo's default abandoned cart flow needs full rewriting.

**DO NOT include:**
- Discount codes
- "Your items are still waiting!" urgency
- "Items selling fast!" stock anxiety
- Cart recovery pop-ups on store

**Instead, send:**

### Email — 4 hours after abandonment

**Subject:** *Your acquisition was not completed.*

```
The acquisition of LOT {{ lot_number }} was not completed.

The object remains available. The lot record is below.

[link: return to lot]

If the acquisition is no longer of interest, no action is needed.

— Section B
```

That's it. One email. No follow-ups. The world doesn't chase.

---

## 7. Field correspondence newsletter (quarterly, Ledger only)

Sent to Ledger members 4 times per year. Long-form. Builds the world.

**Format:** 800–1500 words. Single newsletter. Mix of:
- A "field report" from an estate
- A discussion of one object's provenance
- Mention of the next estate's region
- A fictional letter fragment

### Example structure

**Subject:** *Field correspondence — Q2 2026.*

```
A correspondence to the list.

── ── ── ── ── ── ── ── ── ── ── ── ── ── ──

Estate 049 closed in March. Of seventeen items, fifteen 
reached final disposition within nine days.

The estate originated in Geneva. The owner — referred to in 
documentation only as "M." — held the collection from 1987 
until 2003. The collection was sealed without instruction.

We received the items via an intermediary in May.

── ── ── ── ── ── ── ── ── ── ── ── ── ── ──

A note on LOT 049-D.

The watch was received without strap. A leather band of similar 
era was attached at the archive. The original is presumed lost 
in the years between sealing and release.

This is more common than not.

── ── ── ── ── ── ── ── ── ── ── ── ── ── ──

The next estate originates in Antwerp. We expect to open 
it in late June. Notice will follow.

— Section B
```

These emails don't sell. They build the world. The world sells.

---

## 8. SMS (optional, month 4+)

Klaviyo SMS, low-volume.

**Use cases (only):**
- Estate opening notice (24h before, Ledger only)
- Estate closing notice (T+5d)
- Order shipped notification (with tracking)

**Sample SMS:**

```
Estate 053 opens tomorrow at 19:00 GMT.
— Section B
```

```
Your dispatch has departed. Tracking: {{ tracking }}.
— Section B
```

That's it. No marketing SMS. No "Limited time! 10% off!" Ever.

---

## 9. The metrics that matter

Track these weekly. Ignore vanity metrics.

| Metric | Target |
|---|---|
| Welcome flow → first purchase rate | 8–15% |
| Post-purchase flow open rate | >55% |
| Estate launch email click rate | >20% (full list), >40% (Ledger) |
| Win-back conversion | 3–8% |
| Reply rate to "correspondence open" emails | 5–10% (these become Ledger members) |
| Unsubscribe rate per send | <0.3% |

---

## 10. The compounding effect

After 6 months:
- Welcome flow has converted ~12% of subscribers
- Post-purchase flow has 60%+ open rates because customers actually want the dispatch updates
- Ledger has 200–500 active members generating 40–60% of repeat revenue
- Quarterly correspondence newsletters get reposted on TikTok by fans

**Email is the only channel you fully own.** TikTok throttles. Algorithms shift. Email is the long-term moat. Build it from day one.
