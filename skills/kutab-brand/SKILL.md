---
name: kutab-brand
description: >
  Produce any visual asset for a Kutab academy on the academy's own brand.
  Use whenever you generate an image, poster, card, certificate, social graphic,
  chart, badge, header, or any design for an academy connected through the Kutab
  MCP. It reads the academy's real name, logo and colours (the academy_branding
  MCP tool, or GET /api/info) and renders the house style: flat, light
  background, Cairo font, 2D vector (SVG).
---

# Kutab branded assets

When you make anything visual for a Kutab academy, it must look like **that
academy** — not generic, not Kutab's own brand. Two steps, every time.

## 1. Get the branding (never guess it)

Prefer the MCP tool; fall back to the info API.

- **Connected through the Kutab MCP:** call the **`academy_branding`** tool. It
  returns `name`, `colors` (`primary`, `primary_dark`, `secondary`,
  `secondary_dark`), `assets` (`logo`, `logo_dark`, `favicon`) and `frontend_url`.
- **Not on the MCP:** `GET {frontend_url}/api/info` — same fields, as
  `appName`, `colors.primary` / `colors.secondary`, `assets.logo` /
  `assets.favicon`. Ask the admin for the academy's URL if you don't have it.

Use the real **name** in the copy and the real **logo** in the layout. If a
colour is missing, use the refined Kutab fallback palette: blue `#527CA5`, ink
`#142D43`, reverse blue `#A2C1DE`, ivory `#F6F3ED`, and white `#FFFFFF`. Say
that you used the fallback.

## 2. Render in the house style

Every asset is **flat, on a light background, in Cairo, as a 2D vector (SVG)**.
Full rules in [`reference/design-system.md`](reference/design-system.md); the
short version:

- **Flat.** Solid fills, clean shapes, generous whitespace. No photos, no 3D, no
  bevels/drop-shadow stacks, no gradient-as-decoration (one soft tint at most).
- **Light background.** Use ivory `#F6F3ED` or white `#FFFFFF`. Never a dark
  canvas. Colour comes from the marks and the palette, not the field.
- **Cairo font** (Google Fonts — Arabic + Latin, right for a bilingual academy):
  `@import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&display=swap')`
  and `font-family:'Cairo', system-ui, sans-serif;`. Set `dir="rtl"` for Arabic copy.
- **2D vector.** Author as **SVG** (or HTML+inline-SVG rendered to PNG). Icons and
  illustrations are simple flat vector motifs in the academy's palette — no
  raster clip-art. Start from [`assets/brand-template.svg`](assets/brand-template.svg).
- **Palette.** `primary` for the lead mark/CTA and `secondary` as accent. Use
  academy dark colours when they pass contrast; otherwise use Kutab ink
  `#142D43` for text. Keep body text ≥ 4.5:1 on the light ground.
- **Logo.** Place the academy's `logo` (or `logo_dark` on a tinted panel) with
  clear space around it; never stretch or recolour it.

## Output

Deliver the SVG (and a PNG render if the surface wants an image). Name the
academy in the piece. If you couldn't fetch branding, say so and use the Kutab
fallback rather than inventing a name, colour or logo.
