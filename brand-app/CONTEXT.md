# brand-app — the voice guide as an interactive tool

Two stages. Turns `voice-guide/` from a document into something a new hire opens, reads, and tests their own writing against.

## Stages

1. `01_brand-book/` — one job: translate the voice pillars into a visual system (color, type, layout, shape language). Output is an editable spec, not code. This is the direction-setting stage — get it right here, before anything gets built on top of it.
2. `02_build/` — one job: build the actual single-page app from `voice-guide/` + the brand book. Two areas on one page: a browsable guide (business context + voice principles + phrases + scenarios) and a checker (paste a caption or email, get it flagged against the guide's own rules, with the specific rule cited back).

## Handoff

`01_brand-book/output/brand-book.md` is `02_build`'s input. A human reads it, edits it in place if the palette or type feels off, and only then does the build stage read it.

## Status

Scan `01_brand-book/output/` and `02_build/output/` for files — empty means that stage hasn't run yet.
