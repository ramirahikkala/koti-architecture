# koti-architecture

C4 (Context/Container) diagrams of the whole `koti` home-automation ecosystem — [`koti`](https://github.com/ramirahikkala/koti)
(heating controller), [`koti-wilma`](https://github.com/ramirahikkala/koti-wilma) (Wilma
reminder service), `koti-devices` (ESP32 firmware) and `infra` (MQTT broker, Home Assistant,
Caddy) — described as code with [LikeC4](https://likec4.dev) and published to GitHub Pages.

Published site: https://ramirahikkala.github.io/koti-architecture/

## Local preview

```bash
npm install
npm run dev
```

Opens a live-reloading preview at `http://localhost:5173` — edit `src/model.c4` /
`src/model.views.c4` and see changes immediately.

## Publishing

Push to `main` — `.github/workflows/pages.yml` builds (`likec4 build`) and deploys to GitHub
Pages automatically. Repo Settings → Pages → Source must be set to "GitHub Actions" once.
