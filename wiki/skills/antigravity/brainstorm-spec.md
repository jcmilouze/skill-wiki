---
name: brainstorm-spec
description: Clarifie l'objectif réel, détecte les contraintes cachées, définit les critères d'acceptation et identifie les risques avant toute implémentation.
keywords: ["brainstorm", "spec", "analyse", "risques", "critères", "hypothèses", "clarification"]
priority: high
allowed-tools:
  - Bash(find *)
  - Bash(grep *)
  - Bash(ls *)
---

# Brainstorm-Spec

**Mission : transformer une demande floue en spécification claire et exécutable** avant toute implémentation. Ne pas produire de code — seulement clarifier.

## Quand l'utiliser

OBLIGATOIRE pour : nouvelle feature, endpoint, refactor multi-fichiers, modification DB, bug non reproductible, intégration externe, changement d'architecture.

FACULTATIF pour : edits < 1 fichier / 50 lignes, CSS visuel, documentation.

## Processus (7 étapes)

1. **REFORMULER** → Objectif en 1 phrase claire
2. **CONTEXTE** → Fichiers, dépendances, contraintes existantes
3. **HYPOTHÈSES** → Ce qui doit être vrai pour réussir
4. **CRITÈRES** → Conditions d'acceptation mesurables (MAJEUR / SECONDAIRE)
5. **RISQUES** → Ce qui peut casser (CRITIQUE / MOYEN / FAIBLE)
6. **CLASSIFICATION** → Type de tâche + modèle Ollama recommandé
7. **PROCHAINES ÉTAPES** → Skill suivante suggérée

## Format de sortie obligatoire

```
🎯 Objectif reformulé
[1 phrase précise]

📂 Contexte projet
Fichiers concernés : [...]
Contraintes existantes : [...]

❓ Hypothèses à valider
- [hypothèse 1]
- [hypothèse 2]

✅ Critères d'acceptation
MAJEUR : [critères sans lesquels = échec]
SECONDAIRE : [critères souhaitables]

⚠️ Risques identifiés
CRITIQUE : [risque → impact → mitigation]
MOYEN / FAIBLE : [...]

📊 Classification
Type : [LOCAL-SAFE | LOCAL-FIRST | PREMIUM-ONLY | VISION]
Complexité : [basse | moyenne | haute]
Modèle : ollama/[gemma4:31b | qwen3.5:35b]

🚀 Prochaine étape : /write-plan
```

## Classification des tâches

| Type | Modèle | Ressource |
|------|--------|-----------|
| Code/refactor/API/SQL | `qwen3.5:35b` | — |
| Architecture/analyse/vision | `gemma4:31b` | — |
| Landing page / UI | `qwen3.5:35b` | 21st.dev → Stitch pour maquette |
| Deploy Coolify | aucun LLM | Config VPS direct |

## Contraintes strictes

- Ne pas proposer de code
- Ne pas élargir le périmètre
- Toujours classer la tâche explicitement
- Toujours proposer des critères mesurables
- Pour les tâches UI : toujours mentionner 21st.dev comme source de composants

## Tâche reçue

$ARGUMENTS
