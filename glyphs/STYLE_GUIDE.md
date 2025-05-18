# FYC Glyph Style Guide – v0.1 (2025-05-18)

This guide keeps every icon in **Faceless-Youtube** visually coherent and
animation-friendly.  
Follow these rules whenever you draw or revise an SVG.

---

## 1 · Canvas & Grid
| Property | Spec |
|----------|------|
| **Artboard** | 24 × 24 px `viewBox="0 0 24 24"` |
| **Grid** | Invisible 24 × 24 grid; align key points to 2 px increments |
| **Origin** | Centre the design optically—tiny left/right tweaks allowed |

> **Why:** 24 px fits most UI toolkits and scales cleanly to 48 / 96 / 192.

---

## 2 · Strokes & Paths
| Property | Spec |
|----------|------|
| **Stroke width** | 2 px |
| **Stroke linecap** | `round` |
| **Stroke linejoin** | `round` |
| **Fill** | `none` (no interior colour) |
| **Precision** | Minimise nodes; prefer straight lines + simple curves |

Use <https://github.com/svg/svgo> (`svgo --pretty`) to optimise before commit.

---

## 3 · Naming & Filing
File name pattern `NN_concept.svg`

| Segment | Meaning | Example |
|---------|---------|---------|
| `NN` | zero-padded order | `01`, `02`, … |
| `concept` | lowercase snake-case | `worldview`, `activation_threshold` |

---

## 4 · Semantic Mapping
| Glyph | Egyptian roots | Semantic role in FYC |
|-------|---------------|-----------------------|
| **01_worldview** | D4 “Eye” | A whole worldview (macro-lens) |
| **02_viewgroup** | A1 “Man” ×3 under D4 | A group sharing one worldview |
| **03_power** | S40 “Was-scepter” | Coercive / structural power |
| **04_money** | V31 “Bag of grain” | *TBD* financial resources |
| … | … | … |

Add a **one-line definition** for every new glyph here.

---

## 5 · Colour Policy
* **Source SVGs** are monochrome (`stroke="currentColor"`).
* Colour is applied only at the animation stage by CSS/tint.

---

## 6 · Animation Constraints
Icons should animate smoothly at 30 fps with simple transforms:
* **Opacity / scale / rotate** only—avoid path morphing.
* Keep stroke width constant during scale animations.

---

## 7 · Contribution Checklist
1. Draw on a 24 × 24 canvas → align to grid.
2. Run `svgo` locally (`svgo input.svg -o output.svg`).
3. Name the file `NN_concept.svg`; update table in §4.
4. Push via PR; include a 100 × 100 px PNG in the PR comment for preview.

---

## 8 · Versioning
* Minor tweaks → bump `STYLE_GUIDE.md` date.
* Breaking changes (e.g. stroke width change) → tag repo `glyphs-v2`.

---

*Maintainer: Guy Schultz • Last updated 2025-05-18*
