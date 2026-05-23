---
title: update-config
category: claude
type: skill
trigger: /update-config
source: Claude Code natif
---

# update-config — Configurer le harness Claude Code

**Mission :** Modifier `settings.json` (ou `settings.local.json`) pour configurer les comportements automatisés, permissions, variables d'env et hooks du harness Claude Code.

## Quand l'utiliser

- Comportements automatisés : "à chaque fois que X", "avant/après X"
- Permissions : "autorise npm", "ajoute permission bq"
- Variables d'env : "set DEBUG=true"
- Hooks : "quand Claude s'arrête affiche X"
- Troubleshooting de hooks

**Note :** Les comportements automatisés NÉCESSITENT des hooks dans settings.json — la mémoire/préférences ne suffisent pas, c'est le harness qui les exécute.

## Différence settings.json vs settings.local.json

- `settings.json` → versionné, partagé avec l'équipe
- `settings.local.json` → local uniquement, non versionné

## Cas simples

Pour des réglages simples (thème, modèle), utiliser `/config` directement.

## Liens

- Voir aussi : [keybindings-help](keybindings-help.md)
