---
title: loop
category: claude
type: skill
trigger: /loop
source: Claude Code natif
---

# loop — Exécution récurrente d'un prompt

**Mission :** Exécuter un prompt ou un slash command de façon répétée à un intervalle donné.

## Quand l'utiliser

- Tâche récurrente : "vérifier le deploy toutes les 5 min"
- Polling de statut
- Exécution continue d'une commande

## Syntaxe

```
/loop 5m /foo          → execute /foo toutes les 5 minutes
/loop                  → self-paced (le modèle choisit l'intervalle)
```

## Omission de l'intervalle

Sans intervalle → le modèle auto-pace selon le contexte (utilise `ScheduleWakeup` en interne).

## Liens

- Voir aussi : [schedule](schedule.md)
