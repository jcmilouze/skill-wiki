---
title: brainstorm-spec
category: antigravity
type: skill
trigger: /brainstorm-spec
priority: high
depends_on: []
models: [gemma4:31b]
---

# brainstorm-spec — Clarifie avant d'implémenter

**Mission :** Transformer une demande floue en spécification claire et exécutable. Ne produit pas de code — seulement clarifie.

## Quand l'utiliser

**OBLIGATOIRE** : nouvelle feature, endpoint, refactor multi-fichiers, modification DB, bug non reproductible, intégration externe, changement d'architecture.

**FACULTATIF** : edits < 1 fichier / 50 lignes, CSS visuel, documentation.

## Processus (7 étapes)

1. **REFORMULER** → Objectif en 1 phrase claire
2. **CONTEXTE** → Fichiers, dépendances, contraintes existantes
3. **HYPOTHÈSES** → Ce qui doit être vrai pour réussir
4. **CRITÈRES** → Conditions d'acceptation mesurables (MAJEUR / SECONDAIRE)
5. **RISQUES** → Ce qui peut casser (CRITIQUE / MOYEN / FAIBLE)
6. **CLASSIFICATION** → Type de tâche + modèle Ollama recommandé
7. **PROCHAINES ÉTAPES** → Skill suivante suggérée

## Format de sortie

```
🎯 Objectif reformulé
📂 Contexte projet
❓ Hypothèses à valider
✅ Critères d'acceptation (MAJEUR / SECONDAIRE)
⚠️ Risques identifiés (CRITIQUE / MOYEN / FAIBLE)
📊 Classification (type, complexité, modèle)
🚀 Prochaine étape : /write-plan
```

## Classification des tâches

| Type | Modèle |
|------|--------|
| Code/refactor/API/SQL | `qwen3.5:35b` |
| Architecture/analyse/vision | `gemma4:31b` |
| Landing page / UI | `qwen3.5:35b` + 21st.dev + Stitch |

## Contraintes strictes

- Ne pas proposer de code
- Ne pas élargir le périmètre
- Toujours classer la tâche explicitement
- Pour les tâches UI : mentionner 21st.dev comme source

## Liens

- Suivant : [write-plan](write-plan.md)
- Pipeline complet : [agent](agent.md)
