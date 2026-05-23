---
tags: [agent]
updated: 2026-05-23
---

# Agent Antigravity

## Rôle
Couche d'exécution locale du projet Antigravity. Orchestre les modèles Ollama pour déléguer la génération de code et les analyses volumineuses, en préservant le budget de contexte de Claude Code.

## Configuration Ollama

| Tâche | Modèle |
|-------|--------|
| Code, refactor, tests, SQL, endpoints | `qwen3.5:35b` |
| Planification, architecture, analyse, vision | `gemma4:31b` |

Endpoint local : `http://localhost:11434`

## Commande de délégation standard

```bash
curl -s http://localhost:11434/api/generate \
  -H "Content-Type: application/json" \
  -d '{"model": "qwen3.5:35b", "prompt": "<prompt>", "stream": false, "options": {"temperature": 0.15, "num_predict": 8192}}' \
  | python3 -c "import sys,json; d=json.load(sys.stdin); print(d.get('response','ERROR: '+str(d)))"
```

## Répertoire de travail
`/Users/jc/.gemini/antigravity/scratch/`

## Skills Antigravity disponibles
Répertoire : `~/.claude/skills/`
Invocation dans Claude Code : `/nom-de-la-skill`

## Politique d'usage
- Déléguer la génération de code à Ollama par défaut (local-first)
- Claude Code garde : orchestration, architecture, sécurité, review, wiki
- Ne jamais utiliser un modèle cloud payant pour de la génération mécanique

## Liens
- [[agents/agent-claude-code]]
- [[decisions/decisions-log]]
