# Hawai Guy Project

Development review repo: [MetasysConsulting/reovana_development_repo](https://github.com/MetasysConsulting/reovana_development_repo)

Two separate Next.js websites in this folder.

| Folder | Site | Port (dev) | Production repo |
|--------|------|------------|-----------------|
| [`proty-web/`](proty-web/) | **REOVANA** public site | 3000 | `realestatetemplate` |
| [`site-2-web/`](site-2-web/) | **REOVANA Admin** dashboard | 3001 | `realestatetemplate2` |

## Push to dev (review repo)

```bash
./scripts/push-to-dev.sh "describe your changes"
```

This syncs both apps to `reovana_development_repo` for client review.

**Vercel:** This repo is a monorepo — you must set **Root Directory** to `proty-web` or `site-2-web` (see [DEPLOYMENT.md](DEPLOYMENT.md)). Leaving it at the repo root causes `404 NOT_FOUND`.

## Quick start

**Site 1 (Proty):**
```bash
cd proty-web
pnpm dev
```

**Site 2 (paste your template):**
```bash
cd site-2-web
# 1. Copy your HTML template into template-source/ (see site-2-web/README.md)
# 2. Convert and run:
pnpm convert-template
pnpm dev
```

## From the repo root

```bash
pnpm install          # installs both workspaces
pnpm --filter proty-web dev
pnpm --filter site-2-web dev
```

## Other folders

- `proty-package/` — original Proty HTML zip (reference for site 1)
- `themeforest-*.zip` — ThemeForest download archive
