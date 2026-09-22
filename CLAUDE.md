# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

C4-model-as-code documentation of the whole koti platform (`infra`, `koti-devices`,
`services`), built with [likec4](https://likec4.dev) and published to GitHub Pages. Source
lives in `src/model.c4`, `src/model.views.c4`, `src/deployment.c4`.

- `npm run dev` — `likec4 start`, live-reload preview at `localhost:5173`
- `npm run build` — `likec4 build --base /koti-architecture/ --output dist`

Push to `main` builds and deploys to GitHub Pages via `.github/workflows/pages.yml` (requires
repo Settings → Pages → Source = "GitHub Actions", already configured).

## Gotcha

This is documentation, not application code — a good source of architectural *rationale*,
but it can drift from what the other repos actually do. Check commit dates and cross-check
against the real repos before treating a detail here as current; the README notes level-3
components are only modeled for the two first-party service containers.
