# Ruff Cuts — Brand Voice Workspace

A brand voice guide for **Ruff Cuts**, a mobile dog grooming service in Austin, built for Clief Notes Weekly Competition #1 ("The Fake Client"). See [references/client_brief.md](references/client_brief.md) for the original brief.

Rather than a single document, the deliverable is a small ICM (Interpretable Context Methodology — Van Clief & McDermott, arXiv:2603.16021) workspace: the voice guide as a navigable knowledge bundle, plus a pipeline that turns it into an interactive tool — a new hire can read the guide and paste a draft caption or email to have it checked against the guide's own rules.

**Live app:** https://jdmonroyr.github.io/brand-voice-icm-community-competition-1/ — deployed via GitHub Actions on every push to `main` (see `.github/workflows/pages.yml`).

## Start here

[CLAUDE.md](CLAUDE.md) is the entry point — it routes to everything below in one screen.

- **[voice-guide/](voice-guide/)** — the guide itself. Identity, voice principles, language rules, and per-scenario examples (captions, apology emails, complaint responses, competitor mentions).
- **[brand-app/](brand-app/)** — a two-stage pipeline that turns the guide into the interactive app: a brand book (visual system) → the built page.
- **[generate/](generate/)** — a one-stage pipeline for drafting on-brand content by hand from a request.
- **[references/](references/)** — the original competition brief. Input, not output.

## Why it's structured this way

Built with [`icm-architect`](https://github.com/RinDig/icm-architect), a Claude Code skill (tooling used to build this — not vendored in this repo): numbered folders carry sequencing, folder hierarchy carries context scoping, and plain markdown carries state — so a human (or an AI) can open any folder and see exactly what it's for, without a wiki or a framework. Every working folder has a `CONTEXT.md` stating its inputs, its job, its outputs, and what a human should check before moving on.

## Rebuilding the app

The checker's rules are data, not hardcoded logic: `voice-guide/02_language/rules.md` is the single source of truth for every banned phrase and pattern. If that file changes, `brand-app/02_build/output/index.html` needs to be recompiled from it by hand — see `brand-app/02_build/CONTEXT.md` for the process. Don't edit the checker's JS rule list independently, or the two will drift.
