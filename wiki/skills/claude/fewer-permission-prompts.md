---
title: fewer-permission-prompts
category: claude
type: skill
trigger: /fewer-permission-prompts
source: Claude Code natif
---

# fewer-permission-prompts — Réduire les prompts de permission

**Mission :** Scanner les transcripts des conversations pour identifier les outils Bash et MCP fréquemment utilisés en lecture seule, puis ajouter une allowlist priorisée dans `.claude/settings.json` pour réduire les interruptions de permission.

## Quand l'utiliser

Quand Claude demande trop souvent des permissions pour des opérations de lecture courantes (`ls`, `cat`, `grep`, etc.).

## Ce que ça fait

- Analyse l'historique des appels d'outils
- Identifie les patterns récurrents et non-destructifs
- Ajoute les permissions manquantes dans `.claude/settings.json`

## Liens

- Voir aussi : [update-config](update-config.md)
