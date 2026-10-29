# TraceDesk: Brand Guidelines
Color palette, typography and layout · Version 1.1 · October 2026

Version 1.1 updates v1.0 (May 2026) to document the full-width color bands used on the September 2026 one-pager, clarifies text colors on green, and moves to US spelling. The reference layout is `tracedesk_onepager_09092026.pdf`. Verbal identity: [`brand-voice.md`](brand-voice.md).

---

## Brand character

TraceDesk serves procurement teams in manufacturing, logistics, construction and food & beverage. The brand should feel **precise, reliable, and quietly confident** — the design equivalent of a tool that does exactly what it says, without fuss. Not clinical. Not playful. Not startup-energetic. Earned trust, clearly communicated.

The visual identity draws from industrial precision and natural authority: deep navies, warm off-whites, and a forest green that signals compliance and safety without the sterility of a hospital palette.

---

## Color palette

### Primary colors

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **Midnight** | `#1A2332` | 26, 35, 50 | Primary text, headlines, structural UI, dark backgrounds and bands |
| **Compliance** | `#2F6B4A` | 47, 107, 74 | Primary CTA buttons, positive status, accent highlights, logo italic, and full-width stat and quote bands (see Color bands) |
| **Parchment** | `#F5F3EE` | 245, 243, 238 | Page background, primary surface; text on dark and on solid green |
| **Slate** | `#3A4452` | 58, 68, 82 | Body text, secondary headings, softer structural elements |

### Secondary colors

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **Amber** | `#C8954A` | 200, 149, 74 | Warning states, expiring soon indicators, caution |
| **Alert** | `#C0392B` | 192, 57, 43 | Error states, lapsed status, critical flags |
| **Warm grey** | `#D8D4CC` | 216, 212, 204 | Borders, dividers, disabled states |
| **Linen** | `#EAE7DF` | 234, 231, 223 | Card backgrounds, secondary surfaces, hover states |
| **Forest** | `#1C4A34` | 28, 74, 52 | Text on tinted light-green backgrounds (such as the Compliant badge) |

### Color principles

- **Midnight** is the structural color. It replaces pure black everywhere — it reads as authoritative without harshness.
- **Compliance green** earns its meaning through restraint. Use it for positive status, primary CTAs, the italic in the wordmark, and the defined color bands below. Never use it as a page background or for decorative fills.
- **Parchment** is the page background throughout. It distinguishes TraceDesk from the clinical white-on-white defaults of enterprise SaaS and reinforces warmth without sacrificing professionalism.
- **Amber and Alert** are reserved strictly for status communication. Do not use them decoratively.
- Gradients, glows, and drop shadows are not part of the TraceDesk visual language.

---

## Color bands

Full-width bands break up a page and carry the proof. They are used on the one-pager for the headline, the stat strip, the quote and the call to action.

| Band | Background | Text | Typical content |
|------|-----------|------|-----------------|
| **Header / footer** | Midnight | Parchment (headline in Instrument Serif; supporting copy in DM Sans 300) | Wordmark, headline, call to action |
| **Stat band** | Compliance `#2F6B4A` | Parchment | 3–4 headline numbers: numeral in Instrument Serif 48–64px; label in DM Sans 12–13px; source line in italic 11px |
| **Quote band** | Midnight or Compliance | Parchment (quote in Instrument Serif italic; attribution in DM Sans 13–15px) | One customer quote with name, title and company |

**Rules for green bands**

- Up to **two** solid Compliance bands per page, and together no more than about a quarter of the page area.
- Text on solid Compliance green is **Parchment** (contrast about 5.7:1). Do not use Forest or Warm grey for body text on solid green; Warm grey is acceptable for large text only.
- Source lines under stats stay at 11px or larger.
- Bands are flat: no gradients, no shadows, no pattern fills.
- Never use Compliance green for the page background or for large areas inside body content.

**Forest on tinted green:** on light-green tinted surfaces (the Compliant badge background `#E8F3EE`, icon tiles) use **Forest** `#1C4A34` for text.

---

## Status color system

These four states appear throughout the product UI and should be used consistently across all customer-facing materials.

| State | Background | Text | Dot | Label |
|-------|-----------|------|-----|-------|
| **Compliant** | `#E8F3EE` | `#1C4A34` | `#2F6B4A` | "Compliant" |
| **Expiring soon** | `#FBF0E0` | `#6B3D0A` | `#C8954A` | "Expiring soon" |
| **Lapsed** | `#FAECEA` | `#7A1A14` | `#C0392B` | "Lapsed" |
| **Pending upload** | `#EAE7DF` | `#3A4452` | `#8A8880` | "Pending upload" |

Status badges use a small filled circle (6px) paired with the label text. Never use status colors outside of their defined states.

---

## Typography

### Type system

TraceDesk uses a two-family system: **Instrument Serif** for display and emotional emphasis, **DM Sans** for all UI and body copy.

This pairing is deliberate. Instrument Serif gives the brand warmth and confidence at large sizes — it signals "we've thought carefully about this" without being ornate. DM Sans is clean, highly legible, and slightly less sterile than neutral grotesques like Inter or Roboto, which reinforces the brand's approachable-but-professional character.

### Instrument Serif

