---
tags: project
updated: 2026-05-23
sources: /Users/jc/.gemini/antigravity/scratch/velotrack/
---

# velotrack

Application de planification de sorties vélo avec routing BRouter, cartes MapLibre et profils d'élévation.

## Variantes

| Repo | Rôle |
|------|------|
| `velotrack` | App principale — routing, UI, Express backend |
| `velotrack-pro` | Version Pro — Prisma + Postgres, Radix UI |
| `velotrack-storage` | Module stockage — GeoJSON, segments |
| `velotrack-storage-gh` | Variante GitHub storage — Radix UI |

## Stack (velotrack principal)

| Couche | Tech |
|--------|------|
| Cartes | MapLibre GL |
| Routing | BRouter (VPS externe) |
| State | Zustand |
| Style | Tailwind + clsx + tailwind-merge |
| Backend | Express + cors + dotenv |
| Données | @mapbox/polyline, geojson |

## Infrastructure VPS

- Segments France sur VPS Coolify
- Bridge Garmin pour import .fit
- Alias réseau configuré
- Profils .brf custom

→ Voir [[project_velotrack_infra]] (mémoire persistante)

## Chemins

```
/Users/jc/.gemini/antigravity/scratch/velotrack/        ← app principale
/Users/jc/.gemini/antigravity/scratch/velotrack-pro/    ← version Prisma
/Users/jc/.gemini/antigravity/scratch/velotrack-storage/
/Users/jc/.gemini/antigravity/scratch/velotrack-storage-gh/
```
