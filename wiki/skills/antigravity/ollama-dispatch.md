---
title: ollama-dispatch
category: antigravity
type: skill
trigger: /ollama-dispatch
priority: high
depends_on: []
models: [qwen3.5:35b, gemma4:31b]
---

# ollama-dispatch — Délégation local-first vers Ollama

**Mission :** Router toute génération de code, refactoring, tests, CRUD et composants UI vers les LLMs locaux Ollama. Claude garde orchestration, planification, architecture et sécurité.

## Déclenchement automatique

Invoquer automatiquement quand l'utilisateur demande d'implémenter, écrire, générer ou refactorer du code — sauf si la tâche requiert des décisions de sécurité ou des choix architecturaux.

## Modèles disponibles

| Modèle | Spécialité |
|---|---|
| `qwen3.5:35b` | TypeScript, React, Node.js, SQL, tests, refacto, CRUD, endpoints, UI |
| `gemma4:31b` | Documentation, README, explications, analyses, code review narratif |

## Ce que Claude garde (ne jamais déléguer)

- Planification et architecture système
- Brainstorming et choix technologiques
- Décisions de sécurité et review final
- Orchestration multi-étapes
- Debugging de régression critique
- Tout ce qui implique secrets, auth, infrastructure

## Ce qu'Ollama traite

- Génération de code (tout langage)
- Refactoring et amélioration
- Tests unitaires et d'intégration
- CRUD, endpoints API REST/tRPC
- Composants UI (React, Tailwind)
- Migrations et requêtes SQL/Prisma
- Documentation technique et JSDoc
- Scripts d'automatisation

## Workflow

1. **Classify** → Tâche d'implémentation/code ? → Déléguer
2. **Select model** → Code/tests : `qwen3.5:35b` | Doc/explication : `gemma4:31b`
3. **Build prompt** → Contexte précis (chemin, langage, contraintes)
4. **Call Ollama** → Execute via Bash
5. **Review** → Qualité, sécurité, cohérence projet
6. **Deliver** → Résultat + verdict

## Commande Ollama

```bash
curl -s http://localhost:11434/api/generate \
  -H "Content-Type: application/json" \
  -d '{"model": "qwen3.5:35b", "prompt": "<prompt>", "stream": false, "options": {"temperature": 0.15, "num_predict": 8192}}' \
  | python3 -c "import sys,json; d=json.load(sys.stdin); print(d.get('response','ERROR: '+str(d)))"
```

## Format de réponse

```
[LOCAL] qwen3.5:35b — <description courte>
<code généré>
Verdict : APPROUVÉ | CORRIGÉ (liste des corrections)
```