- **Use for:** Hero headlines, taglines, large display copy, stat numerals, the wordmark
- **Italic variant:** Use for key phrases, emotional emphasis, the "Desk" in the wordmark, and any pull quote or testimonial callout
- **Do not use for:** Body copy, UI labels, navigation, anything below 24px
- **Fallback:** Georgia, serif

```
Display / hero:   48–64px, regular or italic
Stat numerals:    48–64px, regular
Section headline: 32–40px, regular
Subheading:       24–28px, italic for emphasis
```

### DM Sans

- **Use for:** All body copy, UI labels, navigation, buttons, form fields, metadata, captions
- **Weights in use:** 300 (body), 500 (headings, labels, bold)
- **Do not use 700 or above** — it reads heavy against the warm palette
- **Fallback:** system-ui, sans-serif

```
Section heading:  22px, weight 500
Body copy:        15–16px, weight 300, line-height 1.7
UI labels:        13px, weight 500
Metadata / tags:  11px, weight 500, uppercase, letter-spacing 0.1em
Source lines:     11px, italic
```

### Type color rules

- **Midnight** (`#1A2332`) — all headings, primary body copy
- **Slate** (`#3A4452`) — secondary body copy, supporting text
- **Medium grey** (`#5A6372`) — metadata, captions, placeholder text
- **Light grey** (`#8A8880`) — disabled text, very secondary information
- Text on dark backgrounds (Midnight): **Parchment** (`#F5F3EE`) or **Warm grey** (`#D8D4CC`)
- Text on solid Compliance green: **Parchment** (`#F5F3EE`)
- Text on tinted light-green surfaces: **Forest** (`#1C4A34`)

---

## Wordmark

The wordmark is set in Instrument Serif. "Trace" is in regular weight in Midnight. "Desk" is in italic in Compliance green.

```
TraceDesk   →   "Trace" (#1A2332, regular) + "Desk" (#2F6B4A, italic)
```

On Midnight backgrounds, "Trace" is Parchment and "Desk" stays Compliance green (or a lighter tint for contrast).

**Usage rules:**
- Never separate "Trace" and "Desk" into two lines
- Never use the wordmark in colors other than the approved combination, or all-Midnight on light backgrounds
- Minimum size: 18px in digital, 12mm in print
- Clear space: equal to the height of the capital "T" on all sides

---

## Buttons

| Variant | Background | Text | Use for |
|---------|-----------|------|---------|
| **Primary** | `#1A2332` | `#F5F3EE` | Main actions, navigation CTAs |
| **Accent** | `#2F6B4A` | `#F5F3EE` | "Book a demo," "Start a free trial," conversion actions |
| **Secondary** | Transparent | `#1A2332` | Secondary actions, "Learn more", outlines |

Button typography: DM Sans, 13px, weight 500. Border radius: 6px. No uppercase.

The primary call to action is **Book a demo**; the secondary is **Start a free trial**.

---

## One-pager structure (reference layout)

1. Midnight header band: wordmark, category label, hero headline (Instrument Serif), one-sentence definition.
2. Parchment intro paragraph.
3. Compliance green stat band: four numbers, each with a one-line label and a source line.
4. "How it works" section: three Linen cards, each with an icon tile, an uppercase label, a heading and a short paragraph.
5. Midnight quote band with one customer quote.
6. Module cards (CertVault, RenewalPulse, RiskMap, SyncBridge) and a product screenshot.
7. Midnight footer band with the call to action and a green accent button.

---

## Do and don't

| Do | Don't |
|----|-------|
| Use Instrument Serif italics for hero statements and emotional emphasis | Use Instrument Serif for body copy or UI labels |
| Use Midnight as the primary structural and text color | Use pure black (`#000000`) |
| Use Parchment as the page background | Default to pure white |
| Use Compliance green for positive status, primary CTAs and up to two full-width bands per page | Use Compliance green as a page background or decorative fill |
| Use Parchment text on solid green; Forest on tinted light green | Put Forest or Warm grey body text on solid Compliance green |
| Use the Amber / Alert / Compliant system consistently for status | Invent new status colors or use status colors decoratively |
| Design flat — clean surfaces, sharp borders, no shadows | Use gradients, drop shadows, glows, or abstract illustrative shapes |
| Use DM Sans 300 for body | Use heavy weights (600+) |

---

## Voice alignment

The visual identity should reinforce the verbal identity. The "stop chasing vendors" message works in part because it's direct and specific — the design should feel the same way. Every visual choice should communicate: **we understand your world, we've solved the problem precisely, and you can trust this.**

Avoid: playful illustrations, abstract tech imagery, purple gradients, startup-style geometric patterns, anything that signals "we are a disruptor." The customer base is procurement teams at manufacturing, logistics, food and construction companies — they want a tool that earns confidence, not one that performs excitement.

---

## Fonts — installation

| Font | Source | Weights needed |
|------|--------|----------------|
| Instrument Serif | Google Fonts | Regular 400, Italic |
| DM Sans | Google Fonts | Light 300, Medium 500 |

Google Fonts import:
```
https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,500;1,9..40,300&display=swap
```

---

*Update this document when a new product or major feature launches, the ICP shifts, or a brand refresh is undertaken. Pair with `brand-voice.md`, `company-facts.md` and `products.md`.*
