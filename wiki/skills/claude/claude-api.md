---
title: claude-api
category: claude
type: skill
trigger: /claude-api
source: Claude Code natif
---

# claude-api — Build avec l'API Anthropic / Claude SDK

**Mission :** Aider à construire, déboguer et optimiser des applications utilisant l'API Claude (Anthropic SDK). Inclut le prompt caching par défaut.

## Déclenchement automatique

Se déclenche quand :
- Le code importe `anthropic` ou `@anthropic-ai/sdk`
- L'utilisateur parle de l'API Claude, Anthropic SDK, Managed Agents
- Modification d'une feature Claude (caching, thinking, compaction, tool use, batch, files, citations)
- Questions sur le prompt caching / cache hit rate
- Migration entre versions de modèles

## Ce que ça couvre

- Utilisation de l'API Claude (Opus, Sonnet, Haiku)
- Prompt caching (TTL 5 min, économies de tokens)
- Tool use / function calling
- Streaming et batch requests
- Migration de modèles (4.5 → 4.6 → 4.7)
- Managed Agents (SDK)

## Modèles actuels (mai 2026)

| Modèle | ID |
|---|---|
| Opus 4.7 | `claude-opus-4-7` |
| Sonnet 4.6 | `claude-sonnet-4-6` |
| Haiku 4.5 | `claude-haiku-4-5-20251001` |

**Ne pas déclencher** si le code utilise un autre provider SDK (`openai`, etc.).
