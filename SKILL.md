---
name: photo-to-impasto
description: Convert any photo into a square palette-knife impasto oil painting miniature with 3-5mm thick paint texture, directional knife strokes, top-left lighting, and handwritten caption on warm-ivory paper. Use when user says 照片转厚涂油画, 厚涂, impasto, 调色刀, 油画小品, 照片转油画, photo to oil painting, or wants textured palette-knife painting with 1:1 ratio.
---

# Photo to Impasto

Turn a source photo into a 1:1 palette-knife impasto miniature — thick paint, visible strokes, physical light/shadow on the paint surface.

## Required reading

Before generating, read [references/style-spec.md](references/style-spec.md) for the full spec and caption rules.

## Workflow

1. Identify subject, crop, and caption type from the photo (food→menu name, product→product name, person→short phrase, animal→species, landscape→place).
2. Keep silhouette/color/composition from the original; simplify forms into thick paint blocks — do NOT photoreal render.
3. Build prompt using the Prompt Contract below.
4. Generate via the image tool that supports image-to-image (GPT-Image-2 / Flux / DALL-E). Pass the source photo as reference/edit input.
5. Inspect: paint must look 3-5mm raised, strokes directional, left-top highlight/shadow visible, background flat ivory paper, text handwritten black only. Revise with one targeted fix if any check fails.

## Prompt contract (v0.31 — current, absorbs Chinese spec useful parts)

Copy verbatim, replace bracketed parts only:

```text
1:1 square canvas, palette-knife impasto oil painting miniature, heavy thick raised paint 3-5mm, distinct directional grooves and ridges per paint lump, top-left single light source, strong highlight on raised ridges, deep shadow in recesses and stacked layers, subtle edge shadow so color masses stack on different layers, follow original silhouette, palette and composition, simplified block-shaped forms with restrained density (few bold strokes still recognizable), no over-detailing.
Background: flat warm-ivory textured paper, subtle fine grain only, flat to contrast dimensional subject, NO border, NO black outline, NO frame, clean wide margin of empty paper around subject.
Bottom corner: natural crooked black hand-written caption text "[Caption]" — auto by type (food→menu name like Pancake, product→name, person→short phrase, animal→species, landscape→place), hand-drawn script, neat printed font forbidden, no extra decorations.
Composition: subject ([subject description]) centered in canvas, single cohesive cluster, generous empty margin, keep [layout] layout, no extra props.
Forbidden: watercolor wash, transparent layers, soft color blending, gradient, photorealism, glossy finish, airbrush, black border, frame, outline, extra text.
```

For API calls: set `size` to `1024x1024` (square), `n=1`. When caption text is known, insert it verbatim inside Caption quotes.

## Caption rules

| Photo type | Caption content | Example |
|---|---|---|
| Food/drink | Menu name | Pancake, Earl grey cake |
| Product | Product/category name | Camera, Perfume |
| Person | Short phrase or name-like text | A quiet afternoon |
| Animal | Species/name | White cat |
| Landscape | Place or short word | Jeju Sea |

Handwriting: black, crooked, human — never typeset.

## Quality gate

Accept only when all true:
- Paint looks physically thick (3-5mm), not flat digital brush
- Directional knife marks visible on every lump
- Top-left light creates highlight vs shadow contrast on paint
- Background is flat warm ivory/cream paper with light grain
- Subject centered 1:1 with generous margin, single object
- Caption is black handwritten, placed in whitespace corner, no other text
