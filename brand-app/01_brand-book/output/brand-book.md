# Ruff Cuts — visual system

No existing brand assets. This system is derived from the same five voice pillars that govern the writing, plus the concrete subject: a van, a driveway, grooming tools, Austin. It deliberately avoids two defaults: the "premium pet brand" look (pastel pinks/blues, cutesy paw iconography) and the "corporate SaaS" look (blue/purple gradients, generic rounded cards).

## Direction

**Workwear, not whimsy.** The reference world is the van itself — canvas, brushed hardware, a stamped tag on a tool bag — not a pet-store shelf. It's the same move as the voice: warmth from specificity and craft, not from decoration.

## Color

| Token | Hex | Role |
|---|---|---|
| `canvas` | `#E8E4D8` | Page ground — warm stone, not white, not cream-yellow |
| `paper` | `#F8F6F0` | Card/panel surface, lifted above canvas |
| `ink` | `#2A2521` | Primary text — warm near-black, not pure black |
| `brass` | `#9C7A3C` | The one accent — links, active states, primary actions. Reads as hardware, not as "brand purple" |
| `sage` | `#6E7F5C` | Semantic: good / clean / passes |
| `amber` | `#C08A2A` | Semantic: flagged / worth a look |
| `brick` | `#A14B36` | Semantic: violates a hard rule |

Semantic colors (sage/amber/brick) are separate from the accent (brass) — status is never communicated with the same hue as "click here."

Dark mode shifts the same hue family rather than inverting: darker canvas/paper toward ink, and brass/sage/amber/brick each lightened just enough to hold contrast on a dark ground.

## Type

Two roles, used for different jobs — not decoration:

- **UI and headings** — system sans (`-apple-system, "Segoe UI", system-ui`), bold, tight tracking on large sizes. Carries the confident-not-corporate register: direct, no flourish.
- **Quoted examples** — system serif, italic (`Georgia, "Iowan Old Style", ui-serif`). Reserved *only* for text lifted verbatim from the guide's worked examples — the caption, the email. The shift in face itself signals "this is real copy, not UI chrome," so no extra visual scaffolding (quote marks, borders) is needed to say the same thing.

## Layout

A left rail (guide sections + Check Your Draft) next to one content pane showing a single section at a time — an internal tool a new hire operates, not a page they scroll past once. Corners are small and square-ish (2–4px), like a stamped tag, not the default bubble-rounded card. One accent color, spent mostly on the rail's active state and the checker's primary action — everything else stays quiet.

## Handoff

`02_build` implements this directly as CSS custom properties. If the palette or type ever needs to change, edit this file first — the build stage should be regenerated from it, not hand-patched.
