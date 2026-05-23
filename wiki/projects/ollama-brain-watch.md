---
tags: project
updated: 2026-05-23
sources: /Users/jc/.gemini/antigravity/scratch/ollama-brain-watch/
---

# ollama-brain-watch

Dashboard de monitoring temps réel des modèles Ollama locaux — VRAM, GPU, throughput, latence.

## Stack

| Couche | Tech |
|--------|------|
| Framework | React + Vite + TypeScript |
| Style | Tailwind v4 |
| Charts | Recharts |
| HTTP | Axios |
| Animation | Framer Motion |
| Icons | Lucide React |

## Structure

```
src/
├── App.tsx
├── hooks/      ← polling Ollama API
├── logic/      ← calculs métriques
└── index.css
```

## Endpoint Ollama surveillé

```
http://localhost:11434/api/tags
http://localhost:11434/api/generate
```

## Chemin

```
/Users/jc/.gemini/antigravity/scratch/ollama-brain-watch/
```
