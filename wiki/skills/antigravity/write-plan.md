---
title: write-plan
category: antigravity
type: skill
trigger: /write-plan
priority: high
depends_on: [brainstorm-spec]
models: [gemma4:31b, qwen3.5:35b]
---

# write-plan — Plan d'exécution atomique

**Mission :** Produire un plan d'exécution précis et séquencé à partir d'une spécification claire. Ne code pas — seulement planifie.

## Quand l'utiliser

**OBLIGATOIRE** après `/brainstorm-spec` validée, ou pour toute tâche multi-fichiers / complexité moyenne+.

## Contraintes de format

Chaque étape DOIT être :
- **Atomique** (1 responsabilité)
- **Testable** (critère de succès mesurable)
- **Localisée** (max 5 fichiers/étape)
- **Modélisée** (modèle Ollama assigné)

## Processus (5 étapes internes)

1. **ANALYSE** → Comprendre la spec + contraintes
2. **DÉCOUPAGE** → Tâches atomiques, max 8 étapes
3. **LOCALISATION** → Fichiers impactés par étape
4. **MODÉLISATION** → Modèle Ollama optimal par étape
5. **SÉQUENÇAGE** → Ordre logique + dépendances

## Format de sortie

```
🎯 Objectif rappel
📊 Métriques plan (étapes, complexité)
🚀 Plan d'exécution (tableau : #, étape, fichiers, critère, modèle, dépend de)
🔄 Dépendances critiques
⚠️ Points de validation utilisateur
🚀 Prochaine étape : /execute-plan
```

## Spécificité obligatoire

| ❌ Trop vague | ✅ Correct |
|---|---|
| "Ajouter l'auth" | "JWT avec refresh rotation via jose, httpOnly cookies, expiry 15min/7j" |
| "Créer l'API" | "POST /api/projects : validation name (3–50 chars), retourne 201 + objet project" |

## Scope protection

**Langage interdit dans les plans :** "v1", "pour l'instant", "hardcodé temporairement", "placeholder", "à compléter"

## Liens

- Précédent : [brainstorm-spec](brainstorm-spec.md)
- Suivant : [execute-plan](execute-plan.md)
