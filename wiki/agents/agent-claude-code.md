---
tags: [agent]
updated: 2026-05-23
---

# Agent Claude Code

## Rôle
Agent principal d'exécution. Lit le wiki, exécute les skills, modifie les fichiers, maintient la cohérence du wiki au fil du temps.

## Capacités
- Lire et écrire des fichiers markdown
- Exécuter des commandes bash (grep, find, curl)
- Appeler des outils MCP (Google Drive, web search, etc.)
- Maintenir le contexte d'une session (~200k tokens)
- Utiliser des subagents via le tool `Agent`

## Limites à respecter
- Max 10 fichiers complets lus par session
- Ne pas lire `node_modules/`, `dist/`, `build/`, `.next/`, `.cache/`
- Approche chirurgicale : grep avant lecture massive
- Recommander un reset de contexte après ~2h de session

## Outils disponibles

| Outil | Usage |
|-------|-------|
| Read / Edit / Write | Manipulation de fichiers |
| Bash | Commandes shell, grep, find, curl |
| Agent (subagent) | Délégation de tâches complexes ou explorations larges |
| MCP Google Drive | Lecture/écriture Drive |
| WebSearch / WebFetch | Recherche et récupération web |

## Modèle actuel
`claude-sonnet-4-6` — Délégation code vers Ollama : voir [[agents/agent-antigravity]]

## Liens
- [[agents/agent-router]]
- [[agents/agent-antigravity]]
- [[mcp/mcp-overview]]
