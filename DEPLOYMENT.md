# Deploying REOVANA from `reovana_development_repo`

This repo contains **two separate Next.js apps**. There is no app at the repository root, so Vercel (or similar) will show **404 NOT_FOUND** if the **Root Directory** is left blank.

## Vercel setup (required)

Create **two** Vercel projects from the same GitHub repo:

| Vercel project | Root Directory | Dev URL example |
|----------------|----------------|-----------------|
| REOVANA public site | `proty-web` | `reovana-web-dev.vercel.app` |
| REOVANA admin | `site-2-web` | `reovana-admin-dev.vercel.app` |

### For each project in Vercel

1. **Import** [reovana_development_repo](https://github.com/MetasysConsulting/reovana_development_repo)
2. **Root Directory** → Edit → set to `proty-web` or `site-2-web` (not the repo root)
3. **Framework Preset** → Next.js (auto-detected)
4. **Install Command** → `pnpm install` (default)
5. **Build Command** → `pnpm build` (default)
6. Deploy

### After deploy

- **Public site** → open `/` (homepage)
- **Admin** → open `/login` or `/home` (demo: “Continue without login”)

## Why you saw this error

```
404: NOT_FOUND
Code: NOT_FOUND
ID: bom1::...
```

That is a **Vercel** error. It usually means:

- The project is pointed at the **repo root** (no Next.js app there), or
- The deployment failed / produced no routes, or
- You opened a Vercel URL that does not match a deployed project

## Local dev (no Vercel)

```bash
cd proty-web && pnpm install && pnpm dev    # http://localhost:3000
cd site-2-web && pnpm install && pnpm dev   # http://localhost:3001
```

## Push updates to this repo

```bash
./scripts/push-to-dev.sh "your change summary"
```
