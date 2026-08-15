# Ruff Cuts — Brand Voice Workspace

Mobile dog grooming van, Austin. This workspace is the brand voice guide for Ruff Cuts, built so anyone — human writer or AI — can pick it up and sound like Ruff Cuts on the first try.

## Where things live

| Need to... | Go to |
|---|---|
| Understand the voice, top to bottom | [voice-guide/index.md](voice-guide/index.md) |
| Write a caption, email, or reply right now | [generate/CONTEXT.md](generate/CONTEXT.md) |
| Build or update the interactive brand app | [brand-app/CONTEXT.md](brand-app/CONTEXT.md) |
| See who Dana is and what she asked for | [references/client_brief.md](references/client_brief.md) |
| See the workspace's overall shape | [CONTEXT.md](CONTEXT.md) |

## Shape

- `voice-guide/` — the factory. Stable reference: who Ruff Cuts is, how it talks, phrases in and out, and per-situation rules with worked examples. Load this before writing anything.
- `generate/` — the one working stage. Drop a content request in `requests/`, get an on-brand draft in `output/`.
- `brand-app/` — a two-stage pipeline that turns the guide into the interactive deliverable: a brand book (visual system), then the built app.
- `references/` — the original competition brief. Input, not output. Don't edit.

## Rule of thumb

Never write for Ruff Cuts without loading `voice-guide/01_identity/` first. Everything else is situational detail on top of that foundation.
