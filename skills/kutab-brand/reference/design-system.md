# Kutab academy — asset design system

The house style for anything generated for a Kutab academy. Applies to every
asset kind: posters, welcome/summary cards, certificates, schedule graphics,
badges, social images, headers, simple charts.

## Brand inputs (from `academy_branding` / `GET /api/info`)

| Field | Use |
|---|---|
| `name` (`appName`) | The headline identity — name the academy in the copy. |
| `colors.primary` | Lead colour: primary mark, CTA, key shape. |
| `colors.secondary` | Accent: secondary shapes, highlights. |
| `colors.primary_dark` / `secondary_dark` | Deeper tints for text-on-tint or borders. |
| `assets.logo` | The logo on light panels. |
| `assets.logo_dark` | The logo on a coloured/tinted panel. |
| `assets.favicon` | A small mark where the full logo won't fit. |

If an academy value is missing, use the refined Kutab fallback palette and say
you fell back:

| Role | Colour |
|---|---|
| Ink / primary dark | `#142D43` |
| Primary blue | `#527CA5` |
| Light ground | `#F6F3ED` |
| Secondary / reverse blue | `#A2C1DE` |
| White | `#FFFFFF` |

Use ink for body text. Reverse blue is an accent, not a body-text colour. Do not
introduce a gold accent or a second, brighter royal blue into the fallback.

## The five rules

1. **Flat.** Solid fills and clean geometry. No photographs, no 3D, no bevels,
   no stacked drop shadows, no skeuomorphism. One soft tint or a single 6–10%
   shadow for depth is the ceiling — never gradients as decoration.
2. **Light background.** Ground is ivory `#F6F3ED` or white `#FFFFFF`. For a
   fully academy-branded asset, a very light tint of the academy primary is
   also acceptable. Never use a dark canvas. The colour lives in the marks, not
   the field. (A coloured *panel* inside a light layout is fine.)
3. **Cairo, always.**
   ```
   @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;500;600;700;800&display=swap');
   * { font-family:'Cairo', system-ui, 'Segoe UI', sans-serif; }
   ```
   Cairo carries Arabic and Latin, so bilingual academies stay consistent. Set
   `dir="rtl"` (and `text-anchor:end` in SVG) for Arabic copy; `ltr` for English.
   Headline 700–800, body 400–500.
4. **2D vector.** Author as **SVG** (standalone, or inline SVG in HTML rendered
   to PNG). Illustrations/icons are simple flat vector motifs — rounded rects,
   circles, a book/graduation/calendar/check motif — filled from the palette. No
   raster clip-art, no icon fonts baked in as images.
5. **Palette discipline.** Academy `primary` leads and academy `secondary`
   accents. Use a supplied academy dark colour for text only when it passes
   contrast; otherwise use Kutab ink `#142D43`. For fallback artwork, stay
   within blue `#527CA5`, reverse blue `#A2C1DE`, ink `#142D43`, ivory
   `#F6F3ED`, and white `#FFFFFF`. Body text must reach 4.5:1 on its background;
   large or bold text must reach 3:1. Don't tint text light "for elegance".

## Layout

- **Logo** top-left (LTR) / top-right (RTL) with clear space ≥ the logo's cap
  height on every side. Never stretch, rotate, or recolour it; use `logo_dark`
  on a coloured panel.
- **Grid & rhythm:** generous margins (≥ 6% of the shorter side), one clear
  focal element, aligned to a simple grid. Whitespace is the design.
- **Type scale:** one display size, one subhead, one body. `text-wrap: balance`
  on headings. Cap line length ~55–70 characters.
- **Shapes:** rounded corners (8–24px depending on scale), consistent stroke
  weights, flat icons at a single visual size.
- **Common sizes:** social 1600×900 and 1080×1080; card 1200×628; certificate A4
  landscape (297×210mm ≈ 1123×794 at 96dpi); story 1080×1920.

## Do / Don't

- **Do** name the academy, use its real logo + colours, keep it calm and flat.
- **Don't** use a dark background, stock photos, neon, heavy gradients, 3D, drop
  shadows everywhere, exclamation-mark energy, or Kutab's own branding in place
  of the academy's. Kutab is the platform; the academy is the brand.

## Render

Deliver the **SVG**. If the surface wants a bitmap, render the SVG/HTML to PNG at
2× and hand over the PNG too. Start from `assets/brand-template.svg`.
