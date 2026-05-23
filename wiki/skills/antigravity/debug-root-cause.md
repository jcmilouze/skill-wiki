---
name: debug-root-cause
description: Diagnostic méthodique des bugs — reproduction → hypothèses → instrumentation → validation → correctif minimal. Évite les patches empiriques.
keywords: ["debug", "bug", "erreur", "fix", "root-cause", "instrumentation", "hypothèses"]
priority: critical
allowed-tools:
  - Bash(find *)
  - Bash(grep *)
  - Bash(ls *)
  - Bash(cat *)
---

# Debug-Root-Cause

**Mission : identifier et corriger la cause racine d'un bug** avec méthode scientifique. Jamais par essai-erreur.

## Quand l'utiliser

OBLIGATOIRE pour tout bug : "ne marche pas", "erreur", comportement inattendu, test qui échoue.

## Méthode scientifique (5 étapes strictes)

1. **REPRODUIRE** → Steps précises + environnement + logs/screenshots
2. **HYPOTHÈSES** → 3 causes possibles max, classées par probabilité
3. **INSTRUMENTER** → Logs ciblés, breakpoints conditionnels (pas de spray console.log)
4. **VALIDER** → Tester hypothèse #1 → confirmée ou infirmée
5. **CORRIGER** → Patch minimal à la cause + test de non-régression

## Format de sortie obligatoire

```
🐛 BUG ANALYSIS : [Titre court]

🔄 1. Reproduction fiable
Étapes : [...]
Environnement : [OS, version, config]
Logs/erreur : [message exact]

💭 2. Hypothèses
#1 (haute probabilité) : [cause] → [pourquoi probable]
#2 (moyenne) : [cause] → [pourquoi possible]
#3 (faible) : [cause] → [pourquoi peu probable]

🛠️ 3. Instrumentation proposée
[logs ou checks ciblés à ajouter pour valider #1]

✅ 4. Validation
Hypothèse testée : #[X]
Résultat : CONFIRMÉE | INFIRMÉE
[Si infirmée → passer à #2]

🩹 5. Correctif
[diff minimal — uniquement la cause racine]

🧪 Test de protection
[test qui aurait détecté ce bug]

📊 Modèle utilisé : ollama/[gemma4:31b | qwen3.5:35b]
```

## Taxonomie des bug patterns (GSD — par fréquence)

Utiliser pour cibler les hypothèses en priorité :

| Catégorie | Patterns fréquents |
|-----------|-------------------|
| **Null/Undefined** | Property access sur null, return manquant, destructuring sans default, param optionnel sans fallback |
| **Off-by-One/Boundary** | Bounds de boucle, fence-post, range inclusif vs exclusif, collection vide supposée non-vide |
| **Async/Timing** | await manquant, race condition, closure stale, séquence d'init, timers non nettoyés |
| **State** | Mutation in-place, UI désync, closure avec valeur obsolète, double source de vérité, transition invalide |
| **Import/Module** | Dépendance circulaire, mismatch export format, extension manquante, case-sensitivity cross-platform |
| **Type/Coercion** | String vs number, loose equality, floating-point, falsy-but-valid (0, '') |
| **Env/Config** | Env var absente, path hardcodé, conflit de port, permission manquante |
| **API Contract** | Format réponse changé, type container inattendu, champ requis manquant, encoding |
| **Scope/Closure** | Variable shadowing, loop variable partagée, `this` perdu, hoisting var |
| **Error Handling** | Exception swallée, catch mauvais type, cleanup échoué, promise rejection non gérée |

## Contraintes absolues

- Ne jamais patcher sans identifier la cause racine
- Max 3 hypothèses — si plus, la tâche est mal ciblée
- Toujours commencer par la reproduction
- Toujours ajouter au moins 1 test de protection
- Patch minimal : ne corriger que la cause, pas refactorer autour

## Modèles recommandés

- Logique/flux → `gemma4:31b`
- SQL/performance → `qwen3.5:35b`
- UI visuel → `gemma4:31b` (vision)

## Tâche reçue

$ARGUMENTS
