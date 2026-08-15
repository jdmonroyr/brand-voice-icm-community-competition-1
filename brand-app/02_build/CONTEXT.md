# 02_build — build the interactive voicebook

One job: build the single-page app from the guide and the brand book.

## Inputs
- Reference (every run): ../01_brand-book/output/brand-book.md — the token system
- Reference (every run): ../../voice-guide/02_language/rules.md — the checker's phrase/pattern rules, table row for table row. This is the canonical source; the JS array is a compiled copy of it, nothing more.
- Reference (every run): ../../voice-guide/02_language/mechanics.md — the checker's computed rules (counts/thresholds), which can't be expressed as table rows
- Reference (every run): the rest of ../../voice-guide/** — the guide sections are condensed from every file for in-app reading

## Process
1. Read the brand book. Implement its tokens as CSS custom properties, exactly — don't reinterpret the palette or type pairing.
2. Build two areas on one page: a browsable guide (identity, principles, language, scenarios) and a checker (paste text, get it flagged against the guide's own rules, each flag citing the specific rule and linking back to that guide section).
3. Compile the checker's phrase/pattern rule array directly from `rules.md`, one JS rule object per table row, carrying its severity and context columns through. Compile the counting/threshold checks (exclamations, emoji, sentence length, caption length) from `mechanics.md` as procedural logic.
4. If either source file changes, redo step 3 — don't hand-patch the JS rule list independently, or the two will drift.

## Outputs
- index.html → output/ (also published as a Claude Artifact)

## Human check
Paste a bad example ("So excited to groom your fur baby today!! 🐾🐾🐾 Per our policy we appreciate your patience!") and confirm every violation gets flagged with the right rule cited. Paste a guide-clean example and confirm it passes. Resize narrow to confirm the rail collapses sanely.
