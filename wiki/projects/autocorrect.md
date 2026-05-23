---
tags: project
updated: 2026-05-23
sources: /Users/jc/.gemini/antigravity/scratch/autocorrect/
---

# autocorrect

App SaaS de correction/analyse de documents (PDF, Excel, Google Drive) avec authentification Clerk.

## Stack

| Couche | Tech |
|--------|------|
| Framework | Next.js + TypeScript |
| Auth | Clerk |
| ORM | Prisma |
| DB | Postgres (docker-compose.dev.yml) |
| Docs | pdf-parse, ExcelJS, Google APIs |
| Style | Tailwind (postcss) |

## Structure

```
app/           ← routes Next.js App Router
lib/           ← utilitaires
prisma/        ← schéma Prisma
public/
proxy.ts       ← proxy custom
docker-compose.dev.yml
CLAUDE.md      ← instructions projet
```

## Chemin

```
/Users/jc/.gemini/antigravity/scratch/autocorrect/
```
