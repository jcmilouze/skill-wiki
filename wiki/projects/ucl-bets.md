---
tags: project
updated: 2026-05-23
sources: /Users/jc/.gemini/antigravity/scratch/ucl-bets-pro/
---

# ucl-bets

Application de pronostics / paris UCL avec intégration Ollama pour l'analyse.

## Variantes

| Repo | Stack |
|------|-------|
| `ucl-bets` | Base UI, Postgres, node-cron |
| `ucl-bets-pro` | Next.js 15, Drizzle ORM, LibSQL, Ollama |

## Stack (ucl-bets-pro)

| Couche | Tech |
|--------|------|
| Framework | Next.js 15 + TypeScript |
| ORM | Drizzle ORM |
| DB | LibSQL (SQLite local via `local.db`) |
| AI | Ollama (intégration native) |
| Style | Tailwind + Lucide |

## Fichiers clés

```
src/           ← app Next.js
drizzle.config.ts
local.db       ← base SQLite locale
CLAUDE.md      ← instructions projet
GSD_ROADMAP.md ← roadmap
```

## Chemin

```
/Users/jc/.gemini/antigravity/scratch/ucl-bets-pro/
```
