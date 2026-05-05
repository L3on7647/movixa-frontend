# Movixa Frontend

Production frontend snapshot of [Movixa](https://app.movixa.uz) — Telegram Mini App for a self-hosted VOD platform (FastAPI + PG16 + Redis7 + Jellyfin pipeline).

This is the **actual running frontend** as served from `https://app.movixa.uz/` (Mini PC `/opt/movixa/static/`). The live React+Vite bundle is committed as-is; only absolute `/static/...` paths were rewritten to relative `./...` for static hosting.

## Stack

- **React** SPA built with **Vite** (single hashed entry chunk + lazy chunks)
- **framer-motion** animation
- **HLS.js** for adaptive video playback
- **Telegram WebApp SDK** for `initData` HMAC auth
- **Manrope / Fraunces / JetBrains Mono** + **Remixicon**
- "Obsidian Glass" dark theme — `#05060d` base, `#ff6b47` accent

## Layout

```
index.html                       boot splash + Vite entry
assets/
  index-Bo8CODWQ.js              app bundle (~244K)
  motion-B4ZqxX2p.js             framer-motion chunk
  hls-CGg9MbMg.js                HLS.js chunk (~512K)
  style-C4GDcb06.css             compiled styles
```

## Live demo

Static shell on Pages: https://l3on7647.github.io/movixa-frontend/ — UI loads but `/api/*` calls fail (no backend). For the real working app: open [@movixa_bot](https://t.me/movixa_bot) on Telegram.

## Source

This repo holds **built artifacts only**. The source TypeScript/JSX project is private. The companion Preact ESM "TMA v2" experiment served at `/v2` lives separately (`/opt/movixa/tma/`).
