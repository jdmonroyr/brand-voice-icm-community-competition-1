# Ruff Cuts Brand Voice — workspace overview

**What this is.** A knowledge bundle (`voice-guide/`) plus a one-stage generation pipeline (`generate/`) that uses it. The bundle is the actual deliverable Dana asked for; the pipeline exists to prove the guide works — feed it a real request and it should produce copy that sounds like Ruff Cuts without further coaching.

## The bundle: `voice-guide/`

Three layers, meant to be loaded in order:

1. `01_identity/` — always load. Who Ruff Cuts is, who the customer is, the core voice principles. ~600 tokens.
2. `02_language/` — load by task. Concrete word choices: phrases to use, phrases to never use, sentence-level mechanics.
3. `03_scenarios/` — load last, only the one you need. Format-specific rules (caption vs. apology email vs. complaint reply vs. competitor mention), each with worked examples baked in.

Full map and reading order: `voice-guide/index.md`.

## The pipeline: `generate/`

One stage. Inputs: a request file in `requests/` + the relevant `voice-guide/` layers. Output: a draft in `output/`. Contract: `generate/CONTEXT.md`.

## The app: `brand-app/`

Two stages, ending in the interactive deliverable Dana can hand to a new hire: a place to read the business context and voice guide, and a place to paste a draft and get it checked against the guide.

1. `01_brand-book/` — translates the voice pillars into a visual system (color, type, layout tone). Direction-setting stage; human edits before build.
2. `02_build/` — reads `voice-guide/` + `01_brand-book/output/` and builds the single-page app. Also published as a Claude Artifact.

Contract: `brand-app/CONTEXT.md`.

## Status

`generate/output/` and `brand-app/*/output/` scanned for files tell you what's been produced so far. Everything in `voice-guide/` is stable reference and doesn't change run to run — edits there are updates to the standard, not outputs of a run.
