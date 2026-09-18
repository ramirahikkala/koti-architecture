# koti-architecture

C4 model of the whole home-automation platform, described as code with
[LikeC4](https://likec4.dev) and published to GitHub Pages. Organized by what things *do*, not
by which git repo they live in ([`koti`](https://github.com/ramirahikkala/koti),
[`koti-wilma`](https://github.com/ramirahikkala/koti-wilma), `koti-devices`, `infra`).

Published site: https://ramirahikkala.github.io/koti-architecture/ — a static landing page
(`landing/index.html`) with just the Level 1 diagram and a short summary, linking through to
the full interactive, click-to-drill-down app at
[`/app/`](https://ramirahikkala.github.io/koti-architecture/app/).

## The four levels

- **Level 1 — Context** (`src/model.c4`, view `index`): one system ("koti"), its two actors
  (Rami, Perheenjäsen), and the genuinely external systems it talks to (Wilma, Anthropic,
  Spot-Hinta, Telegram).
- **Level 2 — Container** (view `containers`): what "koti" is made of — heating controller,
  Wilma reminder service, MQTT broker, Home Assistant, BLE→MQTT gateways, desk display, Shelly
  relays. (Caddy/TLS deliberately left out — plumbing, not architecturally interesting here.)
- **Level 3 — Component** (views `heatingComponents`, `wilmaComponents`): only for the two
  containers that are our own code. Home Assistant/Mosquitto/Shelly/ESPHome are third-party —
  decomposing them wouldn't add anything.
- **Level 4 — Deployment, not Code** (`src/deployment.c4`, view `deployment`): where each
  container physically runs (home network vs. the VM). A UML-style Code diagram was
  deliberately skipped — it goes stale immediately and doesn't suit this tool; Deployment is
  the more standard C4 substitute for a "fourth diagram."

## Local preview

```bash
npm install
npm run dev
```

Opens a live-reloading preview at `http://localhost:5173` — edit `src/model.c4` /
`src/model.views.c4` and see changes immediately.

## Publishing

Push to `main` — `.github/workflows/pages.yml` builds the interactive app into `dist/app/`,
exports the Level 1 diagram as PNG (light + dark) into `dist/assets/`, copies
`landing/index.html` to `dist/index.html`, and deploys `dist/` to GitHub Pages. Repo Settings →
Pages → Source must be set to "GitHub Actions" once.
