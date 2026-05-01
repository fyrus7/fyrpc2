# FyRPC GitHub Pages + Cloudflare Workers

## Letak fail di GitHub Pages

Upload semua fail ini ke root repository GitHub Pages:

- `index.html` = login page
- `mobile.html` = mobile dashboard
- `desktop.html` = desktop dashboard
- `shared.js` = semua function mobile/desktop yang call Worker
- `monitor.html` = basic monitor page untuk endpoint `/monitor` dan `/clear`
- `admin.html` = basic admin page untuk endpoint session/performance/sale

## Letak fail di Cloudflare Workers

- `worker.js` = backend Worker

## Wajib tukar URL Worker

Dalam `index.html` dan `shared.js`, cari:

```js
https://YOUR-WORKER-NAME.YOUR-SUBDOMAIN.workers.dev
```

Tukar kepada URL Worker sebenar awak.

## Worker environment variables

Set di Cloudflare Worker Settings > Variables:

- `SHEET_ID`
- `GOOGLE_CLIENT_EMAIL`
- `GOOGLE_PRIVATE_KEY`
- `SESSION_SHEET_ID`
- optional: `REG_COLOR_ID` kalau nak guna semula color update

## Endpoint frontend guna

- `POST /login`
- `POST /validate`
- `POST /logout`
- `GET /search?ic=...&mode=...`
- `POST /collect`
- `POST /hold`
- `GET /status`
- `POST /walkin`
- `GET /walkin-categories`
- `GET /monitor`
- `POST /clear`
- `GET /sessions`
- `POST /terminate`
- `GET /dates?mode=performance|sale`
- `POST /performance`
- `POST /sale`
